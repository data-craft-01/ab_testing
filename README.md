# A/B Testing

-	A/B testing is a method of comparing two versions of a webpage or app against each other to determine which one performs better against a specific objective.
-	A/B testing is a conversion rate optimization (CRO) technique that businesses use to boost conversions.

### Disclaimer !!
Please don't take data/metrics can’t at face value, could be because sample sizeis too small, so the test is not properly powered.
As a result, the effect (conversion difference) shown isn’t real orrealistic. It’s often overly exaggerated.

### Nomenclature
1. Test vs Control/Baseline
   - Control Group - group of visitors shown existing version of the web page. 
   - Test Group - group of visitors shown the new version of the web page.
   - Based on how both groups respond, we can determine if new page is better and should be launched.

2. Null & Alternate Hypothesis
- $H_0$ - Null Hypothesis: the two designs have the same efficacy, i.e. that they produce an equivalent CTR, or average revenue per user, etc.  OR There is no impact of change OR The new page is no better or worse than the old page.
- $H_a$ - Alternate Hypothesis: The new page is better than the old page.

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

4. Statistical Power (1-β)  
- Standard Best Practice: keep power at 80%
- A power of 80% or 0.80 means there's an 80% chance that, if there is an effect, accurately detecting it without error. Meaning there's only a 20% chance we'd miss properly detecting the effect.  
- statistical power 1−β, often just called power is the probability of finding an “effect,” or conversion difference between the control and variant(s), assumingthere is one.  
- The aim is to ensure to have enough power to meaningfully detect a difference in conversion rates. Therefore, a higher power is always better. But the trade-offis, it requires a larger sample size.  
- In tune, the larger the sample size, the higher your power which is part of why a large sample size is required for accurate A/B testing.  


6. Statistical Significance (α)
- Standard Best Practice: 5% or lower
- α is the false positive rate, or the percentage of time a conversion difference will be detected, even though one doesn'tactually exist.
- α = 5% means that there’s less than a 5% chance you’ll find a difference between the control and variant- when no difference actually exists. As such, you’re 95% confident results are accurate, reliable,and repeatable. Results can never actually achieve 100% statistical significance.
- It's like a thumbs-up telling you whether the differences seen between two versions (A and B) are likely real or just due to random chance. It helps to trust that findings are meaningful and not just a fluke.  
- A common method is to perform Hypothesis Test and use the t-test or its variations, depending on data distribution and assumptions.  
- Statistical significance is measured by the p-value (probability of observing a t-statistic as extreme as the one computed from the sample data, assuming the null hypothesis (no difference between groups)).  
- If the p-value is below a chosen significance level (commonly 0.05), it can be concluded that there's a statistically significant difference between the groups. 

6. Hypothesis Test - One tailed vs Two tailed for devising Ha

| One-Tailed Test | Two-Tailed Test  |
| ------- | --- |
| Null hypothesis (H0) specifies a particular direction of the effect or difference | null hypothesis does not specify a particular direction of the effect or difference. |
| It is used when you want to test whether the sample statistic is significantly greater than or less than a population parameter, but not both. | It is used when you want to test whether the sample statistic is significantly different from a population parameter in either direction (greater than or less than). |
| Null Hypothesis (H0): The population parameter is equal to a specific value (e.g., μ = 100). | Null Hypothesis (H0): The population parameter is equal to a specific value (e.g., μ = 100). |
| Alternative Hypothesis (Ha): The population parameter is greater than or less than the specific value (e.g., μ > 100 or μ < 100). | Alternative Hypothesis (Ha): A and B have different efficacy. OR The population parameter is not equal to the specific value (e.g., μ ≠ 100). |
| ------- | --- |

