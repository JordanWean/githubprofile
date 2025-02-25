---
title: Using Prism for One Factor ANCOVA Analysis
draft: false
tags:
---
 
# Forget SPSS, R, Matlab, and everything else

You can use Prism for ANCOVA. Even though it looks like you can't, I promise you can. This isn't some weird workaround either, this is the real deal. This is because ANCOVA is just a special form of `multiple linear regression` (something that Prism handles just fine).

> [!Info] Regressions
> Your standard, simple linear regression takes the form of:
`Y ~ Intercept + ßX`
>
> Where Y is your dependent variable and X is your predictor variable. ß is the slope of the line created by X and Y. 
> 
> Multiple linear regression just adds more X values. For example:
> `Y ~ Intercept + ß1X1 + ß2X2 + ß3X3`
>
> In a standard linear regression you typically think of X as being continuous. For example:
> `Food Intake ~ Intercept + ß*BodyWeight`
> 
> But X can be categorical too. The categories are turned into numerical form in a process called `dummy coding`. When you have something like genotype as an X variable, the software interprets it like this: `WT = 0, KO = 1`.
> 
> **In fact, a standard 2-way ANOVA is just a `multiple linear regression` with both X variables as categorical. It's the exact same math.**

# ANCOVA

ANCOVA is a `multiple linear regression` with two special characteristics:
1. You have both a continuous X variable and a categorical X variable
	- Typical ANCOVA terminology:
		- Continuous variable = `covariate`
		- Categorical variable = `independent variable`
2. You have `homogeneity of slopes`. 
	- In our case, this means that the effect of mass on energy expenditure is the same in all groups.


> [!warning] Assumptions
> There are other assumptions of ANCOVA too but for normal mouse data, we are less likely to violate them. Here is some more information:
> 1. [ANCOVA Assumptions: When Slopes are Unequal (theanalysisfactor.com)](https://www.theanalysisfactor.com/ancova-assumptions-when-slopes-are-unequal/)
> 2. [When Assumptions of ANCOVA are Irrelevant | by Karen Grace-Martin | Medium](https://medium.com/@kgm_52135/when-assumptions-of-ancova-are-irrelevant-c4a19593a0f5)


> [!danger] 1 factor analysis only
> This analysis only applies to data with one factor (i.e. something you might usually analyze with a t-test or one way ANOVA). When adding another factor, the homogeneity of slopes assumption is more complicated to deal with and I don't have a straight answer as to whether you need to do factor1 * covariate + factor2 * covariate or whether you'd need to include the three way interaction too.

## How to run ANCOVA in Prism

#### Create a new Multiple Variables sheet

![[Pasted image 20240718113708.png]]

#### Add data in columns as shown (it doesn't matter what order)

![[Pasted image 20240718113854.png]]

#### Click Analyze at the top and choose Multiple Linear Regression

![[Pasted image 20240718113930.png]]

#### Run first with interaction
Under "Choose Dependent (or outcome) variable (Y)", choose your energy expenditure column title. All your main effects should already be selected but you need to add your two way interaction. Either group:mass or mass:group will get you the same answer.

![[Pasted image 20240718114144.png]]

#### Check for interaction
In your results page, you have to check that the Group:Mass term is not significant. This ensures that `homogeneiety of slopes` is not violated. In this case, the p-value is 0.3071 so we are good to go.

![[Pasted image 20240718114305.png]]

#### Re-analyze without interaction term
Click the red grid at the top under Analysis to change your analysis settings. Then uncheck the Two-way interactions checkbox to leave only Main Effects checked and rerun the analysis.

![[Pasted image 20240718114530.png]]

#### Check results
Now you have your final results. Your Mass variable should be significant (meaning that energy scaled with mass). Also, in this case, the group variable was significant (p = 0.0007). This means that the grouping had a significant effect on energy expenditure after controlling for the effect of mass.

![[Pasted image 20240718114715.png]]


> [!important] Group comparisons
> If your factor contains more than 2 levels (i.e. 3 different drug groups) this method will not tell you which of the groups are different, only that one or more of them are different than others.


# Congratulations. You ran an ANCOVA in Prism.