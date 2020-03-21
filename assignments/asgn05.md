# Our first real data science project

**PLEASE RECHECK THESE INSTRUCTIONS BEFORE SUBMITTING**

**Due date: See the [schedule](https://ledatascifi.github.io/#schedule).**

**Warning/time guidance:** This assignment is the first project where you will have to get data, clean it yourself, and parse the data to create variables to analyze. These steps take time! 

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
    - **THIS IS REALLY IMPORTANT!!!**
1. Create `NEAR_regex.py`: Download this from [here](https://github.com/LeDataSciFi/lectures-spr2020/blob/master/assignment_data/NEAR_regex.py) and copy it into your repo
1. Create `measure_risk.ipynb`: Measure risks by counting the number of times a given risk is discussed in the 10-K. [Go here for more details](asgn05_measurerisk.html).
    - creates an `output/` folder with `ccm_with_risk.dta` inside (which is the original data plus 5 new risk variables)
    - At this point, I would delete the input and edgar filings folders, then run the `download` file twice (see if it works from scratch, and if it works once it's already been run), then run the `measure_risk` file twice.
1. Create `analysis.ipynb`: Load `output/ccm_with_risk.dta` and see how **2008 investment** is related to **2007 technology and risk.** [Go here for more details](asgn05_analysis.html).
    - When you're done, restart the kernel in this file, clear the output, and make sure it works **from scratch**. This means no errors, and also check that your answers didn’t change!
1. Create `README.md`: It should 
    - Tell readers what the `py` and `ipynb` files do and the order they should be run in.   
    - Inform them if they need to `pip install` anything
    - Should note that running this code will create subfolders with approx 250MB in size
1. Finish up
      - Clean up your repo - delete extraneous files not needed by peer reviews, or if you want to keep them: move them to a "`dev`" subfolder (which is commonly known to be a place where you put files you used while developing the code). You could call this subfolder "old files" or "my files" or whatever you want. Just clean it up for your reviewers and external eyes :)
    - In Jupyter: Save all of the ipynb files.
    - In Github Desktop: "Commit" and "Push to origin"
    - github.com/ledatascifi : go to your assignment and make sure that the input and output folders are there, that the edgar filings are NOT there, that all the code and the README is there.

## Cheers!

**Give yourself a big round of applause at this point!**

Your code is probably very flexible and powerful at this point. If you have the appetite + a larger list of EDGAR files to download + a large enough hard drive + and time, then you could download more than 100GB of 10-K filings and run this analysis across 20 years of data for all publicly traded firms. 

**OOOOR**, even cooler, you are in the ball park of pulling off any analysis you want that needs to harness the power of these filings. These four studies are variously provocative, great, and (in one case) mine:
- [Claim: Identifying changes in 10-K/Q filings can generate a 20% alpha](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=1658471)
- [Prof. Hanley measured emerging risks in the financial sector](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2792943)
- [Build a unique list of competitors for each firm (really powerful!)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=1520062)
- [I used 10-K text to identify public rivals of startup firms](https://ssrn.com/abstract=3245839)

## Grading breakdown

| Part | Portion |
| :--- | :--- |
| `README.md` and repo organization | 10% | 
|  `Download_10Ks.ipynb`, `screenshot.png`, and  `.gitignore` | 35% |
| `measure_risk.ipynb` | 35% |
| `analysis.ipynb` | 20% |

## Peer review instructions

1. Click on the two invitation links I sent to you and accept the assignment on GitHub. You will have access to two peer's assignment repos.
2. **CLONE BOTH REPOS TO YOUR COMPUTER, AND RUN JUST `analysis.ipynb`. IT SHOULD WORK ON YOUR COMPUTER AS WELL!**
   - JUST THE ANALYSIS FILE!
3. After you run it, do not push any changes to the repo. Simply delete it off your computer and remove it from GitHub Desktop (click "Repository" then "Remove") so it doesn't try to update it in the future. This isn't necessary, but will save you disk space and keep GH Desktop a little tidier. 
2. Open an issue on their homework repo, copy the rubric below ([available here](https://raw.githubusercontent.com/LeDataSciFi/LeDataSciFi.github.io/master/assignments/asgn05.md)), and fill in your review there.  You can delete the "notes" I put in each row (the non-bolded explanatory parts).

## Rubric

| Evaluate | Does it? / Is it? | Yes | No | Comments - explain if no| 
| :--- | :--- | :--- | :--- |  :--- |
| `README.md` | Orients readers nicely to the repo's goal and explains how to replicate the results. | | | |
| Repo | Logically organized (subfolders for inputs and outputs), the code is in the main folder, and there are no extraneous files |  | |
| `screenshot.png` | Shows 148 files inside their `edgar_filings` folder of 100-400 MB. (The file size can vary based on some choices you make when saving the webpages. ) | | | |
| `.gitignore`  | Exists and is correct (the repo online shows no edgar files) | | | |
|  `Download_10Ks.ipynb` | Do the files all get saved to a single folder? (This is **not** what you want to do, per class discussions.) | | | |
|                        | Is this code easy to read and follow? | | | |
|                        | Are there any concerns you have with this file/code? | | | Explain if yes |
| `measure_risk.ipynb`  | Is this code easy to read and follow? | | |  |
|                       | Are there any concerns you have with this file/code? | | | Explain if yes |
|                       | Comment about how they defined the risk variables. (I.e how the word lists are set up.) Do you think they will be overly broad (lots of false positives) or overly narrow (lots of false negatives) based on how the word lists are set up? Suggest an alteration they could consider to improve their measure. | | |  |
|                   | Are you **really** impressed with how they wrote this file? (E.g. the organization of code was extremely easy to follow and understand, how they defined the dictionaries was especially thoughtful, the code goes above and beyond?) If yes, comment. | | | |
|                   | Did they measure the bonus variables? If so, which? | | | |
|  `analysis.ipynb` | Runs **on your computer** without error | | | |
|                   | Shows five risk variables with 148 observations | | | |
|                   | Put "No" if any of the search variables are always 0 | | | |
|                   | Do they show visualizations that help you see the correlation between the measures and investment? | | | |
|                   | Did they try the regression bonus? | | | |
|                        | Are you **really** impressed with the execution and presentation of results? If yes, comment.  | | | |
|                        | Is this code easy to read and follow? | | | |
|                        | Are there any concerns you have with this file/code? | | | Explain if yes |

Additional remarks:

- Some specific praise?
- Something I learned?
- Specific constructive criticism?
- Something I know and that you, my peer, might like to know because it is relevant to something you struggled with.

