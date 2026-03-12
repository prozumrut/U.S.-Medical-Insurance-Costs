# U.S.-Medical-Insurance-Costs
📈 Insurance Cost Analysis &amp; Segmentation Data-driven study of medical insurance charges using Python 🔍 Key insight: We could save $458,010 by helping just 14 people from the Smoker / Obese group quit smoking 🧪 Tools: Pandas, Seaborn, Matplotlib 📁 Includes a comprehensive PDF presentation and step-by-step data exploration in Google Colaboratory.
We can identify **lifestyle choices** and **demographic factors** as the primary predictors of medical insurance charges. The most significant finding is the overwhelming impact of smoking status on total costs.

### 1. The "Smoker" Effect: The Primary Cost Driver

The data shows a massive disparity in costs based on smoking habits:

* **Correlation:** Smoking has a high positive correlation of **0.79**, indicating it is the strongest predictor of high charges in this dataset.
* **Cost Gap:** On average, smokers are charged **\$32,050**, while non-smokers are charged only **\$8,434**.
* **Insight:** A smoker’s charges are nearly **4x higher** than those of a non-smoker. This suggests that smoking cessation programs could be the most effective way to reduce overall insurance payouts.


### 2. The Impact of Aging

While not as drastic as smoking, age remains a steady contributor to rising costs:

* **Correlation:** Age shows a moderate positive correlation of **0.30**.
* **Binned Analysis:** There is a clear "step-up" in costs as patients move through life stages:
* **Seniors** pay roughly **83% more** than **Young** adults.
* **Middle-aged** patients represent a mid-point transition, paying about **34% more** than the youngest group.

* **Insight:** The data confirms a predictable, linear increase in healthcare utilization as the population ages.


### 3. Secondary Factors: BMI and Demographics

The remaining variables play a much smaller role in determining charges:

* **BMI (0.20):** Body Mass Index has a weak-to-moderate correlation. While high BMI increases risk, it is a less consistent predictor of cost than smoking or age in this specific group.
* **Geography and Household:** Factors like **region**, **number of children**, and **sex** show near-zero correlations (all < 0.08).
* **Insight:** For this dataset, **where** someone lives or their **gender** has almost no statistical impact on what they are charged compared to **how** they live (smoking) and **how old** they are.

### Summary Table

| Factor | Strength of Impact | Key Takeaway |
| --- | --- | --- |
| **Smoking** | **Very High** | Increases charges by ~$23,600 on average. |
| **Age** | **Moderate** | Costs rise significantly between "Young" and "Senior" groups. |
| **BMI** | **Low/Moderate** | Influences costs, but less than lifestyle and age. |
| **Region/Sex** | **Negligible** | These factors are not meaningful predictors of cost. |

## Data Information

* Average age of the policyholders - 39.2
* Average yearly medical charges of the policyholders - $13 270.4
* Quick correlation and smoker impact check to inform the plan - the analysis identifies lifestyle choices and demographic factors as the primary predictors of medical insurance charges. The most significant finding is the overwhelming impact of smoking status on total costs.
* Number of men vs. women counted in the dataset - almost equal number of men and women among policyholders
* Geographical location of the policyholders - the company's clients are almost evenly distributed across all four regions, with only slightly more policyholders in the southwest.

# Project Plan
## Business Case & Context

AN Health Insurance (a fictional company) is a regional provider facing rising medical claim costs. In a competitive market, they cannot simply raise premiums across the board without losing customers to cheaper rivals. They need a data-driven approach to understand cost drivers and implement a "Risk-Based Pricing" model.
##Problem

**Problem Statement**

The organization lacks a granular understanding of why certain policyholders incur 4x higher costs than the average. Without this insight, low-risk customers are overcharged (and leaving), while high-risk customers are underpriced (causing financial "leakage").

**Size of the Problem**

Approximately 20% of the policyholder base (the high-cost segment) accounts for nearly 52% of total charges.

Based on the dataset, the average charge for a smoker (approx \$32,050) is nearly 4 times that of a non-smoker (approx \$8,434). Inaccurate pricing for just 1,000 such individuals represents a potential miscalculation of millions of dollars.

The **Core Problem**: Financial Risk and Pricing Accuracy
Insurance companies operate on the ability to predict future costs. If the organization cannot accurately estimate "charges" based on the other attributes, they face two major risks:

* Underpricing: Charging a premium that is too low to cover the actual medical claims, leading to financial loss.

* Overpricing: Charging too much and losing healthy customers to competitors, leaving the company with a "sick" (high-risk) pool of clients.

**Specific Challenges**

