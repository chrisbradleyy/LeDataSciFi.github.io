# Homework guidelines

## Homework workflow

This follows the spirit of the [workflow recipe from lecture 1](https://ledatascifi.github.io/lectures-spr2020/01/01_Motivation_and_Getting_Started.html#***-THE-WORKFLOW-RECIPE--***):

**To start the assignment:**

1. Assignments are released via email invitations. When you click on the link and accept the assignment, GitHub will create a repo for you. Inside the repo will be the README.md file (with instructions and the rubric you will be graded on) and possibly starter code/data.
2. Clone the repo to your local machine using GitHub desktop. 

**As you work on the assignment, remember to cycle through these steps:**

1. Pull the existing master repo ("fetch origin") into your local repo on your computer (just in case a change was made by others). 
2. Work on the project in the local repo (on your computer).
3. GitHub desktop sees any changes to files when you save them and automatically "stages" them, by listing them as "changed" files in the left part of the screen.
4. To "commit" the changes, add a short informative description and (optionally) a longer description, then click the **"Commit to master"** buttom. **Do this early and often!!!**
5. You're almost ready to push the changes to cloud, but not yet! What if someone else (or you on a different machine) made changes to the master repo? Prevent issues by doing this step: "Pull/fetch" from the origin/master. (Select the "repository" menu and then "Pull" on GitHub Desktop for Windows.) If there are any conflicts, you'll be notified and prompted to fix them. If there are conflicts, fix them!
6. Push the changes by clicking the **"Push origin"** button!

Even though steps 1 and 5 might seem pointless during solo assignments, I encourage you to practice these good habits now, so that when you do collaborative work, you're protected from mistakes. 

## Homework tips

### **Q: What should your repo contain?**

**A: In addition to your Python code/Jupyter-based report, everything that is necessary to replicate your findings!** Your peers should be able to download the folder to their computer and execute the main analysis file and receive back the same results you generated.

**TIP 1:** Before you push what you think are your final changes to the master repo, delete all temporary files you generated, along with any outputs, and rerun the analysis/code as though you just downloaded. Did it work? If not, then the code is not reproducible. Probably, you referenced a temporary file you created outside of the flow of the code, or accidentally put an input file in the temporary file folder. Whoops!

**TIP 2:** After you push what you think are your final changes to the master repo, download it to your computer in a different spot (say a temporary folder on your desktop), and run the analysis again, there. Did it work? If not, then the code is not reproducible outside the directory you built it in. Probably, your code included absolute references like `C:\Users\DonBowen\Documents\project1\code\main_analysis.py` instead of `code\main_analysis.py`. Don't do that!

### **Q: What are my reviewers grading?**

**A:**  Details on what exactly is graded and how depend on the specific assignment (and you'll see this when it's time), but for a good summary, see the [Guidelines for peer review](guidelines-peerreview.html) page. 

Generically and briefly, I'll say that reproducibility is huge. Additionally, they will look at your (1) Your README.md file, which should describe the repo to readers. (2) The main analysis file. 



## Markdown files

You see the markdown files I'm providing with the blank rubrics and 
