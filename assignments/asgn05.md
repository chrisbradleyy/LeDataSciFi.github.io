# Assignment under construction!

Come back soon!

## Objective

Economic theory tells us that a firm's investment policy (both R&D and CAPX), in the absence of _"economic frictions"_, should equate the marginal cost (MC) of an additional unit of capital to the marginal benefit (MB) of investing that capital today. If it was true that there are no relevant frictions (but there are!) **and** we could measure the ratio of MB/MC (which is called "Marginal Q"), then we could perfectly predict investment with only Marginal Q! 

Alas, measuring Marginal Q is impossible :( , so empirical researchers interested in understanding corporate investment policies have proposed many fixes. I won't discuss these other than to say most focus on improved estimation of Marginal Q or adding additional variables to investment models. And that's the approach this assignment is going to take. 

**So today, we are going to an exploratory analysis: Are the investment choices (R&D and CAPX) a firm makes related to its technology and risks it faces?**

## Data

So, we need an annual dataset of firms with three sets of variables: (1) investment,  (2) technology, and (3) risks. I've provided the first two in (A, described below), but **you'll need to develop three measures of risk on your own using the text in firm 10-K filings.**

A. Provided for you: variables describing investment (CAPX and R&D, both scaled by last year's assets) and technology (various patent measures)
  - "2007_inv_and_tech.dta", which is in the [usual place](https://github.com/LeDataSciFi/lectures-spr2020/tree/master/assignment_data)
  - This sample includes data for **2007 and 2008** fiscal years for ~200 firms

B. You'll need to get: Variables describing risks a firm faces 
  - Possibilities not limited to: antitrust; litigation - e.g. patent, consumer, class action; real estate; inflation; commodity; supply chain; natural disasters; weather; employees (fraud, compensation, departure); changes in tax policy; currency rates; regulatory approval; reputation; refinancing
  - Prof. Kathleen Hanley [has a recent paper](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2792943) on risks. It focuses on financial firms, which isn't our sample, but nevertheless, it contains a long list of risks in Table 5 you might find interesting.
  
## What to do


