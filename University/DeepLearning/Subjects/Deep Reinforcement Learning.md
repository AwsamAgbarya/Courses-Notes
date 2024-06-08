---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Good Boy!! ^nwDNNZQZ

Reinforcement Learning ^jwBsgGnp

Warning Big subject and has many details
that I wont be able to explain in time ^dfS84YUy

What is reinforcement learning? ^vBYX9S2P

Reinforcement learning is an algorithmic concept that places you (the agent) in an
environment that reacts to your actions, the goal is to explore the environment
such that you find the best course of action at any given situation to maximize your rewards. ^0yfF2saI

There will be a lot of notation to keep track of
Brace yourself: ^PYErfphE

s ∈ S - such that S is all possible states s of our system

a ∈ A(s) - A is all possible actions A which may or may not
            depend on the value of s

T (s′|s, a) - a state sampling distribution conditioned
             on the previous action and state.

π(a|s) - an action sampling distribution conditioned on
         the previous state given by the environment.

R(s, a) - a reward sampling distribution, given the current
          state and action, what is the appropriate reward.

V (s) -  Value function, evaluating the future potential of our
         system given the current state we are at.

Q(s, a) - Value-action function, evaluating the future potential
          of our system given the action we are about to take
          in our state.

γ ∈ (0, 1] -  Disount factor, how much weight are we willing to put
              on long term future rewards. ^pXr8kINO

Metrics ^GbTT3UbB

Supervised and unsupervised methods have their
own metrics to compare how well your model is doing at each
step.

Reinforcement learning does not, it instead has a holistic view
on the total performance, youre given an evaluation on how
well you did without breaking it down into steps. ^6I7aJ2LY

Exploitation vs Exploration ^71yBwebG

How much do we care about exploring new routes that
open up new possibilities even if they're risky?

are we willing to make sacrifices in the short term
by exploring and losing in order to potentially
gain in the long term?

or do we just prefer exploiting the best route we
currently have for the solutions we consider? ^hPDs5cjG

our final
output
(optimal) ^CaIc0kPM

Markov Decision
Process ^IEoee9br

A markov decision process is a decision process that bases
its distribution off of the entire history of the markov
chain.
This can be seen as a generalization of our situation
if our situation st encompasses and encodes our entire
history and is arrived at by our history then we can
define the history as ^9o8izerV

And the decision process defines ^MpZTcv5V

Value function
Estimation ^q6hh5ZP2

base state ^uNckFRCO

our current
action policy ^XHtpfjFz

sampling a new
state every iteration
from the state distribution ^YMUB8xMX

weight on
future values
exponentially
decreasing ^CNs7doEA

rewards ^HBEfZqP7

future ^baNqHacx

Which translates to ^WTG3QUFY

Problem: this provides us no information on which action
to take as it does not evaluate individual actions
(reminder that our goal is to find the optimal course
of action)
solution: Replace with an action dependent alternative ^B69lToYh

State-action value function ^A7zeQJtY

more expressive but requires more information ^6GrnWZB9

According to the Bellman equation ^cTaBKTir

unknown ^MFOSVbrD

According to the bellman equation ^NZKdVs6X

This equation defines a recursive relationship
into future values
Which can be solved and evaluated iteratively
using dynamic programming backwards ^hO9wuCDu

determined by T
and pi dynamics
implicitly ^PTQpiWVk

last iterations
value of the future ^Fd7BfXrC

next iterations
value of the present ^G7uZO9aq

Which is equivalent to ^c6WyDmql

all possible actions
we can take
at this state ^Q0kkjOO0

all possible
states that
cane be generated
from the action
we take ^mpXoJjLk

appropriate
reward ^QaWFrlyl

value of
future given
that state ^42nJrpE8

Value-Based
 methods ^yaEkR6FB

Monte Carlo Method ^1Mt65U6Z

The term ”Monte Carlo” is generally used for estimation methods that
use random sampling in their process. it is a way to estimate
intractable values by sampling a lot from it and updating the "estimation" 
of the value. (Simulation and law of large numbers)

Note in RL we only use Monte Carlo for tasks that have an ending
(Win/Lose situation, no infinite situation)

an Episode is a full simulation from start to finish
The process goes as follows:
 1. Run a full simulation.
2. Improve your estimation of the future value of each
state you have visited in that simulation by averaging
over the future value you just experienced and your prior
experiences. ^osgSO3b2

G is the collection of G0 -> Gn
episode results that include the
state s.
Meaning that the value of s is the
expected value of all values of S
in our simulations
note that for a sequence of events
(episode) σi to include the value s
we wouldve had to sample that
value at least once ^0nedfzhU

How to update the value of V ? ^YWu3wYAs

Which we can then update just after simulating
every episode ^WSihQLBq

Temporal Difference method ^9O0feIMt

Uses dynamic programming to recursively update state value based on experience
(Like monte carlo)
But unlike monte Carlo, TD assumes that not all previous steps contribute to
the current reward gotten, instead theres a finite window of previous temporal
steps that lead up to the current reward (In the simplest case we assume
that only the LAST action led up to our reward but this can be expanded
to a window instead)
Key concept:
Update state value function by using reward Rt+1 of next step
(experience) and current estimate of next state’s value V (St+1) ^beCYiCfg

treats the model as a blackbox
and learns from the data collected ^TXWcnmyq

somehow learns a model
of the environment ??
provided some extra
known information ^6MjdUoXA

I.e The algorithm does N episodes iteratively and unlike monte carlo it
updates its value estimation after every step not after every episode.

1) we take a step according to our best value estimate (random at the start)

2. We observe the reward we just got from taking that action

3. we calculate the temporal difference which is Our estimate - what we experienced
which is the immediate reward + next state's discounted reward 
something which we derives from the bellman equation


4. we update our estimate with the temporal difference * learning rate and go back to step 1 ^OG31LUJI

we will not focus on MBRL
we assume that we do not have a model
given  ^cXPJ5xwH

Monte Carlo is the
Simplest approach for Free learning
but is not recommended ^6icj0Q5I

How much knowledge do 
i have after this episode ^g0A8BGGT

Old value ^IJlpjehn

usually an average
normalizing term ^7ISHNYIu

reward i gained in the total
sequence ^a2pcs0MW

reward i had at s previously
the reason we do this is so that
when we converge we do not have 
infinite learning (i.e optimal V(s) should
predict Gt and thus the learning stops)
real == estimate ^gV69JnRx

Which basically says, play one episode, after youre done
update the estimate of the value s that was apart of your episode
as the old value + the average reward per step in your episode
assumes that every single step you took along the way to the reward
is equally as important and contributing to that reward
(if you play a good game of chess and win, but you made a bad move at
the start, Monte carlo weighs that move just as important as a good move,
which after billions of games will "even out" the bad moves but it requires
a lot) ^TxzhkgwH

real ^aVbIhVIC

estimate ^8GLELixB

real ^12M31jE6

estimate ^HQlfifCf

TD(N)
Method ^vqdDsPrC

As we said before the TD algorithm that we introduced only takes
into account the last action we took as the responsible for our current
reward, but we can adapt this to a window of size n of last n actions.
at the extreme case of N=entire episode, this will converge into Monte carlo ^56yt6cNC

Deep RL ^wcCTaKiR

Model-free RL ^CqRQyjQP

Model-based RL ^BOIm6c8T

Markov decision Process ^OBdZLt4N

Non-linear Dynamics ^81xOGj0W

Dynamic Programming
and Bellman optimality ^XrotJUFH

Actor
Critic ^P6IuWuvF

Deep
MPC ^vJZNY6jW

Policy Iteration ^SjGjq7Th

Value Iteration ^Vit19t6F

Optimal Control and HJB ^4FMK2LHS

Gradient Free ^fAH2boJT

Gradient Based ^jJXLmEU5

SARSA ^ncC0jVzs

Q-Learning ^yR6u86pZ

Policy Gradient Optimization ^rJix9T3k

Deep
Policy
Network ^MBINYVJd

DQN ^Db8Mt1SB

Q(s,a) ^hn3hIcME

Off Policy ^gxACb2CW

On Policy ^RtfhrmhC

TD(0)
TD(n)
TD( ) ^QCNjx3VE

doesnt always take the best
action, takes risks
explores ^5CxEz2Pq

always takes the best
action,
very safe and conservative
doesnt explore ^RTxcNoVQ

ON policy ^LR45oJJf

OFF policy ^3dp9Gok5

or as I like to call it "Fuck around and find out",
Off policy methods are methods that tend to have a sense
of exploration, they will update their value estimation
according to the reward but then dont have to necessarily
take that reward all the time instead they will have an
element of randomness where they decide to take a risk
and explore to find new routes. This results in worse
performance while learning but it has higher potential of
reaching better results. it also learns faster due to not
being scared of risk taking and learning from those mistakes.
these methods can often learn from imitation as well, just by watching
others play and make mistakes. also produces higher variance ^0fvv4LHO

On Policy methods are methods that
only consider and take the best option estimate
they have, while this give a better performance
during training because we always maximizing
the reward we would get, this is very conservative
and doesnt like to explore, meaning it will be slower
to train and less potential for an optimal path.
While worse than Off policy, in certain situations
where mistakes are very costly, this is desired. ^4hR56NvV

IN this example, an OFF policy will learn the optimal path while an ON
policy will learn the safer path, this is because an ON policy will try to
take the optimal path but jump into the cliff by accident and then realize
that the optimal path is "dangerous" and thus will stay away from it
while OFF policy does not care about the consequences of the cliff, it will
go to the optimal path ^9rMxCA0a

Example SARSA ^tGkT9RcI

Example Q-learning ^774jJOua

How do we choose what action
to take if we dont take the optimal
action?
Epsilon greedy Q-learning says that for a given epsilon between
0 and 1, you go to the optimal path epsilon% of the time and otherwise go explore
some random path  ^85tpBv9F

Deep Reinforcement Learning ^nNY57Uz5

Everything we learned so far works in a tabular dynamic programming way.
This is an intractable way to approximate large environments
Board game Go on 19 × 19 board: 3^19×19 ≈ 10172 ^kTFVnUse

MSE between the truth and our approximation
which we can subsequently minimize by finding the gradient for it ^YKy3ZHRX

Batch based algorithms are obviously unfeasible, thus we perform SGD ^1kWdOCzX

Problem:
Unlike Supervised learning, true Q of oru "dataset" is unknown
Solution:
Bootstrap your model as a predictor of future models ^ntMHeLjT


Use function approximators (e.g. neural networks) to generalize Value
and Q-Value function, by using replay buffers to collect trajectories of agent interaction with
environment and computing discounted reward for all actions in trajectories.
thus training the neural network to predict the maximum Q value

Our Objective ^iJwZ3W1p

Deep Q-Learning ^pFIJyo0M

Deep Policy Gradient ^VtSoSC6j

Unlike Q-learning based which learns a determinstic value function and infers the 
policy from it, Policy gradient learns the Policy itself ^BSMBi05m

More effective in high-dimensional or continuous spaces and better convergence
But does not really learn a value function and cannot evaluate value

Our objective measures the quality of our policy estimation ^TiHS9VEt

all possible actions
at time t ^uQtXkAFl

And the gradient is acquired by ^Bcx0Smfy

But this is highly inefficient and has high variance because
it requires us to sample a trajectory with its corresponding reward to compute this
policy estimation ^xruyBHWx

Alternative methods to check later ^Ta6c0iSA

Actor Critic ^r14Pf3A0

Simulate two networks one as an actor that learns the policy
and another as a critic that learns the value function ^NxEDMgIG

Actor performs and critic evaluates and updates value function and policy
which reduces variance

We can similarly formulate our object as policy gradient methods except we now
replace the trajectory reward with a long term value ^nXYb7643

WIP ^dUl469Er

