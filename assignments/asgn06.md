# Assignment 6 - Prediction Models and Regressions

### Overview

**Due date: See the [schedule](https://ledatascifi.github.io/#schedule).**

I'm sure these dates will change a few times, so check back regularly...

### Let's get started

1. Again, read the [homework guidelines](guidelines-asgn.html).
2. Click on the invitation link I sent to you and accept the assignment on GitHub. This will create a repo.
3. Clone it to your computer, a la assignment 1.

## PART 1: Regression

Load the following dataset (do not change these lines at first). Variable descriptions can be found [here](https://github.com/LeDataSciFi/lectures-spr2020/tree/master/assignment_data). 

```python
url = 'https://github.com/LeDataSciFi/lectures-spr2020/blob/master/assignment_data/Fannie_Mae_Plus_Data.gzip?raw=true'
fannie_mae = pd.read_csv(url,compression='gzip')  
print(fannie_mae.info())
pd.options.display.float_format = '{:,.1f}'.format
fannie_mae.drop('Loan_Identifier',axis=1).describe().round(1).transpose()
```

### Before you start on the questions... EDA (exploratory data analysis)

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

### Questions 

Coming tonight. For now, focus on the peer reviews that are due and the EDA.

<!--
OK, now you are in a better position to think about these questions. Within the file you intend to be the "nice, pretty" submission file:
1. Write a short data section that summarizes the data for someone who has never opened it before. Answer essential questions about the dataset (observation units, time period, sample size, many of the questions above) and note any issues you have with the data (variable X has problem Y that needs to get addressed before using it in regressions or a prediction model because Z).
2.


    You can fit a regression with statsmodels or sklearn
    You can view the results visually or numerically of your model with either
    You can interpret the mechanical meaning of the coefficients in a regression
        continuous variables
        categorical a.k.a qualitative variables with two values (aka "dummy" or "binary" variables)
        categorical a.k.a qualitative variables with more than values (aka "fixed effects")
        how an interaction term changes interpretation
    You understand what a t-stat / p-value does and does not tell you
    You can measure the goodness of fit on a regression
    You are aware of common regression analysis pitfalls and disasters

-->

## PART 2: Prediction with Regression 

Coming later.

## PART 2: Prediction with Boosted Regression Trees

Coming later.


## When you're done all of these parts (How to finalize your assignment)

_Well, this is a ways away. But it will look similar to prior assignments._

<!-- 
- Your repo should be logically organized, with subfolders for inputs, outputs, and temp files (if needed). No file should be in a folder that it doesn't belong to. (No outputs in the input folder!) The code should be in the main folder.
- Clean up your repo - delete extraneous files not needed by peer reviews, or if you want to keep them: move them to a "`dev`" subfolder (which is commonly known to be a place where you put files you used while developing the code). You could call this subfolder "old files" or "my files" or whatever you want. Just clean it up for your reviewers and external eyes :)
- If you create output or temp folders, make sure your analysis file begins by deleting those folders and remaking them from scratch.
- If you need any additional inputs, download them to inputs. You don’t need to save the Fannie Mae file to your computer unless you want!
- Make sure that you refer to files with relative paths ("/input/wine.csv") and NOT absolute paths ("User/Don/Desktop/Project/input/wine.csv") because the latter won't work on anyone else's computer
- In Jupyter: Restart the kernel and clear the output
- In Jupyter: Run the entire file, and make sure it works **from scratch**. This means no errors, and also check that your answers didn’t change!
- In Jupyter: Save the file.
- In Github Desktop: "Commit" and "Push to origin"
- github.com/ledatascifi : go to your assignment and make sure everything is there
- **Edit the readme file so visitors know what the repo is doing** (like "(yada yada) ... assignment.ipynb runs the main analysis based on ... (yada yada))
-->

## Peer review instructions

_Well, this is a ways away. But it will look similar to prior assignments._

<!--
1. Click on the two invitation links I sent to you and accept the assignment on GitHub. You will have access to two peer's assignment repos.
2. **CLONE BOTH REPOS TO YOUR COMPUTER, AND RUN THEIR CODE. IT SHOULD WORK ON YOUR COMPUTER AS WELL!**
2. Open an issue on their homework repo, copy the rubric below ([available here](https://raw.githubusercontent.com/LeDataSciFi/LeDataSciFi.github.io/master/assignments/asgn03.md)), **need to update** and fill in your review there.  You can delete the "notes" I put in each row (the non-bolded explanatory parts).
-->

## Grading rubric

_Well, this is a ways away. But it will look similar to prior assignments._

<!--
See [the rubric guidelines](guidelines-peerreview.html#filling-out-the-rubric).

Remarks:

* Elaborate on above, especially for "needs work."
* Some specific praise?
* Something I learned?
* Specific constructive criticism?
* Something I know and that you, my peer, might like to know because it is relevant to something you struggled with.
-->