* The "Smoker" Multiplier: Determining exactly how much smoking increases health risk compared to non-smokers.

* BMI Thresholds: Identifying at what point Body Mass Index (BMI) creates a "cliff" where medical costs spike.

* Regional Variance: Understanding if certain regions have higher healthcare costs due to local regulations or provider networks.

## 4. Past vs. Present Approach

Past: The organization used "Community Rating," where premiums were largely based on age and region alone.

Present: They are starting to collect BMI and lifestyle data (like smoking status) but haven't integrated these into a predictive model to automate premium adjustments or wellness incentives.

## 5. Stakeholders

Internal:
 * Underwriting Team: Need the model to set accurate premiums.
 * Marketing Team: To target low-risk "healthy" segments.
 * Finance Dept: To forecast annual claim payouts.

External:
 * Policyholders: Impacted by premium changes.
 * Regulators: To ensure pricing is fair and non-discriminatory.

## Goals & Outcomes

### **Customer Segmentation** (The "Who" approach)

To segment the customer base into distinct risk profiles based on age, region, and family size to create targeted insurance products that remain competitive while maintaining the company's loss ratio.

**Goal 1**: Identify the top 3 drivers of charges and quantify their impact by the end of the sprint.

### **Predictive Modeling** (The "How Much" approach)

To develop a high-precision predictive model that estimates annual insurance charges for individual policyholders based on demographic and lifestyle variables, reducing the variance between predicted and actual costs to improve profit margins.

**Goal 2**: Develop a predictive model with an $R^2$ score of $>0.75$ to estimate individual charges.

### **Risk Factor Analysis** (The "Why" approach)

To identify and quantify the primary drivers of healthcare costs within the insured population, specifically focusing on the interaction between BMI and smoking status, to better inform risk-based premium adjustments.

**Goal 3**: Define a "High-Risk Segment" (standard threshold BMI > 30 + Smoker) and calculate the potential savings if 10% of this group joins a smoking cessation program.

### **Success Metric**:
* Feature Engineering - creating an is_obese flag for BMI > 30.

### **Constraints**:
 * Legal: Cannot discriminate based on gender in certain regions (depending on local laws).
 * Data: We lack information on specific pre-existing conditions beyond BMI.

## Actions & Interventions

Action A: Implement a "Smoker Surcharge" or a "Non-Smoker Discount." (Acted by: Underwriting. Impact: Revenue protection).

Action B: Launch a "BMI Reduction Incentive" (e.g., gym membership rebates). (Acted by: Marketing/Wellness. Impact: Long-term cost reduction).

Action C: Regional adjustment of premiums in the Southeast, where data suggests higher average charges.

Ethics: We must ensure that "High BMI" surcharges don't unfairly penalize individuals with medical conditions that prevent weight loss.

## Data Profile

Dataset source: https://www.kaggle.com/mirichoi0218/insurance

Access: 1,338 anonymized historical records.

Granularity: Individual policyholder level.

| Variable | Type | Description |
| :--- | :---: | :---: |
| **age** | int64 | 'female' 'male' |
| **sex** | object | age of policyholder |
| **bmi** | float64 | Body Mass Index |
| **children** | int64 | number of children |
| **smoker** | object | 'yes' 'no' |
| **region** | object | 'southwest' 'southeast' 'northwest' 'northeast' |
| **charges** | float64 | annual insurance charges (USD) |

Gaps: We lack "Plan Type" (Gold, Silver, Bronze) and "Actual Health Outcomes" (years lived).

Filling Gaps: We will use BMI as a proxy for general physical health.

## Analysis Types

Description: Distribution of charges across regions and age groups.

Detection: Identifying the "Smoking-Obesity" correlation (the most expensive subgroup).

Prediction: Using Linear Regression to forecast charges for new applicants.

# Step 1: Data Preparation
# Step 2: EDA (Exploratory Data Analysis)
## Outlier Detection
## Data Distribution
### What these distributions tell us about the dataset:

**1. BMI**

This is the most "well-behaved" variable. The Mean (30.66) and Median (30.40) are almost identical.

**2. Age**

We see how the bars for ages 25 to 64 are relatively flat. This is a nearly Uniform Distribution.

There is a significant spike in the "young" category (around age 18–20).

Our dataset has an **over-representation of young adults**. This is likely why the "Young" group in our previous calculation had lower average charges—they haven't had time to develop chronic conditions yet.

**3. Charges**

To analyze the distribution of 'charges', we look at the central tendency (mean/median), the spread, and the skewness. Insurance data is typically right-skewed - and this dataset confitms that, meaning most policyholders have low costs, but a few "high-risk" individuals incur very high charges.

