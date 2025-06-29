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
| extractedNetworkPath   | Extracted Networks/A1/      | Change accordingly      |
| rockPrefix             | A1                          | Change accordingly      |

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

### [Fluids]

| Parameter                   | Value         | Notes |
|----------------------------|---------------|-------|
| pressureDependentDataPath  | Pressure Data/| Change accordingly      |
| waterDiffusionCoef         | 3.5           |       |
| overrideWithFixedData      | false         |       |
| initialWaterSaturation     | 0             |       |
| initialTemperature         | 333.15        | in Kelvin |
| waterDistribution          | 1             | Not in use      |
| IrreducibleWaterSaturation | 0.0           | For drainage     |
| SwirrD                     | 0.0           | For depletion     |

### [Misc]

| Parameter                         | Value     | Notes |
|----------------------------------|-----------|-------|
| gravity                          | true      |       |
| g                                | 9.8       |       |
| viscousForces                    | false     |       |
| PinViscous                       | 0         |       |
| PoutViscous                      | -10000    |       |
| relativePermeabilitiesCalculation| true      |       |
| depVideoRecording                | true      |       |
| FramePerSecond                   | 24        |       |
| twoPhaseSimulationSteps          | 1000      |       |
| capillaryLimit                   | 10        |       |
| capillaryIncrement               | 0.01      |       |
| irreSwInEffect                   | false     |       |
| nonIdealGas                      | false     |       |
| videoRecording                   | true      |       |
| OstwaldRipening                 | true      |       |
| restSim                          | true      |       |
| restTime                         | 2         | in days |
| skipDepletion                    | false     |       |
| initializePc                     | false     |       |
| checkPC                          | false     |       |
| extendDepletion                  | false     |       |
| imbibeWater                      | true      |       |
| stopAfterBreakthrough            | false     |       |
| noSnapOff                        | false     |       |
| extractData                      | true      |       |
| filmConductanceResistivity       | 100       |       |
| MW                               | 0.044     | Molar mass, kg/mol |
| equilibriumThreshold             | 0.001     |       |
| thresholdCount                   | 100       |       |

### [Network_Wettability]

| Parameter                | Value   | Notes |
|-------------------------|---------|-------|
| wettabilityFlag         | 1       | Water wet, 6 for mixed wet (in future release)      |
| minWaterWetTheta        | 40      | degrees |
| maxWaterWetTheta        | 40      | degrees |
| minGasWetTheta          | 120     | degrees |
| maxGasWetTheta          | 120     | degrees |
| gasWetFraction          | 0.5     | For mixed wet      |
| wettabilityDistributionFlag | uniform | Or normal   |
| normalWetMu             | 45      | degrees |
| normalWetSigma          | 5       | degrees |
| minRecedingTheta        | 0       | degrees |
| maxRecedingTheta        | 10      | degrees |
| minAdvancingTheta       | 60      | degrees |
| maxAdvancingTheta       | 60      | degrees |
| wettabilityHys          | false   |       |
| wettabilityHysTheta     | 10      | degrees |
| dynamicWettability      | false   |       |

### [NetworkGeneration_Geometry]
This is for generating networks
| Parameter                  | Value  | Notes |
|---------------------------|--------|-------|
| Nx                        | 200    |       |
| Ny                        | 200    |       |
| Nz                        | 1      | 2D network |
| minRadius                 | 1      | units assumed consistent |
| maxRadius                 | 30     |       |
| radiusDistribution        | 4      | Likely enum for distribution type |
| rayleighParameter         | 10     |       |
| triangularParameter       | 10     |       |
| normalMuParameter         | 9      |       |
| normalSigmaParameter      | 6      |       |
| poreVolumeConstant        | 12     |       |
| poreVolumeExponent        | 0.5    |       |
| poreConductivityConstant  | 1      |       |
| poreConductivityExponent  | 4      |       |
| coordinationNumber        | 3.65   | Average per pore |
| degreeOfDistortion        | 0.3    |       |
| aspectRatio               | 1.5    |       |
| length                    | 100    | units assumed consistent |
| seed                      | 50     | Random seed |
| solverChoice              | 1      |       |
| absolutePermeabilityCalculation | true |  |
| extractData               | false  |       |
