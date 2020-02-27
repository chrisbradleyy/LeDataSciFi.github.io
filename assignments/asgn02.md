# Assignment 2 - Golden Pandas

## Overview

**Due date: See the [schedule](https://ledatascifi.github.io/#schedule).**

Let's practice the golden rules and flex our new panda muscles. We will:

1. Use two datasets with different observation  levels
2. Calculate and analyze the distribution of returns at the daily, monthly, and annual level, both overall and for subsamples
3. Keep the golden rules in mind, both within our code and within our repo.

## Let's get started

1. Again, read the [homework guidelines](guidelines-asgn.html).
2. Click on the invitation link I sent to you and accept the assignment on GitHub. This will create a repo.
3. Clone it to your computer, a la assignment 1. 

Now we are ready to do some science. Instead of describing the next step, let's work _backwards_.

## What should your final product look like?

1. Your repo should be logically organized, with subfolders for inputs, outputs, and temp files (if needed). No file should be in a folder that it doesn't belong to. (No outputs in the input folder!)
2. Your code, in this case, should be in the main repo folder (not a subfolder). It should:
	1. Start by **deleting** the temp and output folders if they exist, then create new temp and output folders. 
	2. If you need any additional inputs, download them to inputs. If the file already exists, skip the download.
	3. Only then, conduct your the analysis as described below.
	
_Note: In all assignments, it may or may not make sense to save temp (intermediate) and output files. Do so if you think it's worth it. For example, saving temp files can make resuming the study easier in the future if you take a break, and saving outputs may be important when it comes to sharing the repo with others. So: Create these files **if** you think it is worth it._
	
## The analysis:

### Inputs you already have 

I've given you a list of firms from 2006 with variables
- "permno" = an identity for firms used by CRSP to track stocks 
- "fyear" = the fiscal year the remaining variable apply to 
- "gsector" = gsector (see [the wiki article on GICS](https://en.wikipedia.org/wiki/Global_Industry_Classification_Standard))
- "state" = of headquarters

You also have a data set of daily returns for 2006 with "permno", "date", and "ret".

Both of these datasets are `.dta` files, meaning they come from Stata. Have no fear, pandas can **read** these easily!

### Sample restrictions

Your analysis should only consider firms in **both** datasets. (HINT: Which type of merge should you use?) 

We will talk more about merging in future weeks, but [the top voted answer here is pretty good](https://stackoverflow.com/questions/53645882/pandas-merging-101).

### Your goal

Let's explore risk and return by industry and state. For simplicity, let's only look at CA and NY firms and only at tech and finance. 

At a minimum, you should produce the following tables, **along with some discussion, analysis, and interpretation**:
- T1 ("Daily return characteristics"): Using daily returns, report for each state and industry combination (so each stat for the 4 combinations of CA/NY and Fin/IT): 
	- the number of observations
	- the number of unique firms
	- return statistics (mean, std, min, max), which should be based on the daily **percent** return (i.e. return*100)
- T2 ("Annual return characteristics"): Using _**annualized**_ returns, output information about the distribution of returns across firms in each industry-state combination. (Compute statistics you think are useful!)
	- **Annualized -->** Use the daily returns (the raw value, not the percent return) to compute the **exact** annual return. It might help to try to write out the math; try to write out a formula that uses 5 days of returns to compute the total week's return. Then you can extrapolate the "computational steps embedded" in that formula to do an entire year. 
	- Your resulting temporary data structure after this should have one observation per firm per year.
	- HINT: Load the following "test unit" dataframe. You should get 61.051% and -1.0% returns for each firm, respectively. Use pandas functions only. If you do that, the code you just developed _should_ be applicable to the larger/realer dataset.

	
```
returns = pd.DataFrame({
    'permno' : [1,1,1,1,1,2,2,2,2,2], 
    'year' : [2000,2000,2000,2000,2000,2000,2000,2000,2000,2000],
    'ret' : [.1,.1,.1,.1,.1,.1,0,-0.1,0,0]
    })
```

And I have some questions:
- Q1: Which firm in each industry-state had the best month within the year? (Again: Compute _exact_ monthly returns from the daily.)
- Q2: Same, but look for the worst month?
- Q3: Which industry-state had the lowest average volatility? (Compute volatility for each firm then take the average.)

**Don't forget the golden rules:**

1. Organize your repo using our guidelines.
2. For each dataset, and different slices/aggregations/combinations of each dataset, explore the data.
3. Explore and check for data issues. If found, speculate on what might be causing them and if possible, fix them or alter your analysis to account for them. 

## A few comments

_Answer to merging Q above: Inner! (If you've read this far on the instructions before charging ahead, nice!)_

**Relax about the following things:**

- Tidying/reshaping is NOT your assignment. Some of your tables may be awkwardly shaped in the report. That’s OK.
- Table beauty is not a big deal. Simply printing to “screen” is fine.
- (Later in the semester, easier-to-read tables will be more important, but it's early, and I want you to concentrate on getting the concrete parts of the analysis right.)

**Tip: Treat this assignment as a “cheat sheet” for future-you!** Don’t assume that you’ll remember the lessons you learned while writing this assignment. Write things down:

- Add notes on difficulties/oddities you encountered. For example, which tables/figures are easy/hard to make, which data formats make better inputs for plotting functions or for human-friendly tables.
- Provide attribution whenever you take code or an idea from somewhere else, whether a blog post, a colleague, a vignette, etc. Putting those pointers in your “cheat sheet” will be useful for future-you – and it’s just good practice to indicate where you got things from. It also protects you on the plagiarism front. 

 
## When you are done with the analysis

The readme file should be "publication ready". It should describe to the reader what this repo is analyzing, the necessary packages (might a reader need to `pip install` anything?), and the key inputs (are any "API" tokens needed?). 

Open your main python file, clear any and all results, and run the analysis from scratch. Save the file, and commit the repo to GitHub.

## Peer review instructions

1. Click on the two invitation links I sent to you and accept the assignment on GitHub. You will have access to two peer's assignment repos.
2. Open an issue on their homework repo, copy the rubric below ([available here](https://raw.githubusercontent.com/LeDataSciFi/LeDataSciFi.github.io/master/assignments/asgn02.md)), and fill in your review there.  

## Grading rubric

See [the rubric guidelines](guidelines-peerreview.html#filling-out-the-rubric).

| Topic                       | Excellent | Satisfactory | Needs Work |
|-----------------------------|-----------|--------------|------------|
| **Coding style**                               |        |          |            |
| **Coding strategy**                             |        |          |            |
| **Code executes without error** \*                     |        |          |            |
|  **Code gives correct answers** \*\*    |        |          |            |
| **Repo follows golden rules as needed**      |        |          |            |

\* _See "ease of access" in guidelines_

\*\* _See answer key_

Remarks:

* Elaborate on above, especially for "needs work."
* Some specific praise?
* Something I learned?
* Specific constructive criticism?
* Something I know and that you, my peer, might like to know because it is relevant to something you struggled with.

