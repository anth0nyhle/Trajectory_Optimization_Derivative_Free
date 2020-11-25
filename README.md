This C++ [Robot Operating System](https://www.ros.org/) (ROS) package utilizes the Constrained Optimization BY Linear Approximation ([COBYLA](https://nlopt.readthedocs.io/en/latest/NLopt_Algorithms/#cobyla-constrained-optimization-by-linear-approximations)) algorithm to optimally map a motion capture trajectory from the motion capture lab reference frame to the robot joint space. This mapping preserves the kinetic properties of the trajectory while minimizing the robot joint usage. The [Gradient Based Trajectory Optimization](https://github.com/klevis-a/Trajectory_Optimization_Gradient_Based) repository also provides a C++ ROS package for performing the aforementioned mapping, but utilizes the [Sparse Nonlinear OPTimizer](https://web.stanford.edu/group/SOL/snopt.htm) (SNOPT). In practice, the COBYLA-based approach outperforms the SNOPT-based optimization when the initial input guess to the optimization problem (the robot's initial joint angles) is far from optimal. However, once a close to optimal joint-space trajectory has been found, the SNOPT-based optimization outperforms the COBYLA-based optimization for minimizing joint velocity usage while satisfying joint and joint velocity limits. The details of each algorithm are described in the [associated PLOS One manuscript](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0242005).

Algorithms for pre/post optimization processing of the motion capture trajectory (augmenting, smoothing, subsampling, etc.) can be found at the [Motion Capture to Robot](https://github.com/klevis-a/Mocap_To_Robot) software repository. The user manual for this package is attached to the release (and could be different with each release). Example configuration files for the package are also attached to the release.

The corresponding Zenodo archive (see below) provides a link to the dataset that was processed via this algorithm. The dataset includes motion capture trajectories that were replicated on a M20-iA industrial robot, and the optical motion capture data that verify proper replication.

[![DOI](https://zenodo.org/badge/239802588.svg)](https://zenodo.org/badge/latestdoi/239802588)