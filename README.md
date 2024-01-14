# A/B Testing

-	A/B testing is a method of comparing two versions of a webpage or app against each other to determine which one performs better against a specific objective.

### Nomenclature
1. Test vs Control/Baseline
   - Control Group - group of visitors shown existing version of the web page. 
   - Test Group - group of visitors shown the new version of the web page.
   - Based on how both groups respond, we can determine if new page is better and should be launched.

2. Null & Alternate Hypothesis
- NULL: the two designs have the same efficacy, i.e. that they produce an equivalent CTR, or average revenue per user, etc.  OR There is no impact of change OR The new page is no better or worse than the old page.
- Alternate: The new page is better than the old page.

3. Metrics  
3.1 Binomial/Discrete  
   o CTR (Click Through Rate)  
   o Conversion Rate  
   o Bounce Rate  
3.2 Continuous  
   o ARPU (Average Revenue Per User)  
   o Average Session Duration  
   o Average Order Value  

- Discrete & continuous metrics require different statistical tests.  

4. Statistical Significance
- It's like a thumbs-up telling you whether the differences seen between two versions (A and B) are likely real or just due to random chance. It helps to trust that findings are meaningful and not just a fluke.
- A common method is to perform Hypothesis Test and use the t-test or its variations, depending on data distribution and assumptions.
- Statistical significance is measured by the p-value (probability of observing a t-statistic as extreme as the one computed from the sample data, assuming the null hypothesis (no difference between groups)).
- If the p-value is below a chosen significance level (commonly 0.05), it can be concluded that there's a statistically significant difference between the groups.

5. Hypothesis Test - One tailed vs Two tailed for devising Ha

| One-Tailed Test | Two-Tailed Test  |
| ------- | --- |
| Null hypothesis (H0) specifies a particular direction of the effect or difference | null hypothesis does not specify a particular direction of the effect or difference. |
| It is used when you want to test whether the sample statistic is significantly greater than or less than a population parameter, but not both. | It is used when you want to test whether the sample statistic is significantly different from a population parameter in either direction (greater than or less than). |
| Null Hypothesis (H0): The population parameter is equal to a specific value (e.g., μ = 100). | Null Hypothesis (H0): The population parameter is equal to a specific value (e.g., μ = 100). |
| Alternative Hypothesis (Ha): The population parameter is greater than or less than the specific value (e.g., μ > 100 or μ < 100). | Alternative Hypothesis (Ha): A and B have different efficacy. OR The population parameter is not equal to the specific value (e.g., μ ≠ 100). |
| ------- | --- |

6. Tests for Binomial/Discrete  vs Continuous
- Binomial/Discrete - Fisher’s exact test, Pearson’s chi-squared test
- Continuous - One tailed	Two tailed test

  ![image](https://github.com/data-craft-01/ab_testing/assets/153006864/fe15ef4b-1ee4-4eaa-a2a4-d65040edfda7)
Quick references
> Fisher’s exact test
> Pearson’s chi-squared test

### A/B testing process
1.	Understanding business problem & data - decide what to test and based on what the objective is ?  
2.	Create one or more variations of original web element.   
3.Split the website traffic randomly between two variations (i.e., we randomly allocate visitors according to some probability), and finally, collect data regarding web page performance (metrics).  
4.	Detect and resolve problems in the data (Missing Value, Outliers, Unexpected Value)  
5.	Look summary stats and plots – A/B groups  
6.	Outliers treatment  
7.	Apply hypothesis testing and check assumptions  
   • Looking at the summary statistics, the control and Test groups seem similar, but are the two groups **statistically significant**? - always investigate statistically.  
   • Check Normality & if Normal Distribution, check homogeneity.  
  	      > Test for normality - Shapiro Test  
  	      > Test for homogeneity - Levene Test  
   • Apply tests (Shapiro, Levene Test, T-Test, Welch Test, Mann Whitney U Test)  
9.	Evaluate the results, pick the variation that performed best, and cancel the one that performed poorly.  
10.	Recommend business decision to your customer/director/ceo etc.  


### Approach
1. Interpret descriptive statistics
2. Perform Hypothesis Testing
3. Z_test
4. Logistic Regression
