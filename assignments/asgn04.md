# Assignment 4 - Merging, and Good Viz

### Overview

**Due date: See the [schedule](https://ledatascifi.github.io/#schedule).**

The goal is to explore merging functions and to implement some of our improved plotting skills. 
We will try a few different types of merges, see how they work, and explore some data operations around those merges.

### Let's get started

1. Again, read the [homework guidelines](guidelines-asgn.html).
2. Click on the invitation link I sent to you and accept the assignment on GitHub. This will create a repo.
3. Clone it to your computer, a la assignment 1. 

## PART 1:

Load the following two datasets (do not change these lines) and answer the follow on questions:

```python
crsp = pd.read_stata('https://github.com/LeDataSciFi/lectures-spr2020/blob/master/assignment_data/3firm_ret_1990_2020.dta?raw=true')
crsp['ret'] = crsp['ret']*100 # convert to precentage to match FF's convention on scaling
ff = pdr.get_data_famafrench('F-F_Research_Data_5_Factors_2x3_daily',start=1980,end=2010)[0] 
ff.rename(columns={"Mkt-RF":"mkt_excess"}, inplace=True) 
```

### Questions

Assume that the **stock data is the "left" dataset and the French data is the "right" dataset**. You're going to do a bunch of merges. I strongly encourage you to, after each merge, look at the data (look at larger chunks than usual), and play around creating variables to see when it works like you expect and when it doesn't. 

1. How many observations are there in `crsp` data?
1. How many observations are there in `ff` data?
1. How many observations are there after a left merge?
2. After a right merge? 
1. Why isn't the answer to Q2 and Q4 the same?
3. After an outer merge? 
4. After an inner merge?
5. Do a _**right**_ merge. Now, add a variable to this dataset that equals "the variance of the market return for the year" for every observation in the dataset. What is the average of this variable? (See the hints below on this.)

**For the sake of your classmates doing the review, please put your answers to these questions in one concise cell at the end of this "Part" of the assignment.**

HINT 1 for Q8:  You know that this variable should have a count equal your answer to Q4. 

HINT 2 for Q8: If you get a mean of 1.289761, that is wrong.

## PART 2: The glow up

**Task:** Repeat any 2 plots you've done before in the course that you think could be improved based on what we discussed in the "Good Viz" lectures. For each, replicate _**exactly**_  what you did before, and then create a better one. (Like a before/after picture comparison.) Briefly explain why you made the changes/what is better about them. 

**How your improvements will be graded: Effectiveness and creativity.**  Focus on "first-order" issues first (choosing effective chart types, facets/hues _**as needed**_), then on informative labels, axis titles, chart titles, and the like. **Be creative!** Figures might get completely reimagined as new types, or multiple figures, or the data will be altered in some way. (The before and after picture might not present the _exact same_ underlying data, but they must be attempting to convey the same point.)

**A recommendation:** We did not talk about customizing figures in class, and instead used the time on getting the "meat on the slab" first, but the lecture pages do include helpful links that will get you started on customization. I'd look at those before running off to Stack Overflow, as the background will make S.O. posts more intelligible. 

## When you're done with both parts (How to finalize your assignment)

- Your repo should be logically organized, with subfolders for inputs, outputs, and temp files (if needed). No file should be in a folder that it doesn't belong to. (No outputs in the input folder!) The code should be in the main folder. 
- If you create output or temp folders, make sure your analysis file begins by deleting those folders and remaking them from scratch. 
- If you need any additional inputs, download them to inputs. You don’t need to save the CCM file to your computer unless you want!
- Make sure that you refer to files with relative paths ("/input/wine.csv") and NOT absolute paths ("User/Don/Desktop/Project/input/wine.csv") because the latter won't work on anyone else's computer
- In Jupyter: Restart the kernal and clear the output
- In Jupyter: Run the entire file, and make sure it works **from scratch**. This means no errors, and also check that your answers didn’t change!
- In Jupyter: Save the file.
- In Github Desktop: "Commit" and "Push to origin"
- github.com/ledatascifi : go to your assignment and make sure everything is there
- **Edit the readme file so visitors know what the repo is doing** (like "(yada yada) ... assignment.ipynb runs the main analysis based on ... (yada yada))
  
## Peer review instructions

1. Click on the two invitation links I sent to you and accept the assignment on GitHub. You will have access to two peer's assignment repos.
2. **CLONE BOTH REPOS TO YOUR COMPUTER, AND RUN THEIR CODE. IT SHOULD WORK ON YOUR COMPTUER AS WELL!**
2. Open an issue on their homework repo, copy the rubric below ([available here](https://raw.githubusercontent.com/LeDataSciFi/LeDataSciFi.github.io/master/assignments/asgn03.md)), and fill in your review there.  You can delete the "notes" I put in each row (the non-bolded explanatory parts).

## Grading rubric

See [the rubric guidelines](guidelines-peerreview.html#filling-out-the-rubric).

| Topic                       | Excellent | Satisfactory | Needs Work |
|-----------------------------|-----------|--------------|------------|
| **Code executes without error.** This means that the code runs **on your own computer** after you clone the repo. \*                     |        |          |            |
| **Code gives correct answers to Part 1** \*\*    |        |          |            |
| **Coding style (overall)** - comments when code isn't self documenting, notebook cells are divided sensibly (but not excessively), notebook report is structured nicely for a reader (headers, informative text exists and is well placed, etc.)                         |        |          |            |
| **Graphing - wholistic effectiveness** Did they improve your ability to understand the message of the graph?                              |        |          |            |
| **Graphing - creativeness** How inventive was their glow up? "Excellent" in this category should not be given lightly! But give more than "Needs work" if the graphs exceed a minimal amount of ambition/scope and the execution show reasonable level of mastery of the raw techniques and coding functions.        |        |          |            |
| **Graphing - control**. Is the aspect ratio reasonable? Are the axis ranges and labels sensible? Are axis/graph titles informative (if they are needed - some graphs are so obvious they aren't). Are colors applied sensibly when merited (but not gratitously)?  "Excellent" means you wouldn't tweak much if anything on the figure even if you could do it as easily as with a pencil.            |        |          |            |
| **Repo follows golden rules as needed, including the README**  This means doing all the steps in the "When you're done with the above"  section, plus unlisted golden rules listed in the lectures.  |        |          |            |

\* _See "ease of access" in the rubric guidelines for more details_

\*\* _See answer key_

Remarks:

* Elaborate on above, especially for "needs work."
* Some specific praise?
* Something I learned?
* Specific constructive criticism?
* Something I know and that you, my peer, might like to know because it is relevant to something you struggled with.



