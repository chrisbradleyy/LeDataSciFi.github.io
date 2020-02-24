# Our first real data science project

**Due date: See the [schedule](https://ledatascifi.github.io/#schedule).**

**Warning/time guidance:** This assignment is the first project where you will have to get data, clean it yourself, and parse the data to create variables to analyze. These steps take time! 
- Using the materials from our lectures on "Getting Data From the Web", try to have the [first three steps](#how-to-actually-proceed-and-build-up-your-code) done before next week.
- Steps 4 and 5 build off the lectures on "Parsing Text Documents". They will probably take time because they require creativity and you will have to iterate on ideas to find something that works and is interesting. 

## Objective

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
  - Open one of the 10-Ks in Jupyter to work on. 
  - Develop code to clean it up so that you can actually analyze the text. **More on this later.** 
  - Only when you have this working well, turn it into a function (I called mine `extract_filing_text`) and use it on the 10-K you're practicing on.
  - Develop code that creates your risk measures. Manually check it by opening the 10-K on the browser - do your functions give you the same values you'd create if you did it by hand?
  - Only when you have this working well, turn it into a function (I called mine `create_risk_measures`) and use it on the 10-K you're practicing on. 
5. Now, you need to find a way to run both of these functions on every filing and then add 5 new variables to the dataset. Keep in mind that the new variables will be blank except for the 148 observations with filings. 
6. Analysis. Present you findings visually and follow the lessons on effective visualization!
  - Explore the correlation between 2008 investment (CAPX and R&D) and 2007 technology.
    - _Note: Because investment is the "outcome", we want the "inputs" to be measured before the 2008 fiscal year starts, which is why we use the prior year ("lagged") technology variables
    - You should write brief summaries of your findings.
  - Explore the correlation between 2008 investment (CAPX and R&D) and 2007 risk variables you created
    - You should write brief summaries of your findings.
  - Bonus: Explore the relationships between investment, tech, and risks simulaneously using regressions. (One regression for CAPX and one for R&D.)

## When you're done (this section is different than last time!)

- Your repo should be logically organized, with subfolders for the EDGAR filings, inputs (the CCM file I gave you, and anything else you download to use), outputs (if you create any), and temp files (if your parser creates intermediate files, put them here). No file should be in a folder that it doesn't belong to. (No outputs in the input folder!) The code should be in the main folder. 
  - If you create output or temp folders, make sure your analysis file begins by deleting those folders and remaking them from scratch. (Don't delete the EDGAR filings subfolder though! That's an "input".) 
  - Clean up your repo - delete extraneous files not needed by peer reviews, or if you want to keep them: move them to a "`dev`" subfolder (which is commonly known to be a place where you put files you used while developing the code). You could call this subfolder "old files" or "my files" or whatever you want. Just clean it up for your reviewers and external eyes :)
- **Edit the readme file so visitors know what the repo is doing** (like "(yada yada) ... assignment.ipynb runs the main analysis based on ... (yada yada))
  - You should inform them if they need to `pip install` anything
  - You should note that running this code will create subfolders with approx 250MB in size
- Make sure that your code only refers to files with relative paths ("/input/wine.csv") and NOT absolute paths ("User/Don/Desktop/Project/input/wine.csv") because the latter won't work on anyone else's computer
- In Jupyter: Restart the kernal and clear the output
- In Jupyter: Run the entire file, and make sure it works **from scratch**. This means no errors, and also check that your answers didn’t change!
  - When I do this, my code doesn't attempt to redownload any files I already have, so this is actually fast
- In Jupyter: Save your assignment file.
- In Github Desktop: "Commit" and "Push to origin"
- github.com/ledatascifi : go to your assignment and make sure everything is there

## Cheers!

**Give yourself a hug round of applause at this point!**

Your code should be really flexible now. If you have the appetitie + a larger list of EDGAR files + a large enough hard drive + and time, then you could download more than 100GB of 10-K filings and run this analysis across 20 years of data for all publically traded firms. 

Or, you could do any analysis you wanted that focused in part on the 10-Ks of firms. Some great ones:
- [Claim: Identifying changes in 10-K/Q filings can generate a 20% alpha](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=1658471)
- [Prof. Hanley measured emerging risks in the financial sector](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2792943)
- [Build a unique list of competitors for each firm (really powerful!)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=1520062)
- [I used 10-K text to identify public rivals of startup firms](https://ssrn.com/abstract=3245839)

## Peer review instructions

1. Click on the two invitation links I sent to you and accept the assignment on GitHub. You will have access to two peer's assignment repos.
2. **CLONE BOTH REPOS TO YOUR COMPUTER, AND RUN THEIR CODE. IT SHOULD WORK ON YOUR COMPTUER AS WELL!**
3. After you run it, do not push any changes to the repo. Simply delete it off your computer and remove it from GitHub Desktop (click "Repository" then "Remove") so it doesn't try to update it in the future. This isn't necessary, but will save you disk space and keep GH Desktop a little tidier. 
2. Open an issue on their homework repo, copy the rubric below ([available here](https://raw.githubusercontent.com/LeDataSciFi/LeDataSciFi.github.io/master/assignments/asgn03.md)), and fill in your review there.  You can delete the "notes" I put in each row (the non-bolded explanatory parts).

## Grading rubric

Coming soon!
