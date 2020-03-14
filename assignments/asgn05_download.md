# Download_10Ks.ipynb

This file:
1. Downloads the starting dataset 
    ```PYTHON
    url = 'https://github.com/LeDataSciFi/lectures-spr2020/blob/master/assignment_data/2007_inv_and_tech.dta?raw=true'
    ccm = pd.read_stata(url)
    ```
1. Save that dataset into a folder inside your assignment repo called `input/`.  
1. Uses the information to download all 148 10-Ks referred to in the data to a folder structure inside your repo. Each 10_k should be saved inside a folder like `edgar_filings/cik_<#>/raw/`. 

## Recommendations

1. After you download the `ccm` dataset, look at the data I've provided. Manually try to find two of the 10-Ks on the internet using the EDGAR and the variables in the dataset. Look for a pattern you can repeat in your scraper.
1. Try to download just one 10-K. 
    - Start by writing a few simple lines of code that can download a filing. Once you have that, then try to move it to a function. Go in small steps! Do not write the function all at once!
    - Save the 10-Ks to `edgar_filings/cik_<#>/raw/<downloaded file name>`. You'll have to use the `os` package to create directories/folders as needed. 
    - You can use a different folder structure if you want but **you must use `edgar_filings/cik_<#>/` as the first two levels!**
    - You shouldn't upload these to GitHub! Instead, ask GitHub Desktop to create a "gitignore" file and add a line to that file that says: `/edgar_filings/*`. 
    - Test this function on at least 5 random rows. You can use `df.sample(5)` to pick 5 rows at random from the dataset.
    - HINT: Your function will have more than this, but this code will probably be inside the function. Replace the comments with code that does whatever the comments mention.
      ```python
      if you haven't already downloaded the file:
        try:
          # open url with filing you want
        except:
          #you can print info about any errors you can check later
        else:
          #whatever you need to do after/if the scraper successfully loads the url
          sleep(3) # take a pause before trying another filing
      ```
1. When you can successfully download one 10-K, try a few more, one at a time. Check the folders on your computer - did they download like you expected? Are the files correct? If yes, continue. If not, you have an error to fix. 
1. When you are confident the program works, delete your whole `edgar_filings/` folder on your computer so you have a "fresh start" and then loop over all the rows in the dataset to download the 10-Ks. My code took about 10 minutes, and downloaded files for 148 firms that took about 232MB on my computer. 

