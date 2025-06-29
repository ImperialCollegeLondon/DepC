# DepC: An Open Source Pore-Network Model for Studying Trapping and Remobilization of CO2 during Geological Storage

# Introduction
This is the executable version of the modified code, built upon the *numSCAL* code originally developed by Ahmed Hamdi Boujelben (2017) at Heriot-Watt University. New features have been added into the code (in C++) to model trapping and remobilization of residual CO2 under pressure depletion conditions.

# Features


# Input data
### [Cycles]

| Parameter              | Value   | Notes                                                                 |
|------------------------|---------|-----------------------------------------------------------------------|
| injectionSimulation    | false   | Since no further injection is performed                              |
| diffusionSimulation    | true    | Default case                                                          |
| growthSimulation       | true    | Default case                                                          |
| migrationSimulation    | true    | Default case                                                          |
| threePhaseDepletion    | false   | Default case; current version does not take this into account         |
| residualState          | true    | Default case; otherwise, a drainage and imbibition cycle is modeled  |
| readFromCT             | true    | Pore occupancy data should be provided as `_node3.dat` and `_link3.dat` |

### [Network_Source]

| Parameter              | Value                       | Notes                   |
|------------------------|-----------------------------|-------------------------|
| source                 | 3                           | Default case            |
| extractedNetworkPath   | Extracted Networks/A1/      |                         |
| rockPrefix             | A1                          |                         |

### [Parameters]

| Parameter              | Value    | Notes                                                                 |
|------------------------|----------|-----------------------------------------------------------------------|
| BPPressure             | 10       | in MPa                                                                |
| overPressure           | 0        | Not in use in the current version                                     |
| depletionRate          | 1.034    | in MPa/day                                                            |
| depletionSteps         | 500      | Determines number of steps for depletion                              |
| diffusionSteps         | 1000     | Very low or high values not recommended for convergence               |
| depletionTime          | 10       | in days                                                               |
| optimalDepletionStep   | false    |                                                                       |
| injectionRate          | 1        |                                                                       |
| depletionDeltaP        | 2000     | Not in use in the current version                                     |
| depletionSeed          | 50       | Not in use in the current version                                     |
| nucleationType         | 1        | Not in use in the current version                                     |
| bubblesToNucleateIN    | 0        | Not in use in the current version                                     |
| maxCavityRadius        | 1        | Not in use in the current version                                     |
| minCavityRadius        | 0.1      | Not in use in the current version                                     |
| cavityDensity          | 200      | Not in use in the current version                                     |
| growthType             | 2        | Do not change                                                         |
| solverChoice           | 2        | Do not change                                                         |

