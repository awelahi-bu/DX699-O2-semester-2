# Milestone Three: Exploratory Data Analysis and Evaluation of Multiple Datasets

## Student and Course
- Student: Awais Elahi
- Course: DX699 - AI for Leaders
- Milestone: Milestone Three

## Abstract
This report presents a rubric-aligned exploratory data analysis for Milestone Three using completed work from Weeks 1 through 7, with emphasis on Week 5 to Week 7 notebook artifacts. The primary analytical dataset is Social_Media_Advertising.csv, which was evaluated through preprocessing, univariate analysis, bivariate analysis, trend inspection over time, and data storytelling design. The analysis indicates that engagement-oriented variables provide stronger linear signal for return on investment than raw volume variables, while some campaign metrics appear partially redundant. The findings also show that average monthly ROI is relatively stable in aggregate, supporting the dataset's use for subsequent modeling. The report maps each rubric criterion to concrete evidence and recommends supervised and unsupervised next steps.

## Project Statement and Description
The chosen project evaluates campaign-level social media performance to determine which observable attributes are most useful for understanding ROI outcomes. The industry problem is resource allocation under uncertainty: organizations must decide where to invest marketing effort without over-relying on a single metric such as impressions or clicks. The project therefore focuses on identifying data-informed indicators that are practical for managerial decision-making.

The potential impact of the project is twofold. First, it supports tactical decisions such as campaign optimization by channel and audience segment. Second, it supports strategic decisions by indicating which variables are likely to matter for deeper predictive modeling in later milestones.

## Data Sources and Scope
The primary dataset for milestone analysis is Social_Media_Advertising.csv. The file includes 300,000 rows and 16 columns, with variables including campaign metadata, engagement behavior, conversion, cost, and ROI. Weekly notebooks from Week 1 to Week 7 were also completed, and Weeks 5 through 7 were used as the main evidence base for graphing, interpretation, and communication techniques.

A secondary healthcare dataset was reviewed for context, but the social media advertising dataset was retained as the principal source because it aligns more directly with the campaign performance problem and has strong completeness for exploratory analysis.

## Exploratory Data Analysis: Preprocessing
Preprocessing tasks included parsing Date into datetime format, converting Acquisition_Cost from currency string to numeric type, and checking structural quality indicators such as row/column consistency and blank-value frequency. A missing-field check returned zero blank values across the evaluated records, improving confidence in baseline usability.

Categorical distributions were examined for Channel_Used, Campaign_Goal, and Customer_Segment. Channel and goal counts were broadly balanced, which reduces immediate risk of severe imbalance in simple exploratory comparisons. During notebook polishing, pandas 3.x compatibility was also handled by using month-end frequency code ME where required for date_range operations.

The preprocessing stage revealed one practical caution: Acquisition_Cost appears constrained in the dataset structure, which may limit direct inferential value for pairwise cost-to-ROI interpretation. This is not a disqualifying issue, but it informs downstream model feature treatment.

## Exploratory Data Analysis: Univariate Analysis
Univariate analysis summarized central tendency and spread for major numeric variables. ROI ranges from 0 to 8 with a mean near 3.18. Conversion rate is bounded between 0.01 and 0.15, while Engagement_Score ranges from 1 to 10. Clicks and Impressions occupy much larger numeric scales, indicating the need for scale-aware interpretation in charts and future models.

Distribution views in weekly graphs suggest that some variables are highly structured or discretized. This does not invalidate the dataset, but it implies that assumptions of smooth continuous behavior may be weak for certain features. For subsequent modeling, standardized scaling and robust diagnostics should be used where appropriate.

## Exploratory Data Analysis: Bivariate Analysis
Bivariate analysis used correlations, scatter plots, pair plots, and time-series line charts. The strongest observed linear association with ROI among tested numeric variables was Engagement_Score (approximately 0.355). Clicks and Impressions had weaker positive relationships with ROI (approximately 0.188 and 0.166), while Conversion_Rate and Acquisition_Cost were near zero in pairwise linear terms.

Pair-plot evidence indicates overlap between Clicks and Impressions, suggesting partial redundancy for explanatory purposes. Time-series analysis of monthly average ROI shows modest movement rather than dramatic drift, which supports broad comparability across the observed period at aggregate level.

Week 5 through Week 7 charting exercises were incorporated to validate communication quality: targeted highlighting, reduced clutter, and selective annotation were used to draw attention to decision-relevant features without overstating certainty.

## Data Conclusions: Expected and Unexpected Findings
Expected findings included co-movement of volume-based variables and a positive relationship between engagement and ROI. Unexpected findings included near-zero pairwise relationships for Conversion_Rate and Acquisition_Cost with ROI in aggregate form.

These results are meaningful because they warn against simplistic single-metric decision policies. They also demonstrate why EDA is necessary before model selection: expected business logic can hold in part, while still missing interactions that only multivariate analysis can reveal.

## Data Conclusions: Disqualified Data
No full dataset was disqualified. The primary advertising dataset remained usable based on completeness and practical relevance. However, selected variables were treated as lower-confidence standalone predictors due to constrained ranges and weak pairwise behavior.

The secondary healthcare dataset was not used as the central milestone dataset because it was less aligned to the campaign-performance industry problem addressed in this project.

## Data Conclusions: Supervised and Unsupervised Analysis Recommendations
Recommended supervised analyses include regularized linear regression and tree-based regression for ROI prediction, plus optional classification framing for high versus low ROI campaigns. Tree-based methods are recommended because interaction effects are likely and pairwise linear signals are moderate.

Recommended unsupervised analyses include clustering campaign archetypes and dimensionality reduction to identify dominant structure across behavior and outcome variables. These methods can support strategy by exposing hidden segment patterns that are not visible from aggregate metrics alone.

## Response to Dataset Creator Concerns and Industry Problem
The dataset appears designed to address campaign effectiveness and optimization questions. This EDA directly contributes to those concerns by identifying which measurable attributes are most informative, clarifying where metrics overlap, and showing where broad trend stability does or does not support straightforward comparison.

In practical terms, the analysis helps answer whether current data can guide better investment decisions. The answer is yes for exploratory prioritization, with the caveat that richer segmented and multivariate analyses are needed for stronger decision confidence.

## Weekly Graphs and Homework Assignments (Weeks 1-7 Evidence)
Week 5 homework was completed end-to-end with all required graph tasks, including corrected and generated visual references where hidden image files were absent. Week 6 included completed weekly graph response, dataset-focused exploratory analysis, and storytelling chart design. Week 7 included completed weekly response, preattentive highlighting demonstration, and storytelling comparison chart.

These notebook outputs provide direct evidence supporting the claims in this report and satisfy the requirement that weekly graphs and assignments be completed through the Milestone Three checkpoint.

## Communication and Audience Fit
The report is written for a decision-making audience and follows communication principles from Storytelling With Data: one core message per figure, selective emphasis, concise interpretation, and explicit distinction between exploratory evidence and causal claims.

This approach supports instructor communication criteria by improving clarity, coherence, and practical relevance while retaining methodological transparency.

## Final Recommendations
1. Prioritize engagement-oriented variables in baseline model development and campaign diagnostics.
2. Perform segmented analysis by channel, campaign goal, and customer segment to reduce aggregation bias.
3. Benchmark linear and nonlinear models side-by-side to evaluate interaction effects.
4. Preserve annotation-driven communication style in milestone presentations to help stakeholders quickly identify actionable findings.

## References
- Boston University. (2026). BU-omds-moduleB-MilestoneThree-guidelines-rubric.pdf.
- Social_Media_Advertising.csv. (2026). Course dataset used for exploratory analysis.
