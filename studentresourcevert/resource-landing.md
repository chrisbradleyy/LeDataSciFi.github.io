# Fixing Issues 

## Are you stuck on something? 

We all get stuck sometimes.  Here is the sequence of steps you might follow, although the exact things you do obviously will depend on the task:
1. Help functions and Python documentation
1. Search Google/Stack Overflow. Stack Overflow in particular is where the programming community asks and answers questions. 
1. Ask your peers - either in person or by posting an issue in the [class discussion repo page](https://github.com/LeDataSciFi/Discussion) - and other programmers on Stack Overflow. 
1. The TA's office hours
1. My office hours or email. I've listed myself last because, although I'm happy to help (I am!), I can't actually debug for 60+ students.

Asking questions (steps 3-5 above) is an important part of this class! I'm borrowing the **15 minute rule**:

> Once you’ve spent 15 minutes attempting to troubleshoot a problem, you must ask for help!


### How to properly ask for help

This section applies to Stack Overflow, our discussion repo, and if you follow this, office hours will be more efficient too. Coders expect other programmers will try the obvious (documentation, and previous Stack Overflow threads) and then follow these tips so the community can answer effectively and efficiently. 

Making your question _effective_ is an art. To make your question effective, the idea is to make things as easy as possible for someone to answer. 

- Will they have to dig to find a resource you're talking about, or do you provide links?
- If your code isn't doing what you expect, or you don't know how to obtain an output, do you provide a [__reproducible example__](https://stackoverflow.com/help/minimal-reproducible-example) (aka "reprex")?
  - Ideally, someone should be able to copy and paste a chunk of code to reproduce the problem you are talking about.
- Is your reproducible example _minimal_, meaning you've removed all the unnecessary parts to reproduce the problem?

You'll probably find that the act of writing an effective question causes you to answer your own question! So, here are the elements of a good question:

**# 1: Introduce the problem with an informative title**

Be specific with your title. It should be brief, but also informative so that when others are looking at the Issues page (and they have a similar error and/or solution), they can easily find it.

- Bad title: “I need help!”
- Good title: “Getting a ‘file not found error’ when importing scotus.csv”

**# 2: Summarize the problem**

Introduce the problem you are having. Include what task you are trying to perform, pertinent error messages, and any solutions you’ve already attempted. This helps us narrow down and troubleshoot your problem.

**# 3: Include a reproducible example**

Including a [minimal, complete, and verifiable example](https://stackoverflow.com/help/minimal-reproducible-example) of the code you are using greatly helps us resolve your problem. You don’t need to copy all the code from your program into the comment, but include enough code that we can **run it successfully until the point at which the error occurs**.

**# 4: Post your solution**

Once you have solved the problem (either by yourself or with the help of an instructor/classmate), **post the solution**. This let’s us know that you have fixed the issue AND if anyone else encounters a similar error, they can refer to your solution to fix their problem.

**# 5: Acknowledgments for this section**

- https://stackoverflow.com/help/how-to-ask
- https://www.propublica.org/nerds/how-to-ask-programming-questions
- https://cfss.uchicago.edu/faq/asking-questions/

### A few more tricks to deal with getting stuck

1. Stop coding! Take a quick break and clear your head.
2. Get out a piece of paper and map out how to solve the problem using plain words (pseudocode).
3. Add print statements everywhere (old school).
4. Use %debug in IPython.
5. Clear your head more substantive - go for a run, take a nap, get groceries. Returning to the code with a fresh eye will solve problems more often than you would believe. 
6. Sleep! Coding tired is a sure way to make mistakes.  


# Resources 

###  <u><b> THE MOST ESSENTIAL RESOURCES </b></u>  
- Help: Google, [Stack Overflow](https://stackoverflow.com), [Github help](https://help.github.com), [Jupyter documentation](https://jupyter.readthedocs.io/en/latest/running.html), [Python help](https://www.python.org/doc/)
- Cheat sheets to bookmark! [python basics](/img/pythonbasics.pdf), [python basics](/img/pythonbasics.pdf), [jupyter notebook](/img/jupyternotebook.pdf), [importing data](/img/importingdata.pdf), [numpy](/img/numpy.pdf), [pandas basics](/img/pandasbasics.pdf) and [more on pandas](/img/pandas.pdf), [matplotlib](/img/matplotlib.pdf), [scitkit-learn](/img/scitkit-learn.pdf), [seaborn](/img/seaborn.pdf)
- [Coding best practices, and project management](https://web.stanford.edu/~gentzkow/research/CodeAndData.xhtml)
- <b><u> Anything that is bolded/underlined below is also considered essential.</u></b>

### Python
- <b><u>Essential:</u></b> [A whirlwind tour of python](https://github.com/jakevdp/WhirlwindTourOfPython)
- <b><u>Essential:</u></b> [datacamp.com](https://www.datacamp.com/) has many self guided lessons
- Lessons 3 and 5 of the [official documentation](https://docs.python.org/3/tutorial/introduction.html)
- [Dive Into Python](https://diveinto.org/python3/table-of-contents.html)
- [This has to be the best list of Python resources on the internet](https://github.com/EbookFoundation/free-programming-books/blob/master/free-programming-books.md#python). 

### Data Science (broad)
- <b><u>Essential:</u></b> [Python Data Science Handbook](https://github.com/jakevdp/PythonDataScienceHandbook)
- [Probably the best collection of Python notebooks on the web](https://github.com/jupyter/jupyter/wiki/A-gallery-of-interesting-Jupyter-Notebooks)

### Data visualization
- <b><u>Essential:</u></b> [Kaggle's Data viz tutorial](https://www.kaggle.com/residentmario/welcome-to-data-visualization) is excellent. It has reproducible code and data, using python.
- <b><u>Essential:</u></b> [An Economist's Guide to Visualizing Data](https://pubs.aeaweb.org/doi/pdf/10.1257/jep.28.1.209) is excellent as well.
- <b><u>Essential:</u></b> [Data Visualization: A practical introduction, by Kieran Healy](https://socviz.co/lookatdata.html#lookatdata) especially discusses the "whys" of visualization in a smart way. The walkthroughs are in R, not python, however.
- [STAT545 on good visualization](https://stat545.com/effective-graphs.html)
- [Some good data viz blogs](https://www.tableau.com/learn/articles/best-data-visualization-blogs)

### Github, Git, and Version control
- [Getting started on GitHub](https://guides.github.com/activities/hello-world/) and a twitter length [description of how a project flows](https://help.github.com/en/articles/github-glossary) 
- [https://try.github.io/](https://try.github.io/) is awesome if you ever want or need to use Git (just plain "Git"). It has a cheatsheet and some very nice visual walkthroughs, including the "branching" link.
- [Jenny Bryan on version control](https://pdfs.semanticscholar.org/2575/6e04f126da30e26b447801a5e2d3e51e3154.pdf)
- Again... [Coding best practices, and project management](https://web.stanford.edu/~gentzkow/research/CodeAndData.xhtml)
- [The most thorough yet simple walkthrough of Git and Github use on the web](https://happygitwithr.com). Applies to python use for the most part. 
  
### Getting data and practicing ML
- [Scikit (python package) can read in some data](https://scikit-learn.org/stable/datasets/index.html), which has data on Boston real estate, wine, a larger california housing dataset 
- <b><u>Essential:</u></b> [Pandas can read in a LOT of useful data!](https://pandas-datareader.readthedocs.io/en/latest/readers/index.html) Data providers include: Federal Reserve ("FRED"), Ken French, NASDAQ, OECD, Qunadl, TSP, World Bank, and more!
- [ML competitions with serious prizes at drivendata.org](https://www.drivendata.org/competitions/54/machine-learning-with-a-heart/)
  - [This comp was interesting](https://www.drivendata.org/competitions/50/worldbank-poverty-prediction/page/99/). You could start trying [to analyze it here](http://drivendata.co/blog/worldbank-poverty-benchmark/). This has a good example of the process you might follow. After you're done, you can see [the winner's code and discussion of the winning approach](https://github.com/drivendataorg/pover-t-tests/tree/9a1918856c5e6ee537caed103eb80dabefb2fe44)  
- <b><u>Essential:</u></b> [kaggle.com](kaggle.com) has ML competitions, some FAQs, tutorials, data and competitions
  - [Real estate data](https://www.kaggle.com/c/house-prices-advanced-regression-techniques), a tutorial [exploring that data](https://www.kaggle.com/pmarcelino/comprehensive-data-exploration-with-python), and a [pass at a model](https://www.kaggle.com/juliencs/a-study-on-regression-applied-to-the-ames-dataset)
  - Philly based data would be fun. Here is [real estate, one option for data, seems ok, N=805](https://www.kaggle.com/harry007/philly-real-estate-data-set-sample)
  - [Predict box office for movies](https://www.kaggle.com/c/tmdb-box-office-prediction). VaultML claims they can do this by reading the screenplays and using textual analysis tools
  - [Wine, but not necessarily the best data source](https://www.kaggle.com/zynicide/wine-reviews)
- [UC Irvine has a data repo](https://archive.ics.uci.edu/ml/index.php), some of these are available via scikit package
  - [Predicting where the wine is from (wine/location](https://archive.ics.uci.edu/ml/datasets/Wine) <--- easy starter challenge (where is the wine from?)
  - [Wine Quality](https://archive.ics.uci.edu/ml/datasets/Wine+Quality)
  - [German credit data by person](https://archive.ics.uci.edu/ml/datasets/statlog+(german+credit+data))
- More good sources: <data.gov>, <data.census.gov>, <data.world>, <https://ourworldindata.org/> is incredible and [has many repos on Github](https://github.com/owid) including [one that imports data via python](https://github.com/owid/owid-importer), ...

### Some books you might look for
- [Signal and the Noise, by Nate Silver](https://www.amazon.com/gp/product/159420411X)
- [Range, by David Epstein](https://www.amazon.com/Range-Generalists-Triumph-Specialized-World/dp/0735214484) is a very interesting book generally, and it touches on prediction skill too
- [Superforecasters](https://www.amazon.com/Superforecasting-Science-Prediction-Philip-Tetlock/dp/0804136718)
  - A decent [free summary](https://medium.com/west-stringfellow/superforecasting-the-art-and-science-of-prediction-review-and-summary-e075be35a936)
