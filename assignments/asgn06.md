# Assignment 6 - Prediction Models and Regressions

Because of how it's formatted on the site, [it's actually easier to read this page here](https://github.com/LeDataSciFi/LeDataSciFi.github.io/blob/master/assignments/asgn06.md).

### Overview

**Due date: See the [schedule](https://ledatascifi.github.io/#schedule).**

I'm sure these dates will change a few times, so check back regularly...

### Let's get started

1. Again, read the [homework guidelines](guidelines-asgn.html).
2. Click on the invitation link I sent to you and accept the assignment on GitHub. This will create a repo.
3. Clone it to your computer, a la assignment 1.

This assignment is going to focus on the **original interest rate** variable in a dataset from Fannie Mae on loans. 

## PART 1: Regression within `regression.ipynb`

Create `regression.ipynb` and follow [the directions for that file here](asgn06_reg.html).
    
## PART 2: Prediction contest within `contest.ipynb`

Create `contest.ipynb` and follow [the directions for that file here](asgn06_pred.html).

## When you're done all of these parts (How to finalize your assignment)

- [ ] Follow the directions [here](asgn06_reg.html#when-youre-done-with-this) and [here](asgn06_pred.html#when-youve-done-the-above) to finish both files and save your prediction model.

The rest of the steps are the same as earlier assignments: 
- [ ] If you create output or temp folders, make sure your analysis file begins by deleting those folders and remaking them from scratch.
- [ ] If you need any additional inputs, download them to inputs. You don’t need to save the Fannie Mae file to your computer unless you want!
- [ ] Make sure that you refer to files with relative paths ("/input/wine.csv") and NOT absolute paths ("User/Don/Desktop/Project/input/wine.csv") because the latter won't work on anyone else's computer
- [ ] Delete all the temp files and output files your code created
- [ ] In Jupyter: Restart the kernel and clear the output for each file
- [ ] In Jupyter: Run all of your files completely, and make sure they work **from scratch**. This means no errors, and also check that your answers didn’t change!
- [ ] In Jupyter: Save the file.
- [ ] Your repo should be logically organized, with subfolders for inputs, outputs, and temp files (if needed). No file should be in a folder that it doesn't belong to. (No outputs in the input folder!) The code should be in the main folder.
- [ ] Clean up your repo - delete extraneous files not needed by peer reviews, or if you want to keep them: move them to a "`dev`" subfolder (which is commonly known to be a place where you put files you used while developing the code). You could call this subfolder "old files" or "my files" or whatever you want. Just clean it up for your reviewers and external eyes :)
- [ ] In Github Desktop: "Commit" and "Push to origin"
- [ ] github.com/ledatascifi : go to your assignment and make sure everything is there
- [ ] **Edit the readme file so visitors know what the repo is doing** (like "(yada yada) ... assignment.ipynb runs the main analysis based on ... (yada yada))

## Peer review instructions

1. Click on the two invitation links I sent to you and accept the assignment on GitHub. You will have access to two peer's assignment repos.
2. **CLONE BOTH REPOS TO YOUR COMPUTER, AND RUN JUST `regression.ipynb`. IT SHOULD WORK ON YOUR COMPUTER AS WELL!**
   - JUST THE REGRESSION FILE!
3. After you run it, do not push any changes to the repo. Simply delete it off your computer and remove it from GitHub Desktop (click "Repository" then "Remove") so it doesn't try to update it in the future. This isn't necessary, but will save you disk space and keep GH Desktop a little tidier. 
2. Open an issue on their homework repo, copy the rubric below once I post it ([available here](https://raw.githubusercontent.com/LeDataSciFi/LeDataSciFi.github.io/master/assignments/asgn06.md)), and fill in your review there. 

## Grading rubric

_This will look similar to prior assignments. You can get a sneak preview of what it will cover [here](https://raw.githubusercontent.com/LeDataSciFi/LeDataSciFi.github.io/master/assignments/asgn06.md)_

| Evaluate | Does it? / Is it? | Yes | No | Comments - explain if no| 
| :--- | :--- | :--- | :--- |  :--- |
| `README.md` | Orients readers nicely to the repo's goal and explains how to replicate the results. | | | |
| `regression.ipynb` | Runs **on your computer** without error  |
| Average interest rate plot | Match answer key |
| Regression coefficients for models 1, 2A, 2B, 4A  | Match answer key | | | _Put # of wrong coefficients here_ | 
| Model 1 Coefficient Interpretation |  Match answer key |
| Model 2B <img src="https://render.githubusercontent.com/render/math?math=\beta_2"> Interpration | Match answer key |
| R2 on Model 4A and 4B  | Match answer key |

Remarks:

OMG, I can't believe we finished the last assignment of this class!

![](https://media.giphy.com/media/iHyVaHfEYXZos8qPX2/giphy.gif)

Congrats on making it this far, friend. Let's graduate, get out into the real world (if quarantine ever ends), and go long on oil. 

![](oilcrop.png)

<!--
See [the rubric guidelines](guidelines-peerreview.html#filling-out-the-rubric).

Prof/TA review:
q1, q4 (both parts), q6 (all parts)
prediction code
score on prediction

-->
