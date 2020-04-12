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

Use your new skills to estimate a model you think will produce the most accurate out-of-sample predictions. Try as many model types as you want, tune the models' hyperparameters, use folds to generate extra samples, preprocess and modify the sample as you please. 

At the end of the file, specify an object called `model` with which I can run `model.predict()` on hold-out data I kept secret. I will evaluate your R2 on the hold-out predictions. 

**The grade for this file is not based on effort, but on results:** Your grade will be based on how far your R2 is from the class leader's. 

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
