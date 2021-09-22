# Demo topics

for
if-else,
factor/as.factor
Variable types
summarize & group_by
ggplot
Transforming Data
lm


Variable types
- Nominal Level: Only labels data in different categories, example categorizing as : Male or Female
- Ordinal Level: Data can be arranged and ordered but difference doesn't make sense, for example: ranking as 1st, second and 3rd.
- Interval Level: Data can be ordered as well as differences can be taken, but multiplication/division is not possible. for example: categorizing as different years like 2011, 2012 etc
- Ratio Level: Ordering, difference and multiplication/division - all operations are possible. For example: Age in years, temperature in degrees etc.

Discrete Variable: the variable can only take point values and no values in between. For example: Number of people in a bus.
Continuous Variable: the variable can take any value within an interval, for example height of a person.

# Course Topics
https://www.kaggle.com/learn/overview
https://www.kaggle.com/learn/data-cleaning

Handle missing values
Scale and normalize data
Identify and manipulate dates
Read files with encoding problems
Quickly fix typos and inconsistencies


Introduction to computational social science
Basic data analysis and visualization
Data collection

Introduction, setup, and compilation.
Basics, data preprocessing, and visualization

Model

Environment

Collection
Visualization

Challenge Forecasting votes

Part 1: Foundation
Session 01: Introduction to computational methods for social science
Session 02: Digital traces, public opinion and political behavior
Session 03: Experimental research in the digital age

Part 2: Data Collection
Session 04: Scalable data collection pipelines, APIs and databases
Session 05: Automated data preprocessing, cleaning, and visualization of big data
Session 06: Statistical modeling vs. predictive modeling

Part 4: Application & Validation
Session 10: Analytical data pipelines for textual data analysis
Session 11: Analytical data pipelines for network data analysis
Session 12: Analytical data pipelines for visual data analysis

Introduction to Analytics, Introduction to R
Basic Data Analysis	Initial Evaluation and Homework
Linear Regression	Homework
Logistic Regression
Classification and Regression Trees
Text as data methods
Clustering
Kaggle Competition








For your demo you will explore the `lm()` function.
Your goal is to answer 3 questions:
What is this function?
Why we use it?
How (live demo in RStudio)?

Here is a dataset to help you getting started.
```
data_url <- "https://github.com/mickaeltemporao/CMT4A-CMSS-TEMPLATE/raw/main/data/clean_2016.rds"
tb <- readRDS(url(data_url,"rb"))
```

Try to keep it short (~5 minutes). Also, preparation shouldn't take you more than 30 minutes.
Let me know if you are stuck or if you have any questions.




Your goal is to answer 3 questions:
What are those?
Why we use them?
How (live demo in RStudio)?

Try to keep it in under 5 minutes. Also, preparation shouldn't take you more than 30 minutes.
Let me know if you are stuck or if you have any questions.




For your demo I would like you to discuss how one can change data types in R.

You should focus mostly on these functions:
    as.numeric(), as.factor(), as.character(), as.logical()
    and how to use them with
    mutate()

Your goal will be to answer these 3 questions:
- What are those functions
- Why we use them
- How (live demo in RStudio)

Use google to find some examples.
Also this website often has lots of great applications - https://www.r-bloggers.com/

