# _C. elegans_ low dimensional activity modeled by a nonlinear dynamical system with control

_C. elegans_ neural activity and its relation to behavior is difficult to characterize as both the dynamics and control are nonlinear. We propose a minimally parameterized nonlinear control model that can be fit to have the same features as those observed in the neural activity data. Nonlinear interpretable models such as this may give us insight into _C. elegans_ dynamics in ways that linear models are unable to due to the intrinsic nonlinearities in the system.

This notebook reproduces select results from the paper "Neuro-sensory integration in the nematode _C. elegans_ as a nonlinear dynamical system with control". More specifically, we implement PCA on the neural activity of a single _C. elegans_ and generate a nonlinear control model with tunable parameters that emulates the _C. elegans_ low dimensional activity.  We compare the state distributions of the data and model and quanitify goodness of fit of the model to the data by calculating the Kullback–Leibler divergence between the probability distribution functions.


## Table of contents
1. [_C. elegans_ dimensionality reduction](#Celegans)
2. [Nonlinear control model](#nonlin_control)
3. [Compare distributions](#compare_dist)



## C. elegans dimensionality reduction <a name="Celegans"></a>

![Image description](figures/PCA_Celegans.png)





## Nonlinear control model <a name="nonlin_control"></a>

This nonlinear control model is a system of stochastic differential equations with two stable fixed points and a control signal that eliminates a given fixed point in order to transition the system to the other fixed point.

<img src="figures/control_model_eq.png" width="500">

Where &sigma; is the diffusion term, &gamma; is the damping term, +1, -1, and &beta; are the fixed points of the system, and u(t) is the control signal. In order to simulate the movement between fixed points the system is hit with a control signal with average frequency &omega;. We measure the distribution of time spend in different states along the x dimension.

![Image description](figures/nonlin_control_model.png)



## Compare distributions <a name="compare_dist"></a>

![Image description](figures/KL_distributions.png)
