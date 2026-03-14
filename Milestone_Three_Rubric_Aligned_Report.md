# Milestone Three Report (Rubric-Aligned)

## Course and Student
- Course: DX699 - AI for Leaders
- Student: Awais Elahi
- Milestone: Milestone Three - Exploratory Data Analysis

## Project Statement and Description
This project evaluates campaign performance drivers in the Social Media Advertising dataset, with emphasis on how exploratory analysis can guide later supervised and unsupervised modeling. The business problem is practical: identify which campaign variables are most informative for ROI, detect data quality issues before modeling, and determine whether campaign outcomes are stable enough over time for reliable comparison.

The potential impact is decision support for marketing strategy. If the analysis identifies high-value signals early, teams can prioritize channels, audience segments, and content strategies that are more likely to improve financial outcomes.

## Executive Summary
Using completed work from Weeks 5 to 7, I performed preprocessing checks, univariate analysis, bivariate analysis, and storytelling-oriented visual design. I used Social_Media_Advertising.csv as the primary dataset for milestone analysis and used class weekly notebooks as evidence artifacts.

Key findings are:
- Engagement Score has the strongest positive linear relationship with ROI among the tested numeric variables.
- Clicks and Impressions appear partially redundant because they trend together more than either relates strongly to ROI.
- Monthly average ROI shows only modest movement, suggesting relatively stable aggregate performance across the observed time period.
- Visual emphasis methods (color contrast, shading, line thickness, and annotation) materially improve interpretability and managerial focus.

## Exploratory Data Analysis: Preprocessing
### What was done
1. Parsed Date as datetime to enable monthly trend analysis.
2. Cleaned Acquisition_Cost by removing currency symbols and converting to numeric.
3. Checked basic structural quality: row count, column count, and missing-field count.
4. Reviewed category balance for Channel_Used, Campaign_Goal, and Customer_Segment.
5. Updated notebook code for pandas 3.x compatibility (using frequency ME for month-end date ranges).

### What was learned
- The advertising dataset is large (300,000 rows, 16 columns) and has no blank fields in the checked records.
- Categorical classes are broadly balanced across channels, goals, and segments, which helps reduce simple class-imbalance bias in exploratory comparisons.
- Acquisition_Cost appears highly constrained in this dataset, which may explain its near-zero linear association with ROI.

### Preprocessing concerns and risks
- Even with no blank fields, semantic data quality issues can still exist (for example, synthetic-like regularities, constrained value ranges, or omitted contextual variables such as creative quality).
- Cost representation appears limited, so cost-based inference should be treated cautiously.

## Exploratory Data Analysis: Univariate Analysis
### What was done
1. Summarized key numeric columns (mean, min, max) for Conversion_Rate, ROI, Clicks, Impressions, and Engagement_Score.
2. Examined distributions in pair-plot diagonals and histogram-style views in weekly homework.
3. Reviewed range concentration and scale differences across variables.

### What was learned
- ROI spans from 0 to 8 with a center around 3.18.
- Conversion_Rate is bounded between 0.01 and 0.15 with a narrow spread.
- Engagement_Score ranges from 1 to 10 and shows structured levels rather than continuous behavior.
- Clicks and Impressions are high-range volume variables and should be interpreted with scale awareness.

### Univariate implications
- Some variables appear discretized or constrained, which may affect assumptions in parametric models.
- Variable scaling and transformation choices will matter for later modeling and interpretation.

## Exploratory Data Analysis: Bivariate Analysis
### What was done
1. Computed correlation relationships between ROI and numeric features.
2. Produced pair plots for Conversion_Rate, ROI, Clicks, and Engagement_Score.
3. Built monthly line plots for average ROI and trend inspection.
4. Applied weekly bivariate exercises (scatter, pair plots, line/area comparisons, and highlighted time-window focus).

### Correlation summary (ROI focus)
- ROI: 1.000
- Engagement_Score: 0.355
- Clicks: 0.188
- Impressions: 0.166
- Conversion_Rate: approximately 0.000
- Acquisition_Cost: approximately -0.002

### What was learned
- Engagement quality indicators appear more informative for ROI than raw scale indicators.
- Clicks and Impressions show overlap, suggesting partial redundancy.
- No strong simple linear signal emerges from Conversion_Rate or Acquisition_Cost in this dataset.

## Data Conclusions: Expected and Unexpected Findings
### Expected
- Engagement-related variables would carry meaningful signal for ROI.
- Clicks and Impressions would show co-movement because both represent attention volume.

### Unexpected
- Conversion_Rate shows almost no linear relationship with ROI at the aggregate level.
- Acquisition_Cost contributes little pairwise linear signal, likely due to constrained value patterns in the data.

### Why this matters
These findings indicate that pairwise relationships alone are useful for screening but insufficient for causal claims. They also emphasize the need for segmentation and multivariate approaches.

## Data Conclusions: Disqualified Data
No dataset was fully disqualified at this stage. However, I treated some variables as limited for direct inference due to constrained ranges and potential structural simplification.

### Impact on analysis
- I retained the primary dataset because it is complete and analytically usable for EDA.
- I explicitly reduced reliance on any single weak-signal variable and focused on converging evidence across plots and statistics.

## Data Conclusions: Suggested Supervised and Unsupervised Analyses
### Supervised analyses suggested
1. Regression models for ROI prediction (regularized linear regression, tree-based regression).
2. Classification models for high-vs-low ROI campaigns after thresholding ROI.

### Unsupervised analyses suggested
1. Clustering campaigns by engagement, conversion, and volume behavior.
2. Dimensionality reduction (for example PCA) to identify dominant variation patterns.
3. Segment-level profiling to discover hidden campaign archetypes.

### Model selection rationale
- Mixed variable behavior and weak pairwise signals suggest interaction effects, so nonlinear supervised models should be compared with linear baselines.
- Balanced categorical structure supports segmentation and clustering without severe class dominance.

## Response to Dataset Creator Concerns and Industry Relevance
The dataset creator context implies marketing optimization and campaign effectiveness evaluation. This EDA directly supports those concerns by:
1. Identifying which variables appear most decision-relevant for ROI.
2. Flagging where naive assumptions may fail (for example, conversion alone may not explain return).
3. Demonstrating trend stability and where segmentation is needed for deeper insights.

In short, the EDA answers core industry concerns by providing practical, evidence-backed guidance on where to focus further modeling and business experimentation.

## Weekly Graphs and Homework Completion (Weeks 1 to 7 Scope)
For the Weeks completed through Week 7, notebook work includes:
- Week 5: complete bivariate graph exercises and completed homework plot generation cells.
- Week 6: completed weekly graph response, dataset EDA section, and storytelling graph.
- Week 7: completed weekly graph response, preattentive highlighting demonstration, and storytelling graph.

These notebook artifacts serve as direct evidence for the findings in this summary report.

## Communication and Visualization Strategy
To align with stakeholder communication quality criteria, visuals and explanations follow these principles:
1. State the business question before presenting the chart.
2. Use direct labels and concise captions to reduce cognitive load.
3. Highlight only the decision-relevant portion of the chart.
4. Distinguish exploratory findings from causal claims.

## Final Recommendations
1. Prioritize Engagement Score and audience-behavior features in subsequent model development.
2. Test segmented models by channel, customer segment, and campaign goal.
3. Add interaction-aware models to capture effects missed by pairwise analysis.
4. Keep report visuals focused on one message per figure to support executive decision-making.

## References
- Boston University. (2026). BU-omds-moduleB-MilestoneThree-guidelines-rubric.pdf.
- Social_Media_Advertising.csv dataset used in weekly notebooks and milestone analysis.
