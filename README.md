# DepC: An Open Source Pore-Network Model for Studying Trapping and Remobilization of CO2 during Geological Storage

# Introduction
This is the executable version of the modified code, built upon the *numSCAL* code originally developed by Ahmed Hamdi Boujelben (2017) at Heriot-Watt University. New features have been added into the code (in C++) to model trapping and remobilization of residual CO2 under pressure depletion conditions.

# Features


# Input data
[Cycles]
injectionSimulation=false  ---> since no further injection is performed

diffusionSimulation=true   ---> Default case

growthSimulation=true      ---> Default case
migrationSimulation=true   ---> Default case
threePhaseDepletion=false  ---> Default case: current version do not take this into account
residualState=true         ---> Default case: otherwise, a drainge and imibition cycle will be modelled first
readFromCT=true            ---> Pore occupancy data should be provided as _node3.dat and _link3.dat

[Network_Source]
source=3                  ---> Default case
extractedNetworkPath=Extracted Networks/A1/ 
rockPrefix=A1

[Parameters]
BPPressure=10             ---> in MPa
overPressure = 0          ---> not in use in the current version
depletionRate=1.034       ---> in MPa/day
depletionSteps=500        ---> Determines in how many steps depletion should proceed. 
diffusionSteps=1000       ---> A very low or high number is not recommended for convergence 
depletionTime=10          ---> in days
optimalDepletionStep=false
injectionRate=1
depletionDeltaP=2000     ---> not in use in the current version
depletionSeed=50         ---> not in use in the current version
nucleationType=1         ---> not in use in the current version
bubblesToNucleateIN=0    ---> not in use in the current version
maxCavityRadius=1        ---> not in use in the current version
minCavityRadius=0.1      ---> not in use in the current version
cavityDensity=200        ---> not in use in the current version
growthType=2             ---> do not change
solverChoice=2           ---> do not change
