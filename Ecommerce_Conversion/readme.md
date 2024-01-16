**Objective**
Determine the efficacy of a new web page design in driving conversions compared to the existing design.

**Approach**  
I. Probability based  
II. Hypothesis Test  
III. Regression based  

$H_a$: The new page is no better or worse than the old page.  
$H-a$: The new page is better than the old page.  

**Data Source**
1. `ab_data.csv`: file containing the A/B test results. The structure of the file is as follows
- user_id: Unique identifier for each user
- timestamp: The date and time when the user visited the page
- group: Indicates whether the user was in the control or treatment group
- landing_page: Shows the version of the page the user landed on (old_page or new_page)
- converted: Indicates whether the user converted (1) or not (0)

2. `countries.csv`: This file contains country information corresponding to each user in ab_data.csv. It helps in understanding geographical influences in the A/B test results.

**Key Insights**
1. A/B test results indicate a preference for the current web page. The conversion rate uplift with the new design was not statistically significant.  
2. Extended testing duration could potentially yield different outcomes.  

**Recommendation**  
Maintain the current web page design for now, but consider longer experimentation for a more definitive conclusion.
