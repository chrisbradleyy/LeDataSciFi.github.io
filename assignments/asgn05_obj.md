# Project set up

## Objective

Economic theory tells us that a firm's investment policy (both R&D and CAPX), in the absence of _"economic frictions"_, should equate the marginal cost (MC) of an additional unit of capital to the marginal benefit (MB) of investing that capital today. If it was true that there are no relevant frictions (but there are!) **and** we could measure the ratio of MB/MC (which is called "Marginal Q"), then we could perfectly predict investment with only Marginal Q! 

The problem with this theory is that measuring Marginal Q is impossible. Because of that, empirical researchers interested in understanding corporate investment policies have proposed many fixes. I won't discuss these other than to say most fixes focus on improved estimation of Marginal Q or adding additional variables to investment models. **The latter is the approach this assignment is following - seeing if and how other variables are related to investment.**

## Question

Your boss explains that she needs an exploratory analysis done:

**Are the investment choices (R&D and CAPX) a firm makes related to its technology and risks it faces?** Specifically, you should try to see how **2008 investment** is related to **2007 technology and risk.**

## Data necessary to get from the question to an answer

We need an annual dataset of firms with three sets of variables
1. investment in CAPX and R&D (both scaled by last year's assets, and when I say CAPX and R&D I always mean the scaled versions)
1. technology
1. risks
  
[This dataset](https://github.com/LeDataSciFi/lectures-spr2020/blob/master/assignment_data/2007_inv_and_tech.dta) has investment and technology data for **2007 and 2008**  fiscal years for ~200 firms but nothing on risks. 

To download it in Python, use 

```PYTHON
url = 'https://github.com/LeDataSciFi/lectures-spr2020/blob/master/assignment_data/2007_inv_and_tech.dta?raw=true'
ccm = pd.read_stata(url)
```

## So, your main challenge...

... is to create variables that measure risks for each firm. Please return to the main assignment page now and continue.





