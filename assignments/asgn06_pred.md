# `contest.ipynb`

First, load the same dataset as in part 1:

```python
url = 'https://github.com/LeDataSciFi/lectures-spr2020/blob/master/assignment_data/Fannie_Mae_Plus_Data.gzip?raw=true'
fannie_mae = pd.read_csv(url,compression='gzip')  
fannie_mae.drop('Loan_Identifier',axis=1).describe().round(1).transpose()
```

## Your mission

These aren't the only loans in existence. I want you to build a model to help me price the interest rates I should charge to customers in a completely different set of loans that aren't in this dataset. The stakes are high! If I give them the wrong rates, well...

![](https://media.giphy.com/media/kC2cRqEt8o41COgjoV/giphy.gif)

So now we're doing real business. Thus, **the grade for this file is not based on effort, but on results:** Your grade will be based on how far your R2 is from the class leader. 

## Now what?

Use your new skills to estimate a model you think will produce the most accurate out-of-sample predictions **AS MEASURED BY R2**! Try as many model types as you want. For each model,
- preprocess and modify the sample as you please (but these steps **MUST BE DONE WITHIN A PIPELINE I CAN USE WITH PREDICT**)
- tune and optimize the models' hyperparameters
- use folds to generate extra samples as you tune the models

## TO GET GRADED, YOU MUST DO THIS STEP

When you've picked your best pipeline/model for submission, put this at the end of your code:
```python
# save the finalized model to hard drive

import pickle
filename = 'finalized_model.sav'
pickle.dump(my_best_pipeline, open(filename, 'wb'))    
```

Obviously, replace `my_best_pipeline` with whatever your best pipeline/model is named. 

**When you run this, it will create a file called `finalized_model.sav` in your assignment folder. This is what I will grade.**

If you want to check your submission can be graded, 
1. Save the `finalized_model.sav` file to your computer with the above code,
2. Clear the kernel
3. Copy the code below at the very end of your file and run ONLY it. If it prints out an r2 score, all is well!

```python
import pickle
import pandas as pd
from sklearn import metrics

# load data to test the model on. this is just the same data as before, 
# because it's all you have. i'll load the real test data

url = 'https://github.com/LeDataSciFi/lectures-spr2020/blob/master/assignment_data/Fannie_Mae_Plus_Data.gzip?raw=true'
holdout = pd.read_csv(url,compression='gzip') 
y_holdout = holdout['Original_Interest_Rate']
holdout.drop('Original_Interest_Rate',axis=1,inplace=True)

# load the saved model, predict, and score

filename = 'finalized_model.sav'
loaded_model = pickle.load(open(filename, 'rb'))    
metrics.r2_score(y_holdout,loaded_model.predict(holdout))

############################################################################
# obviously, the holdout data is different, so the score this prints
# is not what you'll get on the actual holdout sample
############################################################################
```

## When you've done the above

1. Make sure you clean up your file for publication. Make the code and markdown headers/text easy to read and follow. 
2. Clear the kernal and run all. 
3. Save it.
4. Commit and push it via GitHub Desktop.
