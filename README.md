# BIOST 505 
# WRITING, PRESENTATION, AND COLLABORATION SKILLS FOR BIOSTATISTICS  
Winter 2022 
Instructor: Marco Carone  

## HOMEWORK 2 
 
1. In this exercise, you will perform a simulation study to investigate the impact of subgroup mining, a type of p-
hacking, on type I error control. Subgroup mining occurs, for example, when an analyst looks through a list of 
patient covariates (e.g., age, sex, blood type) to identify covariates associated with a particular patient 
outcome, and then reports such covariates without accounting for the search process. Such analysis is 
expected to result in an inflation of type I error, with the severity of inflation depending on the number of 
covariates examined. 
 
 In your simulation, you will generate 50,000 random datasets, each containing data for n=200 patients. To 
create a single random dataset, for each patient i=1,2,...,200, generate independently: 
 
- (i) an outcome Yi drawn from the standard normal distribution; 
- (ii) independent covariates Xi1, Xi2, ..., Xi10 each drawn from a Bernoulli distribution with success 
probability 0.5. 
   
 Observe that, by design, in the setting of this simulation, none of the covariates are truly (i.e., at the 
population level) associated with the outcome. 
 
 For any single random dataset generated, perform the following analysis: 
 
- (i) for each of the 10 covariates, record the p-value from a t-test comparing the mean outcome in those 
with covariate value 1 versus 0; 
- (ii) for each k=1,2,...,10, compute the smallest among the first k p-values obtained and denote it by sk. 
 
 Observe that, for each k=1,2,...,10, step (ii) is meant to mimic a situation in which the analyst is looking at the 
marginal association between the outcome and each of k covariates and then reporting the ‘most significant’ 
p-value found among the k hypothesis tests conducted. 
 
 For each k=1,2,...,10, compute the proportion qk of times that sk < 0.05 (i.e., a significant association is found 
for any of the first k covariates) across 50,000 randomly generated datasets. 
 
 Produce a plot of qk versus k and interpret the trend you see in a single sentence. Submit both your plot and 
the (carefully commented) code you used to produce it. 
 
 Note: If you wish, you may make use of the R code (phackingexample.R) provided for the p-hacking simulation 
summarized on slide 6 of Chapter 2. 