This chart is highly right-skewed (Skewness: 1.51). Most people are clustered at the low end (under \$15,000), but a "long tail" stretches all the way to \$60,000.

This chart shows that **medical costs are not "average" for everyone**. A few high-cost individuals (likely the smokers and seniors we identified earlier) drive the mean (\$13,270) much higher than the median (\$9,382).

**The "Gap"**: In typical insurance data, we will often see a "bimodal" or "trimodal" shape. This happens because smokers or people with major health conditions form a separate peak at a much higher cost level compared to the healthy majority. However, in this dataset, we see a very slight second peak after \$30000 charges, so in this insurance company clients tend to be a healthy majority

**4. Children**

Most patients have 0, 1, or 2 children. Very few have 4 or 5.

This explains why "children" had such a low correlation with charges (0.06). Since most people have a similar number of children, it doesn't help the model distinguish between a high-cost and a low-cost patient.

## Charges, Smoker, and Age
### How smoker status increases charges

<img width="879" height="558" alt="smoker charges" src="https://github.com/user-attachments/assets/ac313ebe-34d8-4db7-84cb-d6c4e6c976ce" />

The most striking takeaway is that **smokers consistently pay more than non-smokers**.

The median charge for smokers (represented by the line inside the green box) is roughly \$35,000, whereas the median for non-smokers (the line in the orange box) is below \$10,000.

In fact, the 25th percentile for smokers is higher than the 75th percentile for non-smokers, meaning almost any smoker can expect to pay more than the vast majority of non-smokers.

Smokers (Green): There is a much wider "interquartile range" (the height of the box), indicating that insurance costs for smokers vary wildly, likely depending on age, BMI, or existing health complications.

Non-Smokers (Orange): The costs are much more concentrated at the lower end of the scale. The "whiskers" are shorter, suggesting more predictable and lower baseline costs for this group.

While the non-smoker group generally has lower costs, there are several outliers (the circles above the orange whisker) ranging from \$20,000 to nearly \$40,000.

This suggests that while non-smoking keeps costs low for most, other factors (like chronic illness or accidents) can still drive costs up to "smoker-level" prices for a small subset of individuals.

### Age, smoker status and charges relationship
<img width="1035" height="635" alt="age and charges" src="https://github.com/user-attachments/assets/8af0ae25-4b0c-4908-a44a-e5aaf1a0215f" />

This scatterplot reveals a stark and systematic relationship between age, smoking habits, and healthcare insurance charges.

We can clearly see the data splits into three distinct, upward-sloping bands:

The Bottom Band (Blue): This represents non-smokers. Their charges are the lowest and show the least variance.

The Middle Band (Mixed): This contains non-smokers with higher costs (likely due to other health factors like BMI or pre-existing conditions) and some smokers.

The Top Band (Red): This is exclusively smokers. Their charges are significantly higher, starting at a baseline that is often double or triple that of non-smokers in the same age bracket.

The Age Factor (Linear Trend)

Across all groups, there is a positive linear correlation between age and charges. As age increases, the "floor" of insurance costs rises steadily. This reflects the natural increase in health risks and medical utilization as individuals grow older.

The "Smoking Premium"

Smoking acts as a vertical multiplier. While a 20-year-old non-smoker might pay under \$5,000, a 20-year-old smoker is frequently charged between \$15,000 and \$40,000. The "gap" between the blue and red clusters represents the significant financial penalty (or risk premium) associated with smoking.

The data indicates that while age is a consistent driver of insurance costs, smoking status is the primary determinant of high-cost outliers.
 * Non-Smokers: Exhibit a highly predictable, low-variance increase in costs as they age, generally staying below the \$15,000 threshold until their late 50s.
 * Smokers: Experience a massive "step-up" in premiums. Even the youngest smokers (age 18–20) often face charges higher than the oldest non-smokers (age 60+).

There is no evidence in this dataset that the cost gap closes with age; the financial disparity between smokers and non-smokers remains wide and persistent across the entire lifespan.

### Smoker status impact

This heatmap mathematically confirms what we saw in the boxplots and scatterplots: Smoking is the single most powerful predictor of insurance costs.

1. The Strongest Predictor: Smoking Status

The most significant finding in the matrix is the correlation between smoker and charges, which stands at 0.79.
This is a very strong positive correlation, indicating that smoking is the single most influential factor in determining higher insurance premiums in this dataset.

2. Secondary Physical Factors

Two other variables show a moderate positive correlation with charges:
Age (0.30): As age increases, insurance charges tend to rise, which aligns with standard actuarial expectations.

