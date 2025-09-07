# The Hierarchical Subspace Iteration Method for Laplace–Beltrami Eigenproblems
#### Motivation:
- **Laplace–Beltrami eigenproblems** arise in many graphics tasks—spectral shape analysis, mesh processing, non-rigid registration—because the eigenfunctions form an orthonormal basis of functions on a surface and capture intrinsic geometry.

# Surface Multigrid via Intrinsic Prolongation (Liu et al., 2021)

**Surface multigrid** methods build a hierarchy of discretizations (coarse-to-fine meshes) and use _prolongation_ operators to transfer functions between levels. Liu _et al._ introduce a _novel intrinsic prolongation operator_ for unstructured curved surfaces[ar5iv.org](https://ar5iv.org/pdf/2104.13755#:~:text=structured%20domains%2C%20generalizing%20multigrid%20to,we%20upgrade%20existing%20algorithms%20to)[ar5iv.org](https://ar5iv.org/pdf/2104.13755#:~:text=Our%20method%20computes%20the%20prolongation,Furthermore%2C%20our%20approach). They first decimate a fine mesh to create coarser meshes, while computing local bijective maps (via _successive self-parameterization_) between each mesh pair. These maps yield a sparse **prolongation matrix** $P$ whose rows encode barycentric interpolation weights of fine vertices in coarse triangles[ar5iv.org](https://ar5iv.org/pdf/2104.13755#:~:text=Our%20linear%20prolongation%20is%20a,3). Using $P$, the method constructs a Galerkin multigrid: coarse-system matrices $A_{l+1}=P_l^T A_l P_l$ and typical V-cycle relaxation. This enables efficient, geometry-aware multigrid solves on curved surfaces[ar5iv.org](https://ar5iv.org/pdf/2104.13755#:~:text=relaxation%20step%2C%20we%20use%20the,can%20further%20accelerate%20the%20computation)[ar5iv.org](https://ar5iv.org/pdf/2104.13755#:~:text=Our%20method%20computes%20the%20prolongation,Furthermore%2C%20our%20approach).

Below we detail each component: hierarchy construction, parameterization, joint flattening, and the Galerkin solver. Formula and pseudocode references are given where appropriate.

## Hierarchy Construction via Decimation

The multigrid hierarchy is built by successively _coarsening_ the input mesh. Starting from the fine mesh $M^0$, the mesh is repeatedly simplified (e.g. by edge collapses) to form meshes $M^1,M^2,\dots,M^L$, until the coarsest level has a manageable number of vertices. At each step an edge collapse is chosen (using standard decimation metrics like quadric error)[ar5iv.org](https://ar5iv.org/pdf/2104.13755#:~:text=match%20at%20L130%20Euclidean%20domains,free%E2%80%9D%20alternative)[ar5iv.org](https://ar5iv.org/pdf/2104.13755#:~:text=Our%20method%20computes%20the%20prolongation,Furthermore%2C%20our%20approach). The key difference is that after collapsing an edge, the method immediately computes how the local neighborhood is mapped to the coarse mesh (so as to build prolongation weights). Importantly, the coarser meshes need not be regular or subdivision-based; arbitrary unstructured decimation can be used, and the intrinsic prolongation will still be defined via geometry[ar5iv.org](https://ar5iv.org/pdf/2104.13755#:~:text=Our%20method%20computes%20the%20prolongation,Furthermore%2C%20our%20approach)[ar5iv.org](https://ar5iv.org/pdf/2104.13755#:~:text=match%20at%20L130%20Euclidean%20domains,free%E2%80%9D%20alternative).

Each collapse from $M^l$ to $M^{l+1}$ affects only a local patch (the 1-ring around the collapsed edge). We compute a local _bijection_ $\phi^l: M^l \to M^{l+1}$ on that patch. Globally, the mapping from the original fine mesh $M^0$ to a coarse mesh $M^k$ is then the composition of these local maps:

$Φ0→k  =  ϕk−1∘ϕk−2∘⋯∘ϕ0 .\Phi_{0\to k} \;=\; \phi^{k-1}\circ\phi^{k-2}\circ\cdots\circ\phi^0\,.Φ0→k​=ϕk−1∘ϕk−2∘⋯∘ϕ0.$

In practice, each $\phi^l$ is computed “on the fly” during decimation and stored. Figure 8 (below) illustrates a single collapse: the blue patch on the fine mesh $M^l$ and the green patch on the coarse mesh $M^{l+1}$ are flattened to a common 2D domain, so that any point’s coordinates can be mapped between them.

The **precomputation** stage thus produces:
- A sequence of meshes $M^0\rightarrow M^1 \rightarrow \cdots \rightarrow M^L$.
- For each collapse $l$, the vertex sets and faces of the local patches before/after collapse, and their joint 2D parameterization (Section 4.2).
- A record of each fine-mesh vertex’s coordinates in the eventual coarse triangle, computed by chaining the mappings.
In Appendix C of the paper, the authors note that implementing successive self-parameterization “only requires a small change to an existing edge collapse algorithm After each collapse, both patches are flattened to a UV plane (Sec. 4.2–4.3) and the mappings are stored. Later, to map any point (given by barycentric coordinates in a fine triangle) to the coarse mesh, one successively applies each local map in order. (In implementation, one also stores which faces were involved in each collapse so that a query only updates barycentric weights when the point lies in the collapsed region.

## Successive Self-Parameterization
The key to intrinsic prolongation is that each fine patch and its collapsed version share the same _boundary curve_ in the flattened domain. Concretely, suppose an interior edge $(i,j)$ collapses to a vertex $k$. Let $V^l$ be the vertices of the edge 1‑ring patch before collapse (including $i,j$), and $V^{l+1}$ be the vertices of the vertex 1‑ring after collapse (including $k$). Crucially, the set of boundary vertices is the same: $\partial V^l = \partial V^{l+1}$ (see Fig. 8). We thus seek a shared 2D parameterization ${u_i^l}_{i\in V^l}$ and ${u_k^{l+1}}_{k\in V^{l+1}}$ of these two patches so that boundary vertices have identical UV values.

In practice, for each collapse we solve for this parameterization by minimizing a distortion energy on _both_ patches simultaneously (see next section). Once the joint UV map is computed, any point in the fine patch (with barycentric weights in some triangle of $V^l$) can be mapped to its corresponding point in the coarse patch via the shared UV coordinates. In particular, the fine point’s barycentric coordinates are updated to barycentric coordinates in the coarse patch, defining a **prolongation weight vector** for that point. These local maps $\phi^l$ are then composed to define a global map from $M^l$ to $M^{l+1}$, and ultimately from $M^0$ to any coarser level.

Mathematically, if a fine-level vertex $x^l$ lies in some triangle $(a,b,c)$ of the coarse mesh $M^{l+1}$ (in the shared UV domain), then its prolongation row has three nonzeros $(\alpha,\beta,\gamma)$ corresponding to vertices $a,b,c$, where $(\alpha,\beta,\gamma)$ are the barycentric coordinates of $x^l$ in $(a,b,c)$[ar5iv.org](https://ar5iv.org/pdf/2104.13755#:~:text=Our%20linear%20prolongation%20is%20a,3). For example, one can write the linear prolongation matrix $P^l$ (mapping from level $l+1$ to $l$) by:

$Px,al=α,Px,bl=β,Px,cl=γ,P^l_{x,a} = \alpha,\quad P^l_{x,b} = \beta,\quad P^l_{x,c} = \gamma,Px,al​=α,Px,bl​=β,Px,cl​=γ$
with all other entries of row $x$ zero. Here $P^l$ is “tall” (size $\text{fine vertices}\times\text{coarse vertices}$), and each row has exactly 3 nonzeros

This _successive self-parameterization_ approach guarantees _bijectivity_ and intrinsic consistency. By composing the local maps, every fine-level vertex can be traced to a unique triangle of the coarse mesh. The paper’s Appendix C notes that after each collapse one simply flattens both patches to UV and stores the local map; then at query time, “we go through the list of local joint UV parameterizations... and update the barycentric coordinates successively. This yields a final coarse-level barycentric representation for every fine vertex, which defines $P^l$.
## Joint Flattening (Low-Distortion UV Maps)

A novel contribution is the **joint flattening** method (Section 4.2) that minimizes distortion over both patches at once. Liu _et al._ point out that simply flattening the edge 1-ring then the vertex 1-ring separately (as in prior work) can create high distortion in one of the patches[ar5iv.org](https://ar5iv.org/pdf/2104.13755#:~:text=The%20base%20method%20proposed%20by,Although%20this%20method%20can). Instead, they formulate a single optimization for the UV coordinates of both patches.

Let $V^l$ and $F^l$ denote the vertices and faces of the patch before collapse, and $V^{l+1},F^{l+1}$ the patch after. Write ${\bf u}^l$ for the UV positions of $V^l$ and ${\bf u}^{l+1}$ for those of $V^{l+1}$. Define a distortion energy $D({\bf u})$ (e.g. symmetric Dirichlet) over each triangulated patch. The joint optimization is:

$min⁡ul,ul+1  D(ul)+D(ul+1)s.t. ubl=ubl+1 for all boundary vertices b.\min_{{\bf u}^l,{\bf u}^{l+1}} \; D({\bf u}^l) + D({\bf u}^{l+1})\quad \text{s.t. }{\bf u}^l_b = {\bf u}^{l+1}_b\text{ for all boundary vertices }b.ul,ul+1min​D(ul)+D(ul+1)s.t. ubl​=ubl+1​ for all boundary vertices b.$

In other words, the boundary vertices (black in figures) of both patches are constrained to share the same 2D positions, ensuring a continuous mapping[ar5iv.org](https://ar5iv.org/pdf/2104.13755#:~:text=For%20the%20notational%20convenience%2C%20we,joint%20energy%20optimization%20problem%20as)[ar5iv.org](https://ar5iv.org/pdf/2104.13755#:~:text=In%20order%20to%20handle%20the,%283%29%20into%20an%20unconstrained%20problem). To handle the equality constraints ${\bf u}^l_b={\bf u}^{l+1}_b$, the authors introduce a **joint variable** ${\bf U}$ that embeds the shared boundary coordinates. With this, the problem becomes unconstrained: solve for ${\bf u}^l$, ${\bf u}^{l+1}$, and ${\bf U}_b$ so that at convergence the boundary UVs coincide in both patches[ar5iv.org](https://ar5iv.org/pdf/2104.13755#:~:text=In%20order%20to%20handle%20the,%283%29%20into%20an%20unconstrained%20problem).

The result is a single flattened domain (see Fig. 9 in the paper) that minimizes distortion on _both_ patches, rather than warping one to fit the other. Empirically, this yields much lower quasiconformal distortion (blue curves in Fig. 9) compared to the earlier two-stage method.

### Handling Boundary Edges

If the collapsed edge lies on the mesh boundary, additional constraints are needed to preserve the boundary curve (Section 4.3). Two cases arise:

- **One endpoint on the boundary:** Suppose vertex $i$ lies on the boundary $b$ and the other endpoint $j$ is interior. After collapse to $k$, we require that $k$ lie on the same boundary segment. In the UV flattening, this is enforced by _snapping_ the interior vertex onto the boundary line. Concretely, we add a joint constraint so that the boundary coordinate ${\bf u}_b$ equals both ${\bf u}^l_j$ (pre-collapse) and ${\bf u}^{l+1}_k$ (post-collapse)[ar5iv.org](https://ar5iv.org/pdf/2104.13755#:~:text=The%20creation%20of%20the%20joint,Liu%20et%C2%A0al.%2C%202017)[ar5iv.org](https://ar5iv.org/pdf/2104.13755#:~:text=In%20the%20case%20where%20one,appearance%20preservation). Figure 11 in the paper illustrates this case.
    
- **Both endpoints on the boundary:** If both vertices $i,j$ of the collapsed edge are on the mesh boundary, one must preserve the straight boundary segment after collapse. The paper handles this by enforcing colinearity of the boundary curve in UV (several sub-cases, see Fig. 12). In each sub-case, appropriate equalities (using the joint variable) ensure that the flattened boundary remains a single straight line (up to colinearity)

## Prolongation Operator

The **intrinsic prolongation operator** $P^l$ from level $l+1$ to $l$ is defined by these barycentric maps. As noted, $P^l$ is an $(n_l\times n_{l+1})$ sparse matrix (fine‐by‐coarse size) with exactly 3 nonzeros per fine-row. Formally, if a fine-level vertex $x$ is located (in the flattened domain) in triangle $(v_1,v_2,v_3)$ of the coarse mesh $M^{l+1}$ with barycentric coordinates $(\alpha_1,\alpha_2,\alpha_3)$, then the prolongation entries are:

$Px,v1l=α1,Px,v2l=α2,Px,v3l=α3,P^l_{x,v_1} = \alpha_1,\quad P^l_{x,v_2} = \alpha_2,\quad P^l_{x,v_3} = \alpha_{3,\quad}Px,v1​l​=α1​,Px,v2​l​=α2​,Px,v3​l​=α3​$

and all other entries in row $x$ are zero. In practice, the triangular containment is determined via the saved patch parameterizations: each fine vertex is only involved in a few edge-collapses, so one identifies in which coarse patch it fell and what triangle contained it. The result is that $P^l$ is built _intrinsically_ using geometry (through the joint UV maps) but the interpolation itself is linear (barycentric).

The authors choose _linear interpolation_ on each triangle for all prolongations[ar5iv.org](https://ar5iv.org/pdf/2104.13755#:~:text=We%20choose%20linear%20interpolation%20as,still%20converges%20in%20most%20cases). This choice is justified by the fact that most geometry-processing PDEs are second‐order (so linear prolongation suffices)[ar5iv.org](https://ar5iv.org/pdf/2104.13755#:~:text=We%20choose%20linear%20interpolation%20as,still%20converges%20in%20most%20cases). Higher-order prolongations were not needed in practice. Importantly, because the mapping is intrinsic, it does not rely on any global parameterization or embedding – it works purely with the triangulated geometry[ar5iv.org](https://ar5iv.org/pdf/2104.13755#:~:text=Our%20method%20computes%20the%20prolongation,Furthermore%2C%20our%20approach).

## Galerkin-Style Multigrid Solver

With the hierarchy and prolongation operators in hand, one can perform a standard Galerkin V-cycle on the curved surface. Let $A^0$ be the finest-level system matrix (e.g. a Laplace or Laplace–Beltrami operator on $M^0$) and $f^0$ the right-hand side. At each level $l$, we define the coarse system by the Galerkin rule:

Al+1=(Pl)T Al Pl,fl+1=(Pl)T fl.A^{l+1} = (P^l)^T \,A^l\, P^l, \qquad f^{l+1} = (P^l)^T \,f^l.Al+1=(Pl)TAlPl,fl+1=(Pl)Tfl.

Because each $P^l$ is sparse and geometry-based, $A^{l+1}$ correctly approximates the operator on $M^{l+1}$. We then solve $A^{l+1} u^{l+1} = f^{l+1}$ (either recursively via multigrid or directly at the coarsest level).

A typical **V-cycle** works as follows (pseudocode in Alg. 1/2 of the paper):

1. **Pre-smoothing:** On the finest level $l=0$, apply a few Gauss–Seidel relaxations to $A^0 u^0 = f^0$ (with current guess $u^0$).
    
2. **Compute residual:** $r^0 = f^0 - A^0 u^0$.
    
3. **Restrict residual:** $r^1 = (P^0)^T r^0$ on level 1.
    
4. **Coarse solve:** Solve $A^1 e^1 = r^1$. (If $l=1$ is still not the coarsest, recurse to level 2, etc.; if at coarsest, solve directly.)
    
5. **Prolong correction:** $e^0 = P^0 e^1$. Update $u^0 \leftarrow u^0 + e^0$.
    
6. **Post-smoothing:** Apply Gauss–Seidel relaxations on the corrected fine-level $u^0$.
    

Repeat this cycle until the solution converges. In each coarse-grid correction step, the prolongation $P^l$ and its transpose handle the inter-grid transfer[ar5iv.org](https://ar5iv.org/pdf/2104.13755#:~:text=relaxation%20step%2C%20we%20use%20the,can%20further%20accelerate%20the%20computation). In code, Liu _et al._ implement this with $\nu_\text{pre}=\nu_\text{post}=2$ Gauss–Seidel sweeps by default[ar5iv.org](https://ar5iv.org/pdf/2104.13755#:~:text=In%20terms%20of%20hyperparameters%20of,to%20get%20visually%20distinguishable%20results).

The overall algorithm (summarized in Alg. 1 of the paper) is: load mesh, build hierarchy of $P^l$, assemble finest $A^0,f^0$, then iterate V-cycles until tolerance. Because the hierarchy and $P^l$ depend only on the mesh geometry (not on $A$ itself), this multigrid precomputation need only be done once per geometry[ar5iv.org](https://ar5iv.org/pdf/2104.13755#:~:text=Switching%20from%20direct%20solvers%20to,until%20getting%20the%20desired%20accuracy). Thereafter, any number of linear solves on the same mesh can reuse the same prolongation hierarchy, making it very efficient for time-varying systems.

[ar5iv.org](https://ar5iv.org/pdf/2104.13755#:~:text=relaxation%20step%2C%20we%20use%20the,can%20further%20accelerate%20the%20computation)[ar5iv.org](https://ar5iv.org/pdf/2104.13755#:~:text=Output%20%3A%C2%A0%20%20%2F%2F%20new,solution) summarize the core: “restricting the residual to the coarser level via $P^T$, solving a coarsened linear system with left-hand-side $P^TAP$, prolonging the low-res solution back to the fine domain using $P$, and using it to update the current high-res solution.” Figure 15–17 of the paper show that this _intrinsic_ prolongation yields much faster convergence than naive extrinsic projections or algebraic multigrid, especially on complex surfaces[ar5iv.org](https://ar5iv.org/pdf/2104.13755#:~:text=Our%20linear%20prolongation%20is%20a,3).

## Algorithmic Summary

Putting it all together, the Surface Multigrid solver proceeds in two phases:

- **Precomputation (Hierarchy + Prolongation):**
    
    - Load fine mesh $M^0$.
        
    - Repeatedly collapse edges (e.g. by quadric error) to create meshes $M^1,\dots,M^L$.
        
    - After each collapse, compute the local shared UV parameterization (Sec. 4.2–4.3) to get a bijection between patches. Record the barycentric maps for all affected vertices.
        
    - Assemble prolongation matrices $P^l$ from these barycentric weights
        
- **Solve (Galerkin V-cycle):**
    - Assemble the finest-level system $A^0 u = f$ (e.g. mass or stiffness matrix).
    - Repeat until convergence (or for a fixed number of cycles):
        1. Pre-smooth (e.g. Gauss–Seidel) on current level $l=0$.
        2. Compute residual $r^l = f^l - A^l u^l$.
        3. Restrict $r^{l+1} = (P^l)^T r^l$ and form $A^{l+1} = (P^l)^T A^l P^l$.
        4. Recurse to solve $A^{l+1} e^{l+1} = r^{l+1}$ on level $l+1$ (either by further multigrid or direct solve at $L$).
        5. Prolong correction $u^l \leftarrow u^l + P^l e^{l+1}$.
        6. Post-smooth on level $l=0$ and return.

This is essentially Algorithm 1/2 in Liu _et al._, rewritten here for clarity. The critical new piece is the intrinsic construction of $P^l$ at each level. Once $P^l$ is available, the coarse operators and V-cycles follow standard Galerkin multigrid logic[ar5iv.org](https://ar5iv.org/pdf/2104.13755#:~:text=relaxation%20step%2C%20we%20use%20the,can%20further%20accelerate%20the%20computation)[ar5iv.org](https://ar5iv.org/pdf/2104.13755#:~:text=Output%20%3A%C2%A0%20%20%2F%2F%20new,solution).

In practice, the authors report that this solver dramatically accelerates geometry-processing tasks. Replacing a direct solver with intrinsic multigrid achieves orders-of-magnitude speed-ups on large meshes[ar5iv.org](https://ar5iv.org/pdf/2104.13755#:~:text=structured%20domains%2C%20generalizing%20multigrid%20to,we%20upgrade%20existing%20algorithms%20to), without sacrificing convergence accuracy.