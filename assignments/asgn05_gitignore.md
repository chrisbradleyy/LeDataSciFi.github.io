# `.gitignore` and `screenshot.png`

It's not polite to upload so many 10-Ks to GitHub. It takes up space on the server, and your collaborators/peer reviewers will have to download them all when they clone your repo. 

So, you should tell GitHub not to upload those from your computer to the website!

## Step 1: `.gitignore`.

The easiest way is probably:
1. Open GitHub Desktop and go to your assignment 5 repo.
2. Click on "repository" and then "repository settings"
3. Click on "Ignored files".
4. This is where you tell GitHub not to upload those files. Assuming that you saved all the 10-Ks inside a folder called "edgar_filings", you should type `/edgar_filings/*`. Click Save.

## Step 2: Push the repo to origin

After you do this, open the repo in your browser. You should "see" two things:
1. `.gitignore`. Click on it and see that it says `/edgar_filings/*` inside it.
2. Your computer has a `/edgar_filings/*` folder on it with 148 10-Ks and 200+MB of hard drive space used, yet the repo in your browser doesn't show this at all! Good job!

## Step 3: `screenshot.png` - Upload proof of the files for your reviewers.

Right click your `edgar_filings` folder so it shows the number of files inside of it, and take a screenshot showing this. Save it as `screenshot.png` inside your repo. 
