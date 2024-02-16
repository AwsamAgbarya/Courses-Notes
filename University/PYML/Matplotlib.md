```python
import matplotlib.pyplot as plt
```
### Normal plotting:

```python
fig, ax = plt.subplots(nrows=N, ncols=M, sharey=True, sharex=True,figsize=(12, 6)) # To decide figsize for subplot
ax.plot(x, y, 'X-', color='red', ms=10, label='$f(x) = \sin(x)$') # to plot array x according to array y
ax.set_xlabel('x-axis', fontsize=20, rotation=45, labelpad=50) # setting the properties of each label
ax.set_ylim(-1,1) # To set limits of axis
ax.legend(loc='best', fontsize=25) # to create a legend
ax.set_title('Simple trigonometric functions', fontsize=25) # to set title
ax.grid(axis='y') # to set grid lines
ax.set_yticks(np.arange(-1, 1.01, .07)) #details te ticks
```

### Histograms

```python
hist, bin_edges, _ = ax.hist(samples, bins=30, rwidth=0.8, alpha=0.6, label='samples', color=color, density=True,,weights=frequencies) # for computing histograms
ax.axvline(x=samples.mean(), ls='--', c='r', label='$\mu$') # for vertical line

```

### Contour
```python
cntr = ax.contourf(x, y, z, cmap='rainbow', alpha=0.5, levels=10)
from mpl_toolkits.axes_grid1 import make_axes_locatable
divider = make_axes_locatable(ax)
cax = divider.append_axes('right', size='5%', pad=0.5)

fig.colorbar(cntr, cax=cax, orientation='vertical')
```

### Scatter plot:
```python
plt.scatter(c.T[0],
			c.T[1],
			alpha=0.6,
			color=customPalette[i])
plt.annotate(letters[i]+'-'+str(i),
			 means[i]+(0,2),
			 horizontalalignment='center',
			 verticalalignment='center',
			 size=15,
			 color='white',
			 backgroundcolor=customPalette[i])
```