BMI (0.20): There is a slight positive correlation between Body Mass Index and charges, suggesting that higher BMI contributes to higher costs, though less significantly than smoking or age.

3. Negligible Factors

Interestingly, some variables show almost zero correlation with insurance charges:
 * Sex (0.06) and Number of Children (0.07) have very little statistical impact on the cost of insurance in this specific model.
 * Region: All geographic regions (Northeast, Northwest, Southeast, Southwest) show correlation coefficients near zero (ranging from -0.04 to 0.07), suggesting that where a person lives has a minimal direct effect on their premiums compared to lifestyle and health factors.

4. Inter-Variable Observations
 * BMI and Region: There is a notable correlation of 0.27 between BMI and the Southeast region, indicating that individuals in this dataset from the Southeast tend to have a higher BMI than those in other regions.
 * Regional Exclusivity: The negative correlations between the various "region" variables (roughly -0.32 to -0.35) are expected, as these are  "one-hot encoded" variables (if you are in the Northeast, you cannot be in the Southwest).

# Step 3: Step-by-Step Analysis
### Segment Analysis
<img width="1223" height="558" alt="Risk Segment charges" src="https://github.com/user-attachments/assets/452f1635-247d-4cee-a9e1-44d43f30badd" />

We see that for Smoker / Obese group mean charges are almost twice hier than for Smoker / Non-Obes group and there is no such sharp difference in charges between two Non-Smoker groups.

By combining the Smoker status and the BMI threshold (>= 30), we create four quadrants of risk.

**The High-Risk Segment**

These are individuals who face both lifestyle and physiological risks. Historically, in this dataset, this group's costs are not just "higher"—they are often exponentially higher due to the interaction of respiratory and metabolic strain.

The Contrast: The average cost for a Smoker / Obese patient (\$41,558) is 4.7x higher than a Non-Smoker / Non-Obese patient (\$7,977).

Moving from "Non-Obese" to "Obese" adds only about \$866 in costs for non-smokers. However, for smokers, that same BMI increase adds over \$20,000. This suggests that obesity and smoking do not just add up—they multiply each other's risks.

The Smoker / Obese group is clearly the "High-Risk Segment." Targeted health interventions for this specific group (like weight management combined with smoking cessation) would yield the highest return on investment for an insurance provider.


**The "Potential Savings" Calculation**

To find the the potential savings if 10% of this group joins a smoking cessation program, we first identify the average cost difference between a Smoker and a Non-Smoker within the Obese category. We then apply that "avoided cost" to 10% of the high-risk population.

As a result, we see that Potential Savings if 10% (14) quit smoking: \$474,371.83 (this is actually for 14.5, not for 14 people)

If we have 145 people in the "Smoker / Obese" group and 10% (14 people) successfully join a program and quit smoking, they transition toward the "Non-Smoker / Obese" cost profile.

Savings per person: \$41,558 - \$8,843 = \$32,715
Total Savings for 14 people: \$458,010 annually.

### Regression Modeling
By using Linear Regression with a Log Transformation and an Interaction Term, we are building a **"Generalized Linear Model" strategy**.

**Log Transformation**: Because 'charges' are skewed, the log transform will "compress" the high-value outliers and "stretch" the low-value clusters. This helps the model satisfy the assumption that errors are normally distributed.

**Interaction Term (BMI X Smoker)**: As we saw in the segment analysis, the cost of being a smoker is much higher if you are also obese. A standard Linear Regression treats these as independent. By multiplying them, we create a new variable that tells the model: "If both are present, add an extra penalty."

**Interpretability**: Since we are using Linear Regression, the "Risk Score" for our dashboard will be a simple mathematical formula (Weights + Intercept) that an underwriter can easily justify.

**BMI-Smoker Interaction**

The model was trained on 1,070 records and validated on 268 records (20% split). This ensures that the accuracy score is a reflection of how the model performs on "unseen" data, rather than just memorizing the training set.

The model achieved an R2 score of 0.8170 on the test set.

This means that approximately 81.7% of the variance in the insurance charges (on a log scale) is explained by the features included in the model (Age, Sex, BMI, Children, Smoking Status, Region, and the Interaction term).

This significantly exceeds our target goal of >0.75, providing a high-confidence tool for cost estimation.

By creating the bmi_smoker_interaction feature, we have captured the non-linear relationship between health risks and lifestyle.

In medical underwriting, the risk of a high BMI is compounded significantly if the policyholder also smokes. A standard linear model treats these as separate additions; our model identifies that their combined effect is greater than the sum of its parts.

