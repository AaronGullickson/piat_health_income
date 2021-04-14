# Data Source Description

The data we will use is extracted from the [National Health Interview Survey](https://www.cdc.gov/nchs/nhis/index.htm) (NHIS) from 2017. The NHIS is a national survey of Americans that is conducted every year by the National Center for Health Statistics, which is part of the Centers for Disease Control and Prevention. It is one of the major national surveys of health and health behaviors collected at the national level. We are using the full sample from 2017 but only a small extract of the many variables available.  

From the full data, I have extracted and recoded the following variables for our use as an analytical dataset. To load this dataset in R, you just need to run the setup code chunk in the full_report.Rmd R Markdown document. The name of the dataset in R is `nhis`. 

* **age**: The age of the respondent in years.
* **gender**: The gender of the respondent. Currently the NHIS does not include non-binary categories, so the only categories are male and female.
* **mar_stat**: The marital status of the respondent in the categories of married, never married, divorced/separated, and widowed.
* **race**: The self-reported race of the respondent. To keep our analysis manageable, the categories have been collapsed into the categories of white, Latino, black, Asian, American Indian/Alaska Native, and Other/Multiple Races. This is the key contextual variable.
* **us_born**: This variable indicates whether the respondent was born in the US or not.
* **high_degree**: The highest educational degree of the respondent, in the categories of no high school diploma, high school diploma, associate's degree, bachelor's degree, and graduate degree.
* **family_income**: The NHIS reports the family income of the respondent in brackets: $0-34,999, $35,000-49,999, $50,000-74,999, $75,000-99,999, and $100,000 and over. This is the key independent variable.
* **health_cat**: Respondents were asked to rate their own health in the following categories: poor, fair, good, very good, and excellent. This is the key dependent variable, along with the `health_score` variable.
* **health_score**: For the linear models, we need a quantitative dependent variable. So, I have converted the `health_cat` variable into a score that goes from 0 (poor) to 4 (excellent). So a one unit increase here means moving up one category on the ordinal scale. This will be the key dependent variable for the linear models. 