7. Tests for Binomial/Discrete  vs Continuous
- Binomial/Discrete - Fisher’s exact test, Pearson’s chi-squared test
- Continuous - One tailed	Two tailed test

  ![image](https://github.com/data-craft-01/ab_testing/assets/153006864/fe15ef4b-1ee4-4eaa-a2a4-d65040edfda7)
Quick references
> Fisher’s exact test
> Pearson’s chi-squared test

### A/B testing scenarios
1. Landing pages
2. Email
3. Pay-per-click (PPC) ads
4. Discover how decreasing the number of form fields in the checkout process increases purchases.
5. Discover how adding testimonials to a product page increases conversions.
6. Discover how email CTR (click-through rate) increase when adding a video thumbnail to the email body copy.


### A/B testing process
1.	Understanding business problem & data - decide what to test and based on what the objective is ?   
2.	Create one or more variations of original web element.  
3.	Calculate sample size  
  - It's recommended that test should run no longer shorter than 2 and no longer than 6 weeks to smooth out any data discrepancies.
  - It shows how many visitors are required per variant. **Anything less than this, the study won’t be properly powered. Keep the study running until this sample      is achieved.**  
  - Sample size calculations should take into account this suggested testing time period.
  - Pre-requisite  
       a. Baseline Conversion rate  
          > Current conversion rate of the control version we want to test.  
          > Google Analytics - it's available in section - Reports > Life cycle > Monetization > Ecommerce purchases > Conversion =  'Items Purchased' / 'Items Viewed'  
          > Can have a baseline conversion rate for entire website, a single page, or a single product on site.  
          > Average e-Commerce website baseline conversion rate is in the range of 2-5%, refer to this range in case the decision is stuck on what to consider.  
       b. Minimum Detectable Effect  
          > It answers - what’s the smallest conversion difference we expect to see?   
          > It's an speculative one to determine, as we haven't still tested any version & don't know the winner or loose yet.  
          > Two approaches to determine MDE to start with:  
             - i. Use historical data - look at past test results, see how they’ve performed, and plug-in the average conversion rate for those test which should provide a reasonable sense of a somewhat accurate                   MDE.
             - ii. USE AN MDE OF NO MORE THAN 2-5% - according to stats expert, Ron Kohavi, an MDE of a anythingmore than about 5% is high unlikely. Tests that appeal to get lifts of 5%+ tend to be                                  inaccurate exaggerations and can’t be trusted. Therefore, use of MDE of no more than 5%. However, anything less than about 2% isn’t really worthtesting, so 2% should be the minimum threshold.

    
             - Two Type of MDE - Absolute or Relative  
             - i. Absolute MDE - actual raw number difference between theconversion rates of the control and variant. Using this sample size requirements appear to be way less, but that could be a trap. What it                    means is, you need to see a raw 5% conversion lift,for example 0.96% to 5.96%, which is quite difficult to achieve.
             - ii. Relative MDE: the % difference between the baseline conversion rate and the MDE of the variant. Using this the sample size requirements appear a lot higher, but are much more realistic because                    you’re only lifting the conversion rate arelative amount. For example, from 0.96% to 1.01%.
                   In general, **_business takeholders are used to seeing a relative percentage lift_**, so it’s typically best to use a relative percentage calculation and report results this way.  
4. **General Sense Check**  
    - In general, to run a properly-powered study, based on anaverage eCommerce conversion rate of 2-5%, with areasonable MDE also at 2-5%, the smallest sample size required  is at least 120,146 visitors, per variant. And , the more variants you test, the more visitors you need.
    - Trustworthy testing is really best achieved by large, enterprise-level sites with huge amounts of traffic of atleast (120,000 for version A + 120,000 for version B) =240,000 visitors within a 2-6 week time period.  
3.Split the website traffic randomly between two variations (i.e., we randomly allocate visitors according to some probability), and finally, collect data regarding web page performance (metrics).  
5.	Detect and resolve problems in the data (Missing Value, Outliers, Unexpected Value)  
6.	Look summary stats and plots – A/B groups  
7.	Outliers treatment  
8.	Apply hypothesis testing and check assumptions  
   • Looking at the summary statistics, the control and Test groups seem similar, but are the two groups **statistically significant**? - always investigate statistically.  
   • Check Normality & if Normal Distribution, check homogeneity.  
  	      > Test for normality - Shapiro Test  
  	      > Test for homogeneity - Levene Test  
   • Apply tests (Shapiro, Levene Test, T-Test, Welch Test, Mann Whitney U Test)  
9.	Evaluate the results, pick the variation that performed best, and cancel the one that performed poorly.  
10.	Recommend business decision to your customer/director/ceo etc.  


### Approach
1. % Change based
2. Probability based
3. Hypothesis Test
4. Regression based

### Best practices
1. Only test one variable at a time (Split Testing approach).
2. Split your groups equally and randomly.
3. Test early and test often for the best results.
4. Test as large a sample as you can for more accurate results.
5. Trust the data collected, not gut instinct.


### % Change based - Deriving & interpreting results  
1. Calculate conversion rates for each variant with formula:   
Conversion Rate = $\frac{Conversions}{Views}$ X 100  
 
For example, for 90 conversions and 1,000 views:   
Conversion Rate = $\frac{90}{1000}$ X 100 = 9%  
 
2. Derive percentage differences between the two conversion rates as follows:  
% Difference = $\frac{(larger - smaller)}{smaller}$ X 100  
 
For example, if Test A converted at 9% and Test B converted at 12%:  
 % Difference = $\frac{(12 - 9)}{9}$ X 100 = 33% difference  

This means that **Test B converted 33% better than Test A.**   
Generally speaking, **anything higher than a 5% difference counts as statistical significance.**  
