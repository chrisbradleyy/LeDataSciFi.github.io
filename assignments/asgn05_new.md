# Our first real data science project

**PLEASE RECHECK THESE INSTRUCTIONS BEFORE SUBMITTING**

**Due date: See the [schedule](https://ledatascifi.github.io/#schedule).**

## Project Set Up

Your boss explains that she needs an exploratory analysis done. Her full explanation about why you're doing this is [here](asgn05_obj.html). The nuts and bolts of the set up are: 

1. Question: Are the investment choices (R&D and CAPX) a firm makes related to its technology and risks it faces?
1. Data you have - You are given [data on investment in R&D and CAPX and technology](https://github.com/LeDataSciFi/lectures-spr2020/tree/master/assignment_data) for **2007 and 2008** fiscal years for about 200 firms
1. Data you need - Variables describing the risk a firm faces. The data above has information that will help you find 10-K filings for firms in the sample, and using this, you will create the risk variables. 

## Let's get started

1. Again, read the homework guidelines.
2. Click on the invitation link I sent to you and accept the assignment on GitHub. This will create a repo.
3. Clone it to your computer, a la assignment 1.

## Steps to complete the assignment

1. Create `download_10Ks.ipynb`: Downloads the 10-K filings for the sample firms. [Go here for more details](asgn05_download.html).
    - creates an `input/` folder with the original dataset inside
    - creates an `edgar_filings/` folder with all the files inside
1. Create `.gitignore` and `screenshot.png`: [Go here for more details](asgn05_gitignore.html).
1. Create `NEAR_regex.py`: Download this from [here](https://github.com/LeDataSciFi/lectures-spr2020/blob/master/assignment_data/NEAR_regex.py) and copy it into your repo
1. Create `measure_risk.ipynb`: Measure risks by counting the number of times a given risk is discussed in the 10-K. [Go here for more details](asgn05_measurerisk.html).
    - creates an `output/` folder with `ccm_with_risk.dta` inside (which is the original data plus 5 new risk variables)
    - At this point, I would delete the input and edgar filings folders, then run the `download` file twice (see if it works from scratch, and if it works once it's already been run), then run the `measure_risk` file twice.
1. Create `analysis.ipynb`: Load `output/ccm_with_risk.dta` and see how **2008 investment** is related to **2007 technology and risk.** [Go here for more details](asgn05_analysis.html).
1. Create `README.md`: It should 
    - Tell readers what the `py` and `ipynb` files do and the order they should be run in.   
    - Inform them if they need to `pip install` anything
    - Should note that running this code will create subfolders with approx 250MB in size
    






## Rubric

Coming soon!

<!--
`README.md`
`Download_10Ks.ipynb` is correct
    - the path to the 10k files is `edgar_filing/cik_<#>/` and then sensible subfolder
    - `screenshot.png` - shows 148 files inside their `edgar_filings` folder of 100-400 MB. The file size can vary based on some choices you make when saving the webpages. 
    - `.gitignore` - exists and is correct (the repo online shows no edgar files)


`analysis.ipynb`
- runs
- describe - 148 obs for each variable, not all 0
--!>
