# Assignment under construction!

Come back soon!

## Objective

**Due date: See the [schedule](https://ledatascifi.github.io/#schedule).** Warning: This assignment is the first project where you will have to get data, clean it yourself, and parse the data to create variables to analyze. These take time! 

Economic theory tells us that a firm's investment policy (both R&D and CAPX), in the absence of _"economic frictions"_, should equate the marginal cost (MC) of an additional unit of capital to the marginal benefit (MB) of investing that capital today. If it was true that there are no relevant frictions (but there are!) **and** we could measure the ratio of MB/MC (which is called "Marginal Q"), then we could perfectly predict investment with only Marginal Q! 

Alas, measuring Marginal Q is impossible :( , so empirical researchers interested in understanding corporate investment policies have proposed many fixes. I won't discuss these other than to say most focus on improved estimation of Marginal Q or adding additional variables to investment models. And that's the approach this assignment is going to take. 

**So today, we are going to an exploratory analysis: Are the investment choices (R&D and CAPX) a firm makes related to its technology and risks it faces?**

## Data

So, we need an annual dataset of firms with three sets of variables: (1) investment,  (2) technology, and (3) risks. I've provided the first two in (A, described below), but **you'll need to develop five measures of risk on your own using the text in firm 10-K filings.**

**A.** Provided for you: variables describing investment (CAPX and R&D, **both scaled by last year's assets, and when I say CAPX and R&D I always mean the scaled versions**) and technology (various patent measures)
  - "2007_inv_and_tech.dta", which is in the [usual place](https://github.com/LeDataSciFi/lectures-spr2020/tree/master/assignment_data)
  - This sample includes data for **2007 and 2008** fiscal years for ~200 firms
  - **This data also includes variables that will help you find the 10-K filing online**

**B.** You'll need to get: Variables describing risks a firm faces 
  - Possibilities not limited to: antitrust; litigation - e.g. patent, consumer, class action; real estate; inflation; commodity; supply chain; natural disasters; weather; employees (fraud, compensation, departure); changes in tax policy; currency rates; regulatory approval; reputation; refinancing
  - Prof. Kathleen Hanley [has a recent paper](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2792943) on risks. It focuses on financial firms, which isn't our sample, but nevertheless, it contains a long list of risks in Table 5 you might find interesting.
  - Pick a risk type (e.g. antitrust) and come up with 3 different ways to measure it from the text. 
  - Pick a second risk type and create a measure for it (you only need to do one, but you can do more)
  - Pick a third risk type and create a measure for it (you only need to do one, but you can do more)
  
Let's get started

1. Again, read the homework guidelines.
2. Click on the invitation link I sent to you and accept the assignment on GitHub. This will create a repo.
3. Clone it to your computer, a la assignment 1.
  
## What to do (big picture)

1. Download and save 10-Ks for all firms in the sample. (See the next section for more details.)
2. Loop over those files, and for each one, create your risk variables. (See the next section for more details.)
3. Explore the correlation between 2008 investment (CAPX and R&D) and 2007 technology. You should do this visually.
  - _Note: Because investment is the "outcome", we want the "inputs" to be measured before the 2008 fiscal year starts, which is why we use the prior year ("lagged") technology variables
4. Explore the correlation between 2008 investment (CAPX and R&D) and 2007 risk variables you created
5. Bonus: Explore the relationships between investment, tech, and risks simulaneously using regressions. (One regression for CAPX and one for R&D.)

## How to actually proceed and build up your code

1. Load and look at the data I've provided. Manually try to find two of the 10-Ks on the internet using the EDGAR and the variables in the dataset. Look for a pattern you can repeat in your scraper.
2. Write a function that takes a row of the dataset as an input, and saves the 10-Ks to your computer, inside the repo. 
  - Start by writing a few simple lines of code that can download a filing. Once you have that, then try to move it to a function. Go in small steps! Do not write the function all at once!
  - Save the 10-Ks to `<repo>/edgar_filings/cik_<#>/raw/<downloaded file name>`. You'll have to use the `os` package to create directories/folders as needed. 
  - You shouldn't upload these to GitHub! Instead, ask GitHub Desktop to create a "gitignore" file and add a line to that file that says: `/edgar_filings/*`. 
  - Test this function on at least 5 random rows. You can use `df.sample(5)` to pick 5 rows at random from the dataset.
  - HINT: Your function will have more than this, but this code will probably be inside the function. Replace the comments with code that does whatever the comments mention.
    ```python
    try:
      # open url with filing you want
    except:
      #you can print info about any errors you can check later
    else:
      #whatever you need to do after/if the scraper successfully loads the url
      sleep(3) # take a pause before trying another filing
    ```
  - You might add a check to only download a file if you don't already have it. 
3. When you are confident the program works, let it run on the whole dataset! Mine took about 10 minutes, and downloaded 148 files that took about 232MB on my computer. 
4. Write a function that takes a row of the dataset as an input, opens the filing in question, and creates your risk measures. Here's one (but there are many more) way to do that:
  1. Open one of the 10-Ks in Jupyter to work on. 
  2. Develop code to clean it up so that you can actually analyze the text. **More on this later.** 
  3. Only when you have this working well, turn it into a function (I called mine `extract_filing_text`) and use it on the 10-K you're practicing on.
  3. Develop code that creates your risk measures. Manually check it by opening the 10-K on the browser - do your functions give you the same values you'd create if you did it by hand?
  4. Only when you have this working well, turn it into a function (I called mine `create_risk_measures`) and use it on the 10-K you're practicing on. 
5. Now, you need to find a way to run both of these functions on every filing and then add 5 new variables to the dataset. Keep in mind that the new variables will be blank except for the 148 observations with filings. 
3. Explore the correlation between 2008 investment (CAPX and R&D) and 2007 technology. You should do this visually.
  - _Note: Because investment is the "outcome", we want the "inputs" to be measured before the 2008 fiscal year starts, which is why we use the prior year ("lagged") technology variables
4. Explore the correlation between 2008 investment (CAPX and R&D) and 2007 risk variables you created
5. Bonus: Explore the relationships between investment, tech, and risks simulaneously using regressions. (One regression for CAPX and one for R&D.)



