# Homework guidelines

## Homework workflow

This follows the spirit of the [workflow recipe from lecture 1](https://ledatascifi.github.io/lectures-spr2020/01/01_Motivation_and_Getting_Started.html#***-THE-WORKFLOW-RECIPE--***):

**To start the assignment:**

1. **You will get an email invitation to start the assignment.** When you follow the link and accept the assignment, GitHub will create a repo for you. The repo will be a private repo (only you, me, and the TA can see it) under the LeDataSciFi organization on GitHub. Inside the repo will be the README.md file (with instructions and the rubric you will be graded on) and possibly starter code/data.
2. Clone the repo to your local machine using GitHub desktop. 

**As you work on the assignment, remember to cycle through these steps:**

1. Pull the existing master repo ("fetch origin") into your local repo on your computer (just in case a change was made by others). 
2. Work on the project in the local repo (on your computer).
3. GitHub desktop sees any changes to files when you save them and automatically "stages" them, by listing them as "changed" files in the left part of the screen.
4. To "commit" the changes, add a short informative description and (optionally) a longer description, then click the **"Commit to master"** buttom. **Do this early and often!!!**
5. You're almost ready to push the changes to cloud, but not yet! What if someone else (or you on a different machine) made changes to the master repo? Prevent issues by doing this step: "Pull/fetch" from the origin/master. (Select the "repository" menu and then "Pull" on GitHub Desktop for Windows.) If there are any conflicts, you'll be notified and prompted to fix them. If there are conflicts, fix them!
6. Push the changes by clicking the **"Push origin"** button! **Do this early and often!!!**

Even though steps 1 and 5 might seem pointless during solo assignments, I encourage you to practice these good habits now, so that when you do collaborative work, you're protected from mistakes. 

**Shortly after the deadline, GitHub will stop you from editing the repo!** So commit _**and**_ push your changes often, and do not wait until minutes before the deadline.

## Homework tips

### **Q: What should your repo contain?**

**A: In addition to your Python code/Jupyter-based report, everything that is necessary to replicate your findings!** Your peers should be able to download the folder to their computer and execute the main analysis file and receive back the same results you generated.

**TIP #1:** Before you push what you think are your final changes to the master repo, delete all temporary files you generated, along with any outputs, and rerun the analysis/code as though you just downloaded. Did it work? If not, then the code is not reproducible. Probably, you referenced a temporary file you created outside of the flow of the code, or accidentally put an input file in the temporary file folder. Whoops!

**TIP #2:** After you push what you think are your final changes to the master repo, download it to your computer in a different spot (say a temporary folder on your desktop), and run the analysis again, there. Did it work? If not, then the code is not reproducible outside the directory you built it in. Probably, your code included absolute path references like `C:\Users\DonBowen\Documents\project1\code\main_analysis.py` (bad!!!) instead of relative path references like `code\main_analysis.py` (good!!!).

### **Q: What are my reviewers grading?**

**A:**  Details on what exactly is graded and how depend on the specific assignment (and you'll see this when the assignment is posted), but for a good summary, see the [Guidelines for peer review](guidelines-peerreview.html) page. 

Generically and briefly, I'll say that reproducibility is huge. Additionally, they will specifically look at (1) your README.md file, which should describe the repo to readers and (2) the main analysis file. 

### How can I get a great grade on assignments?

Blow your reviewers away!

**TIP #3:** Make it easy for others to see the source code that executes the analysis as well as the report. 
  - The README.md in the main directory is what they will see first. GitHub can format "Markdown" nicely, with headers, links, media, and more and will show visitors this. Create annotated links to documents graders need to access. For example, in the way [the main assignments landing page](assignments.html) points to key documents for students. You should point them to your main Jupyter file, which GitHub will also render!
  
**TIP #4:** Make it easy for others to run your code.
  - At the top of the code, load all packages you need
  - Under that, list parameters a user would set (you obviously choose these during your analysis, but it's nice to see quickly and wholly)
  - Under that, import external files. This makes it easy for someone to see which data files are required and edit the paths if necessary. Even though I said absolute path references are bad just a few paragraphs ago, there are situations where you might not keep data in the repo itself. (Typically: Huge data files or sensitive data subject to privacy issues.) When this is the case and you have to use absolute path references, you want those at the top of your code so people see them!
  - Again, see tip #2 above.
  
**TIP #5:** Make your work product (especially tables and figures) pretty. 
  - Use good design concepts that we discuss early in the semester for figures and tables.
  - I google "markdown cheat sheet" often (sometimes with "github" or "jupyter" added to it depending on what I'm writing). [This is a good start cheat sheet](https://guides.github.com/pdfs/markdown-cheatsheet-online.pdf) and there is so much good stuff online. 


