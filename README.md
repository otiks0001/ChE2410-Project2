# ChE2410-Project2

# Recreating the Modeling Process for Hydrogen Generation from Sugar and Sweet Sorghum Biomass Utilizing Ruminococcus albus

### Havard Citation for the referenced paper:
Ntaikou, I.; Gavala, H. N.; Kornaros, M.; Lyberatos, G. Hydrogen production from sugars and sweet sorghum biomass using Ruminococcus albus. Int J Hydrogen Energy 2008, 33, 1153-1163.https://doi.org/10.1016/j.ijhydene.2007.10.053

### Background

The for exploring "Hydrogen production from sugars and sweet sorghum biomass using Ruminococcus albus" lies in the pursuit of sustainable and efficient energy sources. This project aimed to replicate, and perhaps improve, the model developed in the above paper. This paper tries to leveraging the natural capabilities of Ruminococcus albus, an organism with the potential to convert sugars found in sweet sorghum biomass into hydrogen gas. Therefore, R. albus seems to be very promising for the production of hydrogen from energy crops such as sweet sorghum, with the potential of utilizing not only the free sugars but also the cellulosic/hemicellulosic biomass as well. Given the pressing need for renewable energy alternatives, investigating this biological pathway offers a promising avenue towards clean and renewable hydrogen production. Such advancements can significantly contribute to addressing energy demands while reducing carbon footprint, fostering a greener and more sustainable future. 

## Data Presentation 

The analysis was executed using the given Ordinary Differential Equations (ODEs). These specified equations, along with their corresponding variables and parameters, are visible in the following section.

The modified Monod equation (Eq. (1)) was used to calculate the growth kinetics of R. albus. This included an inhibition factor (iPh)

<p align="center">

The inhibition factor (iPh) is a function of pH according to Eq. (2)

<p align="center">

The substrate consumption rate was assumed to proceed according to Eq. (3)

<p align="center">
  
where Yx is the biomass (R. albus) yield on glucose, Umax is the maximum specific growth rate, S is the substrate concentration, Ks is the saturation constant, X is the total measured biomass concentration and 
Kd is the decay constant. The calculated values of kinetic constants the author used in designing his model are given in Table 1. However, upon careful examination and scrutiny of the paper, the author failed to provide the pHmeas value, resulting in significant challenges in estimating the iPh values and replicating the published model due to this missing information.

<p align="center">
  
The decision was made to exclusively address the experimental data concerning glucose substrate and microbial biomass in this paper, disregarding other components despite the authors presenting results and models for multiple factors. The figure provided in figure 2 illustrates the authors' model of the glucose substrate and microbial biomass to calculate the growth kinetics of R. albus. The choice not to construct a model for this specific aspect was due to the authors' model impeccably aligning with their experimental data.

<p align="center">

## Optimizing Parameters for a Model Fit

I utilized Python's 'minimize' function to conduct my model fitting, yielding divergent results from the paper's findings. Establishing correlation was challenging due to undisclosed parameters by the author, limiting the solver's attempts. Yet, the derived parameters could not generate a model akin to the one in the paper, illustrated in the subsequent chart from my analysis.

<p align="center">

Improving the accuracy of fitting our data may involve rectifying inaccuracies in initial values, a scarcity of data points, noisy data, and the absence of pH measurement values. To resolve these issues, employing precise parameters, nonlinear modifications, acquiring additional data, reducing noise, and using robust solvers can enhance the accuracy of the analysis.

## Bifurcation Analysis

Bifurcation analyses were conducted to assess the model's stability and steady state behavior. The biomass yield on glucose (Yx) was selected as the parameter for bifurcation due to its straightforward correlation with substrate consumption rate. When a curve changes direction at the origin (0,0), it indicates the potential occurrence of a system bifurcation. These bifurcation points signify critical conditions where the system's behavior undergoes qualitative changes. Investigating this bifurcation offers insights into system stability, transitions, and the potential emergence of multiple stable states or alternative behaviors, aiding in understanding underlying processes and predicting system behavior under varied conditions.

<p align="center">

The system is observed to display varied behavior, potentially adopting an alternative model shape, particularly in the vicinity of Yx near the origin (0,0). This suggests that the system's dynamics may undergo distinct changes in this region.

## Sensitivity Analysis

