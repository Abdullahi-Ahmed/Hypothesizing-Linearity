# Hypothesizing-Linearity
What if I told you that I can show you how ease it is the understand hypothesizing linearity with few python lines and logic calculation on understanding it?
![image](https://user-images.githubusercontent.com/85021780/132937242-e9029126-879a-4830-9f51-c73d60602928.png)  
Before we begin I am assuming you know what hypothesis is, Type I & type II errors, incase you forget this can help  
**type I error** - is like convicting an innocent person  
**type II error** - is like failing to convict a guilty person  
for more check our this blog https://towardsdatascience.com/hypothesis-testing-decoded-for-movers-and-shakers-bfc2bc34da41  
Now that we cleared the base of hypothesis what is linearity? in wikipedia  Linearity is the property of a mathmatical relationship that can be graphically represented as a straight line.  
       in my know definition "is a straight-line relationship given values"  
         
To test linearity of a given value we start assume that there is approximately a linear relationship between X and Y (in this example we will use X to represent Unemployment rate and Y the Weekly Sales). Mathematically we express this as  
     Y ≈ β0 + β1X
     
    Weekly Sales = β0 + β1 x Unemployment
    
β0 is the slope of the straight line while  β1 is the y intercept when x is zreo they are called coefficients or paramteres. In practice the coefficients are unknown. so before we make the decision we must have to estimate or solve of the coefficients. Lucky us we can use this formula given the values of x & y (Weekly Sales & Unemployment)
**β0 =** 
![linear-regression-formula](https://user-images.githubusercontent.com/85021780/132938787-dfbe16fe-61a9-4ff1-99d6-124b9a026636.png)
**β1 =**
![linear-regression-formula2](https://user-images.githubusercontent.com/85021780/132938862-37addc7d-a086-48f4-8e81-8473ea250ae7.png)

The most Staright- forward expanation is to test given the computed best estimate of the cofficients from the above fomula
H0 : β1 = 0
versus 
Ha : β1 $\neq$  0,  
if β1 = 0 then the equation will reduce to  
     Weekly Sales = β0 + (0 x Unemployment)
     Weekly Sales = β0  
     Thus Weekly Sales is not associated with Unemployment.
     
   
To Test for null hypothesis, we have to determine whether our estimate β1 is sufficiently far from zero that we can be confident that β1 is non-zero thus there's linear relationship between Weekly Sales and Unemployment.  
**So how far is far?**
This will depends on the accuracy of the estimated β1, We can measure the accuracy of the estimted β1 and check the error SE(βˆ1). If SE(βˆ1) is
small, then even with a relatively small values of βˆ1 may provide strong evidence that β1 $\neq$ 0, and hence that there is a relationship between Weekly Sales and Unemployment. In contrast, if SE(βˆ1) is large, then βˆ1 must be large in absolute value in order for us to reject the null hypothesis. In practice, we compute a t-statistic, t-statistic
given by
![image](https://user-images.githubusercontent.com/85021780/132939780-ab9dd3e7-ee26-410a-86ab-907f0c5f5c87.png)

which measures the number of standard deviations that βˆ1 is away from
0. If there really is no relationship between X and Y , then we expect
that (3.14) will have a t-distribution with n − 2 degrees of freedom. The tdistribution has a bell shape and for values of n greater than approximately
30 it is quite similar to the normal distribution. Consequently, it is a simple
matter to compute the probability of observing any number equal to |t| or
larger in absolute value, assuming β1= 0. We call this probability the p-value.  
 prebetween the predictor and the response. Hence, if we see a small p-value,
Roughly speaking, we interpret the p-value as follows: a small p-value indicates
t

then we can infer that there is an association between the predictor and the
response. We reject the null hypothesis—that is, we declare a relationship
to exist between X and Y —if the p-value is small enough. Typical p-value
cutoffs for rejecting the null hypothesis are 5 or 1 %.
