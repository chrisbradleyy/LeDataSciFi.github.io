# `regression.ipynb`

_(It might be easier to read this file [here](https://github.com/LeDataSciFi/LeDataSciFi.github.io/blob/master/assignments/asgn06_reg.md))_

This file loads the following dataset (do not change these lines at first). Variable descriptions can be found [here](https://github.com/LeDataSciFi/lectures-spr2020/tree/master/assignment_data). 

```python
url = 'https://github.com/LeDataSciFi/lectures-spr2020/blob/master/assignment_data/Fannie_Mae_Plus_Data.gzip?raw=true'
fannie_mae = pd.read_csv(url,compression='gzip')  
print(fannie_mae.info())
pd.options.display.float_format = '{:,.1f}'.format
fannie_mae.drop('Loan_Identifier',axis=1).describe().round(1).transpose()
```

## Before you start on the questions... EDA (exploratory data analysis)

You should do the usual data exploration. Do this data exploration in a "scrap" file so you can explore quickly and messily. You'll create a "nicer" submission file later. Figure out:
- What are observations? What time does the sample cover?
- Which variables are categorical? Are any of the "number" variables actually categories in disguise?
- What values can the categorical variables take and what do they mean?
- Are there outliers or data errors in some variables?
- You should read up on what all the variables mean from the data repo. (Link is above.) 
- Visually explore the relationship between `Original_Interest_Rate` and other variables.
  - For continuous variables - take note of whether the relationship seems linear or quadratic or polynomial
  - For categorical variables - maybe try a box plot for the various levels?
  - Take notes about what you find

## Questions 

OK, now you are in a better position to think about these questions. Within the file you intend to be the "nice, pretty" submission file:
1. Write a short data section that summarizes the data for someone who has never opened it before. Answer essential questions about the dataset (observation units, time period, sample size, many of the questions above) and note any issues you have with the data (variable X has problem Y that needs to get addressed before using it in regressions or a prediction model because Z).
2. Plot the average interest rate for each year.
2. Regression \#1: **Print a summary table of the following model**

    **Model 1**: <img src="https://render.githubusercontent.com/render/math?math=r_{i,t} = \alpha %2B \beta_0 * \log(\text{Co-Borrower Credit Score}_i)%2B \beta_1 * \text{First time home buyer indicator}_i %2B \beta_2 * \text{10 year treasury rate} %2B u_{i,t}">
    <!-- that hack to put a formula in a MD file comes from https://gist.github.com/a-rodin/fef3f543412d6e1ec5b6cf55bf197d7b , and %2B is the plus sign -->
  
    where _r_ is the original interest rate for loan _i_ origined in year _t_. 
    
    **Be careful about that First Time Home Buyer variable - drop any observations where it is unknown.**

    For each  <img src="https://render.githubusercontent.com/render/math?math=\beta">, write a sentence interpreting what the coefficient means, and whether it is statistically significant (if so, to what level?).

2. Regression \#2: **Print a summary table of the following two models**

    **Model 2A**: <img src="https://render.githubusercontent.com/render/math?math=r_{i,t} = \alpha %2B \beta_0 * \log(\text{Co-Borrower Credit Score}_i) %2B \beta_1 * \log(\text{OLTV}_i) %2B u_{i,t}">
  
    **Model 2B**: <img src="https://render.githubusercontent.com/render/math?math=r_{i,t} = \alpha %2B \beta_0 * \log(\text{Co-Borrower Credit Score}_i) %2B \beta_1 * \log(\text{OLTV}_i) %2B \beta_2 \log(\text{Co-Borrower Credit Score}_i) * \log(\text{OLTV}_i) %2B u_{i,t}">

    - Interpret  <img src="https://render.githubusercontent.com/render/math?math=\beta_2"> in Model 2B, focusing on how it relates to the interpretation of the credit score variable.
    - Why did the credit score coefficient change so much between 2A and 2B?

3. If you were trying to improve the R2 of model 2A, how might you transform the credit score variable? Try at least one! Report whether the R2 went up or not. Call this **Model 3**. 
4. Regression \#2: Estimate both of these models:

    **Model 4A**: <img src="https://render.githubusercontent.com/render/math?math=r_{i,t} = \alpha %2B \beta_0 * Year %2B u_{i,t}">
  
    **Model 4B**: <img src="https://render.githubusercontent.com/render/math?math=r_{i,t} = \alpha %2B \beta_0 * (Year=1999) %2B  \beta_1 * (Year=2000) %2B ... %2B   \beta_N * (Year=2018) %2B u_{i,t}">
    
    Model 4B turns the numeric variable year into a set of what's called "fixed effects", which is a set of dummy variables, one for each value of the variable. See the lecture notes on categorical variables for more details. 
    
    - What is the R2 of models 4A and 4B? 
    - Why is one (of 4A and 4B) so much better?
    - Can you use the specification 4B in a predictive model? Why or why not?
    
**Bonus formatting trick:** This regression section results in 6 models. I reported all six in a _single_ table using 

```python
from statsmodels.iolib.summary2 import summary_col # nicer tables

# format extra stats for the regression table
info_dict={'R-squared' : lambda x: f"{x.rsquared:.2f}",
           'No. observations' : lambda x: f"{int(x.nobs):d}"}

q1 = ols().fit() # give or take ;)
... 
q4b = ols().fit() 
summary_col(results=[q1, q2a, q2b, q3, q4a,q4b],
            float_format='%0.2f',
            stars = True,
            model_names=['Q1','Q2A','Q2B','Q3','Q4A','Q4B'],
            info_dict=info_dict,
            regressor_order=[ # you can specify which variables you
            # want at the top of the table here]
           )
```

## When you're done with this

- [ ] Make sure you clean up your file for publication. Make the code and markdown headers/text easy to read and follow. 
- [ ] Clear the kernal and run all. 
- [ ] Save it.
- [ ] Commit and push it via GitHub Desktop.
