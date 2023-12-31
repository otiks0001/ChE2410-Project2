# ChE2410-Project2

# Recreating the Modeling Process for Hydrogen Generation from Sugar and Sweet Sorghum Biomass Utilizing Ruminococcus albus

### Havard Citation for the referenced paper:
Ntaikou, I.; Gavala, H. N.; Kornaros, M.; Lyberatos, G. Hydrogen production from sugars and sweet sorghum biomass using Ruminococcus albus. Int J Hydrogen Energy 2008, 33, 1153-1163.https://doi.org/10.1016/j.ijhydene.2007.10.053

### Background

The for exploring "Hydrogen production from sugars and sweet sorghum biomass using Ruminococcus albus" lies in the pursuit of sustainable and efficient energy sources. This project aimed to replicate, and perhaps improve, the model developed in the above paper. This paper tries to leveraging the natural capabilities of Ruminococcus albus, an organism with the potential to convert sugars found in sweet sorghum biomass into hydrogen gas. Therefore, R. albus seems to be very promising for the production of hydrogen from energy crops such as sweet sorghum, with the potential of utilizing not only the free sugars but also the cellulosic/hemicellulosic biomass as well. Given the pressing need for renewable energy alternatives, investigating this biological pathway offers a promising avenue towards clean and renewable hydrogen production. Such advancements can significantly contribute to addressing energy demands while reducing carbon footprint, fostering a greener and more sustainable future. 

## Data Presentation 

The analysis was executed using the given Ordinary Differential Equations (ODEs). These specified equations, along with their corresponding variables and parameters, are visible in the following section.

The modified Monod equation (Eq. (1)) was used to calculate the growth kinetics of R. albus. This included an inhibition factor (iPh)

![](Equation1.png)

The inhibition factor (iPh) is a function of pH according to Eq. (2)

![](Equation2.png)


The substrate consumption rate was assumed to proceed according to Eq. (3)

![](Equation3.png)

![](Equation4.png)
  
where Yx is the biomass (R. albus) yield on glucose, Umax is the maximum specific growth rate, S is the substrate concentration, Ks is the saturation constant, X is the total measured biomass concentration and 
Kd is the decay constant. The calculated values of kinetic constants the author used in designing his model are given in Table 1. However, upon careful examination and scrutiny of the paper, the author failed to provide the pHmeas value, resulting in significant challenges in estimating the iPh values and replicating the published model due to this missing information.

![](Table.png)
  
The decision was made to exclusively address the experimental data concerning glucose substrate and microbial biomass in this paper, disregarding other components despite the authors presenting results and models for multiple factors. The figure provided in below illustrates the authors' model of the glucose substrate and microbial biomass to calculate the growth kinetics of R. albus.

![](Modelled.png)

I did try to construct the model for this specific aspect with their experimental data and found that it doesnt produce a good fit.

![](Model_fitting.png)

## Optimizing Parameters for a Model Fit

I utilized Python's 'minimize' function to conduct my model fitting, yielding divergent results from the paper's findings. Establishing correlation was challenging due to undisclosed parameters by the author, limiting the solver's attempts. Yet, the derived parameters could not generate a model akin to the one in the paper, illustrated in the subsequent chart from my analysis.

![](Optimized.png)

Improving the accuracy of fitting our data may involve rectifying inaccuracies in initial values, a scarcity of data points, noisy data, and the absence of pH measurement values. To resolve these issues, employing precise parameters, nonlinear modifications, acquiring additional data, reducing noise, and using robust solvers can enhance the accuracy of the analysis.

## Bifurcation Analysis

Bifurcation analyses were conducted to assess the model's stability and steady state behavior. The biomass yield on glucose (Yx) was selected as the parameter for bifurcation due to its straightforward correlation with substrate consumption rate. When a curve changes direction at the origin (0,0), it indicates the potential occurrence of a system bifurcation. These bifurcation points signify critical conditions where the system's behavior undergoes qualitative changes. Investigating this bifurcation offers insights into system stability, transitions, and the potential emergence of multiple stable states or alternative behaviors, aiding in understanding underlying processes and predicting system behavior under varied conditions.

![](Bifurcation.png)

The system is observed to display varied behavior, potentially adopting an alternative model shape, particularly in the vicinity of Yx near the origin (0,0). This suggests that the system's dynamics may undergo distinct changes in this region.

## Sensitivity Analysis

To evaluate how the model responds to different parameter changes, an investigation into each parameter's sensitivity was conducted by making slight adjustments to their values. Initially, a 1% adjustment was applied to each parameter, but the resulting models lacked clear differences. Consequently, more significant adjustments of 10% and 20% were attempted to better understand their impact. The subsequent figures showcase the outcomes of this comprehensive analysis.


![](1.png)

![](10.png)

![](20.png)

The impact of the 'ks' parameter on the system was negligible at 1% and 10%, but a significant change became evident at 20%. However, the nominal parameter remained relatively unchanged across all three analyses, showing minimal sensitivity to variations.

## Global sensitivity Analysis

**Analysis of Parameter Influence on Steady-State S Value**

The analysis aims to identify the parameters that have the most significant impact on the steady-state value of variable S. To accomplish this, a systematic approach involving the perturbation of model parameters will be employed. The parameters will be randomly adjusted within a range of ±20% for a total of 100 iterations. These alterations will be sampled from a uniform distribution to ensure diverse parameter sets. 

![](Global_1.png)
 
This process shows a comprehensive understanding of how variations in parameter values affect the steady state of S across multiple simulations. This offer valuable insights into the relative impact and sensitivity of individual parameters on the steady-state behavior of variable S.

![](global_+2.png)
  
Additionally, the Global Sensitivity Analysis also utilizes histograms that depict the distribution of parameter values. These histograms provide a visual overview of the spread and frequency of these values. Serving as visual aids, they elucidate the distribution characteristics of the parameters and contribute to a comprehensive understanding of their behavior and variability.
