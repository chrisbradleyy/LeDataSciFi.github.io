# Our first real data science project

**PLEASE RECHECK THESE INSTRUCTIONS BEFORE SUBMITTING**

**Due date: See the [schedule](https://ledatascifi.github.io/#schedule).**

## Project Set Up

Your boss explains that she needs an exploratory analysis done. Her full explanation about why you're doing this is [here](asgn05_obj.html). The nuts and bolts of the set up are: 

1. Question: Are the investment choices (R&D and CAPX) a firm makes related to its technology and risks it faces?
1. Data you have - You are given [data on investment in R&D and CAPX and technology](https://github.com/LeDataSciFi/lectures-spr2020/tree/master/assignment_data) for **2007 and 2008** fiscal years for ~200 firms
1. Data you need - Variables describing the risk a firm faces. The data above has information that will help you find 10-K filings for firms in the sample, and using this, you will create the risk variables. 

## Let's get started

1. Again, read the homework guidelines.
2. Click on the invitation link I sent to you and accept the assignment on GitHub. This will create a repo.
3. Clone it to your computer, a la assignment 1.

## Your assignment should create the following files

1. `download_10Ks.ipynb`: Download the 10-K filings for the sample firms. [Go here for more details](asgn05_download.html).
    - creates an input folder with the original dataset inside
    - creates an `edgar_filings` folder with all the files inside
1. `.gitignore` and `screenshot.png`: [Go here for more details](asgn05_gitignore.html).
1. `NEAR_regex.py`: Download this from [here](https://github.com/LeDataSciFi/lectures-spr2020/blob/master/assignment_data/NEAR_regex.py) and copy it into your repo
1. `parse_10ks.ipynb`: Measure risks by counting the number of times a given risk is discussed in the 10-K.
    - creates an output folder with the analysis dataset inside
1. See how **2008 investment** is related to **2007 technology and risk.**







## Rubric

`Download_10Ks.ipynb` - ...............
`.gitignore` - exists and is correct (the repo online shows no edgar files)
`screenshot.png` - shows 148 files inside their `edgar_filings` folder of 100-400 MB. The file size can vary based on some choices you make when saving the webpages. 