# Embedded files
0c56f3322d97551dfab15d16173f46d7608d9c0c: $$p(s^{'},s,a)$$
50699bce0f593461d93840c3e23985b8fbf68815: $$\frac{d x}{d t} = f(x(t), u(t), t)dt$$
120a11884e18b9a1698118dc7ee755e44d43403b: $$\pi_s(s,a)$$
74e67cfd08dfaa4ff77b8228f721859b51943541: $$V(s)$$
558f0fb0752aaf4b02ebdbca4d3b48f367884038: $$\lambda$$
862e8526888e2dc3ea75a5d20c86e1923336eebb: $$\theta^{new} = \theta^{old} + \alpha \nabla_{\theta} R_{\Sigma, \theta}$$
03ba1593f30fde0b83514ff539f7e7beb9e3b28f: $$\color{red} Q(S,A)_{new} \leftarrow Q(S,A)_{old} + \alpha [ R + \gamma Q(S^{'}, a) - Q_{old}(S,A) ]$$
c3dac01c651eff97ddefcf706d975f3cbadfe324: $$\color{red} Q(S,A)_{new} \leftarrow Q(S,A)_{old} + \alpha [ R + \gamma max_a Q(S^{'}, a) - Q_{old}(S,A) ]$$
61944105ed05ee31c7aa023482b57be59f7c120f: [[Pasted Image 20240605172351_182.png]]
482fe82368ccfcf3b607595015caf6e3a4843b8d: [[Pasted Image 20240607174539_094.png]]
55fd8c3e65b97a8e0ef64f7d375ac6b7b806b474: [[Pasted Image 20240607174612_108.png]]
8c50c4a89a0323294275c35274e5c7b05fc59b2a: [[Pasted Image 20240607185512_464.png]]
acaef36586e3dc827b46bca4e11180fb705cad20: [[Pasted Image 20240607190216_530.png]]
d73a49f1b7cca9453455b31b725fe42bc105b59f: [[Pasted Image 20240607190646_550.png]]
7b9923caf5b124957f790a084759fbfd71645527: [[Pasted Image 20240607190947_586.png]]
a80c20358e3086990451da006cbe01f4309cabaa: [[Pasted Image 20240607191136_630.png]]
b9a89c207ed837d1aa96f6dc3f383b52efe05b8c: [[Pasted Image 20240607191521_663.png]]
4f5800db531f031b3f27104c5b5011624c90779a: [[Pasted Image 20240607191602_681.png]]
a15c56f20c44ba16d92f9dda763b3da14b27069e: [[Pasted Image 20240607194816_633.png]]
04f6d7b90dc747a9d7c5ca93872df27ee2935f13: [[Pasted Image 20240607224600_250.png]]
fe4146ff8ac41e226e1d18f422aec5cd6b7038ac: [[Pasted Image 20240607224746_261.png]]
db2cbe8bfd16a94b5d267fc85cbe317a25c8e49b: [[Pasted Image 20240607225008_302.png]]
46dde5cc9a43202a96503b3907db527908d851e8: [[Pasted Image 20240608114221_124.png]]
6a7fd643c10a4b545463f0fd20ddc7196e1911b0: [[Pasted Image 20240608122627_437.png]]
d160f52c80410ddb80f4a62418419645ba98dae4: [[Pasted Image 20240608133715_022.png]]
4d1467c46a9b4433e2c7eadc6c3322432d67a019: [[Pasted Image 20240608141501_319.png]]
f71ab2ac1658b8cb65509ecd8fd6e60652d1da6b: [[Pasted Image 20240608141601_336.png]]
bb86508b82af370f5414ccc2222f1087afd0ba0e: [[Pasted Image 20240608141601_339.png]]
e6b028853eb4f06d3b5b978afe0cf117a4d91826: [[Pasted Image 20240608141747_344.png]]
da1ca322c8469736cab2905ebc33eae77a0a9c46: [[Pasted Image 20240608141935_382.png]]
694297df5802d28dd7fa822f3245233df2ae2877: [[Pasted Image 20240608141951_405.png]]
ef73c540320202794e021a248074584c5ae5415c: [[Pasted Image 20240608142617_450.png]]
020e555983c85187d9bca99818f7ad5951946dd7: [[Pasted Image 20240608150131_087.png]]
4f1e7203223ed9a1af90935397f2bb3ea08b5e6b: [[Pasted Image 20240608150431_106.png]]
25e52d2485be3d8bc8d272916e35decdcc46bdc1: [[Pasted Image 20240608150859_139.png]]
b8b36f34a5c3ed4c6ab0931e45612fe3debf330c: [[Pasted Image 20240608151340_195.png]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.1.6",
	"elements": [
		{
			"type": "rectangle",
			"version": 180,
			"versionNonce": 910874734,
			"isDeleted": false,
			"id": "PVvg6coOof1h_uJQ6GVKl",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -333.1148701131175,
			"y": 315.8880020443418,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 735.3423823310529,
			"height": 594.8043094708958,
			"seed": 1340266666,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717846065548,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 194,
			"versionNonce": 1254075762,
			"isDeleted": false,
			"id": "D6dVXYR-Ect1UD-yqidcc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -236.5,
			"y": -316,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 508.5956095161049,
			"height": 0.032563459512402915,
			"seed": 1966829523,
			"groupIds": [
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065548,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					508.5956095161049,
					-0.032563459512402915
				]
			]
		},
		{
			"type": "line",
			"version": 278,
			"versionNonce": 74554030,
			"isDeleted": false,
			"id": "Ui9Y2XAQfM9oRV-H1XJvc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -170.66795535734562,
			"y": -306.6617942268773,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 24.912737556926743,
			"height": 145.7301490172107,
			"seed": 1356698685,
			"groupIds": [
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065548,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					18.169440173096973,
					-36.52619416241146
				],
				[
					22.103030313664362,
					-76.23672320052026
				],
				[
					24.912737556926743,
					-130.74504371981112
				],
				[
					21.72840268122934,
					-145.7301490172107
				]
			]
		},
		{
			"type": "line",
			"version": 145,
			"versionNonce": 1762471730,
			"isDeleted": false,
			"id": "ORywh9bRZ4IdYhnspOlsV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -146.31715924907135,
			"y": -440.77848663860334,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 48.51427840033105,
			"height": 47.76502313546109,
			"seed": 850154483,
			"groupIds": [
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065549,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					21.353775048794375,
					35.21499744888894
				],
				[
					48.51427840033105,
					47.76502313546109
				]
			]
		},
		{
			"type": "line",
			"version": 125,
			"versionNonce": 1560679662,
			"isDeleted": false,
			"id": "XOOHldVUf2r-mvtnT1JtQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -147.0664145139413,
			"y": -441.7150557196908,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 19.293323070401925,
			"height": 64.24863896260058,
			"seed": 2053699133,
			"groupIds": [
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065549,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-6.368669751394833,
					41.021725751631266
				],
				[
					12.924653319007092,
					64.24863896260058
				]
			]
		},
		{
			"type": "line",
			"version": 135,
			"versionNonce": 1841592562,
			"isDeleted": false,
			"id": "KOQyxakQFwOAep8ltmXwJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -147.8156697788113,
			"y": -381.0253792652226,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 29.59558296236412,
			"height": 62.56281461664315,
			"seed": 742537747,
			"groupIds": [
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065549,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					20.79183360014187,
					34.46574218401895
				],
				[
					29.59558296236412,
					62.56281461664315
				]
			]
		},
		{
			"type": "ellipse",
			"version": 122,
			"versionNonce": 428951342,
			"isDeleted": false,
			"id": "fkaqYUSsIqJVI3-Bu1iOU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -170.10601390869314,
			"y": -494.35023807680676,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 44.76800207598117,
			"height": 41.95829483271871,
			"seed": 1198005949,
			"groupIds": [
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065549,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 107,
			"versionNonce": 2020379314,
			"isDeleted": false,
			"id": "NF-mpxfG6ULbjiqQ-tQ3V",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -132.64325066519427,
			"y": -460.25912352522295,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 16.108988194704523,
			"height": 5.994042118959783,
			"seed": 1798579005,
			"groupIds": [
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065549,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-8.616435546004709,
					-0.9365690810874412
				],
				[
					-16.108988194704523,
					-5.994042118959783
				]
			]
		},
		{
			"type": "line",
			"version": 101,
			"versionNonce": 2054959470,
			"isDeleted": false,
			"id": "Iv0IvMk_yJmLl9EJUle-b",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -140.6977447625465,
			"y": -480.30170186049486,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 9.365690810874725,
			"height": 4.3082177730023545,
			"seed": 347716413,
			"groupIds": [
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065549,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.120903956784872,
					-4.3082177730023545
				],
				[
					9.365690810874725,
					-2.0604519783923934
				]
			]
		},
		{
			"type": "ellipse",
			"version": 121,
			"versionNonce": 531391602,
			"isDeleted": false,
			"id": "V0iQcl1sXq1Jcgy4kfOCd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -136.20221317332664,
			"y": -478.24124988210235,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 2.99702105947992,
			"height": 5.806728302742272,
			"seed": 54129917,
			"groupIds": [
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065549,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 93,
			"versionNonce": 1259328430,
			"isDeleted": false,
			"id": "9tun78K4Pa1KcMkrdrCmC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -142.59058081661814,
			"y": -493.9036224097155,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 22.005567733623252,
			"height": 4.715478800062101,
			"seed": 1824590589,
			"groupIds": [
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065549,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-8.033778696402152,
					-4.715478800062101
				],
				[
					-22.005567733623252,
					-1.9211209926179436
				]
			]
		},
		{
			"type": "line",
			"version": 99,
			"versionNonce": 223020594,
			"isDeleted": false,
			"id": "-fsfaGeHqzXJEHA7ZgEzF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -139.7962230091739,
			"y": -492.855738231924,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 17.81403102245693,
			"height": 8.907015511228451,
			"seed": 1953717587,
			"groupIds": [
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065549,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.842241985235802,
					-6.811247155645219
				],
				[
					-17.81403102245693,
					-8.907015511228451
				]
			]
		},
		{
			"type": "line",
			"version": 91,
			"versionNonce": 91565550,
			"isDeleted": false,
			"id": "TOdrqSCnqQN_95lQ215Ca",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -151.67224369081185,
			"y": -493.72897504675024,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 15.194320577977976,
			"height": 3.8422419852357734,
			"seed": 286498205,
			"groupIds": [
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065549,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-4.54083143709687,
					-1.047884177791616
				],
				[
					-15.194320577977976,
					2.7943578074441575
				]
			]
		},
		{
			"type": "line",
			"version": 1181,
			"versionNonce": 439316466,
			"isDeleted": false,
			"id": "wSZWRCUGo2FK9iVbQxI_Y",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -99.23896112812439,
			"y": -390.7105511943524,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 12.690017133850333,
			"height": 19.05699896305235,
			"seed": 20812797,
			"groupIds": [
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065549,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.391431800300065,
					-5.7272363904918
				],
				[
					1.1957159001500344,
					-8.007994245112396
				],
				[
					1.3114303421000386,
					-10.491486131254863
				],
				[
					3.0857184520000818,
					-11.201055241581297
				],
				[
					4.6285776780001235,
					-9.984651052450314
				],
				[
					4.860006561900137,
					-7.4504756584273615
				],
				[
					6.71143763310018,
					-8.210728276634274
				],
				[
					8.408582781700218,
					-7.349108642666447
				],
				[
					8.987154991450238,
					-4.865616756524002
				],
				[
					7.637153168700204,
					-3.4971620437516258
				],
				[
					5.4000072910001435,
					-4.105364138317125
				],
				[
					2.7385751261500744,
					2.128707330979257
				],
				[
					3.9728625069501025,
					4.206731154078032
				],
				[
					3.9342910263001105,
					6.842273563861884
				],
				[
					2.198574397050061,
					7.8559437214710535
				],
				[
					0.5785722097500177,
					6.335438485057303
				],
				[
					0.6557151710500193,
					3.0410104728275087
				],
				[
					-1.5814307066500408,
					4.0039971225562105
				],
				[
					-3.702862142400095,
					2.4328083782619885
				],
				[
					-3.4328617778500874,
					0.20273403152184954
				],
				[
					-1.735716629250044,
					-0.7095691103264024
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1498,
			"versionNonce": 1991589934,
			"isDeleted": false,
			"id": "Y7QlMvYdeHKiOObPlCYw4",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -105.12107705165505,
			"y": -478.68307558952586,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 66.65303446783608,
			"height": 45.172986637245245,
			"seed": 1561362419,
			"groupIds": [
				"tRaurGkiAz7cywwh46T5-",
				"HJcKvCAekeHbzJxzfg1BJ",
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065549,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-5.526338550417151,
					4.907536506402298
				],
				[
					-11.187465845966418,
					9.046422716621112
				],
				[
					-8.019930335361467,
					1.3599197547861763
				],
				[
					-5.661127295549276,
					-3.547616751616122
				],
				[
					-12.130987061891297,
					-5.971821531887127
				],
				[
					-14.691973219401675,
					-12.298404738935865
				],
				[
					-12.333170179589487,
					-19.393638242168112
				],
				[
					-4.7176060796243995,
					-23.118635831365044
				],
				[
					-2.5609861575103885,
					-29.681726821854863
				],
				[
					3.5719017460013234,
					-33.99799386965449
				],
				[
					13.074508277816165,
					-33.465851356912054
				],
				[
					20.420494887517048,
					-36.126563920624136
				],
				[
					28.238242105180337,
					-35.890056137183066
				],
				[
					35.382045597182966,
					-32.75632800658883
				],
				[
					41.380144755562554,
					-25.069825044753895
				],
				[
					48.456553874999145,
					-22.882128047923967
				],
				[
					51.961061248434405,
					-16.969433461897108
				],
				[
					50.68056816967923,
					-9.2238035542019
				],
				[
					43.87373654050687,
					-4.907536506402273
				],
				[
					40.504017912203736,
					1.3007928089259053
				],
				[
					31.270988870653145,
					4.9666634522625674
				],
				[
					21.700987966272255,
					2.069443105109407
				],
				[
					15.56810006276054,
					5.735313748446069
				],
				[
					6.200282276077829,
					5.439679019144723
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 145,
			"versionNonce": 1784717746,
			"isDeleted": false,
			"id": "nwDNNZQZ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -114.70628030276386,
			"y": -500.35662610695624,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a18072",
			"width": 54.48976135253906,
			"height": 12.850540802325042,
			"seed": 101236179,
			"groupIds": [
				"HJcKvCAekeHbzJxzfg1BJ",
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065549,
			"link": null,
			"locked": false,
			"fontSize": 10.280432641860035,
			"fontFamily": 1,
			"text": "Good Boy!!",
			"rawText": "Good Boy!!",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Good Boy!!",
			"lineHeight": 1.25
		},
		{
			"type": "ellipse",
			"version": 255,
			"versionNonce": 1656293998,
			"isDeleted": false,
			"id": "ps300acdciGKTkOdlxleX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -55.960191485687595,
			"y": -366.4089488679785,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 3.057123403248027,
			"height": 3.641573465633675,
			"seed": 1331522365,
			"groupIds": [
				"bIjb5NJcVWOP4dCISMX-M",
				"7WUIK_pyDpYhwnTRQAOpp",
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065549,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 257,
			"versionNonce": 151362418,
			"isDeleted": false,
			"id": "0c3AqfuG",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -51.315266632740894,
			"y": -353.76149061931625,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 24.263080517601274,
			"height": 7.520246374798151,
			"seed": 3831,
			"groupIds": [
				"bIjb5NJcVWOP4dCISMX-M",
				"7WUIK_pyDpYhwnTRQAOpp",
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717846065549,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.5007919770924718,
					-0.9487799919352408
				],
				[
					-0.5972688937272612,
					-1.5271098492847106
				],
				[
					-1.1198521921657063,
					-1.722852262541454
				],
				[
					-1.811270094715034,
					-1.8652103812736427
				],
				[
					-2.5026879972643594,
					-1.9363894406397237
				],
				[
					-3.2101853859194898,
					-1.7673391746452631
				],
				[
					-4.046318663421,
					-1.447033407497861
				],
				[
					-5.244240378302977,
					-0.9131904622521965
				],
				[
					-6.594917211190036,
					-0.5661925478425145
				],
				[
					-7.945594044077097,
					-0.21919463343283274
				],
				[
					-9.312350363069955,
					0.21677710518445995
				],
				[
					-11.121292549972267,
					0.7862095801131682
				],
				[
					-11.78055148031,
					0.9641572285283901
				],
				[
					-12.584525785599913,
					1.248873465992745
				],
				[
					-13.372420604784034,
					1.5780766155609045
				],
				[
					-14.039719278174664,
					1.8983823827083148
				],
				[
					-14.972329472310966,
					2.5300965345823507
				],
				[
					-15.744144805389286,
					3.0461447149865077
				],
				[
					-16.31496656214513,
					3.4554243063415173
				],
				[
					-17.014424207747354,
					3.8558065152757663
				],
				[
					-17.754080568614075,
					4.22059919452697
				],
				[
					-18.469617700322104,
					3.5088086008660837
				],
				[
					-19.241433033400426,
					2.3165593564840847
				],
				[
					-19.796175304050468,
					1.586973997981665
				],
				[
					-20.383076546912104,
					1.115412729681328
				],
				[
					-21.018216248091136,
					0.5103907250695753
				],
				[
					-21.58903800484698,
					-0.11242604438369969
				],
				[
					-21.999064900544838,
					-0.7708323435200192
				],
				[
					-22.401052053189797,
					-1.4203412602355776
				],
				[
					-22.786959719728955,
					-1.9452868230604925
				],
				[
					-23.044327499204883,
					-2.6219471860317056
				],
				[
					-24.263080517601274,
					-3.299647180271181
				]
			]
		},
		{
			"type": "line",
			"version": 230,
			"versionNonce": 675908782,
			"isDeleted": false,
			"id": "GPwrEJPu",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -60.70492170688188,
			"y": -359.72463098045506,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 16.60005327010244,
			"height": 6.841981681935401,
			"seed": 38524,
			"groupIds": [
				"bIjb5NJcVWOP4dCISMX-M",
				"7WUIK_pyDpYhwnTRQAOpp",
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717846065549,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.17882961368260133,
					0.12440320951833136
				],
				[
					-1.3995361070812329,
					0.7541944577048906
				],
				[
					-2.853498618326739,
					1.4228617088659385
				],
				[
					-4.221933923028392,
					1.974900951103534
				],
				[
					-6.072431664613583,
					2.744645809998209
				],
				[
					-7.098758143139824,
					3.180057043312369
				],
				[
					-8.09398381928648,
					3.708770683765277
				],
				[
					-8.785976672232202,
					4.0975307135100625
				],
				[
					-9.48574472577282,
					4.33856193195183
				],
				[
					-10.068884770390003,
					4.462965141470161
				],
				[
					-10.613148812032705,
					4.361887533736517
				],
				[
					-11.693901694723214,
					3.7942978903091302
				],
				[
					-12.665801769085183,
					3.2422586480715347
				],
				[
					-13.62992664285226,
					2.8923746213012276
				],
				[
					-14.298593894013292,
					2.666893804049252
				],
				[
					-14.78065633089683,
					2.425862585607485
				],
				[
					-15.254943567185473,
					2.114854561811657
				],
				[
					-15.830308411207762,
					1.671668127902601
				],
				[
					-16.289045246306607,
					1.244032095183337
				],
				[
					-16.55340206653306,
					0.8241712630589519
				],
				[
					-16.60005327010244,
					0.2643568202264542
				],
				[
					-16.545626865938164,
					-0.3032328232009327
				],
				[
					-16.42899885701473,
					-0.8163960624640496
				],
				[
					-16.24239404273723,
					-1.2595824963731053
				],
				[
					-15.838083611802656,
					-1.6250169243332033
				],
				[
					-14.94637970535716,
					-2.3790165404652392
				]
			]
		},
		{
			"type": "line",
			"version": 207,
			"versionNonce": 73751858,
			"isDeleted": false,
			"id": "FyWUp2yE",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -74.14824353545666,
			"y": -361.7384079345331,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 5.683671634868801,
			"height": 5.061655587277154,
			"seed": 93731,
			"groupIds": [
				"bIjb5NJcVWOP4dCISMX-M",
				"7WUIK_pyDpYhwnTRQAOpp",
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717846065549,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.30323282320093564,
					0
				],
				[
					-0.9485744725772833,
					-0.10107760773364424
				],
				[
					-1.368435304701654,
					-0.46651203569374267
				],
				[
					-1.4695129124352981,
					-0.9641248737670782
				],
				[
					-1.4695129124352981,
					-1.4150865082710393
				],
				[
					-1.881598543964774,
					-1.6250169243332269
				],
				[
					-2.884599420706327,
					-1.593916121953644
				],
				[
					-3.6698946807907986,
					-1.6638929273077054
				],
				[
					-3.8331738932836097,
					-2.0371025558626994
				],
				[
					-3.6698946807907986,
					-2.5969169986951908
				],
				[
					-3.498840267703092,
					-3.0945298367685163
				],
				[
					-3.327785854615385,
					-3.553266671867363
				],
				[
					-3.0167778308195548,
					-3.965352303396836
				],
				[
					-2.5424905945309138,
					-4.28413552778756
				],
				[
					-1.920474546939253,
					-4.540717147419118
				],
				[
					-1.2129312928037388,
					-4.859500371809859
				],
				[
					-0.6064656464018704,
					-5.046105186087357
				],
				[
					0.1010776077336434,
					-5.061655587277154
				],
				[
					0.6764424517559297,
					-5.007229183112874
				],
				[
					1.174055289829258,
					-4.6106939527731825
				],
				[
					1.6016913225485245,
					-3.802073090904026
				],
				[
					1.8349473403953984,
					-3.071204234983829
				],
				[
					1.8504977415851909,
					-2.402536983822798
				],
				[
					1.7494201338515447,
					-1.9671257505086381
				],
				[
					1.516164116004671,
					-1.6561177267128098
				],
				[
					1.1896056910190496,
					-1.407311307676147
				],
				[
					0.9019232690079075,
					-1.2051560922088485
				],
				[
					0.7619696582997826,
					-1.1429544874496695
				]
			]
		},
		{
			"type": "line",
			"version": 207,
			"versionNonce": 1695532782,
			"isDeleted": false,
			"id": "BZY7EP6H",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -72.7875834313499,
			"y": -366.146946671839,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 23.29450098230769,
			"height": 4.680670758127241,
			"seed": 57286,
			"groupIds": [
				"bIjb5NJcVWOP4dCISMX-M",
				"7WUIK_pyDpYhwnTRQAOpp",
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717846065549,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.5942873698071118,
					0.14065454698879784
				],
				[
					2.0956449356356037,
					0.4922909144607925
				],
				[
					3.307678387215896,
					0.6563878859477232
				],
				[
					4.261666007169417,
					0.6563878859477232
				],
				[
					5.043623072705089,
					0.6720161689464785
				],
				[
					6.380769654771089,
					0.7110868764433669
				],
				[
					7.7882923727353,
					0.6407596029489679
				],
				[
					8.875212693829885,
					0.6016888954520797
				],
				[
					9.837019884438762,
					0.6251313199502126
				],
				[
					10.767548792426215,
					0.7110868764433669
				],
				[
					11.61206242320474,
					0.7110868764433669
				],
				[
					12.401839059395769,
					0.5548040464558137
				],
				[
					13.152517842310015,
					0.2656808109788404
				],
				[
					13.934474907845685,
					-0.015628282998755315
				],
				[
					14.62259712551708,
					-0.32037980147448736
				],
				[
					15.365456337775967,
					-0.789228291437157
				],
				[
					16.077037267413427,
					-1.3440323378929806
				],
				[
					16.647865925254475,
					-1.789438403357507
				],
				[
					17.351627284236574,
					-2.1410747708295017
				],
				[
					18.227419197636532,
					-2.4692687138033635
				],
				[
					19.103211111036487,
					-2.7896485152778476
				],
				[
					19.79133332870787,
					-3.0162586187597995
				],
				[
					20.495094687689978,
					-3.242868722241752
				],
				[
					21.24577347060423,
					-3.461664684224326
				],
				[
					21.730586851236346,
					-3.6101333727125016
				],
				[
					22.113745813348828,
					-3.813301051696321
				],
				[
					22.449987351529163,
					-3.9461414571857407
				],
				[
					22.864424596263067,
					-3.969583881683874
				],
				[
					23.29450098230769,
					-3.8992566081894746
				]
			]
		},
		{
			"type": "line",
			"version": 217,
			"versionNonce": 166127346,
			"isDeleted": false,
			"id": "YgQsbIrL",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -51.43463327737148,
			"y": -369.8458876761875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 4.046038456014398,
			"height": 2.8711034983383574,
			"seed": 23323,
			"groupIds": [
				"bIjb5NJcVWOP4dCISMX-M",
				"7WUIK_pyDpYhwnTRQAOpp",
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717846065549,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.5808907242225235,
					-1.3082881787643197
				],
				[
					1.1018291640805387,
					-2.101358639443682
				],
				[
					1.7471708134568877,
					-2.6145218787067988
				],
				[
					2.2758844539097978,
					-2.8711034983383574
				],
				[
					2.8045980943627105,
					-2.816677094174087
				],
				[
					3.372187737790101,
					-2.661173082276173
				],
				[
					3.8464749740787414,
					-2.3812658608599273
				],
				[
					4.046038456014398,
					-2.2335370495569093
				]
			]
		},
		{
			"type": "line",
			"version": 207,
			"versionNonce": 429177134,
			"isDeleted": false,
			"id": "28pBL758",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -51.50685940312021,
			"y": -360.6498798512477,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 9.796752749568654,
			"height": 11.973808916139465,
			"seed": 66738,
			"groupIds": [
				"bIjb5NJcVWOP4dCISMX-M",
				"7WUIK_pyDpYhwnTRQAOpp",
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717846065549,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.1321784101132271,
					-1.1027479145497452
				],
				[
					0.6142408469967653,
					-3.449020073166237
				],
				[
					1.127404086259884,
					-5.114873305783932
				],
				[
					1.4695129124352977,
					-6.530457508149224
				],
				[
					1.8582729421800863,
					-7.789623566606734
				],
				[
					2.2237073701401857,
					-8.821983316397981
				],
				[
					2.6357930016696636,
					-9.744850365453797
				],
				[
					3.078979435578719,
					-10.472194734624923
				],
				[
					3.6854450819805895,
					-11.097867310255982
				],
				[
					4.245259524813082,
					-11.355957247703795
				],
				[
					4.843949970620057,
					-11.441987226853065
				],
				[
					5.605919628919842,
					-11.395061783680736
				],
				[
					6.616695706256289,
					-11.24646454696836
				],
				[
					7.308688559202012,
					-10.964911887934383
				],
				[
					8.039557415122212,
					-10.597329249751134
				],
				[
					8.863728678181163,
					-10.261030240349442
				],
				[
					9.485744725772825,
					-9.823059437407679
				],
				[
					9.726775944214593,
					-8.994043274696523
				],
				[
					9.796752749568654,
					-7.860011731365227
				],
				[
					9.757876746594174,
					-7.14048826938951
				],
				[
					9.54794633053199,
					-6.303651199482958
				],
				[
					9.08920949543314,
					-5.326037800059415
				],
				[
					8.381666241297626,
					-4.598693430888308
				],
				[
					7.3475645621764905,
					-4.019946298429578
				],
				[
					6.080206865208482,
					-3.151825599741484
				],
				[
					5.069430787872033,
					-2.338451251421097
				],
				[
					4.097530713510063,
					-1.6111068822499774
				],
				[
					3.2889098516409057,
					-1.0401806569866359
				],
				[
					2.4336377862023726,
					-0.5240007820910121
				],
				[
					1.298458499347592,
					0.10167179354004711
				],
				[
					0.3576592273652044,
					0.5318216892864003
				]
			]
		},
		{
			"type": "line",
			"version": 229,
			"versionNonce": 34683058,
			"isDeleted": false,
			"id": "dLxdIxC9",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -42.47207631185133,
			"y": -365.0584185885536,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 3.1087460631496144,
			"height": 8.73911081175815,
			"seed": 95862,
			"groupIds": [
				"bIjb5NJcVWOP4dCISMX-M",
				"7WUIK_pyDpYhwnTRQAOpp",
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717846065550,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.1321784101132271,
					0.4976128380733255
				],
				[
					0.27990722141625063,
					1.399536107081228
				],
				[
					0.31878322439073004,
					2.1692809659759167
				],
				[
					0.0699768053540614,
					2.9390258248706025
				],
				[
					-0.3110080237958284,
					3.7476466867397566
				],
				[
					-0.8552720654385332,
					4.657345156342555
				],
				[
					-1.4384121100557126,
					5.574818826540252
				],
				[
					-1.8893737445596694,
					6.344563685434941
				],
				[
					-2.2159321695452894,
					7.090982942544936
				],
				[
					-2.3558857802534123,
					7.798526196680445
				],
				[
					-2.7899628387588846,
					8.73911081175815
				]
			]
		},
		{
			"type": "line",
			"version": 261,
			"versionNonce": 1296130926,
			"isDeleted": false,
			"id": "QQsL48AZ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -43.45175158680819,
			"y": -356.7856051555845,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.811556943057555,
			"height": 6.787750119344002,
			"seed": 31679,
			"groupIds": [
				"bIjb5NJcVWOP4dCISMX-M",
				"7WUIK_pyDpYhwnTRQAOpp",
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717846065550,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.8863728678181152,
					0.3032328232009327
				],
				[
					-3.242258648071529,
					1.3373345023220655
				],
				[
					-4.843949970620056,
					2.0448777564575855
				],
				[
					-5.784749242602442,
					2.5269401933411295
				],
				[
					-6.671122110420558,
					2.9468010254654975
				],
				[
					-8.109534220476274,
					3.4133130611592404
				],
				[
					-9.462419123988136,
					3.856499495068296
				],
				[
					-10.18551277931344,
					4.12085631529475
				],
				[
					-10.589823210248015,
					4.424089138495683
				],
				[
					-10.582048009653121,
					4.968353180138382
				],
				[
					-10.395443195375623,
					5.551493224755574
				],
				[
					-10.0766599709849,
					6.165734071752339
				],
				[
					-9.695675141835011,
					6.593370104471609
				],
				[
					-9.081434294838242,
					6.787750119344002
				],
				[
					-8.11730942107117,
					6.671122110420566
				],
				[
					-7.425316568125445,
					6.453416493763487
				],
				[
					-6.787750119343995,
					6.134633269372756
				],
				[
					-5.706997236653484,
					5.512617221781086
				],
				[
					-4.548492348014016,
					5.04610518608734
				],
				[
					-3.4366386629439223,
					4.672895557532345
				],
				[
					-2.970126627250179,
					4.587368350988492
				],
				[
					-2.215932169545289,
					4.424089138495683
				],
				[
					-1.4617377118404002,
					4.198608321243707
				],
				[
					-0.6064656464018671,
					3.9731275039917313
				],
				[
					0.2099304160621867,
					3.7165458843601726
				],
				[
					0.8241712630589512,
					3.4133130611592404
				],
				[
					1.2217337328095397,
					2.809096735152037
				],
				[
					1.102758982705015,
					1.6150898241300795
				],
				[
					0.5340446790802944,
					0.7421154578935109
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 230,
			"versionNonce": 747328114,
			"isDeleted": false,
			"id": "T0hZJ9Tt",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -50.69149058006703,
			"y": -350.52075053413387,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 4.615359073130123,
			"height": 17.192925573349914,
			"seed": 88389,
			"groupIds": [
				"bIjb5NJcVWOP4dCISMX-M",
				"7WUIK_pyDpYhwnTRQAOpp",
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717846065550,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.006747961183988748,
					1.9613076079491207
				],
				[
					-0.5665624040164858,
					4.208340579873995
				],
				[
					-0.5976632063960686,
					5.708954294688877
				],
				[
					-0.6209888081807557,
					7.302870416642511
				],
				[
					-0.7453920176990871,
					8.616879317179887
				],
				[
					-0.7609424188888785,
					9.93866341831217
				],
				[
					-0.7220664159143999,
					11.097168306951643
				],
				[
					-0.5354616016369029,
					12.286773997970686
				],
				[
					-0.06894956594315446,
					13.398627683040779
				],
				[
					0.5141904786740256,
					14.479380565731296
				],
				[
					1.1362065262656864,
					15.49793184366264
				],
				[
					1.8670753821858874,
					16.23657590017773
				],
				[
					2.667921043460151,
					16.741963938845952
				],
				[
					3.4765419053293094,
					17.11517356740095
				],
				[
					3.8544166542412444,
					17.192925573349914
				]
			]
		},
		{
			"type": "line",
			"version": 207,
			"versionNonce": 845071790,
			"isDeleted": false,
			"id": "IINHRcWc",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -50.255052107341974,
			"y": -333.4911041732768,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 10.387667994780735,
			"height": 11.686126494128324,
			"seed": 10057,
			"groupIds": [
				"bIjb5NJcVWOP4dCISMX-M",
				"7WUIK_pyDpYhwnTRQAOpp",
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717846065550,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.24103121844176703,
					0.20215521546729515
				],
				[
					-0.48983763747842973,
					1.135179286854792
				],
				[
					-0.7541944577048856,
					2.247032971924884
				],
				[
					-1.0341016791211353,
					3.180057043312369
				],
				[
					-1.3295593017271723,
					4.253034725407986
				],
				[
					-1.687218529092377,
					5.357113209883188
				],
				[
					-2.1537305647861236,
					6.360114086624738
				],
				[
					-2.7290954088084116,
					7.1298589455194135
				],
				[
					-3.428863462349026,
					7.557494978238677
				],
				[
					-4.245259524813082,
					7.80630139727534
				],
				[
					-5.03832998549245,
					7.938479807388567
				],
				[
					-5.808074844387127,
					7.985131010957947
				],
				[
					-6.6633469098256635,
					8.148410223450764
				],
				[
					-7.425316568125445,
					8.4438678460568
				],
				[
					-8.031782214527313,
					8.71599986687815
				],
				[
					-8.607147058549605,
					9.306915112090234
				],
				[
					-8.646023061524083,
					9.936706360276787
				],
				[
					-8.342790238323147,
					10.434319198350114
				],
				[
					-7.689673388351902,
					10.970808039397918
				],
				[
					-6.826626122318475,
					11.312916865573328
				],
				[
					-5.761423640817753,
					11.515072081040618
				],
				[
					-4.5173915456344345,
					11.670576092938532
				],
				[
					-3.459964264728609,
					11.686126494128324
				],
				[
					-2.861273818921639,
					11.476196078066138
				],
				[
					-2.3325601784687264,
					11.009684042372395
				],
				[
					-1.7416449332566475,
					10.504296003704175
				],
				[
					-1.2751328975629024,
					9.757876746594187
				],
				[
					-0.8163960624640529,
					8.731550268067945
				],
				[
					-0.2643568202264542,
					7.790750996085552
				],
				[
					0.36543442796010256,
					6.795525319938897
				],
				[
					0.9796752749568662,
					5.862501248551412
				],
				[
					1.4384121100557181,
					5.116081991441419
				],
				[
					1.7027689302821725,
					4.439639539685486
				],
				[
					1.7416449332566508,
					3.942026701612152
				],
				[
					1.7416449332566508,
					3.459964264728615
				],
				[
					1.7416449332566508,
					3.265584249856222
				]
			]
		},
		{
			"type": "line",
			"version": 207,
			"versionNonce": 1008481330,
			"isDeleted": false,
			"id": "FkzG7l1n",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -45.68323415754329,
			"y": -339.3147294188537,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.483971278661029,
			"height": 23.838765023950387,
			"seed": 40065,
			"groupIds": [
				"bIjb5NJcVWOP4dCISMX-M",
				"7WUIK_pyDpYhwnTRQAOpp",
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717846065550,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.5683592565032232,
					2.511389792151325
				],
				[
					1.6583633100710529,
					6.943254131241909
				],
				[
					1.6895062830301333,
					9.229163106141257
				],
				[
					1.549362904714268,
					11.001908841777496
				],
				[
					1.3625050669597814,
					12.56472416135154
				],
				[
					1.230147431883689,
					13.948709867242984
				],
				[
					0.9031462158133426,
					15.356021174919123
				],
				[
					0.3192154728305776,
					16.405673255230045
				],
				[
					-0.3425727025498889,
					17.424224533161386
				],
				[
					-0.918717702292883,
					18.131767787296905
				],
				[
					-1.5960773641528898,
					18.419450209308042
				],
				[
					-2.3435087151708283,
					18.48165181406721
				],
				[
					-3.2777979039432505,
					18.644931026560023
				],
				[
					-4.06415797116004,
					18.8859622450018
				],
				[
					-5.006232903172235,
					19.391350283670022
				],
				[
					-5.9093791189855756,
					20.02891673245147
				],
				[
					-6.306452024213853,
					20.744235187181875
				],
				[
					-6.213023105336611,
					21.412902438342908
				],
				[
					-5.387734321920973,
					21.887189674631554
				],
				[
					-4.43787364666901,
					22.042693686529464
				],
				[
					-3.371226822820493,
					22.02714328533968
				],
				[
					-2.281222769252667,
					21.700584860354056
				],
				[
					-1.3002191210416219,
					21.38957683655822
				],
				[
					-0.36592993226919934,
					21.38957683655822
				],
				[
					0.5372162835441425,
					21.234072824660306
				],
				[
					1.3080048642813913,
					20.71313438480229
				],
				[
					1.821863918106226,
					19.896738322338244
				],
				[
					2.0632219585391005,
					18.917063047381376
				],
				[
					2.289008512492435,
					17.556402943274612
				],
				[
					2.7250101339195685,
					15.985812423105676
				],
				[
					3.238869187744398,
					14.835082735061105
				],
				[
					3.643727836212452,
					13.870957861294027
				],
				[
					4.064157971160039,
					12.463646553617895
				],
				[
					4.585802768224644,
					10.722001620361247
				],
				[
					4.889446754575681,
					8.762651070447514
				],
				[
					5.130804795008555,
					6.989905334811283
				],
				[
					5.177519254447176,
					5.504842021186191
				],
				[
					5.177519254447176,
					3.8098482914989185
				],
				[
					5.177519254447176,
					2.379211382038098
				],
				[
					5.177519254447176,
					1.1740552898292524
				],
				[
					5.161947767967636,
					0.45873683509884694
				],
				[
					5.014018646412003,
					-0.3887600297447889
				],
				[
					4.905018241055221,
					-1.3995361070812398
				],
				[
					4.905018241055221,
					-1.796071337420921
				]
			]
		},
		{
			"type": "line",
			"version": 207,
			"versionNonce": 1242947566,
			"isDeleted": false,
			"id": "5rFznrsP",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -38.39009599953106,
			"y": -332.13044406917,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 28.13845095292774,
			"height": 5.9324780539054505,
			"seed": 80656,
			"groupIds": [
				"bIjb5NJcVWOP4dCISMX-M",
				"7WUIK_pyDpYhwnTRQAOpp",
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717846065550,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.261412398304887,
					0.6317447511646378
				],
				[
					3.776450698628837,
					1.0265852206425363
				],
				[
					4.983357622932893,
					0.8291649859035871
				],
				[
					6.338207976667778,
					0.7738873201766813
				],
				[
					8.121315626123454,
					0.7580937013975654
				],
				[
					9.592963424145822,
					0.7186096544497755
				],
				[
					10.862162318736551,
					0.6633319887228697
				],
				[
					12.022350265325613,
					0.6238479417750799
				],
				[
					13.275976167344666,
					0.40273727886745664
				],
				[
					14.490669587934565,
					0.07896809389557972
				],
				[
					15.798800963954452,
					-0.40273727886745664
				],
				[
					17.029067377116007,
					-0.9397203173573987
				],
				[
					18.189255323705073,
					-1.460909737068237
				],
				[
					19.481813707153297,
					-1.8715438253252514
				],
				[
					20.494058224311534,
					-2.12424172579111
				],
				[
					21.607527193185604,
					-2.39273324503609
				],
				[
					22.970164043206328,
					-2.598050289164597
				],
				[
					24.10699250093789,
					-2.866541808409568
				],
				[
					25.142596506953627,
					-3.2218982309396766
				],
				[
					26.287211460971033,
					-3.885230219662546
				],
				[
					27.22159101527095,
					-4.430110067542047
				],
				[
					27.937948673567554,
					-4.848640965188619
				],
				[
					28.13845095292774,
					-4.905892833262914
				]
			]
		},
		{
			"type": "line",
			"version": 207,
			"versionNonce": 1923800562,
			"isDeleted": false,
			"id": "3u9R9U6h",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -11.666731554874339,
			"y": -335.559307531519,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 9.851179153732923,
			"height": 14.803981932681527,
			"seed": 29125,
			"groupIds": [
				"bIjb5NJcVWOP4dCISMX-M",
				"7WUIK_pyDpYhwnTRQAOpp",
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717846065550,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.6737188128994245,
					0.25012007489218896
				],
				[
					2.33451402609336,
					1.016112804249521
				],
				[
					3.8699662043292737,
					1.7821055336068579
				],
				[
					5.1233965539096005,
					2.4777519919007687
				],
				[
					6.063469316094844,
					2.977992141685148
				],
				[
					6.079137195464598,
					3.994104945934666
				],
				[
					5.91462446208218,
					5.424479124224378
				],
				[
					5.554263236577837,
					6.831404545492957
				],
				[
					4.81003896651452,
					8.386838761228757
				],
				[
					4.136320153615094,
					9.715601659093524
				],
				[
					3.4861031597702965,
					10.833325743768004
				],
				[
					2.702709191282583,
					11.513339697381143
				],
				[
					1.7156327909880695,
					11.82598979099638
				],
				[
					0.7833939684877028,
					12.185537398653901
				],
				[
					-0.10967515558827841,
					12.8421025952459
				],
				[
					-0.6893866922691904,
					13.662809090985904
				],
				[
					-0.7755600288028376,
					14.499148091406672
				],
				[
					0.07833939684877028,
					14.803981932681527
				],
				[
					1.4649467210720044,
					14.796165680341147
				],
				[
					2.616535854748936,
					14.592943119491242
				],
				[
					3.7054534709468547,
					14.061437960345335
				],
				[
					4.629858353762347,
					13.248547716945712
				],
				[
					5.146898372964231,
					12.388759959503805
				],
				[
					5.491591719098821,
					11.177240846744764
				],
				[
					5.883288703342672,
					9.840661696539621
				],
				[
					6.549173576557228,
					8.41810377059028
				],
				[
					7.410906941893711,
					7.347277199958097
				],
				[
					8.11596151353265,
					6.471856937835434
				],
				[
					8.61733365336478,
					5.674599199116572
				],
				[
					8.969860939184244,
					5.13527778763028
				],
				[
					9.075619124930085,
					4.883203649652994
				]
			]
		},
		{
			"type": "line",
			"version": 207,
			"versionNonce": 141537838,
			"isDeleted": false,
			"id": "KSk8Q4lI",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -11.938863575695684,
			"y": -345.13835466443055,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 14.096438678545994,
			"height": 23.348927386471946,
			"seed": 9627,
			"groupIds": [
				"bIjb5NJcVWOP4dCISMX-M",
				"7WUIK_pyDpYhwnTRQAOpp",
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717846065550,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.16336932243347924,
					0.9980173330222376
				],
				[
					0.9257594937897157,
					2.939472926167066
				],
				[
					1.7114881397793063,
					4.405310884043489
				],
				[
					2.6528066166579296,
					5.723005644049417
				],
				[
					4.138689501648162,
					7.266813706068199
				],
				[
					5.150023402426846,
					8.389583205718232
				],
				[
					5.920193065327533,
					9.333021465840815
				],
				[
					6.993762898461836,
					10.237474673892219
				],
				[
					8.269599511751876,
					10.978190663244668
				],
				[
					9.825497820642155,
					11.835861808810662
				],
				[
					11.007980535398781,
					12.521998725263458
				],
				[
					12.330494097955528,
					13.11457151674541
				],
				[
					13.349607490278657,
					13.371872860415207
				],
				[
					13.940848847656964,
					13.356278839586734
				],
				[
					14.096438678545994,
					13.792911422783963
				],
				[
					13.785259016767936,
					15.16518525568955
				],
				[
					13.038427828500604,
					17.17681394256251
				],
				[
					12.641673759733584,
					18.54908777546809
				],
				[
					12.377171047222236,
					19.437946962691033
				],
				[
					12.167124775522048,
					20.295618108257028
				],
				[
					11.871504096832895,
					21.20007131630843
				],
				[
					11.435852570343616,
					22.221479680573378
				],
				[
					11.007980535398781,
					22.993383711582776
				],
				[
					10.815049145096372,
					23.348927386471946
				]
			]
		},
		{
			"type": "line",
			"version": 219,
			"versionNonce": 1027493810,
			"isDeleted": false,
			"id": "uMTsLOZy",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4.319166992697838,
			"y": -319.83007672804484,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 6.80330052053377,
			"height": 3.452189064133707,
			"seed": 10775,
			"groupIds": [
				"bIjb5NJcVWOP4dCISMX-M",
				"7WUIK_pyDpYhwnTRQAOpp",
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717846065550,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.8163960624640496,
					-0.6842176523508225
				],
				[
					2.799072214162459,
					-1.5628153195740395
				],
				[
					4.089755512915167,
					-2.2081569689503935
				],
				[
					4.906151575379217,
					-2.511389792151326
				],
				[
					6.002454859259512,
					-2.5347153939360134
				],
				[
					6.80330052053377,
					-2.3247849778738288
				],
				[
					6.80330052053377,
					-1.7882961368260202
				],
				[
					5.87805164974118,
					-1.0574272809058167
				],
				[
					4.812849168240468,
					-0.4276360327192641
				],
				[
					3.5999178754367307,
					0.41208563152947264
				],
				[
					2.550265795125793,
					0.7697448588946754
				],
				[
					1.2207064933986267,
					0.8941480684130068
				],
				[
					0.03110080237957615,
					0.9174736701976938
				],
				[
					0.009256131337973554,
					-0.177348682939521
				],
				[
					0.9883390339976028,
					-0.6991756812433786
				],
				[
					1.6872185290923691,
					-1.0496520803109208
				],
				[
					1.9412084151922957,
					-1.2336651610567861
				]
			]
		},
		{
			"type": "line",
			"version": 368,
			"versionNonce": 2018851950,
			"isDeleted": false,
			"id": "U0jAU1TD",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -45.711538411913686,
			"y": -352.2716274156645,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 53.74834851282071,
			"height": 52.78340194938051,
			"seed": 85592,
			"groupIds": [
				"bIjb5NJcVWOP4dCISMX-M",
				"7WUIK_pyDpYhwnTRQAOpp",
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717846065550,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.3624673430528681,
					0.7420760732085535
				],
				[
					1.5276908712912098,
					1.5903588017660586
				],
				[
					3.26154348130986,
					1.720863836928752
				],
				[
					4.268296609707787,
					1.720863836928752
				],
				[
					5.321658679235248,
					1.720863836928752
				],
				[
					6.869075524735763,
					1.6276459546696842
				],
				[
					8.546997405398976,
					1.5251062841847052
				],
				[
					10.271528227191723,
					1.5251062841847052
				],
				[
					11.940128319629025,
					1.301383366762947
				],
				[
					13.552797682710889,
					0.8539375319194276
				],
				[
					15.65952182176581,
					0.229377720783674
				],
				[
					17.62641913743213,
					-0.30196420809300845
				],
				[
					19.015365583092226,
					-0.5909396430961134
				],
				[
					20.143301958426946,
					-0.8519497134215072
				],
				[
					21.830545627316067,
					-1.3926134305240978
				],
				[
					23.508467507979272,
					-1.7654849595603626
				],
				[
					25.111815082835232,
					-2.2408961590816094
				],
				[
					26.593979410754404,
					-2.7722380879582884
				],
				[
					27.77784651544455,
					-3.0612135229614004
				],
				[
					29.34390693739688,
					-3.2756146521572505
				],
				[
					31.264195311933666,
					-3.3035800168349745
				],
				[
					33.26837978050362,
					-3.434085051997671
				],
				[
					35.263242460847664,
					-3.6857733340971435
				],
				[
					36.61490175360413,
					-3.760347639904402
				],
				[
					38.11570965797512,
					-3.760347639904402
				],
				[
					40.082606973641425,
					-3.760347639904402
				],
				[
					42.19865290092226,
					-3.974748769100262
				],
				[
					43.59692113480828,
					-4.198471686522013
				],
				[
					44.286733463525366,
					-4.366263874588346
				],
				[
					45.181625133212414,
					-4.888284015239117
				],
				[
					46.16041289693262,
					-5.811141049603887
				],
				[
					47.15784423710465,
					-6.957721001390415
				],
				[
					48.01544875388806,
					-8.067013800273314
				],
				[
					48.61204320034609,
					-8.98987083463808
				],
				[
					49.34846447019273,
					-10.052554692391446
				],
				[
					49.82387566971396,
					-11.077951397241184
				],
				[
					50.1501382576207,
					-12.177922407898178
				],
				[
					50.308608657461114,
					-13.371111300814238
				],
				[
					50.40182653972018,
					-14.536334829052585
				],
				[
					50.420470116172005,
					-15.86002875713134
				],
				[
					50.420470116172005,
					-17.183722685210096
				],
				[
					50.32725223391293,
					-18.759104895388326
				],
				[
					50.03827679890982,
					-20.427704987825635
				],
				[
					49.516256658259046,
					-21.648859245419413
				],
				[
					48.66698467503762,
					-22.325912771613996
				],
				[
					47.70340347347262,
					-23.091028658622744
				],
				[
					46.76362136980434,
					-23.622370587499432
				],
				[
					45.99262070886629,
					-24.081845972381068
				],
				[
					45.17157409250212,
					-24.47606883968137
				],
				[
					44.30537703997719,
					-24.594544324805945
				],
				[
					44.09686068471063,
					-24.654641320942375
				],
				[
					45.31900419696832,
					-24.840347832976125
				],
				[
					46.55390651174853,
					-24.675992659206404
				],
				[
					47.81750344369084,
					-24.13189192780721
				],
				[
					48.6123032025256,
					-23.81937739708689
				],
				[
					49.722585256072435,
					-23.129565068369804
				],
				[
					50.66335661440461,
					-22.18879371003762
				],
				[
					51.15985915001036,
					-21.512469436327418
				],
				[
					51.51726411471191,
					-21.10574776868413
				],
				[
					51.8000947736062,
					-20.371774258470193
				],
				[
					52.19160987909428,
					-19.691283717979
				],
				[
					52.47126352587147,
					-18.861644565873306
				],
				[
					52.81616969023002,
					-17.79896070811994
				],
				[
					53.14243227813676,
					-16.7828857914961
				],
				[
					53.41276413668806,
					-15.636305839709571
				],
				[
					53.67377420701345,
					-14.527013040826677
				],
				[
					53.74834851282071,
					-13.044848712907507
				],
				[
					53.68309599523934,
					-11.730476573054656
				],
				[
					53.664452418787526,
					-10.565253044816311
				],
				[
					53.52462559539894,
					-9.1576630227044
				],
				[
					53.384798772010335,
					-8.001761282691964
				],
				[
					53.01192724297407,
					-6.948399213164504
				],
				[
					52.21957524377199,
					-5.988255025896112
				],
				[
					51.61365900908805,
					-4.97218010927228
				],
				[
					50.98909919795231,
					-3.928139827970725
				],
				[
					50.10352931649117,
					-2.9773174289282407
				],
				[
					49.134063340996875,
					-2.0171732416598447
				],
				[
					48.3510331300207,
					-1.2061776660059622
				],
				[
					47.73579510711085,
					-0.5443307019665827
				],
				[
					47.16716602533055,
					0.005654803361912567
				],
				[
					46.63582409645387,
					0.3412391794945547
				],
				[
					46.30956150854713,
					0.7513978614344516
				],
				[
					46.48667548483935,
					1.487819131281086
				],
				[
					46.73836376693883,
					2.4199979538717575
				],
				[
					47.03666099016785,
					3.240315317751548
				],
				[
					47.54935934259273,
					4.358929904860355
				],
				[
					47.95951802453263,
					5.496188068420975
				],
				[
					48.16459736550257,
					6.7825948435961045
				],
				[
					48.164597365502566,
					7.985105524738074
				],
				[
					47.95019623630671,
					9.122363688298691
				],
				[
					47.72647331888495,
					10.455379404603354
				],
				[
					47.54003755436681,
					11.657890085745322
				],
				[
					47.26970569581552,
					12.91633149624273
				],
				[
					46.93412131968287,
					14.006980718673821
				],
				[
					46.49599727306526,
					15.051020999975375
				],
				[
					46.28159614386941,
					15.750155116918378
				],
				[
					46.980730260812415,
					16.057774128373296
				],
				[
					47.88494371872537,
					16.430645657409567
				],
				[
					48.82644432954194,
					16.92470043338263
				],
				[
					49.71201421100308,
					17.381468056452057
				],
				[
					50.25267792810568,
					18.07128038516915
				],
				[
					50.597584092464224,
					19.078033513567078
				],
				[
					50.68148018649739,
					19.944959818576404
				],
				[
					50.68148018649739,
					20.830529700037538
				],
				[
					50.66283661004556,
					21.744064946176405
				],
				[
					50.476400845527436,
					22.713530921670706
				],
				[
					50.1501382576207,
					23.897398026360857
				],
				[
					49.56286559938858,
					25.137195860406454
				],
				[
					49.07813261164143,
					26.106661835900752
				],
				[
					48.63068677679791,
					26.852404893973294
				],
				[
					47.86630014227356,
					27.5608607991422
				],
				[
					47.54935934259273,
					27.943054116404383
				]
			]
		},
		{
			"type": "line",
			"version": 207,
			"versionNonce": 1342015858,
			"isDeleted": false,
			"id": "E8sGaxvC",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3.057207273175159,
			"y": -374.08769895234656,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 3.706250144579117,
			"height": 4.2070947587114365,
			"seed": 39511,
			"groupIds": [
				"bIjb5NJcVWOP4dCISMX-M",
				"7WUIK_pyDpYhwnTRQAOpp",
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717846065550,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.953035751463205,
					0.1040624145264325
				],
				[
					2.1027296738632564,
					0.9811599083920639
				],
				[
					2.692704186673809,
					2.2447749419273055
				],
				[
					3.2221684930422514,
					3.419193620154162
				],
				[
					3.706250144579117,
					4.2070947587114365
				]
			]
		},
		{
			"type": "line",
			"version": 207,
			"versionNonce": 1603239598,
			"isDeleted": false,
			"id": "ettzPNDT",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 6.0581647040329685,
			"y": -379.19631401649616,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 4.607770450017268,
			"height": 5.509290755455443,
			"seed": 7105,
			"groupIds": [
				"bIjb5NJcVWOP4dCISMX-M",
				"7WUIK_pyDpYhwnTRQAOpp",
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717846065550,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.580386969955574,
					0.7667867910691626
				],
				[
					3.436254237426351,
					2.011006867143661
				],
				[
					4.19020031483636,
					3.776063254133062
				],
				[
					4.494678538405766,
					4.919009603085209
				],
				[
					4.607770450017268,
					5.509290755455443
				]
			]
		},
		{
			"type": "line",
			"version": 207,
			"versionNonce": 1110412082,
			"isDeleted": false,
			"id": "kEBludLc",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -55.24086833198216,
			"y": -367.0833143245773,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 2.5176310379689557,
			"height": 0.3596615768527138,
			"seed": 44489,
			"groupIds": [
				"bIjb5NJcVWOP4dCISMX-M",
				"7WUIK_pyDpYhwnTRQAOpp",
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717846065550,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.5716050060694825,
					-0.1321205792520206
				],
				[
					1.4386463074108335,
					-0.3596615768527138
				],
				[
					1.8818007503186351,
					-0.3596615768527138
				],
				[
					2.350645305858772,
					-0.3596615768527138
				],
				[
					2.5176310379689557,
					-0.3596615768527138
				]
			]
		},
		{
			"type": "line",
			"version": 470,
			"versionNonce": 1657239790,
			"isDeleted": false,
			"id": "d6CAt6jwHO8incLS_RbOr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -42.12967245657408,
			"y": -354.0635278987219,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 50.76180783489127,
			"height": 42.81648139116925,
			"seed": 1992402291,
			"groupIds": [
				"7WUIK_pyDpYhwnTRQAOpp",
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065550,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.7955778227911168,
					1.1770853990699948
				],
				[
					5.296884295814749,
					12.212261015350634
				],
				[
					3.2369848474423435,
					36.04824034651699
				],
				[
					16.184924237211717,
					36.78391872093573
				],
				[
					28.691456602329865,
					42.81648139116925
				],
				[
					36.783918720935716,
					38.99095384419189
				],
				[
					50.76180783489127,
					36.489647371168246
				]
			]
		},
		{
			"type": "ellipse",
			"version": 3080,
			"versionNonce": 708531442,
			"isDeleted": false,
			"id": "y8JLHSjbOFc6HV8ZxeNTn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 1.3017186883922633,
			"x": 184.0481509759312,
			"y": -357.428070882895,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 37.04697027407043,
			"height": 40.651504232204545,
			"seed": 1795511443,
			"groupIds": [
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065550,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 3076,
			"versionNonce": 696658734,
			"isDeleted": false,
			"id": "1Ams3mMyDum8Tg9yAItgR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 1.3017186883922633,
			"x": 156.67264866268135,
			"y": -351.7937672643152,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 11.202372283419756,
			"height": 47.47220571872788,
			"seed": 1194543667,
			"groupIds": [
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065550,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					9.114806338755983,
					23.384698438834903
				],
				[
					-2.0875659446637718,
					47.47220571872788
				]
			]
		},
		{
			"type": "line",
			"version": 3079,
			"versionNonce": 967304882,
			"isDeleted": false,
			"id": "yfTSR9-eHVfo4c9dDZOUA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 1.3017186883922633,
			"x": 117.1291499440854,
			"y": -326.18993806250575,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 16.93220021673433,
			"height": 25.69237643296941,
			"seed": 22121427,
			"groupIds": [
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065550,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					16.93220021673433,
					25.69237643296941
				]
			]
		},
		{
			"type": "line",
			"version": 3106,
			"versionNonce": 37000558,
			"isDeleted": false,
			"id": "_AU_WvuXlgwiLsLiQS5VH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 1.3017186883922633,
			"x": 122.53683168114459,
			"y": -340.596684511001,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 13.43347965933414,
			"height": 30.114477478003153,
			"seed": 225876339,
			"groupIds": [
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065550,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-9.500868413279562,
					13.636164956219716
				],
				[
					3.9326112460545772,
					30.114477478003153
				]
			]
		},
		{
			"type": "line",
			"version": 3038,
			"versionNonce": 1495023730,
			"isDeleted": false,
			"id": "_DcXbfyJ02TWIFQ7zU1kK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 1.3017186883922633,
			"x": 170.1324956517425,
			"y": -313.64971057965715,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 13.402293730515403,
			"height": 7.706050664685048,
			"seed": 417919763,
			"groupIds": [
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065550,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-13.402293730515403,
					-7.706050664685048
				]
			]
		},
		{
			"type": "line",
			"version": 3023,
			"versionNonce": 102479790,
			"isDeleted": false,
			"id": "hugXnrRsprA2IgJbv_4NX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 1.3017186883922633,
			"x": 166.19344139853027,
			"y": -307.7593403161113,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 26.305721245448133,
			"height": 14.836060263221073,
			"seed": 1679759539,
			"groupIds": [
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065550,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					26.305721245448133,
					-14.836060263221073
				]
			]
		},
		{
			"type": "line",
			"version": 3256,
			"versionNonce": 1147101746,
			"isDeleted": false,
			"id": "7aZWM3Ug2V3CEtAh2SL23",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.1979160865728442,
			"x": 262.6588815663805,
			"y": -321.38367573484527,
			"strokeColor": "#000000",
			"backgroundColor": "#4c6ef5",
			"width": 57.96522282094665,
			"height": 21.582083962356627,
			"seed": 1556056659,
			"groupIds": [
				"Dd05LGoUV2VYsCPFM3-11",
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065550,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					16.96227128786686,
					-16.542109928865568
				],
				[
					32.89145861969144,
					-0.05147185039389543
				],
				[
					31.035330151256474,
					2.7520609614160847
				],
				[
					29.605936518748273,
					5.039974033491062
				],
				[
					-24.793479978528396,
					2.2392897996773575
				],
				[
					-25.073764201255205,
					-1.0762112685375433
				],
				[
					0.595175681679317,
					-0.281354017166153
				]
			]
		},
		{
			"type": "line",
			"version": 2427,
			"versionNonce": 1030001134,
			"isDeleted": false,
			"id": "6A4IpXQvVdHXqqOjMhgGs",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0.1979160865728442,
			"x": 283.2749395775894,
			"y": -332.04527099937263,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 39.78584099020641,
			"height": 17.161787312837635,
			"seed": 2007025651,
			"groupIds": [
				"Dd05LGoUV2VYsCPFM3-11",
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065550,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.4257766602096669,
					-8.496858789272117
				],
				[
					-11.290551261524852,
					-8.509930879717139
				],
				[
					-17.062812913753326,
					-17.161787312837635
				],
				[
					11.632293054587992,
					-3.901085277096611
				],
				[
					22.723028076453083,
					-9.977739892545248
				],
				[
					1.139139310210116,
					-7.720003128538587
				]
			]
		},
		{
			"type": "line",
			"version": 74,
			"versionNonce": 643320818,
			"isDeleted": false,
			"id": "RUIxzHIs9a1XsqRPZz6Q4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 210.51522425604574,
			"y": -344.0532305927397,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 8.776898353487042,
			"height": 4.3884491767435065,
			"seed": 1354963187,
			"groupIds": [
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065551,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-8.776898353487042,
					4.3884491767435065
				]
			]
		},
		{
			"type": "line",
			"version": 79,
			"versionNonce": 1125655598,
			"isDeleted": false,
			"id": "HwKIOdkLt9QKk2Q2bZIBR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 212.70944884441744,
			"y": -334.3359502728077,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 8.776898353487042,
			"height": 4.3884491767435065,
			"seed": 523098333,
			"groupIds": [
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065551,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-8.776898353487042,
					4.3884491767435065
				]
			]
		},
		{
			"type": "line",
			"version": 20,
			"versionNonce": 890109362,
			"isDeleted": false,
			"id": "N3fK3eaHKosLzi4cBBkcY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 210.20176360056405,
			"y": -339.0378601050328,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 8.776898353487042,
			"height": 6.8961344205969795,
			"seed": 351194909,
			"groupIds": [
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065551,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-8.776898353487042,
					-6.8961344205969795
				]
			]
		},
		{
			"type": "line",
			"version": 22,
			"versionNonce": 1763667566,
			"isDeleted": false,
			"id": "XhgCQ1t5SuNaQwGHzBiMK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 213.33637015538088,
			"y": -327.7532765076923,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 8.776898353487042,
			"height": 6.8961344205969795,
			"seed": 1993913405,
			"groupIds": [
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065551,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-8.776898353487042,
					-6.8961344205969795
				]
			]
		},
		{
			"type": "line",
			"version": 74,
			"versionNonce": 1302820722,
			"isDeleted": false,
			"id": "a-DFYFD4hTZdrNcrAvh5E",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 190.88813838289713,
			"y": -342.8421050078607,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 7.915331905330589,
			"height": 14.626156781589088,
			"seed": 1084000509,
			"groupIds": [
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065551,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-2.9252313563178234,
					10.152273530750108
				],
				[
					4.990100549012766,
					14.626156781589088
				],
				[
					1.2045070290720332,
					0.8603621636228809
				]
			]
		},
		{
			"type": "line",
			"version": 228,
			"versionNonce": 1547923630,
			"isDeleted": false,
			"id": "_MF3ZosirOcg4_jxR0ZX4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 189.6836313538251,
			"y": -333.89433850618263,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 6.194607578084856,
			"height": 17.551388137906883,
			"seed": 1087243805,
			"groupIds": [
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065551,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.548651894521214,
					12.73336002161875
				],
				[
					1.3765794617966094,
					17.551388137906883
				],
				[
					4.129738385389857,
					14.10993948341536
				],
				[
					4.645955683563642,
					3.4414486544915235
				]
			]
		},
		{
			"type": "line",
			"version": 69,
			"versionNonce": 275495218,
			"isDeleted": false,
			"id": "C9PR8642UcuUqKbno2OTu",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 190.946534372668,
			"y": -316.88797186470674,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 0.237475476782123,
			"height": 8.192903948983428,
			"seed": 140581405,
			"groupIds": [
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065551,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.237475476782123,
					-8.192903948983428
				]
			]
		},
		{
			"type": "freedraw",
			"version": 294,
			"versionNonce": 1210919662,
			"isDeleted": false,
			"id": "uK0m1s3pEm55nUdZK0pFu",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0.7206738819818561,
			"x": 111.0783706239624,
			"y": -324.67912222184657,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"width": 6.8502072267461696,
			"height": 12.197488006620647,
			"seed": 391653533,
			"groupIds": [
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065551,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 1,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": 0,
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					-0.8203806484990803,
					0
				],
				[
					4.213579577630616,
					5.90506647885767
				],
				[
					-2.6366276491155527,
					10.759220228846228
				],
				[
					3.23497854523831,
					12.197488006620647
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 585,
			"versionNonce": 2093073138,
			"isDeleted": false,
			"id": "6QEs1gbYVPiddQeZnsCxT",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0.6456850864060701,
			"x": 112.76331707722262,
			"y": -331.8015597156296,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"width": 5.979172090142425,
			"height": 12.789633511526086,
			"seed": 434543763,
			"groupIds": [
				"RRfsJzp93FW0u22AxeSSY"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065551,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 1,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": 0,
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					0.1802896135732006,
					0
				],
				[
					-4.213579577630616,
					6.191736862933916
				],
				[
					1.7655925125118084,
					11.281542848990707
				],
				[
					-3.3594121361817018,
					12.789633511526086
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 54,
			"versionNonce": 2070256942,
			"isDeleted": false,
			"id": "jwBsgGnp",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -164.14573563676552,
			"y": -300.49124148077897,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 397.40411376953125,
			"height": 45,
			"seed": 1471106067,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065551,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "Reinforcement Learning",
			"rawText": "Reinforcement Learning",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Reinforcement Learning",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 141,
			"versionNonce": 221287602,
			"isDeleted": false,
			"id": "dfS84YUy",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -129.61204411993265,
			"y": -255.49124066907817,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"width": 328.33673095703125,
			"height": 40,
			"seed": 21927037,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065551,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Warning Big subject and has many details\nthat I wont be able to explain in time",
			"rawText": "Warning Big subject and has many details\nthat I wont be able to explain in time",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Warning Big subject and has many details\nthat I wont be able to explain in time",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 313,
			"versionNonce": 190170990,
			"isDeleted": false,
			"id": "Qz4DudE5Li9Kr-FT01jCQ",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -108.16759698433144,
			"y": 41.275944531723525,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"width": 271.29380721160095,
			"height": 192.65792106331082,
			"seed": 890426259,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065551,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "61944105ed05ee31c7aa023482b57be59f7c120f",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 59,
			"versionNonce": 1398746738,
			"isDeleted": false,
			"id": "vBYX9S2P",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -177.61457759767455,
			"y": -75.67819077971211,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 424.341796875,
			"height": 35,
			"seed": 2100496307,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065551,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "What is reinforcement learning?",
			"rawText": "What is reinforcement learning?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What is reinforcement learning?",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 328,
			"versionNonce": 2017896878,
			"isDeleted": false,
			"id": "0yfF2saI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -439.21321072509863,
			"y": -40.6781914380774,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 947.5390625,
			"height": 75,
			"seed": 1489508202,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065551,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Reinforcement learning is an algorithmic concept that places you (the agent) in an\nenvironment that reacts to your actions, the goal is to explore the environment\nsuch that you find the best course of action at any given situation to maximize your rewards.",
			"rawText": "Reinforcement learning is an algorithmic concept that places you (the agent) in an\nenvironment that reacts to your actions, the goal is to explore the environment\nsuch that you find the best course of action at any given situation to maximize your rewards.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Reinforcement learning is an algorithmic concept that places you (the agent) in an\nenvironment that reacts to your actions, the goal is to explore the environment\nsuch that you find the best course of action at any given situation to maximize your rewards.",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 114,
			"versionNonce": 336891954,
			"isDeleted": false,
			"id": "PYErfphE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -208.06339956523462,
			"y": 240.88800167658783,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 485.23944091796875,
			"height": 50,
			"seed": 1985540598,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065551,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "There will be a lot of notation to keep track of\nBrace yourself:",
			"rawText": "There will be a lot of notation to keep track of\nBrace yourself:",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "There will be a lot of notation to keep track of\nBrace yourself:",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 1010,
			"versionNonce": 1365328878,
			"isDeleted": false,
			"id": "pXr8kINO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -314.90729982753953,
			"y": 322.84213826152194,
			"strokeColor": "#1971c2",
			"backgroundColor": "#ffc9c9",
			"width": 667.9612426757812,
			"height": 575,
			"seed": 1151673718,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065551,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "s ∈ S - such that S is all possible states s of our system\n\na ∈ A(s) - A is all possible actions A which may or may not\n            depend on the value of s\n\nT (s′|s, a) - a state sampling distribution conditioned\n             on the previous action and state.\n\nπ(a|s) - an action sampling distribution conditioned on\n         the previous state given by the environment.\n\nR(s, a) - a reward sampling distribution, given the current\n          state and action, what is the appropriate reward.\n\nV (s) -  Value function, evaluating the future potential of our\n         system given the current state we are at.\n\nQ(s, a) - Value-action function, evaluating the future potential\n          of our system given the action we are about to take\n          in our state.\n\nγ ∈ (0, 1] -  Disount factor, how much weight are we willing to put\n              on long term future rewards.",
			"rawText": "s ∈ S - such that S is all possible states s of our system\n\na ∈ A(s) - A is all possible actions A which may or may not\n            depend on the value of s\n\nT (s′|s, a) - a state sampling distribution conditioned\n             on the previous action and state.\n\nπ(a|s) - an action sampling distribution conditioned on\n         the previous state given by the environment.\n\nR(s, a) - a reward sampling distribution, given the current\n          state and action, what is the appropriate reward.\n\nV (s) -  Value function, evaluating the future potential of our\n         system given the current state we are at.\n\nQ(s, a) - Value-action function, evaluating the future potential\n          of our system given the action we are about to take\n          in our state.\n\nγ ∈ (0, 1] -  Disount factor, how much weight are we willing to put\n              on long term future rewards.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "s ∈ S - such that S is all possible states s of our system\n\na ∈ A(s) - A is all possible actions A which may or may not\n            depend on the value of s\n\nT (s′|s, a) - a state sampling distribution conditioned\n             on the previous action and state.\n\nπ(a|s) - an action sampling distribution conditioned on\n         the previous state given by the environment.\n\nR(s, a) - a reward sampling distribution, given the current\n          state and action, what is the appropriate reward.\n\nV (s) -  Value function, evaluating the future potential of our\n         system given the current state we are at.\n\nQ(s, a) - Value-action function, evaluating the future potential\n          of our system given the action we are about to take\n          in our state.\n\nγ ∈ (0, 1] -  Disount factor, how much weight are we willing to put\n              on long term future rewards.",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 140,
			"versionNonce": 1664596466,
			"isDeleted": false,
			"id": "GbTT3UbB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 642.2632090788804,
			"y": 57.37267804110621,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 100.01641845703125,
			"height": 35,
			"seed": 1002019830,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065551,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Metrics",
			"rawText": "Metrics",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Metrics",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 382,
			"versionNonce": 1487836718,
			"isDeleted": false,
			"id": "6I7aJ2LY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 384.79171237094204,
			"y": 92.3726784313748,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 614.9594116210938,
			"height": 175,
			"seed": 2127903274,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "T_Kbv_GiUneX4moQezaoN",
					"type": "arrow"
				}
			],
			"updated": 1717846065551,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Supervised and unsupervised methods have their\nown metrics to compare how well your model is doing at each\nstep.\n\nReinforcement learning does not, it instead has a holistic view\non the total performance, youre given an evaluation on how\nwell you did without breaking it down into steps.",
			"rawText": "Supervised and unsupervised methods have their\nown metrics to compare how well your model is doing at each\nstep.\n\nReinforcement learning does not, it instead has a holistic view\non the total performance, youre given an evaluation on how\nwell you did without breaking it down into steps.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Supervised and unsupervised methods have their\nown metrics to compare how well your model is doing at each\nstep.\n\nReinforcement learning does not, it instead has a holistic view\non the total performance, youre given an evaluation on how\nwell you did without breaking it down into steps.",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 145,
			"versionNonce": 1070574514,
			"isDeleted": false,
			"id": "71yBwebG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -770.653527779408,
			"y": 57.3726780582511,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 372.84954833984375,
			"height": 35,
			"seed": 959629034,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065551,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Exploitation vs Exploration",
			"rawText": "Exploitation vs Exploration",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Exploitation vs Exploration",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 445,
			"versionNonce": 655859822,
			"isDeleted": false,
			"id": "hPDs5cjG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -852.7784365484313,
			"y": 92.37267752561631,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 537.099365234375,
			"height": 225,
			"seed": 1566119850,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065551,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "How much do we care about exploring new routes that\nopen up new possibilities even if they're risky?\n\nare we willing to make sacrifices in the short term\nby exploring and losing in order to potentially\ngain in the long term?\n\nor do we just prefer exploiting the best route we\ncurrently have for the solutions we consider?",
			"rawText": "How much do we care about exploring new routes that\nopen up new possibilities even if they're risky?\n\nare we willing to make sacrifices in the short term\nby exploring and losing in order to potentially\ngain in the long term?\n\nor do we just prefer exploiting the best route we\ncurrently have for the solutions we consider?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How much do we care about exploring new routes that\nopen up new possibilities even if they're risky?\n\nare we willing to make sacrifices in the short term\nby exploring and losing in order to potentially\ngain in the long term?\n\nor do we just prefer exploiting the best route we\ncurrently have for the solutions we consider?",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 68,
			"versionNonce": 805528946,
			"isDeleted": false,
			"id": "y3XZeYUvCaaFlM1DQagYN",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -250.17639049187892,
			"y": 524.4909815037101,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 125.31780770348456,
			"height": 29.442135544794553,
			"seed": 798780842,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065551,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "CaIc0kPM",
				"focus": 0.28681759011103286,
				"gap": 1.4908659787802208
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					-53.599785222574724,
					-21.89287002048826
				],
				[
					-125.31780770348456,
					7.549265524306293
				]
			]
		},
		{
			"type": "text",
			"version": 111,
			"versionNonce": 1348821678,
			"isDeleted": false,
			"id": "CaIc0kPM",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -460.06495919367495,
			"y": 496.55869906377677,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 83.07989501953125,
			"height": 75,
			"seed": 1735310134,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "y3XZeYUvCaaFlM1DQagYN",
					"type": "arrow"
				}
			],
			"updated": 1717846065551,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "our final\noutput\n(optimal)",
			"rawText": "our final\noutput\n(optimal)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "our final\noutput\n(optimal)",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 112,
			"versionNonce": 1561978674,
			"isDeleted": false,
			"id": "IEoee9br",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 659.9371514993366,
			"y": 365.1768614343681,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 217.2248992919922,
			"height": 70,
			"seed": 811012522,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065551,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Markov Decision\nProcess",
			"rawText": "Markov Decision\nProcess",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Markov Decision\nProcess",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 363,
			"versionNonce": 121691374,
			"isDeleted": false,
			"id": "9o8izerV",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 474.1299232624776,
			"y": 443.670100332277,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 588.83935546875,
			"height": 175,
			"seed": 847975274,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065552,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "A markov decision process is a decision process that bases\nits distribution off of the entire history of the markov\nchain.\nThis can be seen as a generalization of our situation\nif our situation st encompasses and encodes our entire\nhistory and is arrived at by our history then we can\ndefine the history as",
			"rawText": "A markov decision process is a decision process that bases\nits distribution off of the entire history of the markov\nchain.\nThis can be seen as a generalization of our situation\nif our situation st encompasses and encodes our entire\nhistory and is arrived at by our history then we can\ndefine the history as",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "A markov decision process is a decision process that bases\nits distribution off of the entire history of the markov\nchain.\nThis can be seen as a generalization of our situation\nif our situation st encompasses and encodes our entire\nhistory and is arrived at by our history then we can\ndefine the history as",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 103,
			"versionNonce": 796537074,
			"isDeleted": false,
			"id": "x03qdCi4HpeWSLTyG7eer",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 678.6774763384483,
			"y": 627.1633394663585,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 179.74424849248064,
			"height": 27.61695484650093,
			"seed": 171881462,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065552,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "482fe82368ccfcf3b607595015caf6e3a4843b8d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 63,
			"versionNonce": 1093865262,
			"isDeleted": false,
			"id": "MpZTcv5V",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 609.469782714623,
			"y": 659.214161568119,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 318.1596374511719,
			"height": 25,
			"seed": 1453692586,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065552,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "And the decision process defines",
			"rawText": "And the decision process defines",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "And the decision process defines",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 97,
			"versionNonce": 1789608626,
			"isDeleted": false,
			"id": "LBxJHsrsL1ECRr1wGXhTa",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 706.6986479910892,
			"y": 688.6480298395868,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 123.70190688647274,
			"height": 32.01058116799075,
			"seed": 2078732394,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065552,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "55fd8c3e65b97a8e0ef64f7d375ac6b7b806b474",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 207,
			"versionNonce": 1520761198,
			"isDeleted": false,
			"id": "T_Kbv_GiUneX4moQezaoN",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1012.7604879096748,
			"y": 217.2592153667589,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 395.86650603097587,
			"height": 34.514102601361856,
			"seed": 1365505014,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065552,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "6I7aJ2LY",
				"focus": 0.4588195632859545,
				"gap": 13.009363917639007
			},
			"endBinding": {
				"elementId": "q6hh5ZP2",
				"focus": 0.06589930768052465,
				"gap": 12.209222396909581
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					210.2438362916423,
					-3.2345205583329744
				],
				[
					395.86650603097587,
					31.27958204302888
				]
			]
		},
		{
			"type": "text",
			"version": 98,
			"versionNonce": 1230249074,
			"isDeleted": false,
			"id": "q6hh5ZP2",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1420.8362163375602,
			"y": 237.23290602198796,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 192.92080688476562,
			"height": 70,
			"seed": 1114455210,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "T_Kbv_GiUneX4moQezaoN",
					"type": "arrow"
				},
				{
					"id": "Q4BVrrO2fQkeh6G-oXm9i",
					"type": "arrow"
				}
			],
			"updated": 1717846065552,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Value function\nEstimation",
			"rawText": "Value function\nEstimation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Value function\nEstimation",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 146,
			"versionNonce": 987732910,
			"isDeleted": false,
			"id": "mMjtRejl-2mlhT8OcrER_",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1241.065191399723,
			"y": 307.2329062272337,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 552.4628569811683,
			"height": 105.72739311499448,
			"seed": 1684162486,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "z3ybuCuEfJ26RUF1nSsbX",
					"type": "arrow"
				},
				{
					"id": "SilB6sTe8ZSE9AlSr01TF",
					"type": "arrow"
				},
				{
					"id": "Ub3N-yMkOlQoGvXKmsqfp",
					"type": "arrow"
				}
			],
			"updated": 1717846065552,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "8c50c4a89a0323294275c35274e5c7b05fc59b2a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 70,
			"versionNonce": 423345714,
			"isDeleted": false,
			"id": "Q4BVrrO2fQkeh6G-oXm9i",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1596.2998895117767,
			"y": 324.3212511240706,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 114.62881393409316,
			"height": 62.69494313129991,
			"seed": 997498410,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065552,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "q6hh5ZP2",
				"focus": 1.0629026220000084,
				"gap": 17.088345102082656
			},
			"endBinding": {
				"elementId": "uNckFRCO",
				"focus": 0.525691699815871,
				"gap": 1.1032956834746983
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					59.887706871689716,
					-37.89768950474098
				],
				[
					114.62881393409316,
					-62.69494313129991
				]
			]
		},
		{
			"type": "text",
			"version": 51,
			"versionNonce": 2014049774,
			"isDeleted": false,
			"id": "uNckFRCO",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1712.0319991293445,
			"y": 246.66841791588712,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 90.43220520019531,
			"height": 20,
			"seed": 2076500662,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Q4BVrrO2fQkeh6G-oXm9i",
					"type": "arrow"
				}
			],
			"updated": 1717846065552,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "base state",
			"rawText": "base state",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "base state",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 95,
			"versionNonce": 1464412146,
			"isDeleted": false,
			"id": "-3lKqlKqYgyKsP8SKZeIx",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1644.4907786350896,
			"y": 363.62255875861683,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 106.52252960570672,
			"height": 77.66686984922228,
			"seed": 736583350,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065552,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "XHtpfjFz",
				"focus": 0.10232294653686035,
				"gap": 7.018090649026135
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					86.08857862805348,
					39.7691803444813
				],
				[
					106.52252960570672,
					77.66686984922228
				]
			]
		},
		{
			"type": "text",
			"version": 94,
			"versionNonce": 2066941998,
			"isDeleted": false,
			"id": "XHtpfjFz",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1711.795366280094,
			"y": 448.30751925686525,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 95.58419799804688,
			"height": 40,
			"seed": 1800042358,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "-3lKqlKqYgyKsP8SKZeIx",
					"type": "arrow"
				}
			],
			"updated": 1717846065552,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "our current\naction policy",
			"rawText": "our current\naction policy",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "our current\naction policy",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 51,
			"versionNonce": 1266899378,
			"isDeleted": false,
			"id": "z3ybuCuEfJ26RUF1nSsbX",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1593.024780542231,
			"y": 414.15281143160485,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 31.34747156565004,
			"height": 63.16281584123499,
			"seed": 2071585974,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065552,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "mMjtRejl-2mlhT8OcrER_",
				"focus": -0.25152438243879544,
				"gap": 1.1925120893766916
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					4.210854389415772,
					45.38365286370214
				],
				[
					-27.136617176234267,
					63.16281584123499
				]
			]
		},
		{
			"type": "text",
			"version": 131,
			"versionNonce": 608031342,
			"isDeleted": false,
			"id": "YMUB8xMX",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1391.741864622085,
			"y": 461.4079551350472,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 216.3524932861328,
			"height": 60,
			"seed": 1542101738,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065552,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "sampling a new\nstate every iteration\nfrom the state distribution",
			"rawText": "sampling a new\nstate every iteration\nfrom the state distribution",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "sampling a new\nstate every iteration\nfrom the state distribution",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 68,
			"versionNonce": 621892466,
			"isDeleted": false,
			"id": "SilB6sTe8ZSE9AlSr01TF",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1394.3631133255967,
			"y": 378.6736284683924,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 87.34060543157898,
			"height": 59.46594412362833,
			"seed": 1452904490,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065552,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "mMjtRejl-2mlhT8OcrER_",
				"focus": 0.5992356177713963,
				"gap": 25.179273249792573
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					-15.79564140783873,
					50.638968042777265
				],
				[
					-87.34060543157898,
					59.46594412362833
				]
			]
		},
		{
			"type": "text",
			"version": 100,
			"versionNonce": 1844794542,
			"isDeleted": false,
			"id": "CNs7doEA",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1193.8210376990894,
			"y": 405.7248860401625,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 108.40020751953125,
			"height": 80,
			"seed": 316254954,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065552,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "weight on\nfuture values\nexponentially\ndecreasing",
			"rawText": "weight on\nfuture values\nexponentially\ndecreasing",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "weight on\nfuture values\nexponentially\ndecreasing",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 73,
			"versionNonce": 372905266,
			"isDeleted": false,
			"id": "z2WQZllF4MRzk5Eg6Mj9g",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1424.5606630758768,
			"y": 387.0360268607776,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 86.4114500546475,
			"height": 113.3569559856665,
			"seed": 1183220022,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065552,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "HBEfZqP7",
				"focus": 0.7871398417366715,
				"gap": 13.310233440887032
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					-25.551772865621615,
					84.08856161231824
				],
				[
					-86.4114500546475,
					113.3569559856665
				]
			]
		},
		{
			"type": "text",
			"version": 45,
			"versionNonce": 302157550,
			"isDeleted": false,
			"id": "HBEfZqP7",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1264.1188410305376,
			"y": 492.0305844540589,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 60.72013854980469,
			"height": 20,
			"seed": 137747818,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "z2WQZllF4MRzk5Eg6Mj9g",
					"type": "arrow"
				}
			],
			"updated": 1717846065552,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "rewards",
			"rawText": "rewards",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "rewards",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 52,
			"versionNonce": 1885642482,
			"isDeleted": false,
			"id": "Ub3N-yMkOlQoGvXKmsqfp",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1370.8619726480094,
			"y": 331.83057037112985,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 66.69353048158496,
			"height": 38.745765327396896,
			"seed": 1382231594,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065552,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "mMjtRejl-2mlhT8OcrER_",
				"focus": -1.1276778687076536,
				"gap": 11.607395260392764
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					-15.2442355386479,
					-38.745765327396896
				],
				[
					-66.69353048158496,
					-36.20505940428893
				]
			]
		},
		{
			"type": "text",
			"version": 40,
			"versionNonce": 753828142,
			"isDeleted": false,
			"id": "baNqHacx",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1243.9216858579668,
			"y": 281.01645190896994,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 50.62409973144531,
			"height": 20,
			"seed": 575642998,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065552,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "future",
			"rawText": "future",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "future",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 49,
			"versionNonce": 1075310770,
			"isDeleted": false,
			"id": "WTG3QUFY",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1442.2190493411117,
			"y": 553.4683729814049,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 157.29635620117188,
			"height": 20,
			"seed": 923589238,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065552,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Which translates to",
			"rawText": "Which translates to",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Which translates to",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 152,
			"versionNonce": 1646406510,
			"isDeleted": false,
			"id": "wzZjq9kTWchfsY6nBS8mB",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1273.1065314681464,
			"y": 584.2355320723761,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 488.3801769919946,
			"height": 87.09111523862731,
			"seed": 2038972790,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065552,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "acaef36586e3dc827b46bca4e11180fb705cad20",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 310,
			"versionNonce": 1761282674,
			"isDeleted": false,
			"id": "B69lToYh",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1244.8669626961523,
			"y": 671.3266474269956,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 544.8593139648438,
			"height": 125,
			"seed": 76322410,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065552,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Problem: this provides us no information on which action\nto take as it does not evaluate individual actions\n(reminder that our goal is to find the optimal course\nof action)\nsolution: Replace with an action dependent alternative",
			"rawText": "Problem: this provides us no information on which action\nto take as it does not evaluate individual actions\n(reminder that our goal is to find the optimal course\nof action)\nsolution: Replace with an action dependent alternative",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Problem: this provides us no information on which action\nto take as it does not evaluate individual actions\n(reminder that our goal is to find the optimal course\nof action)\nsolution: Replace with an action dependent alternative",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 294,
			"versionNonce": 2145815982,
			"isDeleted": false,
			"id": "RWCU02zKBQJ3xpsH42Nhp",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1232.0851116143187,
			"y": 850.8228051214985,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 611.8181407795645,
			"height": 89.47017972690404,
			"seed": 1678741942,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "9uFUlbxPXSkLM-lmQPjqq",
					"type": "arrow"
				}
			],
			"updated": 1717846065552,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d73a49f1b7cca9453455b31b725fe42bc105b59f",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 14,
			"versionNonce": 1104473138,
			"isDeleted": false,
			"id": "A7zeQJtY",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1324.1982837523917,
			"y": 815.822805446573,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 384.5256042480469,
			"height": 35,
			"seed": 1280194102,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065552,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "State-action value function",
			"rawText": "State-action value function",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "State-action value function",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 73,
			"versionNonce": 593799150,
			"isDeleted": false,
			"id": "6GrnWZB9",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1340.7548303772987,
			"y": 940.2929849107072,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 360.22479248046875,
			"height": 20,
			"seed": 1874900138,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065552,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "more expressive but requires more information",
			"rawText": "more expressive but requires more information",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "more expressive but requires more information",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 98,
			"versionNonce": 814519794,
			"isDeleted": false,
			"id": "9uFUlbxPXSkLM-lmQPjqq",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1217.6809601211016,
			"y": 881.3622237174068,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 81.74983265062792,
			"height": 82.64818245997549,
			"seed": 612296694,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065552,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "RWCU02zKBQJ3xpsH42Nhp",
				"focus": 0.37349990709622005,
				"gap": 14.404151493217
			},
			"endBinding": {
				"elementId": "cTaBKTir",
				"focus": -0.01843378096864118,
				"gap": 15.271946758908598
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					-73.66468436649984,
					0.8983498093475646
				],
				[
					-81.74983265062792,
					82.64818245997549
				]
			]
		},
		{
			"type": "text",
			"version": 66,
			"versionNonce": 1554348590,
			"isDeleted": false,
			"id": "cTaBKTir",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1001.330846708755,
			"y": 979.2823529362909,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 269.2005615234375,
			"height": 20,
			"seed": 1396525610,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "9uFUlbxPXSkLM-lmQPjqq",
					"type": "arrow"
				}
			],
			"updated": 1717846065552,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "According to the Bellman equation",
			"rawText": "According to the Bellman equation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "According to the Bellman equation",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 122,
			"versionNonce": 1177094066,
			"isDeleted": false,
			"id": "ZSvdVI605PnntiXER3_W7",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 927.5673620928702,
			"y": 1014.5542996216727,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 413.18746787226877,
			"height": 50.73243125307529,
			"seed": 1524521718,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065552,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7b9923caf5b124957f790a084759fbfd71645527",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 87,
			"versionNonce": 1385301102,
			"isDeleted": false,
			"id": "p2mbAd0RueO3XGcwfRZF3",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1190.951447138686,
			"y": 1053.6945369597797,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 27.202980484842783,
			"height": 48.65948258743856,
			"seed": 156470582,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065552,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "MFOSVbrD",
				"focus": 0.10606981661264854,
				"gap": 8.29503408970686
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					7.449418194894633,
					40.97180007191946
				],
				[
					27.202980484842783,
					48.65948258743856
				]
			]
		},
		{
			"type": "text",
			"version": 70,
			"versionNonce": 1523663218,
			"isDeleted": false,
			"id": "MFOSVbrD",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1224.0624082904428,
			"y": 1108.1766783032135,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 57.90411376953125,
			"height": 20,
			"seed": 147589802,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "p2mbAd0RueO3XGcwfRZF3",
					"type": "arrow"
				}
			],
			"updated": 1717846065552,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "unknown",
			"rawText": "unknown",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "unknown",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 468,
			"versionNonce": 1727219374,
			"isDeleted": false,
			"id": "V6m0NLCDiY-YrX1rkgsJ_",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1783.6460110811618,
			"y": 614.8404427190412,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 164.6316608046218,
			"height": 1.4808645462824188,
			"seed": 1397233834,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065552,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					164.6316608046218,
					1.4808645462824188
				]
			]
		},
		{
			"type": "text",
			"version": 86,
			"versionNonce": 701252402,
			"isDeleted": false,
			"id": "NZKdVs6X",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2023.2085255184834,
			"y": 550.5722430547015,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 265.6965637207031,
			"height": 20,
			"seed": 352892470,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065552,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "According to the bellman equation",
			"rawText": "According to the bellman equation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "According to the bellman equation",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 341,
			"versionNonce": 1517437166,
			"isDeleted": false,
			"id": "CDzSDRez5JXlG9JoF0I1t",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1965.4187088824574,
			"y": 578.6985827889125,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 368.9432594584019,
			"height": 69.42676113946281,
			"seed": 1209877686,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065552,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a80c20358e3086990451da006cbe01f4309cabaa",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 211,
			"versionNonce": 1837174002,
			"isDeleted": false,
			"id": "hO9wuCDu",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1973.83244214446,
			"y": 649.8054519489244,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 364.44873046875,
			"height": 80,
			"seed": 66295914,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065553,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This equation defines a recursive relationship\ninto future values\nWhich can be solved and evaluated iteratively\nusing dynamic programming backwards",
			"rawText": "This equation defines a recursive relationship\ninto future values\nWhich can be solved and evaluated iteratively\nusing dynamic programming backwards",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This equation defines a recursive relationship\ninto future values\nWhich can be solved and evaluated iteratively\nusing dynamic programming backwards",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 557,
			"versionNonce": 1889006382,
			"isDeleted": false,
			"id": "MBcKUCAk5MNiv88Y9lJhT",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2292.424185920677,
			"y": 596.7120986599524,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 173.48811789305182,
			"height": 36.044753178833616,
			"seed": 103741174,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065553,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "PTQpiWVk",
				"focus": 0.9313212437762837,
				"gap": 4.777135371770896
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					78.94479970597422,
					-36.044753178833616
				],
				[
					173.48811789305182,
					-27.583014955792123
				]
			]
		},
		{
			"type": "text",
			"version": 141,
			"versionNonce": 2071371442,
			"isDeleted": false,
			"id": "PTQpiWVk",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2420.6498790226365,
			"y": 573.9062190759312,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 125.98426818847656,
			"height": 60,
			"seed": 1045018730,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "MBcKUCAk5MNiv88Y9lJhT",
					"type": "arrow"
				}
			],
			"updated": 1717846065553,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "determined by T\nand pi dynamics\nimplicitly",
			"rawText": "determined by T\nand pi dynamics\nimplicitly",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "determined by T\nand pi dynamics\nimplicitly",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 99,
			"versionNonce": 332225902,
			"isDeleted": false,
			"id": "pclVi1sm2zYszb6Hoh5Bj",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2023.2085259919154,
			"y": 738.9472402097596,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 291.8688847950671,
			"height": 42.998541063558996,
			"seed": 541846902,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065553,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b9a89c207ed837d1aa96f6dc3f383b52efe05b8c",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 58,
			"versionNonce": 1616115826,
			"isDeleted": false,
			"id": "WMbOsln9Xq_OrMY1wTbXg",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2240.9060076670353,
			"y": 775.9353578232387,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 74.63026131848255,
			"height": 31.14068457893518,
			"seed": 22537590,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065553,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					34.89904306259996,
					31.14068457893518
				],
				[
					74.63026131848255,
					29.529959514507482
				]
			]
		},
		{
			"type": "text",
			"version": 70,
			"versionNonce": 2036039598,
			"isDeleted": false,
			"id": "Fd7BfXrC",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2313.2900090601515,
			"y": 788.8211583386601,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 158.04830932617188,
			"height": 40,
			"seed": 2117125802,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065553,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "last iterations\nvalue of the future",
			"rawText": "last iterations\nvalue of the future",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "last iterations\nvalue of the future",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 58,
			"versionNonce": 2078284338,
			"isDeleted": false,
			"id": "QZvEqCjsbEJ9wzZOlyHnA",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2040.6391913231935,
			"y": 777.5460828876664,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 23.087059256796692,
			"height": 49.93247699725816,
			"seed": 399642986,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065553,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "G7uZO9aq",
				"focus": -0.6358968349471041,
				"gap": 4.5309875855400605
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					-5.369083548092249,
					40.26812661069198
				],
				[
					17.717975708704444,
					49.93247699725816
				]
			]
		},
		{
			"type": "text",
			"version": 69,
			"versionNonce": 1164663278,
			"isDeleted": false,
			"id": "G7uZO9aq",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2062.888154617438,
			"y": 809.2236758214109,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 164.89633178710938,
			"height": 40,
			"seed": 221987638,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "QZvEqCjsbEJ9wzZOlyHnA",
					"type": "arrow"
				}
			],
			"updated": 1717846065553,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "next iterations\nvalue of the present",
			"rawText": "next iterations\nvalue of the present",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "next iterations\nvalue of the present",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 190,
			"versionNonce": 486671346,
			"isDeleted": false,
			"id": "CYnMkT3F2BQ8KHWo_o2kq",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1948.2776719223255,
			"y": 893.8105351263229,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 481.3046374297335,
			"height": 46.48244962007962,
			"seed": 909884854,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065553,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4f5800db531f031b3f27104c5b5011624c90779a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 39,
			"versionNonce": 788917294,
			"isDeleted": false,
			"id": "c6WyDmql",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2097.574967119837,
			"y": 869.2290051466573,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 171.96836853027344,
			"height": 20,
			"seed": 1487168566,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065553,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Which is equivalent to",
			"rawText": "Which is equivalent to",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Which is equivalent to",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 46,
			"versionNonce": 499168690,
			"isDeleted": false,
			"id": "P3At3uEam85iylza8TSdV",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2099.8925874422357,
			"y": 931.095126371921,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 15.319230017684276,
			"height": 49.49289698021107,
			"seed": 962011574,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065553,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "Q0kkjOO0",
				"focus": -0.2273728027288948,
				"gap": 4.713609236210459
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					2.9460057726319064,
					32.99526465347401
				],
				[
					-12.37322424505237,
					49.49289698021107
				]
			]
		},
		{
			"type": "text",
			"version": 73,
			"versionNonce": 605304430,
			"isDeleted": false,
			"id": "Q0kkjOO0",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2003.641184746476,
			"y": 985.3016325883425,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 150.080322265625,
			"height": 60,
			"seed": 479169194,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "P3At3uEam85iylza8TSdV",
					"type": "arrow"
				}
			],
			"updated": 1717846065553,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "all possible actions\nwe can take\nat this state",
			"rawText": "all possible actions\nwe can take\nat this state",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "all possible actions\nwe can take\nat this state",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 53,
			"versionNonce": 2135109490,
			"isDeleted": false,
			"id": "h3WzAaaVHkitcU679DRBP",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2223.035628738237,
			"y": 929.9167240628683,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 40.065678507789926,
			"height": 70.11493738863237,
			"seed": 1320534838,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065553,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "mpXoJjLk",
				"focus": 0.10944445591835698,
				"gap": 7.659615008842138
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					36.53047158063191,
					37.11967273515825
				],
				[
					40.065678507789926,
					70.11493738863237
				]
			]
		},
		{
			"type": "text",
			"version": 119,
			"versionNonce": 1834956974,
			"isDeleted": false,
			"id": "mpXoJjLk",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2188.1203494907145,
			"y": 1007.6912764603428,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 145.24830627441406,
			"height": 100,
			"seed": 547624042,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "h3WzAaaVHkitcU679DRBP",
					"type": "arrow"
				}
			],
			"updated": 1717846065553,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "all possible\nstates that\ncane be generated\nfrom the action\nwe take",
			"rawText": "all possible\nstates that\ncane be generated\nfrom the action\nwe take",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "all possible\nstates that\ncane be generated\nfrom the action\nwe take",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 55,
			"versionNonce": 97546546,
			"isDeleted": false,
			"id": "9T8hIqGGr_fcvKIcl8S6v",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2316.1294111533966,
			"y": 934.630333299079,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 60.098517761684434,
			"height": 78.36375355200073,
			"seed": 2073077930,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065553,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "QaWFrlyl",
				"focus": 0.0256443895039025,
				"gap": 7.659615008842252
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					32.40606349894779,
					37.11967273515825
				],
				[
					60.098517761684434,
					78.36375355200073
				]
			]
		},
		{
			"type": "text",
			"version": 40,
			"versionNonce": 1385165550,
			"isDeleted": false,
			"id": "QaWFrlyl",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2348.850658697614,
			"y": 1020.653701859922,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 88.92820739746094,
			"height": 40,
			"seed": 21908010,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "9T8hIqGGr_fcvKIcl8S6v",
					"type": "arrow"
				}
			],
			"updated": 1717846065553,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "appropriate\nreward",
			"rawText": "appropriate\nreward",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "appropriate\nreward",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 58,
			"versionNonce": 1422883570,
			"isDeleted": false,
			"id": "Zl335ilXT0-t5zoMbH_Qu",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2402.3243004384067,
			"y": 937.0652209219907,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 78.77929939161731,
			"height": 52.519532927744876,
			"seed": 1452050410,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065553,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					39.17440570840017,
					39.17440570839983
				],
				[
					78.77929939161731,
					52.519532927744876
				]
			]
		},
		{
			"type": "text",
			"version": 41,
			"versionNonce": 1043293486,
			"isDeleted": false,
			"id": "42nJrpE8",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2487.546501284273,
			"y": 990.0152418245531,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 94.73619079589844,
			"height": 60,
			"seed": 1625271798,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065553,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "value of\nfuture given\nthat state",
			"rawText": "value of\nfuture given\nthat state",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "value of\nfuture given\nthat state",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 365,
			"versionNonce": 1023918190,
			"isDeleted": false,
			"id": "yaEkR6FB",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -90.08856759070227,
			"y": 1058.9800800351566,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 216.93606567382812,
			"height": 90,
			"seed": 358173174,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "Value-Based\n methods",
			"rawText": "Value-Based\n methods",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Value-Based\n methods",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 472,
			"versionNonce": 1934721710,
			"isDeleted": false,
			"id": "1Mt65U6Z",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -634.6434626290941,
			"y": 1158.9594074808033,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 278.6571960449219,
			"height": 35,
			"seed": 732665898,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Monte Carlo Method",
			"rawText": "Monte Carlo Method",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Monte Carlo Method",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 1199,
			"versionNonce": 933821678,
			"isDeleted": false,
			"id": "osgSO3b2",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -867.3444359589571,
			"y": 1203.2274108897484,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 744.0591430664062,
			"height": 375,
			"seed": 1536529642,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "LcKT8vFWd0fvYA0QXrpK7",
					"type": "arrow"
				}
			],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The term ”Monte Carlo” is generally used for estimation methods that\nuse random sampling in their process. it is a way to estimate\nintractable values by sampling a lot from it and updating the \"estimation\" \nof the value. (Simulation and law of large numbers)\n\nNote in RL we only use Monte Carlo for tasks that have an ending\n(Win/Lose situation, no infinite situation)\n\nan Episode is a full simulation from start to finish\nThe process goes as follows:\n 1. Run a full simulation.\n2. Improve your estimation of the future value of each\nstate you have visited in that simulation by averaging\nover the future value you just experienced and your prior\nexperiences.",
			"rawText": "The term ”Monte Carlo” is generally used for estimation methods that\nuse random sampling in their process. it is a way to estimate\nintractable values by sampling a lot from it and updating the \"estimation\" \nof the value. (Simulation and law of large numbers)\n\nNote in RL we only use Monte Carlo for tasks that have an ending\n(Win/Lose situation, no infinite situation)\n\nan Episode is a full simulation from start to finish\nThe process goes as follows:\n 1. Run a full simulation.\n2. Improve your estimation of the future value of each\nstate you have visited in that simulation by averaging\nover the future value you just experienced and your prior\nexperiences.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The term ”Monte Carlo” is generally used for estimation methods that\nuse random sampling in their process. it is a way to estimate\nintractable values by sampling a lot from it and updating the \"estimation\" \nof the value. (Simulation and law of large numbers)\n\nNote in RL we only use Monte Carlo for tasks that have an ending\n(Win/Lose situation, no infinite situation)\n\nan Episode is a full simulation from start to finish\nThe process goes as follows:\n 1. Run a full simulation.\n2. Improve your estimation of the future value of each\nstate you have visited in that simulation by averaging\nover the future value you just experienced and your prior\nexperiences.",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 401,
			"versionNonce": 1736776046,
			"isDeleted": false,
			"id": "FOSMsAMz2vq_4nHfrmRwb",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -601.1611747707356,
			"y": 1583.3782530127255,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 214,
			"height": 46,
			"seed": 759117174,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "h0tfCRpK6tmySItglWay-",
					"type": "arrow"
				}
			],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a15c56f20c44ba16d92f9dda763b3da14b27069e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 1481,
			"versionNonce": 250809906,
			"isDeleted": false,
			"id": "LcKT8vFWd0fvYA0QXrpK7",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -403.7746032248797,
			"y": 1594.6725166888837,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 129.09271200807677,
			"height": 44.00679869155351,
			"seed": 1563211242,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717848649310,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "osgSO3b2",
				"focus": 0.6783407352318034,
				"gap": 16.445105799135263
			},
			"endBinding": {
				"elementId": "0nedfzhU",
				"focus": 0.3871636037296784,
				"gap": 10.705574664763844
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					35.40836022233816,
					-16.899444651570548
				],
				[
					129.09271200807677,
					27.107354039982965
				]
			]
		},
		{
			"type": "text",
			"version": 880,
			"versionNonce": 1183262766,
			"isDeleted": false,
			"id": "0nedfzhU",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -316.3153954403954,
			"y": 1632.4854453936305,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 266.38507080078125,
			"height": 184.47286351454966,
			"seed": 940911478,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "LcKT8vFWd0fvYA0QXrpK7",
					"type": "arrow"
				}
			],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"fontSize": 14.757829081163974,
			"fontFamily": 1,
			"text": "G is the collection of G0 -> Gn\nepisode results that include the\nstate s.\nMeaning that the value of s is the\nexpected value of all values of S\nin our simulations\nnote that for a sequence of events\n(episode) σi to include the value s\nwe wouldve had to sample that\nvalue at least once",
			"rawText": "G is the collection of G0 -> Gn\nepisode results that include the\nstate s.\nMeaning that the value of s is the\nexpected value of all values of S\nin our simulations\nnote that for a sequence of events\n(episode) σi to include the value s\nwe wouldve had to sample that\nvalue at least once",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "G is the collection of G0 -> Gn\nepisode results that include the\nstate s.\nMeaning that the value of s is the\nexpected value of all values of S\nin our simulations\nnote that for a sequence of events\n(episode) σi to include the value s\nwe wouldve had to sample that\nvalue at least once",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 1422,
			"versionNonce": 396798386,
			"isDeleted": false,
			"id": "h0tfCRpK6tmySItglWay-",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -483.6542178382049,
			"y": 1641.9895218812317,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.09698243659840955,
			"height": 40.17006818884511,
			"seed": 2067362101,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717848649311,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "FOSMsAMz2vq_4nHfrmRwb",
				"focus": -0.09894802441154076,
				"gap": 12.611268868506158
			},
			"endBinding": {
				"elementId": "J_advw7kBa5gUd_FTJWHJ",
				"focus": -0.0286148866666656,
				"gap": 12.846225691518157
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					-0.09698243659840955,
					40.17006818884511
				]
			]
		},
		{
			"type": "image",
			"version": 476,
			"versionNonce": 1078636270,
			"isDeleted": false,
			"id": "J_advw7kBa5gUd_FTJWHJ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -621.3586772042917,
			"y": 1695.005815761595,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 283,
			"height": 107,
			"seed": 1810895957,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "h0tfCRpK6tmySItglWay-",
					"type": "arrow"
				}
			],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "04f6d7b90dc747a9d7c5ca93872df27ee2935f13",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 558,
			"versionNonce": 1960987502,
			"isDeleted": false,
			"id": "mSwX2rSaiREdxaTRyH6Hz",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -690.2233945503633,
			"y": 1896.6619030695438,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 416,
			"height": 97,
			"seed": 400417947,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "fe4146ff8ac41e226e1d18f422aec5cd6b7038ac",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 442,
			"versionNonce": 94547374,
			"isDeleted": false,
			"id": "YWu3wYAs",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -641.6132257143818,
			"y": 1851.7479801066984,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 318.7796630859375,
			"height": 25,
			"seed": 814217045,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "How to update the value of V ?",
			"rawText": "How to update the value of V ?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How to update the value of V ?",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 519,
			"versionNonce": 1553778670,
			"isDeleted": false,
			"id": "WSihQLBq",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -715.5884138788786,
			"y": 1993.6619029226058,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 471.45947265625,
			"height": 50,
			"seed": 1110107643,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Which we can then update just after simulating\nevery episode",
			"rawText": "Which we can then update just after simulating\nevery episode",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Which we can then update just after simulating\nevery episode",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 420,
			"versionNonce": 2044303918,
			"isDeleted": false,
			"id": "1wrGMldn2hSqIc2EH2556",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -681.2512003668544,
			"y": 2057.7116136235763,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 395,
			"height": 73,
			"seed": 134558619,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "db2cbe8bfd16a94b5d267fc85cbe317a25c8e49b",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 439,
			"versionNonce": 1950491758,
			"isDeleted": false,
			"id": "9O0feIMt",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 385.40809127293164,
			"y": 1147.4715711048702,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 385.3936767578125,
			"height": 35,
			"seed": 1649548507,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Temporal Difference method",
			"rawText": "Temporal Difference method",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Temporal Difference method",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 855,
			"versionNonce": 496985774,
			"isDeleted": false,
			"id": "beCYiCfg",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 155.77717545840233,
			"y": 1209.9619690201955,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 802.8191528320312,
			"height": 250,
			"seed": 1818066101,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Uses dynamic programming to recursively update state value based on experience\n(Like monte carlo)\nBut unlike monte Carlo, TD assumes that not all previous steps contribute to\nthe current reward gotten, instead theres a finite window of previous temporal\nsteps that lead up to the current reward (In the simplest case we assume\nthat only the LAST action led up to our reward but this can be expanded\nto a window instead)\nKey concept:\nUpdate state value function by using reward Rt+1 of next step\n(experience) and current estimate of next state’s value V (St+1)",
			"rawText": "Uses dynamic programming to recursively update state value based on experience\n(Like monte carlo)\nBut unlike monte Carlo, TD assumes that not all previous steps contribute to\nthe current reward gotten, instead theres a finite window of previous temporal\nsteps that lead up to the current reward (In the simplest case we assume\nthat only the LAST action led up to our reward but this can be expanded\nto a window instead)\nKey concept:\nUpdate state value function by using reward Rt+1 of next step\n(experience) and current estimate of next state’s value V (St+1)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Uses dynamic programming to recursively update state value based on experience\n(Like monte carlo)\nBut unlike monte Carlo, TD assumes that not all previous steps contribute to\nthe current reward gotten, instead theres a finite window of previous temporal\nsteps that lead up to the current reward (In the simplest case we assume\nthat only the LAST action led up to our reward but this can be expanded\nto a window instead)\nKey concept:\nUpdate state value function by using reward Rt+1 of next step\n(experience) and current estimate of next state’s value V (St+1)",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 588,
			"versionNonce": 647651566,
			"isDeleted": false,
			"id": "g3SmVJxUdf63dGmffB7tK",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 300.24255638459954,
			"y": 1472.28748066466,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 506.65587621769964,
			"height": 40.979519399961,
			"seed": 1533275566,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "46dde5cc9a43202a96503b3907db527908d851e8",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 832,
			"versionNonce": 1203033902,
			"isDeleted": false,
			"id": "IEoseJYTbH8V4id1e8U3N",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -845.4844736336875,
			"y": 506.63914972811335,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 54.56323874283429,
			"height": 69.98328447450461,
			"seed": 121908018,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065553,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "CqRQyjQP",
				"focus": 0.14668257972681573,
				"gap": 15.245146626901658
			},
			"endBinding": {
				"elementId": "TXWcnmyq",
				"focus": 0.855145702832356,
				"gap": 5.994559303866708
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					11.268494957759339,
					-49.225530604948176
				],
				[
					54.56323874283429,
					-69.98328447450461
				]
			]
		},
		{
			"type": "text",
			"version": 392,
			"versionNonce": 1544157874,
			"isDeleted": false,
			"id": "TXWcnmyq",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -784.9266755869864,
			"y": 421.8288982039253,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 265.5096435546875,
			"height": 37.704013038478074,
			"seed": 1536893294,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "IEoseJYTbH8V4id1e8U3N",
					"type": "arrow"
				}
			],
			"updated": 1717846065553,
			"link": null,
			"locked": false,
			"fontSize": 15.08160521539123,
			"fontFamily": 1,
			"text": "treats the model as a blackbox\nand learns from the data collected",
			"rawText": "treats the model as a blackbox\nand learns from the data collected",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "treats the model as a blackbox\nand learns from the data collected",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 903,
			"versionNonce": 1034797422,
			"isDeleted": false,
			"id": "NLdLJk9CYtJevvpwyVnoq",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1613.7098387807164,
			"y": 506.18490878341254,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 64.10546948067125,
			"height": 45.111256301213096,
			"seed": 327303794,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065553,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "UtvNId8TvplDVMjph0q3W",
				"focus": -0.07339643139689053,
				"gap": 12.437592210427738
			},
			"endBinding": {
				"elementId": "6MjdUoXA",
				"focus": -0.03765293087221924,
				"gap": 9.346739990707647
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					-28.491319769187143,
					-45.111256301213096
				],
				[
					-64.10546948067125,
					-40.661716874672834
				]
			]
		},
		{
			"type": "text",
			"version": 377,
			"versionNonce": 236704882,
			"isDeleted": false,
			"id": "6MjdUoXA",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1920.1418928985004,
			"y": 433.37375826215623,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 232.9474334716797,
			"height": 100.627185330364,
			"seed": 1573344178,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "NLdLJk9CYtJevvpwyVnoq",
					"type": "arrow"
				}
			],
			"updated": 1717846065553,
			"link": null,
			"locked": false,
			"fontSize": 20.1254370660728,
			"fontFamily": 1,
			"text": "somehow learns a model\nof the environment ??\nprovided some extra\nknown information",
			"rawText": "somehow learns a model\nof the environment ??\nprovided some extra\nknown information",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "somehow learns a model\nof the environment ??\nprovided some extra\nknown information",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 1036,
			"versionNonce": 1119621934,
			"isDeleted": false,
			"id": "OG31LUJI",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 97.09248604991069,
			"y": 1525.5925120638935,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 940.1589965820312,
			"height": 325,
			"seed": 396286318,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "ZHuNFI60aFtX-12xIYf76",
					"type": "arrow"
				}
			],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "I.e The algorithm does N episodes iteratively and unlike monte carlo it\nupdates its value estimation after every step not after every episode.\n\n1) we take a step according to our best value estimate (random at the start)\n\n2. We observe the reward we just got from taking that action\n\n3. we calculate the temporal difference which is Our estimate - what we experienced\nwhich is the immediate reward + next state's discounted reward \nsomething which we derives from the bellman equation\n\n\n4. we update our estimate with the temporal difference * learning rate and go back to step 1",
			"rawText": "I.e The algorithm does N episodes iteratively and unlike monte carlo it\nupdates its value estimation after every step not after every episode.\n\n1) we take a step according to our best value estimate (random at the start)\n\n2. We observe the reward we just got from taking that action\n\n3. we calculate the temporal difference which is Our estimate - what we experienced\nwhich is the immediate reward + next state's discounted reward \nsomething which we derives from the bellman equation\n\n\n4. we update our estimate with the temporal difference * learning rate and go back to step 1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "I.e The algorithm does N episodes iteratively and unlike monte carlo it\nupdates its value estimation after every step not after every episode.\n\n1) we take a step according to our best value estimate (random at the start)\n\n2. We observe the reward we just got from taking that action\n\n3. we calculate the temporal difference which is Our estimate - what we experienced\nwhich is the immediate reward + next state's discounted reward \nsomething which we derives from the bellman equation\n\n\n4. we update our estimate with the temporal difference * learning rate and go back to step 1",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 387,
			"versionNonce": 465965490,
			"isDeleted": false,
			"id": "cXPJ5xwH",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1971.0564772440666,
			"y": 611.8520844078662,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 288.3148193359375,
			"height": 53.372347812684865,
			"seed": 937199150,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065553,
			"link": null,
			"locked": false,
			"fontSize": 14.232626083382629,
			"fontFamily": 1,
			"text": "we will not focus on MBRL\nwe assume that we do not have a model\ngiven ",
			"rawText": "we will not focus on MBRL\nwe assume that we do not have a model\ngiven ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "we will not focus on MBRL\nwe assume that we do not have a model\ngiven ",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 495,
			"versionNonce": 1761058734,
			"isDeleted": false,
			"id": "6icj0Q5I",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -631.8964210728891,
			"y": 2450.7945087828266,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 345.99957275390625,
			"height": 75,
			"seed": 1477832754,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Monte Carlo is the\nSimplest approach for Free learning\nbut is not recommended",
			"rawText": "Monte Carlo is the\nSimplest approach for Free learning\nbut is not recommended",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Monte Carlo is the\nSimplest approach for Free learning\nbut is not recommended",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 248,
			"versionNonce": 746813934,
			"isDeleted": false,
			"id": "xJ0qY0K0-Dz5ZZPAJ4HdI",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -677.4952410666572,
			"y": 2114.9454073476454,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 63.98744516046645,
			"height": 18.60100150013568,
			"seed": 347256754,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					-63.98744516046645,
					18.60100150013568
				]
			]
		},
		{
			"type": "text",
			"version": 281,
			"versionNonce": 1041894446,
			"isDeleted": false,
			"id": "g0A8BGGT",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -982.6768126841077,
			"y": 2120.897727827689,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 248.75967407226562,
			"height": 50,
			"seed": 1021475250,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "How much knowledge do \ni have after this episode",
			"rawText": "How much knowledge do \ni have after this episode",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How much knowledge do \ni have after this episode",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 242,
			"versionNonce": 2074367598,
			"isDeleted": false,
			"id": "XBi1eZXY6ja75JhvBiUda",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -550.2643908057298,
			"y": 2123.87388806771,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 61.75532498045004,
			"height": 62.499365040455814,
			"seed": 970596910,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					-17.11292138012459,
					44.64240360032545
				],
				[
					-61.75532498045004,
					62.499365040455814
				]
			]
		},
		{
			"type": "text",
			"version": 224,
			"versionNonce": 501962926,
			"isDeleted": false,
			"id": "IJlpjehn",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -724.4992298571311,
			"y": 2175.2126522080844,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 92.5198974609375,
			"height": 25,
			"seed": 1083607730,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Old value",
			"rawText": "Old value",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Old value",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 245,
			"versionNonce": 1553470190,
			"isDeleted": false,
			"id": "dq5xi7KuX3oTTlQlxigly",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -462.4676637250898,
			"y": 2116.433487467656,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 33.48180270024409,
			"height": 66.96360540048818,
			"seed": 1197945586,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					-2.976160240021727,
					56.54704456041236
				],
				[
					30.50564246022236,
					66.96360540048818
				]
			]
		},
		{
			"type": "text",
			"version": 263,
			"versionNonce": 305366318,
			"isDeleted": false,
			"id": "7ISHNYIu",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -432.5268990180957,
			"y": 2169.260331728042,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 187.1397705078125,
			"height": 50,
			"seed": 61380846,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "usually an average\nnormalizing term",
			"rawText": "usually an average\nnormalizing term",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "usually an average\nnormalizing term",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 525,
			"versionNonce": 810197874,
			"isDeleted": false,
			"id": "ryG2skdKH-uOMjyHStCSa",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -406.6646592246832,
			"y": 2114.9454073476454,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 188.1696590771901,
			"height": 54.5330432686128,
			"seed": 762526770,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717848649314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "a2pcs0MW",
				"focus": -0.3630739330443335,
				"gap": 8.178534551226676
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					72.17188582052609,
					33.48180270024386
				],
				[
					188.1696590771901,
					54.5330432686128
				]
			]
		},
		{
			"type": "text",
			"version": 281,
			"versionNonce": 1387958702,
			"isDeleted": false,
			"id": "a2pcs0MW",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -210.31646559626643,
			"y": 2152.891450407923,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 276.9396667480469,
			"height": 50,
			"seed": 1464050606,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "ryG2skdKH-uOMjyHStCSa",
					"type": "arrow"
				}
			],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "reward i gained in the total\nsequence",
			"rawText": "reward i gained in the total\nsequence",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "reward i gained in the total\nsequence",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 743,
			"versionNonce": 231302450,
			"isDeleted": false,
			"id": "hM0V0orb9ggQodPZ6zJ0o",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -292.08248998384806,
			"y": 2101.552686267548,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 63.87727660449468,
			"height": 9.344528919422828,
			"seed": 837724078,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717848649314,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "gV69JnRx",
				"focus": -0.6363620985564199,
				"gap": 3.4939486430050692
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					34.331760967991215,
					9.344528919422828
				],
				[
					63.87727660449468,
					9.05522087527379
				]
			]
		},
		{
			"type": "text",
			"version": 517,
			"versionNonce": 942966894,
			"isDeleted": false,
			"id": "gV69JnRx",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -224.7112647363483,
			"y": 1984.681164264367,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 395.09954833984375,
			"height": 150,
			"seed": 1783739442,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "hM0V0orb9ggQodPZ6zJ0o",
					"type": "arrow"
				}
			],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "reward i had at s previously\nthe reason we do this is so that\nwhen we converge we do not have \ninfinite learning (i.e optimal V(s) should\npredict Gt and thus the learning stops)\nreal == estimate",
			"rawText": "reward i had at s previously\nthe reason we do this is so that\nwhen we converge we do not have \ninfinite learning (i.e optimal V(s) should\npredict Gt and thus the learning stops)\nreal == estimate",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "reward i had at s previously\nthe reason we do this is so that\nwhen we converge we do not have \ninfinite learning (i.e optimal V(s) should\npredict Gt and thus the learning stops)\nreal == estimate",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 874,
			"versionNonce": 1413727470,
			"isDeleted": false,
			"id": "TxzhkgwH",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -855.7338034225875,
			"y": 2228.7835365284755,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 765.6991577148438,
			"height": 225,
			"seed": 578727858,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Which basically says, play one episode, after youre done\nupdate the estimate of the value s that was apart of your episode\nas the old value + the average reward per step in your episode\nassumes that every single step you took along the way to the reward\nis equally as important and contributing to that reward\n(if you play a good game of chess and win, but you made a bad move at\nthe start, Monte carlo weighs that move just as important as a good move,\nwhich after billions of games will \"even out\" the bad moves but it requires\na lot)",
			"rawText": "Which basically says, play one episode, after youre done\nupdate the estimate of the value s that was apart of your episode\nas the old value + the average reward per step in your episode\nassumes that every single step you took along the way to the reward\nis equally as important and contributing to that reward\n(if you play a good game of chess and win, but you made a bad move at\nthe start, Monte carlo weighs that move just as important as a good move,\nwhich after billions of games will \"even out\" the bad moves but it requires\na lot)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Which basically says, play one episode, after youre done\nupdate the estimate of the value s that was apart of your episode\nas the old value + the average reward per step in your episode\nassumes that every single step you took along the way to the reward\nis equally as important and contributing to that reward\n(if you play a good game of chess and win, but you made a bad move at\nthe start, Monte carlo weighs that move just as important as a good move,\nwhich after billions of games will \"even out\" the bad moves but it requires\na lot)",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 167,
			"versionNonce": 1033434926,
			"isDeleted": false,
			"id": "mI73tqScSGlzV1NbnnpJU",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 405.73121668000863,
			"y": 1781.0900093572404,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 295.67855527871836,
			"height": 38.238938842967215,
			"seed": 94327726,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6a7fd643c10a4b545463f0fd20ddc7196e1911b0",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 145,
			"versionNonce": 571335022,
			"isDeleted": false,
			"id": "aVbIhVIC",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -418.0833605246188,
			"y": 2041.6250360603972,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 38.13995361328125,
			"height": 25,
			"seed": 1344201646,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "real",
			"rawText": "real",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "real",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 145,
			"versionNonce": 1961591726,
			"isDeleted": false,
			"id": "8GLELixB",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -360.9460272697788,
			"y": 2041.6250360603972,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 85.71989440917969,
			"height": 25,
			"seed": 1072888434,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "estimate",
			"rawText": "estimate",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "estimate",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 158,
			"versionNonce": 1482350062,
			"isDeleted": false,
			"id": "wmkUDmRDoMfVfaLlKmE2s",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 533.9312060918842,
			"y": 1478.3516398125885,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 162.44512903358805,
			"height": 1.1603223502402216,
			"seed": 1588737394,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					162.44512903358805,
					1.1603223502402216
				]
			]
		},
		{
			"type": "text",
			"version": 194,
			"versionNonce": 1097134126,
			"isDeleted": false,
			"id": "12M31jE6",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 600.1449220278773,
			"y": 1455.1451928077904,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 38.13995361328125,
			"height": 25,
			"seed": 231897390,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "real",
			"rawText": "real",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "real",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 149,
			"versionNonce": 468892270,
			"isDeleted": false,
			"id": "6MIEFP6G0W2YfZP7kN_aI",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 734.6669726833893,
			"y": 1476.030995112109,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 58.596278687115955,
			"height": 1.7404835253596502,
			"seed": 174316974,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					58.596278687115955,
					1.7404835253596502
				]
			]
		},
		{
			"type": "text",
			"version": 153,
			"versionNonce": 1858944174,
			"isDeleted": false,
			"id": "HQlfifCf",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 721.9754065850375,
			"y": 1452.2443869321905,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 85.71989440917969,
			"height": 25,
			"seed": 1943044658,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "estimate",
			"rawText": "estimate",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "estimate",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 264,
			"versionNonce": 1502211826,
			"isDeleted": false,
			"id": "ZHuNFI60aFtX-12xIYf76",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 562.2435125272514,
			"y": 1872.45382684704,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 2.2187195007390983,
			"height": 114.2640542880672,
			"seed": 40957042,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717848649314,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "OG31LUJI",
				"focus": 0.0179790296143548,
				"gap": 21.861314783146554
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					2.2187195007390983,
					114.2640542880672
				]
			]
		},
		{
			"type": "text",
			"version": 147,
			"versionNonce": 1995204910,
			"isDeleted": false,
			"id": "vqdDsPrC",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 515.5320173479199,
			"y": 1984.645768652108,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 97.86042785644531,
			"height": 70,
			"seed": 1588795374,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "TD(N)\nMethod",
			"rawText": "TD(N)\nMethod",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "TD(N)\nMethod",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 494,
			"versionNonce": 69407598,
			"isDeleted": false,
			"id": "56yt6cNC",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 177.92587028786147,
			"y": 2071.0292221631953,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 761.9791259765625,
			"height": 100,
			"seed": 2124920750,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "HOvbsyQfTkCpM0kI1_EzO",
					"type": "arrow"
				},
				{
					"id": "-5GQuzPwhHMwt4H0W-2qI",
					"type": "arrow"
				}
			],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "As we said before the TD algorithm that we introduced only takes\ninto account the last action we took as the responsible for our current\nreward, but we can adapt this to a window of size n of last n actions.\nat the extreme case of N=entire episode, this will converge into Monte carlo",
			"rawText": "As we said before the TD algorithm that we introduced only takes\ninto account the last action we took as the responsible for our current\nreward, but we can adapt this to a window of size n of last n actions.\nat the extreme case of N=entire episode, this will converge into Monte carlo",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "As we said before the TD algorithm that we introduced only takes\ninto account the last action we took as the responsible for our current\nreward, but we can adapt this to a window of size n of last n actions.\nat the extreme case of N=entire episode, this will converge into Monte carlo",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 334,
			"versionNonce": 1451866926,
			"isDeleted": false,
			"id": "CUI7v14qDxe53OtgKnrFJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 30,
			"angle": 0,
			"x": -1206.0108698954623,
			"y": 517.7030162259996,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 457.15329410573844,
			"height": 427.88433320262726,
			"seed": 1448620590,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "IEoseJYTbH8V4id1e8U3N",
					"type": "arrow"
				}
			],
			"updated": 1717846065553,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 305,
			"versionNonce": 2087016114,
			"isDeleted": false,
			"id": "UtvNId8TvplDVMjph0q3W",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 30,
			"angle": 0,
			"x": -1672.6156596188619,
			"y": 518.6225009938403,
			"strokeColor": "#1971c2",
			"backgroundColor": "#1971c2",
			"width": 457.15329410573844,
			"height": 427.88433320262726,
			"seed": 2096514290,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "NLdLJk9CYtJevvpwyVnoq",
					"type": "arrow"
				}
			],
			"updated": 1717846065553,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 334,
			"versionNonce": 1749427566,
			"isDeleted": false,
			"id": "rpK1jV1zBx2F8q_ygBCY4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 30,
			"angle": 0,
			"x": -1355.840074638675,
			"y": 505.15917634649054,
			"strokeColor": "#9c36b5",
			"backgroundColor": "#9c36b5",
			"width": 299.65840924613957,
			"height": 522.6600161269876,
			"seed": 1206516338,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717846065553,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 262,
			"versionNonce": 1118548082,
			"isDeleted": false,
			"id": "wcCTaKiR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1278.3027046438356,
			"y": 980.4313505037587,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"width": 126.39173889160156,
			"height": 38.146791268332514,
			"seed": 1118132270,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065553,
			"link": null,
			"locked": false,
			"fontSize": 30.51743301466601,
			"fontFamily": 1,
			"text": "Deep RL",
			"rawText": "Deep RL",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Deep RL",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 250,
			"versionNonce": 1400588206,
			"isDeleted": false,
			"id": "CqRQyjQP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -974.6576432611338,
			"y": 521.8842963550151,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"width": 210.35806274414062,
			"height": 38.146791268332514,
			"seed": 693490478,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "IEoseJYTbH8V4id1e8U3N",
					"type": "arrow"
				}
			],
			"updated": 1717846065554,
			"link": null,
			"locked": false,
			"fontSize": 30.51743301466601,
			"fontFamily": 1,
			"text": "Model-free RL",
			"rawText": "Model-free RL",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Model-free RL",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 288,
			"versionNonce": 713085490,
			"isDeleted": false,
			"id": "BOIm6c8T",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1657.629443002747,
			"y": 526.5048214519384,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"width": 235.49000549316406,
			"height": 38.146791268332514,
			"seed": 1870517042,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false,
			"fontSize": 30.51743301466601,
			"fontFamily": 1,
			"text": "Model-based RL",
			"rawText": "Model-based RL",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Model-based RL",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 449,
			"versionNonce": 1481777646,
			"isDeleted": false,
			"id": "-Qbxc1fEFJYpIWFpGQDN3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 60,
			"angle": 0,
			"x": -1659.6506996500907,
			"y": 597.5344203883292,
			"strokeColor": "#1971c2",
			"backgroundColor": "#1971c2",
			"width": 398.615372299516,
			"height": 117.07584361244504,
			"seed": 418616878,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 272,
			"versionNonce": 650886130,
			"isDeleted": false,
			"id": "OBdZLt4N",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1641.8175237111539,
			"y": 597.2771482455832,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 206.04954528808594,
			"height": 21.79816643904715,
			"seed": 582802546,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false,
			"fontSize": 17.43853315123772,
			"fontFamily": 1,
			"text": "Markov decision Process",
			"rawText": "Markov decision Process",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Markov decision Process",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 481,
			"versionNonce": 1238610990,
			"isDeleted": false,
			"id": "KnlPikFDuDVidgy7kbtw5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 60,
			"angle": 0,
			"x": -1656.8922439630423,
			"y": 766.4891843156558,
			"strokeColor": "#0c8599",
			"backgroundColor": "#0c8599",
			"width": 398.615372299516,
			"height": 117.07584361244504,
			"seed": 1676722926,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 244,
			"versionNonce": 898854322,
			"isDeleted": false,
			"id": "81xOGj0W",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1641.8175235544732,
			"y": 775.3208657850564,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#0c8599",
			"width": 164.62014770507812,
			"height": 21.79816643904715,
			"seed": 454541998,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false,
			"fontSize": 17.43853315123772,
			"fontFamily": 1,
			"text": "Non-linear Dynamics",
			"rawText": "Non-linear Dynamics",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Non-linear Dynamics",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 284,
			"versionNonce": 837353070,
			"isDeleted": false,
			"id": "XrotJUFH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1582.3555945455978,
			"y": 718.312780997022,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#0c8599",
			"width": 190.1956024169922,
			"height": 43.5963328780943,
			"seed": 1022925230,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false,
			"fontSize": 17.43853315123772,
			"fontFamily": 1,
			"text": "Dynamic Programming\nand Bellman optimality",
			"rawText": "Dynamic Programming\nand Bellman optimality",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Dynamic Programming\nand Bellman optimality",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 285,
			"versionNonce": 2080302962,
			"isDeleted": false,
			"id": "Qo1faRdTQsY2kqsB8lbAP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": -1346.4859132168049,
			"y": 614.4109487915043,
			"strokeColor": "#6741d9",
			"backgroundColor": "#6741d9",
			"width": 77.23676022357098,
			"height": 67.12242257524616,
			"seed": 112194034,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 317,
			"versionNonce": 1968898222,
			"isDeleted": false,
			"id": "P6IuWuvF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1332.390120928861,
			"y": 623.6058011990722,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#6741d9",
			"width": 47.16123962402344,
			"height": 43.5963328780943,
			"seed": 1838246642,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false,
			"fontSize": 17.43853315123772,
			"fontFamily": 1,
			"text": "Actor\nCritic",
			"rawText": "Actor\nCritic",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Actor\nCritic",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 341,
			"versionNonce": 1649748274,
			"isDeleted": false,
			"id": "gs7Pl63ri_HBNSsz2NHLt",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": -1345.566427976048,
			"y": 791.4118576371875,
			"strokeColor": "#6741d9",
			"backgroundColor": "#6741d9",
			"width": 77.23676022357098,
			"height": 67.12242257524616,
			"seed": 231736430,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 381,
			"versionNonce": 2010299118,
			"isDeleted": false,
			"id": "vJZNY6jW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1328.506075406599,
			"y": 800.6067100447558,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#6741d9",
			"width": 41.23777770996094,
			"height": 43.5963328780943,
			"seed": 175195822,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false,
			"fontSize": 17.43853315123772,
			"fontFamily": 1,
			"text": "Deep\nMPC",
			"rawText": "Deep\nMPC",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Deep\nMPC",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 261,
			"versionNonce": 805122802,
			"isDeleted": false,
			"id": "7RKaA2KW",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1425.5834826162045,
			"y": 595.2364984051696,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 70.84404092690323,
			"height": 21.798166439047147,
			"seed": 84069,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0c56f3322d97551dfab15d16173f46d7608d9c0c",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 256,
			"versionNonce": 1071197486,
			"isDeleted": false,
			"id": "SjGjq7Th",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1621.914988548807,
			"y": 630.5831135281949,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#6741d9",
			"width": 134.6195068359375,
			"height": 21.79816643904715,
			"seed": 115407150,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false,
			"fontSize": 17.43853315123772,
			"fontFamily": 1,
			"text": "Policy Iteration",
			"rawText": "Policy Iteration",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Policy Iteration",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 291,
			"versionNonce": 662570162,
			"isDeleted": false,
			"id": "Vit19t6F",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1620.9907466164223,
			"y": 667.2021339333583,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#6741d9",
			"width": 132.77279663085938,
			"height": 21.79816643904715,
			"seed": 1320584434,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false,
			"fontSize": 17.43853315123772,
			"fontFamily": 1,
			"text": "Value Iteration",
			"rawText": "Value Iteration",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Value Iteration",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 394,
			"versionNonce": 450320238,
			"isDeleted": false,
			"id": "ueLiXn78",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1615.447337103657,
			"y": 807.3641126923776,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 176.5651481562819,
			"height": 37.056882946380156,
			"seed": 97391,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "50699bce0f593461d93840c3e23985b8fbf68815",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 270,
			"versionNonce": 578723442,
			"isDeleted": false,
			"id": "4FMK2LHS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1580.303437471388,
			"y": 853.4771113882716,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#6741d9",
			"width": 211.8162384033203,
			"height": 21.79816643904715,
			"seed": 815954290,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false,
			"fontSize": 17.43853315123772,
			"fontFamily": 1,
			"text": "Optimal Control and HJB",
			"rawText": "Optimal Control and HJB",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Optimal Control and HJB",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 266,
			"versionNonce": 1091975598,
			"isDeleted": false,
			"id": "jipipvEZ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1463.4021101651438,
			"y": 629.9814008825988,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 71.44713594031722,
			"height": 22.91700586764892,
			"seed": 52479,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "120a11884e18b9a1698118dc7ee755e44d43403b",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 244,
			"versionNonce": 767950898,
			"isDeleted": false,
			"id": "LJDuIVuN",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1464.0800995337172,
			"y": 670.1536441857213,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 35.9669746244278,
			"height": 18.528441473190078,
			"seed": 10296,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "74e67cfd08dfaa4ff77b8228f721859b51943541",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 344,
			"versionNonce": 2042549230,
			"isDeleted": false,
			"id": "qV6bEVy8e5In46iIZIWQc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1185.6124789893177,
			"y": 575.2242116294422,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 426.24676347084846,
			"height": 186.2856225539264,
			"seed": 601053746,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 243,
			"versionNonce": 624634354,
			"isDeleted": false,
			"id": "fAH2boJT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1050.8422495710424,
			"y": 580.9191299795411,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 149.2230682373047,
			"height": 27.24770804880894,
			"seed": 1166934510,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false,
			"fontSize": 21.79816643904715,
			"fontFamily": 1,
			"text": "Gradient Free",
			"rawText": "Gradient Free",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Gradient Free",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 407,
			"versionNonce": 1054484014,
			"isDeleted": false,
			"id": "Tn0aNob3pZibD2iyibl8l",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1190.557605647231,
			"y": 784.8619994067635,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"width": 426.24676347084846,
			"height": 147.34456021214504,
			"seed": 86785134,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 255,
			"versionNonce": 1340414898,
			"isDeleted": false,
			"id": "jJXLmEU5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1066.5131664630048,
			"y": 792.03120737017,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 170.02410888671875,
			"height": 27.24770804880894,
			"seed": 790517426,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false,
			"fontSize": 21.79816643904715,
			"fontFamily": 1,
			"text": "Gradient Based",
			"rawText": "Gradient Based",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Gradient Based",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 384,
			"versionNonce": 1632710766,
			"isDeleted": false,
			"id": "uBkqDXWaPFD942SoFqcHS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1175.0878675455929,
			"y": 614.1652739712235,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 215.75453459635528,
			"height": 133.66256533530301,
			"seed": 1044166190,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 448,
			"versionNonce": 2078987634,
			"isDeleted": false,
			"id": "RlmJboClO_f3GpC_vHHUN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -930.9168820511804,
			"y": 613.6390433990371,
			"strokeColor": "#ffd43b",
			"backgroundColor": "transparent",
			"width": 150.50194364526237,
			"height": 133.66256533530301,
			"seed": 657705842,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 245,
			"versionNonce": 753726126,
			"isDeleted": false,
			"id": "ncC0jVzs",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -883.0937093656589,
			"y": 720.0312369246058,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 55.85481262207031,
			"height": 21.79816643904715,
			"seed": 119712626,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false,
			"fontSize": 17.43853315123772,
			"fontFamily": 1,
			"text": "SARSA",
			"rawText": "SARSA",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "SARSA",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 264,
			"versionNonce": 445863730,
			"isDeleted": false,
			"id": "yR6u86pZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1113.5515404934654,
			"y": 719.41138840847,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 87.33633422851562,
			"height": 21.79816643904715,
			"seed": 1433972206,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false,
			"fontSize": 17.43853315123772,
			"fontFamily": 1,
			"text": "Q-Learning",
			"rawText": "Q-Learning",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Q-Learning",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 269,
			"versionNonce": 206990574,
			"isDeleted": false,
			"id": "rJix9T3k",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1096.67324707958,
			"y": 904.6445498180237,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 240.7715606689453,
			"height": 21.79816643904715,
			"seed": 906318386,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false,
			"fontSize": 17.43853315123772,
			"fontFamily": 1,
			"text": "Policy Gradient Optimization",
			"rawText": "Policy Gradient Optimization",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Policy Gradient Optimization",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 341,
			"versionNonce": 1548067058,
			"isDeleted": false,
			"id": "oPQ2Fb5gTgh14GzAGYrje",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": -1166.3454961606176,
			"y": 816.3553590230329,
			"strokeColor": "#6741d9",
			"backgroundColor": "#6741d9",
			"width": 77.23676022357098,
			"height": 67.12242257524616,
			"seed": 130923570,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 449,
			"versionNonce": 756457262,
			"isDeleted": false,
			"id": "MBINYVJd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1158.9363948215885,
			"y": 817.1305222756209,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#6741d9",
			"width": 66.83064270019531,
			"height": 65.39449931714145,
			"seed": 1592485362,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false,
			"fontSize": 17.43853315123772,
			"fontFamily": 1,
			"text": "Deep\nPolicy\nNetwork",
			"rawText": "Deep\nPolicy\nNetwork",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Deep\nPolicy\nNetwork",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 355,
			"versionNonce": 1284027058,
			"isDeleted": false,
			"id": "pefMwKuPcHM-p3-sjE8Qs",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": -1154.7684235725203,
			"y": 649.0140370678102,
			"strokeColor": "#6741d9",
			"backgroundColor": "#6741d9",
			"width": 77.23676022357098,
			"height": 67.12242257524616,
			"seed": 1843163378,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 423,
			"versionNonce": 597068142,
			"isDeleted": false,
			"id": "Db8Mt1SB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1133.5279640010788,
			"y": 668.7335009191029,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#6741d9",
			"width": 37.09135437011719,
			"height": 21.79816643904715,
			"seed": 583369394,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false,
			"fontSize": 17.43853315123772,
			"fontFamily": 1,
			"text": "DQN",
			"rawText": "DQN",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "DQN",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 276,
			"versionNonce": 1845726322,
			"isDeleted": false,
			"id": "hn3hIcME",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1049.098481045467,
			"y": 665.1160215293385,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 63.71000671386719,
			"height": 27.24770804880894,
			"seed": 668151666,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false,
			"fontSize": 21.79816643904715,
			"fontFamily": 1,
			"text": "Q(s,a)",
			"rawText": "Q(s,a)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Q(s,a)",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 248,
			"versionNonce": 253701038,
			"isDeleted": false,
			"id": "gxACb2CW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1122.8766295231867,
			"y": 620.4800408374583,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 105.98735046386719,
			"height": 27.24770804880894,
			"seed": 1041175342,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "sO-ASLtAk8GAO8HNxdiX9",
					"type": "arrow"
				}
			],
			"updated": 1717846065554,
			"link": null,
			"locked": false,
			"fontSize": 21.79816643904715,
			"fontFamily": 1,
			"text": "Off Policy",
			"rawText": "Off Policy",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Off Policy",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 251,
			"versionNonce": 1451044402,
			"isDeleted": false,
			"id": "RtfhrmhC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -905.8279157830068,
			"y": 622.643103978641,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 94.98785400390625,
			"height": 27.24770804880894,
			"seed": 1034563502,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false,
			"fontSize": 21.79816643904715,
			"fontFamily": 1,
			"text": "On Policy",
			"rawText": "On Policy",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "On Policy",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 267,
			"versionNonce": 1037665774,
			"isDeleted": false,
			"id": "QCNjx3VE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -876.5323088613034,
			"y": 656.263719746122,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 43.862213134765625,
			"height": 54.37913439274273,
			"seed": 1608327598,
			"groupIds": [
				"7fZ3JcEF4b52Utyc5vr_G"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false,
			"fontSize": 14.501102504731396,
			"fontFamily": 1,
			"text": "TD(0)\nTD(n)\nTD( )",
			"rawText": "TD(0)\nTD(n)\nTD( )",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "TD(0)\nTD(n)\nTD( )",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 329,
			"versionNonce": 1255970802,
			"isDeleted": false,
			"id": "xRlgb8dZ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -848.0713109555445,
			"y": 696.3320027787252,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 11.448832416518869,
			"height": 8.081528764601554,
			"seed": 19699,
			"groupIds": [
				"7fZ3JcEF4b52Utyc5vr_G"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "558f0fb0752aaf4b02ebdbca4d3b48f367884038",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 250,
			"versionNonce": 1355716654,
			"isDeleted": false,
			"id": "BgdVhXzz",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1045.99976813324,
			"y": 842.1748705242494,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 224.9034664422554,
			"height": 28.112933305281924,
			"seed": 61530,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "862e8526888e2dc3ea75a5d20c86e1923336eebb",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 482,
			"versionNonce": 1608999534,
			"isDeleted": false,
			"id": "sO-ASLtAk8GAO8HNxdiX9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1116.961059714281,
			"y": 610.912216002549,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 60.517120575871374,
			"height": 219.3745620875335,
			"seed": 138207854,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "gxACb2CW",
				"focus": -0.8121236638898052,
				"gap": 9.567824834909231
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					-19.668064187158123,
					-166.42208158364627
				],
				[
					40.84905638871325,
					-219.3745620875335
				]
			]
		},
		{
			"type": "text",
			"version": 280,
			"versionNonce": 502064302,
			"isDeleted": false,
			"id": "5CxEz2Pq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1152.4286114707104,
			"y": 326.4817492959538,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 315.783935546875,
			"height": 81.74312414642682,
			"seed": 1244966066,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717846065554,
			"link": null,
			"locked": false,
			"fontSize": 21.79816643904715,
			"fontFamily": 1,
			"text": "doesnt always take the best\naction, takes risks\nexplores",
			"rawText": "doesnt always take the best\naction, takes risks\nexplores",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "doesnt always take the best\naction, takes risks\nexplores",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 381,
			"versionNonce": 1928197934,
			"isDeleted": false,
			"id": "EyBU2unsGMTReDc5gXRUC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -784.1168965469885,
			"y": 624.52856813212,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 151.2958724023556,
			"height": 36.310272345522684,
			"seed": 528047406,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717846474687,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "RTxcNoVQ",
				"focus": -0.07117683043573685,
				"gap": 1.5129280143969481
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					99.85324895018762,
					-34.79734433112596
				],
				[
					151.2958724023556,
					1.5129280143967208
				]
			]
		},
		{
			"type": "text",
			"version": 293,
			"versionNonce": 1345897710,
			"isDeleted": false,
			"id": "RTxcNoVQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -684.5545673341021,
			"y": 627.5544241609136,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 294.0898742675781,
			"height": 108.99083219523575,
			"seed": 604701298,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "EyBU2unsGMTReDc5gXRUC",
					"type": "arrow"
				}
			],
			"updated": 1717846474685,
			"link": null,
			"locked": false,
			"fontSize": 21.79816643904715,
			"fontFamily": 1,
			"text": "always takes the best\naction,\nvery safe and conservative\ndoesnt explore",
			"rawText": "always takes the best\naction,\nvery safe and conservative\ndoesnt explore",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "always takes the best\naction,\nvery safe and conservative\ndoesnt explore",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 458,
			"versionNonce": 621566578,
			"isDeleted": false,
			"id": "HOvbsyQfTkCpM0kI1_EzO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 562.1715504971196,
			"y": 2185.586481221758,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 272.3563218390803,
			"height": 255.6814449917896,
			"seed": 1884404590,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717848649315,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "56yt6cNC",
				"focus": -0.04596938358089147,
				"gap": 14.557259058562522
			},
			"endBinding": {
				"elementId": "3dp9Gok5",
				"focus": -0.020264216594454636,
				"gap": 5.854269293924972
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					-33.34975369458127,
					145.6272577996714
				],
				[
					-252.34646962233154,
					150.07389162561572
				],
				[
					-272.3563218390803,
					255.6814449917896
				]
			]
		},
		{
			"type": "arrow",
			"version": 481,
			"versionNonce": 1955194354,
			"isDeleted": false,
			"id": "-5GQuzPwhHMwt4H0W-2qI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 563.700080874788,
			"y": 2187.80979813473,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 275.25773802613696,
			"height": 254.4314449917897,
			"seed": 751485230,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717848649315,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "56yt6cNC",
				"focus": 0.021922497189313907,
				"gap": 16.780575971534745
			},
			"endBinding": {
				"elementId": "LR45oJJf",
				"focus": 0.09501204737501123,
				"gap": 12.380952380952749
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					28.903119868637067,
					144.51559934318524
				],
				[
					252.34646962233145,
					150.07389162561566
				],
				[
					275.25773802613696,
					254.4314449917897
				]
			]
		},
		{
			"type": "text",
			"version": 93,
			"versionNonce": 593702574,
			"isDeleted": false,
			"id": "LR45oJJf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 778.1599038188685,
			"y": 2454.6221955074725,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 122.36050415039062,
			"height": 35,
			"seed": 265095986,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "-5GQuzPwhHMwt4H0W-2qI",
					"type": "arrow"
				}
			],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "ON policy",
			"rawText": "ON policy",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "ON policy",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 127,
			"versionNonce": 1882053422,
			"isDeleted": false,
			"id": "3dp9Gok5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 218.60387354543116,
			"y": 2447.1221955074725,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 136.47256469726562,
			"height": 35,
			"seed": 602456754,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "HOvbsyQfTkCpM0kI1_EzO",
					"type": "arrow"
				}
			],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "OFF policy",
			"rawText": "OFF policy",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "OFF policy",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 1090,
			"versionNonce": 714565550,
			"isDeleted": false,
			"id": "0fvv4LHO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -69.66094655552106,
			"y": 2483.618711404424,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 701.8992309570312,
			"height": 300,
			"seed": 964909294,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "hqziDJznkIitXuPgNrepr",
					"type": "arrow"
				}
			],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "or as I like to call it \"Fuck around and find out\",\nOff policy methods are methods that tend to have a sense\nof exploration, they will update their value estimation\naccording to the reward but then dont have to necessarily\ntake that reward all the time instead they will have an\nelement of randomness where they decide to take a risk\nand explore to find new routes. This results in worse\nperformance while learning but it has higher potential of\nreaching better results. it also learns faster due to not\nbeing scared of risk taking and learning from those mistakes.\nthese methods can often learn from imitation as well, just by watching\nothers play and make mistakes. also produces higher variance",
			"rawText": "or as I like to call it \"Fuck around and find out\",\nOff policy methods are methods that tend to have a sense\nof exploration, they will update their value estimation\naccording to the reward but then dont have to necessarily\ntake that reward all the time instead they will have an\nelement of randomness where they decide to take a risk\nand explore to find new routes. This results in worse\nperformance while learning but it has higher potential of\nreaching better results. it also learns faster due to not\nbeing scared of risk taking and learning from those mistakes.\nthese methods can often learn from imitation as well, just by watching\nothers play and make mistakes. also produces higher variance",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "or as I like to call it \"Fuck around and find out\",\nOff policy methods are methods that tend to have a sense\nof exploration, they will update their value estimation\naccording to the reward but then dont have to necessarily\ntake that reward all the time instead they will have an\nelement of randomness where they decide to take a risk\nand explore to find new routes. This results in worse\nperformance while learning but it has higher potential of\nreaching better results. it also learns faster due to not\nbeing scared of risk taking and learning from those mistakes.\nthese methods can often learn from imitation as well, just by watching\nothers play and make mistakes. also produces higher variance",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 1559,
			"versionNonce": 1617417262,
			"isDeleted": false,
			"id": "4hR56NvV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 582.5112196170271,
			"y": 2495.5357509084024,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 507.5194091796875,
			"height": 225,
			"seed": 1031846574,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "L8CWpF2TsUtcSLIiz2bvf",
					"type": "arrow"
				}
			],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "On Policy methods are methods that\nonly consider and take the best option estimate\nthey have, while this give a better performance\nduring training because we always maximizing\nthe reward we would get, this is very conservative\nand doesnt like to explore, meaning it will be slower\nto train and less potential for an optimal path.\nWhile worse than Off policy, in certain situations\nwhere mistakes are very costly, this is desired.",
			"rawText": "On Policy methods are methods that\nonly consider and take the best option estimate\nthey have, while this give a better performance\nduring training because we always maximizing\nthe reward we would get, this is very conservative\nand doesnt like to explore, meaning it will be slower\nto train and less potential for an optimal path.\nWhile worse than Off policy, in certain situations\nwhere mistakes are very costly, this is desired.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "On Policy methods are methods that\nonly consider and take the best option estimate\nthey have, while this give a better performance\nduring training because we always maximizing\nthe reward we would get, this is very conservative\nand doesnt like to explore, meaning it will be slower\nto train and less potential for an optimal path.\nWhile worse than Off policy, in certain situations\nwhere mistakes are very costly, this is desired.",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 151,
			"versionNonce": 1298604206,
			"isDeleted": false,
			"id": "9EKgh593Ou4fhwgHQD-_U",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 313.93196834737637,
			"y": 2820.2592467969116,
			"strokeColor": "transparent",
			"backgroundColor": "#d0bfff",
			"width": 563,
			"height": 238,
			"seed": 419464110,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d160f52c80410ddb80f4a62418419645ba98dae4",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 538,
			"versionNonce": 962255598,
			"isDeleted": false,
			"id": "9rMxCA0a",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 299.0233692585664,
			"y": 3058.2592472086762,
			"strokeColor": "#e03131",
			"backgroundColor": "#d0bfff",
			"width": 592.8171997070312,
			"height": 120,
			"seed": 1022046194,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "IN this example, an OFF policy will learn the optimal path while an ON\npolicy will learn the safer path, this is because an ON policy will try to\ntake the optimal path but jump into the cliff by accident and then realize\nthat the optimal path is \"dangerous\" and thus will stay away from it\nwhile OFF policy does not care about the consequences of the cliff, it will\ngo to the optimal path",
			"rawText": "IN this example, an OFF policy will learn the optimal path while an ON\npolicy will learn the safer path, this is because an ON policy will try to\ntake the optimal path but jump into the cliff by accident and then realize\nthat the optimal path is \"dangerous\" and thus will stay away from it\nwhile OFF policy does not care about the consequences of the cliff, it will\ngo to the optimal path",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "IN this example, an OFF policy will learn the optimal path while an ON\npolicy will learn the safer path, this is because an ON policy will try to\ntake the optimal path but jump into the cliff by accident and then realize\nthat the optimal path is \"dangerous\" and thus will stay away from it\nwhile OFF policy does not care about the consequences of the cliff, it will\ngo to the optimal path",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 108,
			"versionNonce": 1039947698,
			"isDeleted": false,
			"id": "L8CWpF2TsUtcSLIiz2bvf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 851.0206527449805,
			"y": 2748.386848014318,
			"strokeColor": "#e03131",
			"backgroundColor": "#d0bfff",
			"width": 136.3399385085104,
			"height": 47.05537700736204,
			"seed": 2143398706,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717848649315,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "4hR56NvV",
				"focus": 0.008461327317022463,
				"gap": 27.851097105915414
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					4.82619251357562,
					39.816088236998894
				],
				[
					136.3399385085104,
					47.05537700736204
				]
			]
		},
		{
			"type": "text",
			"version": 113,
			"versionNonce": 1893169006,
			"isDeleted": false,
			"id": "tGkT9RcI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1015.0784743161869,
			"y": 2777.0090082655784,
			"strokeColor": "#e03131",
			"backgroundColor": "#d0bfff",
			"width": 188.15261840820312,
			"height": 31.193927985738426,
			"seed": 1758654126,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"fontSize": 24.95514238859074,
			"fontFamily": 1,
			"text": "Example SARSA",
			"rawText": "Example SARSA",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Example SARSA",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 100,
			"versionNonce": 465211762,
			"isDeleted": false,
			"id": "hqziDJznkIitXuPgNrepr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 217.58288533818472,
			"y": 2803.8880619204374,
			"strokeColor": "#e03131",
			"backgroundColor": "#d0bfff",
			"width": 92.90420588633003,
			"height": 68.77324331845193,
			"seed": 875431858,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1717848649315,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "0fvv4LHO",
				"focus": 0.14183038071705717,
				"gap": 20.26935051601322
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					-4.82619251357562,
					66.36014706166407
				],
				[
					-92.90420588633003,
					68.77324331845193
				]
			]
		},
		{
			"type": "text",
			"version": 88,
			"versionNonce": 641135598,
			"isDeleted": false,
			"id": "774jJOua",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -143.9185251502854,
			"y": 2854.302372083345,
			"strokeColor": "#e03131",
			"backgroundColor": "#d0bfff",
			"width": 252.4490509033203,
			"height": 35,
			"seed": 838441006,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Example Q-learning",
			"rawText": "Example Q-learning",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Example Q-learning",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 65,
			"versionNonce": 1733183022,
			"isDeleted": false,
			"id": "LQ597weS",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 887.2109319002514,
			"y": 2815.169072476626,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 428.5328911312328,
			"height": 20.80256753064237,
			"seed": 53566,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "03ba1593f30fde0b83514ff539f7e7beb9e3b28f",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 85,
			"versionNonce": 641814638,
			"isDeleted": false,
			"id": "dUQoby-Qaqa3SZvt39mLO",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -242.36895242301273,
			"y": 2896.213002526048,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 449.3499046571099,
			"height": 19.83884788773112,
			"seed": 1867405234,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c3dac01c651eff97ddefcf706d975f3cbadfe324",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "64XRe7ImhLM283hsP0dTs",
			"type": "arrow",
			"x": -25.02815104828403,
			"y": 2941.6893903360406,
			"width": 86.31578947368416,
			"height": 70.5263157894733,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1621236974,
			"version": 89,
			"versionNonce": 554406706,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717848649315,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					53.68421052631538
				],
				[
					-86.31578947368416,
					70.5263157894733
				]
			],
			"lastCommittedPoint": [
				-86.31578947368416,
				70.5263157894733
			],
			"startBinding": {
				"elementId": "85tpBv9F",
				"focus": -0.7249603201322263,
				"gap": 25.394736842104976
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "85tpBv9F",
			"type": "text",
			"x": -593.5761359244148,
			"y": 2967.0841271781455,
			"width": 659.2012329101562,
			"height": 120,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 963478130,
			"version": 341,
			"versionNonce": 733908206,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "64XRe7ImhLM283hsP0dTs",
					"type": "arrow"
				}
			],
			"updated": 1717848648863,
			"link": null,
			"locked": false,
			"text": "How do we choose what action\nto take if we dont take the optimal\naction?\nEpsilon greedy Q-learning says that for a given epsilon between\n0 and 1, you go to the optimal path epsilon% of the time and otherwise go explore\nsome random path ",
			"rawText": "How do we choose what action\nto take if we dont take the optimal\naction?\nEpsilon greedy Q-learning says that for a given epsilon between\n0 and 1, you go to the optimal path epsilon% of the time and otherwise go explore\nsome random path ",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How do we choose what action\nto take if we dont take the optimal\naction?\nEpsilon greedy Q-learning says that for a given epsilon between\n0 and 1, you go to the optimal path epsilon% of the time and otherwise go explore\nsome random path ",
			"lineHeight": 1.25
		},
		{
			"id": "MLp9Md69cYji8LBS0_nB8",
			"type": "line",
			"x": -523.2030661714766,
			"y": 3289.821206586475,
			"width": 1105.7142857142853,
			"height": 0.8791208791208192,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1014997806,
			"version": 167,
			"versionNonce": 1790194866,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717848674754,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1105.7142857142853,
					0.8791208791208192
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "nNY57Uz5",
			"type": "text",
			"x": -220.65399793439795,
			"y": 3312.2910132234783,
			"width": 500.61614990234375,
			"height": 45,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 735114798,
			"version": 62,
			"versionNonce": 1368964018,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717848693879,
			"link": null,
			"locked": false,
			"text": "Deep Reinforcement Learning",
			"rawText": "Deep Reinforcement Learning",
			"fontSize": 36,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Deep Reinforcement Learning",
			"lineHeight": 1.25
		},
		{
			"id": "kTFVnUse",
			"type": "text",
			"x": -336.391471340895,
			"y": 3377.155792044947,
			"width": 728.6392822265625,
			"height": 75,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 124539570,
			"version": 369,
			"versionNonce": 1470677166,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717852047176,
			"link": null,
			"locked": false,
			"text": "Everything we learned so far works in a tabular dynamic programming way.\nThis is an intractable way to approximate large environments\nBoard game Go on 19 × 19 board: 3^19×19 ≈ 10172",
			"rawText": "Everything we learned so far works in a tabular dynamic programming way.\nThis is an intractable way to approximate large environments\nBoard game Go on 19 × 19 board: 3^19×19 ≈ 10172",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Everything we learned so far works in a tabular dynamic programming way.\nThis is an intractable way to approximate large environments\nBoard game Go on 19 × 19 board: 3^19×19 ≈ 10172",
			"lineHeight": 1.25
		},
		{
			"id": "q4igPU1RUsUgYUGBJKmZO",
			"type": "image",
			"x": 876.3041393520546,
			"y": 3728.1746027807635,
			"width": 430.5238095238095,
			"height": 90.40258995164331,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1906820402,
			"version": 319,
			"versionNonce": 289321266,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717852037538,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4d1467c46a9b4433e2c7eadc6c3322432d67a019",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "YKy3ZHRX",
			"type": "text",
			"x": 776.736362622237,
			"y": 3806.077193018121,
			"width": 629.6593627929688,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 368316526,
			"version": 330,
			"versionNonce": 1484110578,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717852037538,
			"link": null,
			"locked": false,
			"text": "MSE between the truth and our approximation\nwhich we can subsequently minimize by finding the gradient for it",
			"rawText": "MSE between the truth and our approximation\nwhich we can subsequently minimize by finding the gradient for it",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "MSE between the truth and our approximation\nwhich we can subsequently minimize by finding the gradient for it",
			"lineHeight": 1.25
		},
		{
			"id": "Q1MQqKgKgER8uJLtzqzEk",
			"type": "image",
			"x": 701.1737345999779,
			"y": 3866.3233114027635,
			"width": 375.0278151999838,
			"height": 52.91803527361735,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 288541106,
			"version": 395,
			"versionNonce": 1067814066,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717852037538,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f71ab2ac1658b8cb65509ecd8fd6e60652d1da6b",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "Q-CpRjQCPbzqpFc6x1iIJ",
			"type": "image",
			"x": 1076.2015499765869,
			"y": 3869.856477569335,
			"width": 422.4470060623765,
			"height": 45.851701092153746,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1950361646,
			"version": 497,
			"versionNonce": 1551181426,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717852037538,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "bb86508b82af370f5414ccc2222f1087afd0ba0e",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "1kWdOCzX",
			"type": "text",
			"x": 740.0564009400166,
			"y": 3924.7906800295927,
			"width": 703.019287109375,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 752191474,
			"version": 294,
			"versionNonce": 2007730226,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717852037538,
			"link": null,
			"locked": false,
			"text": "Batch based algorithms are obviously unfeasible, thus we perform SGD",
			"rawText": "Batch based algorithms are obviously unfeasible, thus we perform SGD",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Batch based algorithms are obviously unfeasible, thus we perform SGD",
			"lineHeight": 1.25
		},
		{
			"id": "CKagPZSsK4uqDCGrZnV44",
			"type": "image",
			"x": 857.2502882678871,
			"y": 3955.340013005679,
			"width": 468.631511547404,
			"height": 44.43320998375386,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1368897778,
			"version": 282,
			"versionNonce": 690991602,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717852037538,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e6b028853eb4f06d3b5b978afe0cf117a4d91826",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "ntMHeLjT",
			"type": "text",
			"x": 762.9709981427645,
			"y": 4005.3225557642295,
			"width": 612.5794067382812,
			"height": 100,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1915678834,
			"version": 416,
			"versionNonce": 1946723250,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717852037538,
			"link": null,
			"locked": false,
			"text": "Problem:\nUnlike Supervised learning, true Q of oru \"dataset\" is unknown\nSolution:\nBootstrap your model as a predictor of future models",
			"rawText": "Problem:\nUnlike Supervised learning, true Q of oru \"dataset\" is unknown\nSolution:\nBootstrap your model as a predictor of future models",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Problem:\nUnlike Supervised learning, true Q of oru \"dataset\" is unknown\nSolution:\nBootstrap your model as a predictor of future models",
			"lineHeight": 1.25
		},
		{
			"id": "YrWPk_yCtyxLIMEGN6rMG",
			"type": "image",
			"x": 864.880255177378,
			"y": 4110.871888435703,
			"width": 422.6425891518444,
			"height": 34.57442901383212,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 321552302,
			"version": 296,
			"versionNonce": 1650285938,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717852037538,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "da1ca322c8469736cab2905ebc33eae77a0a9c46",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "ErGRBpqspf5tX0GzQqZLU",
			"type": "image",
			"x": 768.6705288301832,
			"y": 4145.44631801448,
			"width": 615.062043357419,
			"height": 28.996578653296275,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1646909358,
			"version": 441,
			"versionNonce": 561307442,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717852037538,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "694297df5802d28dd7fa822f3245233df2ae2877",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "iJwZ3W1p",
			"type": "text",
			"x": 632.2382844758403,
			"y": 3564.1735910742823,
			"width": 935.319091796875,
			"height": 175,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1495791346,
			"version": 279,
			"versionNonce": 498477298,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717852037538,
			"link": null,
			"locked": false,
			"text": "\nUse function approximators (e.g. neural networks) to generalize Value\nand Q-Value function, by using replay buffers to collect trajectories of agent interaction with\nenvironment and computing discounted reward for all actions in trajectories.\nthus training the neural network to predict the maximum Q value\n\nOur Objective",
			"rawText": "\nUse function approximators (e.g. neural networks) to generalize Value\nand Q-Value function, by using replay buffers to collect trajectories of agent interaction with\nenvironment and computing discounted reward for all actions in trajectories.\nthus training the neural network to predict the maximum Q value\n\nOur Objective",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "\nUse function approximators (e.g. neural networks) to generalize Value\nand Q-Value function, by using replay buffers to collect trajectories of agent interaction with\nenvironment and computing discounted reward for all actions in trajectories.\nthus training the neural network to predict the maximum Q value\n\nOur Objective",
			"lineHeight": 1.25
		},
		{
			"id": "pFIJyo0M",
			"type": "text",
			"x": 989.5773723216712,
			"y": 3546.67359088714,
			"width": 220.6409149169922,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1035094126,
			"version": 107,
			"versionNonce": 514341554,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717852037538,
			"link": null,
			"locked": false,
			"text": "Deep Q-Learning",
			"rawText": "Deep Q-Learning",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Deep Q-Learning",
			"lineHeight": 1.25
		},
		{
			"id": "VtSoSC6j",
			"type": "text",
			"x": -1179.0585914361484,
			"y": 3529.1735913051075,
			"width": 288.065185546875,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2135483250,
			"version": 129,
			"versionNonce": 674795886,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717852031888,
			"link": null,
			"locked": false,
			"text": "Deep Policy Gradient",
			"rawText": "Deep Policy Gradient",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Deep Policy Gradient",
			"lineHeight": 1.25
		},
		{
			"id": "BSMBi05m",
			"type": "text",
			"x": -1438.1555764884458,
			"y": 3576.0787774769046,
			"width": 806.2591552734375,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1804685614,
			"version": 236,
			"versionNonce": 1111503790,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717852031888,
			"link": null,
			"locked": false,
			"text": "Unlike Q-learning based which learns a determinstic value function and infers the \npolicy from it, Policy gradient learns the Policy itself",
			"rawText": "Unlike Q-learning based which learns a determinstic value function and infers the \npolicy from it, Policy gradient learns the Policy itself",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Unlike Q-learning based which learns a determinstic value function and infers the \npolicy from it, Policy gradient learns the Policy itself",
			"lineHeight": 1.25
		},
		{
			"id": "12xdGB3faoM99E6QNj3Z4",
			"type": "image",
			"x": -1124.9786642999677,
			"y": 3634.173591346553,
			"width": 179.90532984417615,
			"height": 35.18148672508334,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 786758258,
			"version": 139,
			"versionNonce": 2006552046,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717852031888,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ef73c540320202794e021a248074584c5ae5415c",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "TiHS9VEt",
			"type": "text",
			"x": -1424.1256084058357,
			"y": 3677.4498923322653,
			"width": 778.19921875,
			"height": 100,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1703687278,
			"version": 217,
			"versionNonce": 1699586094,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717852031888,
			"link": null,
			"locked": false,
			"text": "More effective in high-dimensional or continuous spaces and better convergence\nBut does not really learn a value function and cannot evaluate value\n\nOur objective measures the quality of our policy estimation",
			"rawText": "More effective in high-dimensional or continuous spaces and better convergence\nBut does not really learn a value function and cannot evaluate value\n\nOur objective measures the quality of our policy estimation",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "More effective in high-dimensional or continuous spaces and better convergence\nBut does not really learn a value function and cannot evaluate value\n\nOur objective measures the quality of our policy estimation",
			"lineHeight": 1.25
		},
		{
			"id": "0KId66jNud0JdazFpluSm",
			"type": "image",
			"x": -1257.1844486483951,
			"y": 3785.5447062775384,
			"width": 444.3168994474971,
			"height": 185.55279607608543,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1990469554,
			"version": 154,
			"versionNonce": 524642926,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717852031888,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "020e555983c85187d9bca99818f7ad5951946dd7",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "eB0TBNJ9rRxL76BOmwuOg",
			"type": "arrow",
			"x": -1130.793181133181,
			"y": 3925.909103788456,
			"width": 64.0453622954326,
			"height": 22.038282565250483,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1603209138,
			"version": 179,
			"versionNonce": 2101815666,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717852032402,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-42.74402480173376,
					4.74933608908168
				],
				[
					-64.0453622954326,
					22.038282565250483
				]
			],
			"lastCommittedPoint": [
				-80.21100950448806,
				43.79943282152999
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "uQtXkAFl",
			"type": "text",
			"x": -1355.7012810770107,
			"y": 3953.2111922536596,
			"width": 150.080322265625,
			"height": 40,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1372613870,
			"version": 108,
			"versionNonce": 1430596402,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1717852032402,
			"link": null,
			"locked": false,
			"text": "all possible actions\nat time t",
			"rawText": "all possible actions\nat time t",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "all possible actions\nat time t",
			"lineHeight": 1.25
		},
		{
			"id": "gfzWtSkpRke5jpurEGnR4",
			"type": "image",
			"x": -1300.1525263064532,
			"y": 4007.1620912549656,
			"width": 552.648678059105,
			"height": 194.3266979593876,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 363016494,
			"version": 226,
			"versionNonce": 815645550,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717852031888,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4f1e7203223ed9a1af90935397f2bb3ea08b5e6b",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "Bcx0Smfy",
			"type": "text",
			"x": -1159.4262749275354,
			"y": 3974.816948647585,
			"width": 248.80055236816406,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 934146674,
			"version": 94,
			"versionNonce": 724510126,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717852031888,
			"link": null,
			"locked": false,
			"text": "And the gradient is acquired by",
			"rawText": "And the gradient is acquired by",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "And the gradient is acquired by",
			"lineHeight": 1.25
		},
		{
			"id": "xruyBHWx",
			"type": "text",
			"x": -1369.0906964846329,
			"y": 4208.053861687291,
			"width": 668.12939453125,
			"height": 60,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 494807214,
			"version": 283,
			"versionNonce": 229396398,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717852031822,
			"link": null,
			"locked": false,
			"text": "But this is highly inefficient and has high variance because\nit requires us to sample a trajectory with its corresponding reward to compute this\npolicy estimation",
			"rawText": "But this is highly inefficient and has high variance because\nit requires us to sample a trajectory with its corresponding reward to compute this\npolicy estimation",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "But this is highly inefficient and has high variance because\nit requires us to sample a trajectory with its corresponding reward to compute this\npolicy estimation",
			"lineHeight": 1.25
		},
		{
			"id": "Ta6c0iSA",
			"type": "text",
			"x": -1174.8422986808505,
			"y": 4268.053862375693,
			"width": 279.6325988769531,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1740936110,
			"version": 85,
			"versionNonce": 165298158,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717852031888,
			"link": null,
			"locked": false,
			"text": "Alternative methods to check later",
			"rawText": "Alternative methods to check later",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Alternative methods to check later",
			"lineHeight": 1.25
		},
		{
			"id": "kzIg9KgObMFm1PrfwzsgE",
			"type": "embeddable",
			"x": -1298.022925542597,
			"y": 4307.980786072307,
			"width": 560,
			"height": 294.7126257196787,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 1135978990,
			"version": 120,
			"versionNonce": 1633860654,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717852031822,
			"link": "https://lilianweng.github.io/posts/2018-04-08-policy-gradient/",
			"locked": false,
			"scale": [
				1,
				1
			]
		},
		{
			"id": "r14Pf3A0",
			"type": "text",
			"x": -64.5885704743207,
			"y": 3536.2108354414877,
			"width": 162.00868225097656,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1676888946,
			"version": 16,
			"versionNonce": 1888580654,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717852046775,
			"link": null,
			"locked": false,
			"text": "Actor Critic",
			"rawText": "Actor Critic",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Actor Critic",
			"lineHeight": 1.25
		},
		{
			"id": "NLI-BsVvIkAz--2RO-hfl",
			"type": "image",
			"x": -169.538912065214,
			"y": 3585.3992165493755,
			"width": 394.93416481852506,
			"height": 280.9240943932395,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 324814002,
			"version": 105,
			"versionNonce": 454270446,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717852138304,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "25e52d2485be3d8bc8d272916e35decdcc46bdc1",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "NxEDMgIG",
			"type": "text",
			"x": -304.640333302553,
			"y": 3880.5116929215064,
			"width": 618.8793334960938,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1563422002,
			"version": 124,
			"versionNonce": 1708198770,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717852175237,
			"link": null,
			"locked": false,
			"text": "Simulate two networks one as an actor that learns the policy\nand another as a critic that learns the value function",
			"rawText": "Simulate two networks one as an actor that learns the policy\nand another as a critic that learns the value function",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Simulate two networks one as an actor that learns the policy\nand another as a critic that learns the value function",
			"lineHeight": 1.25
		},
		{
			"id": "nXYb7643",
			"type": "text",
			"x": -390.06028579911737,
			"y": 3930.5116926433443,
			"width": 789.71923828125,
			"height": 125,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1867688114,
			"version": 306,
			"versionNonce": 935501234,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717852404749,
			"link": null,
			"locked": false,
			"text": "Actor performs and critic evaluates and updates value function and policy\nwhich reduces variance\n\nWe can similarly formulate our object as policy gradient methods except we now\nreplace the trajectory reward with a long term value",
			"rawText": "Actor performs and critic evaluates and updates value function and policy\nwhich reduces variance\n\nWe can similarly formulate our object as policy gradient methods except we now\nreplace the trajectory reward with a long term value",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Actor performs and critic evaluates and updates value function and policy\nwhich reduces variance\n\nWe can similarly formulate our object as policy gradient methods except we now\nreplace the trajectory reward with a long term value",
			"lineHeight": 1.25
		},
		{
			"id": "dmduHuhObc6dUZyoVx5MK",
			"type": "image",
			"x": -246.7744323925717,
			"y": 4069.465856263571,
			"width": 503.1475316411509,
			"height": 104.977040321336,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 645421362,
			"version": 109,
			"versionNonce": 1297508082,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717852415135,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b8b36f34a5c3ed4c6ab0931e45612fe3debf330c",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "dUl469Er",
			"type": "text",
			"x": -14.720648802471082,
			"y": 4188.397059790032,
			"width": 39.03996276855469,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1177444334,
			"version": 21,
			"versionNonce": 1650146866,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1717852791081,
			"link": null,
			"locked": false,
			"text": "WIP",
			"rawText": "WIP",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "WIP",
			"lineHeight": 1.25
		},
		{
			"id": "eHKPRpnN",
			"type": "text",
			"x": -64.39660261849372,
			"y": 3028.0051798097247,
			"width": 14.00006103515625,
			"height": 35,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1797214258,
			"version": 4,
			"versionNonce": 216965806,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1717848540028,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "UTa62oI3",
			"type": "text",
			"x": -77.02818156586216,
			"y": 3057.873600862356,
			"width": 14.00006103515625,
			"height": 35,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 237637678,
			"version": 2,
			"versionNonce": 680859378,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1717848542591,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "64XRe7ImhLM283hsP0dTs",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "ThfX4NkC",
			"type": "text",
			"x": -461.36601473286254,
			"y": 3685.620237680693,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1655203378,
			"version": 2,
			"versionNonce": 977920046,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1717849569437,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "7DSgBbHd",
			"type": "text",
			"x": -667.2419693154179,
			"y": 3946.269385877538,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2116329074,
			"version": 2,
			"versionNonce": 1565208686,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1717851803630,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "eB0TBNJ9rRxL76BOmwuOg",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "kuGVxrKS_MLe_9uuBC0mJ",
			"type": "embeddable",
			"x": -664.9483470041823,
			"y": 4332.951770352327,
			"width": 275.9907715469828,
			"height": 61.2843214001723,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 1515055790,
			"version": 35,
			"versionNonce": 202231154,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1717852016759,
			"link": null,
			"locked": false,
			"scale": [
				1,
				1
			]
		},
		{
			"id": "JJcGrkxJ",
			"type": "text",
			"x": 139.5124949627492,
			"y": 3980.775513755512,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1230825070,
			"version": 2,
			"versionNonce": 1256243506,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1717852359261,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "Fld8QRuG",
			"type": "text",
			"x": 45.96309311959783,
			"y": 4170.859936649575,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 674601778,
			"version": 2,
			"versionNonce": 1489705774,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1717852411697,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.25
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#1e1e1e",
		"currentItemBackgroundColor": "#d0bfff",
		"currentItemFillStyle": "solid",
		"currentItemStrokeWidth": 2,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 0,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 20,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "triangle",
		"scrollX": 7921.413181915314,
		"scrollY": 4185.5591732838075,
		"zoom": {
			"value": 0.11422041263504477
		},
		"currentItemRoundness": "round",
		"gridSize": null,
		"gridColor": {
			"Bold": "#C9C9C9FF",
			"Regular": "#EDEDEDFF"
		},
		"currentStrokeOptions": null,
		"previousGridSize": null,
		"frameRendering": {
			"enabled": true,
			"clip": true,
			"name": true,
			"outline": true
		},
		"objectsSnapModeEnabled": false
	},
	"files": {}
}
```
%%