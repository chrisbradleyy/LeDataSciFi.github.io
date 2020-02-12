# Assignment 3 - Explore Compustat

### Overview

**Due date: See the [schedule](https://ledatascifi.github.io/#schedule).**

The goal is to get your feet wet with using `seaborn` to explore a dataset.

### Let's get started

1. Again, read the [homework guidelines](guidelines-asgn.html).
2. Click on the invitation link I sent to you and accept the assignment on GitHub. This will create a repo.
3. Clone it to your computer, a la assignment 1. 

### The analysis:

1. Load "CCM_cleaned_for_class.dta" using the code below. This data are from "Compustat", which collects accounting data from 10-Ks and other corporate disclosures. The "CCM" in the filename means "CRSP-Compustat Merged" because it has a variable called "lpermno" which can be linked to CRSP (a database of stock prices).
  - [Variable descriptions here](https://github.com/LeDataSciFi/lectures-spr2020/tree/master/assignment_data)
  - `ccm = pd.read_stata('https://github.com/LeDataSciFi/lectures-spr2020/blob/master/assignment_data/CCM_cleaned_for_class.dta?raw=true')`
2. Make a section in your notebook called "Data Exploration" and do the following:
  - The best practice data exploration steps from the lecture.
  - Look for two variables (you only need two!) that have noteworthy outliers. Leave whatever table(s) or figure(s) you used to look for them. If you find some outliers, write in a markdown cell that "Future work will need to address outliers in ______ and ______ to ensure they don't skew the results."
  - Look for two variables (you only need two!) with rampant missing values. If found, write in a markdown cell that "Future work will need to understand why there are missing values of ______ and ______ and understand whether and how we should deal with them."
  - Note: You don't need do anything to deal with outliers or missing values, and I did not in my "answer key"
3. Make a section in your notebook called "Case Studies" and do the following:
  - Create a variable describing the change in profits (`prof_a`) for the firm and `describe()` that variable for the whole dataset. The change should be in levels (Profitability(t)-Profitability(t-1) and not in percentages.)
  - Use `query` to filter to four firms of your choice in the decade of the 2000s. Do not use AAPL, MSFT, TSLA, Ford, VZ, or GM - explore some other firms!
  - Plot three variables of your choice for all four firms. Look for noteworthy and meaningful changes (large declines, inclines, or changes in the slope of time path). Do one graph for each variable (and each graph  will have four lines corresponding to each firm). 
  - Use markdown cells before and after your plots to describes the plots for readers and say what you think is interesting about them.
4. Make a section in your notebook called "Financial leverage during the crisis":
  - Start with the original data (CCM_cleaned_for_class.dta) again.
  - Reduce to 2003-2013 (use the fyear variable)
  - Create a "sic2" variable based on the first 2 digits of "sic". This variable describes the industry for the firm. You can learn about [SIC codes here](https://en.wikipedia.org/wiki/Standard_Industrial_Classification) and [this excel file](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=2&ved=2ahUKEwjFs7qX7cfnAhXxtlkKHfB6BUoQFjABegQIAxAC&url=https%3A%2F%2Fwww.dnb.com%2Fcontent%2Fdam%2Fenglish%2Feconomic-and-industry-insight%2Fsic_2_digit_codes.xls&usg=AOvVaw0UCJkYdyG_8d7_wysKwC60) has each industry's name. 
  - Eliminate observations for SIC2 = 99 or 41. 
  - Compute average leverage (using the book value of assets) and average profits for each industry (SIC2)-year. And here I mean the combination of industry and year! (So, for example, Chemicial-2000, Tech-2000, Finance-2000 all have different values than Chemicial-2001, Tech-2001, Finance-2001.)
  - `describe()` the **industry-year** average leverage and profit variables you just made
  - Find the 4 industries with the highest average leverage in 2007 and the 4 industries with the lowest average leverage in 2007
  - Reduce the data to just those 10 industries
  - Plot the average leverage for your 10 industries for 2003-2013
  - Plot the average profit for your 10 industries for 2003-2013
  - Summarize what you learned in a markdown cell. 
5. When you're done with the above
  - Your repo should be logically organized, with subfolders for inputs, outputs, and temp files (if needed). No file should be in a folder that it doesn't belong to. (No outputs in the input folder!) The code should be in the main folder. 
  - If you create output or temp folders, make sure your analysis file begins by deleting those folders and remaking them from scratch. 
  - If you need any additional inputs, download them to inputs. You don’t need to save the CCM file to your computer unless you want!
  - Make sure that you refer to files with relative paths ("/input/wine.csv") and NOT absolute paths ("User/Don/Desktop/Project/input/wine.csv") because the latter won't work on anyone else's computer
  - In Jupyter: Restart the kernal and clear the output
  - In Jupyter: Run the entire file, and make sure it works **from scratch**. This means no errors, and also check that your answers didn’t change!
  - In Jupyter: Save the file.
  - In Github Desktop: "Commit" and "Push to origin"
  - github.com/ledatascifi : go to your assignment and make sure everything is there
  - Edit the readme file so visitors know what the repo is doing (like "(yada yada) ... assignment.ipynb runs the main analysis based on ... (yada yada))
  
### Peer review instructions

1. Click on the two invitation links I sent to you and accept the assignment on GitHub. You will have access to two peer's assignment repos.
2. Open an issue on their homework repo, copy the rubric below ([available here](https://raw.githubusercontent.com/LeDataSciFi/LeDataSciFi.github.io/master/assignments/asgn03.md)), and fill in your review there.  

### Grading rubric

See [the rubric guidelines](guidelines-peerreview.html#filling-out-the-rubric).

Evaluation of: __put the student github id here__

Evaluation by: __put your github id here__

| Topic                       | Excellent | Satisfactory | Needs Work |
|-----------------------------|-----------|--------------|------------|
| **Coding style**                               |        |          |            |
| **Coding strategy**                             |        |          |            |
| **Code executes without error** \*                     |        |          |            |
|  **Code gives correct answers** \*\*    |        |          |            |
| **Repo follows golden rules as needed, including the README**      |        |          |            |

\* _See "ease of access" in guidelines_

\*\* _See answer key_

Remarks:

* Elaborate on above, especially for "needs work."
* Some specific praise?
* Something I learned?
* Specific constructive criticism?
* Something I know and that you, my peer, might like to know because it is relevant to something you struggled with.

  
  
  
