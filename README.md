# Final Project

	- School likes to promote to housholds typically with familie's income >100K & children <18yr.
	- Education level, income & children's ages are not explicity available
	- Maximize the monetary revenue from correct predictions minus the cost of prediction errors. (profit matrix etc...)
	- 2% of warm lead households marketed will enroll.
	- New student has avg. lifetime value of 75K
	- Average rev for each warm lead is 1500(75K * 2%)
	- Willing to spend $500 marketing per warm lead for lunch etc...
	- Hence 1500 - 500 = 1000 profit for a true positive.
	- Hence 500 cost/lost for a false positive.
	- Anyone outside of warm lead (true negative) & (false negative) are not included since no marketing and no enroll.

## Part 1 - 

	- Submit one column with "best" predictions for each of the 10k households.
	- Indicate whether each is or is NOT a "warm lead".


## Part 1 - Submit one column with "best" predictions for each of the 10k households
#### Indicate whether each is or is NOT a "warm lead".

##################
# Data Overview
##################

##############################
#### Variable Definitions ####
##############################

*** Demographic data for head of household: ***

!. age: age in years
2. gender: gender (1=male, 2=female)
3. married: marital status (1=married with spouse present, 2=married with spouse absent, 3=widowed, 4=divorced, 5=separated, 6=never married)
4. nkid: number of children (any age)
5. natvty: country of birth (57=US, 72=Puerto Rico, 109=France, 110=Germany,…)
6. race: race (letting W=White, B=Black, I=American Indian, A=Asian, and H=Hawaiian: 1=W only, 2=B only, 3=I only, 4=A only, 5=H only, 6=W/B, 7=W/I, 8=W/A, 9=W/H, 10= B/I, 11=B/A, 12=B/H, 13= I/A, 14=A/H, 15=W/B/I, 16=W/B/A, 17=W/I/A, 18=W/A/H, 19=W/I/A, 21= other combination of 4 or 5 races)
7. span: spanish origin (1=yes, 2=no)
8. cars: number of cars kept for use by household
9 .prevhome: whether the occupant ever owned a home before (1=yes, 2=no, D= don’t know, R=not answered)

*** Location data: ***

10. region: geographic location of household relative to school (1=north, 2=east, 3=south, 4=west)
11. UnitRating: rating of unit as a place to live (10= best, 1=worst)
12. NbhdRating: rating of neighborhood as place to live (10= best, 1=worst)
13. VeryLoINC: limit on what constitutes “very low income” for the surrounding region
14. LoINC: limit on what constitutes “low income” for the surrounding region
15. MedianINC: median income for the surrounding region

*** Dwelling data: ***

16. bath: number of bathrooms
17. bed: number of bedrooms
18. built: year unit was built
19. condo: whether unit is condominium or cooperative (1=yes, 2=no)
20. floors: # of stories in building
21. garage: garage or carport included (1=yes, 2=no)
22. lot: square footage of lot
23. 2psewer: unit connected to public sewer (1=yes, 2=no)
24. rooms: # of rooms in unit
25. sqft: square footage of unit
26. value: Zillow value of the unit

*** Mortgage data: ***

27. downpct: down payment percentage (0=none, 1=0-2%, 2=3-5%, 3=6-10%, 4=11-15%, 5=16-20%, 6=21-40%, 7=41-99%, 8=100%, B=not applicable, D= don’t know)
28. dwnpay: main source of down payment (1=sale of previous home, 2=savings, 3=sale of other investment, 4=borrowing, 5=gift, 6=land used for financing, 7=other 8=none, B=not applicable, D= don’t know, R=not answered)
29. helc: has a home equity line of credit (1=yes, 2=no)
30. helump: has a lump sum home equity loan (1=yes, 2=no)
31. purchdate: year unit bought/obtained/received

#### Dependent variable ####
 
32. HiEducInc: household with college educated parent(s), income over $100K, and at least one child under 18 years old (0=no, 1=yes)

#######################
#### Column Viewer ####
#######################


*** Variables of question ***

| **column** | **N** | **N Missing** | **N Categories** | **Suspect** |
|-|-|-|-|-|
| ``age``         |  9,723 | 277 |    84 | Cat => Cont.(Check Values)   |
| ``gender``      | 10,000 |   0 |    NA | Cont. => Cat     	        |
| ``married``     | 10,000 |   0 |    NA | Cont. => Cat 		|
| ``nkid``        | 10,000 |   0 |    NA | Seems legit 			|
| ``nativity``    |  9,879 | 121 |    62 | Good, Chk Value Format 	|
| ``race``        | 10,000 |   0 |    NA | Cont. => Cat 		| 
| ``span``        |  9,857 | 143 |     2 | Good, Chk Value Format 	|
| ``cars``        | 10,000 |   0 |    NA | Seems legit			|
| ``prevhome``    | 10,000 |   0 |    NA | Seems legit		 	|
| ``region``      | 10,000 |   0 |    NA | Cont. => Cat 		|
| ``UnitRating``  | 10,000 |   0 |    NA | Cont. => Cat 		|
| ``NbhdRating``  | 10,000 |   0 |    NA | Cont. => Cat (See "0" value) |
| ``VeryLoINC``   | 10,000 |   0 |    NA | Check Values 		|
| ``LoINC``       | 10,000 |   0 |    NA | Check Values 		|
| ``MedianLoINC`` | 10,000 |   0 |    NA | Check Values 		|
| ``bath``        | 10,000 |   0 |    NA | See "0" value 		|
| ``bed``         | 10,000 |   0 |    NA | See "0" value 		|
| ``built``       | 10,000 |   0 |    NA | Cont. => Cat 		|
| ``condo``       | 10,000 |   0 |    NA | Cont. => Cat 		|
| ``floors``      | 10,000 |   0 |    NA | Wide range 			|
| ``garage``      | 10,000 |   0 |    NA | Cont. => Cat 		|
| ``lot``         | 10,000 |   0 |    NA | Wide range 			|
| ``psewer``      | 10,000 |   0 |    NA | Cont. => Cat 		|
| ``rooms``       | 10,000 |   0 |    NA | Wide range 			|
| ``sqft``        |  9,938 |  62 | 1,202 | Cat => Cont.(Check Values) 	|
| ``value``       |  9,940 |  60 |   561 | Cat => Cont.(Check Values) 	|
| ``downpct``     | 10,000 |   0 |    11 | Good, Check Value Format 	|
| ``downpay``     | 10,000 |   0 |    11 | Good, Check Value Format 	|
| ``helc``        | 10,000 |   0 |    NA | Cont. => Cat 		|
| ``helump``      | 10,000 |   0 |    NA | Cont. => Cat 		|
| ``purchdate``   | 10,000 |   0 |    NA | Cont. => Cat 		|
| ``HiEducInc``   | 10,000 |   0 |    NA | Cont. => Cat 		|

Notes
	New Column - Income
	low  - 0 - 34,000
	med  - >34,000 - 55,000
	high - >55,000

	Check Values
	AGE - age_2 => See date year format
	VeryLoINC - VeryLoINC_2 => max 70K? 24K - 34K range (9200)
	LoINC - LoINC_2 => max 114K? 39K - 53K range (13600)
	MedianINC - MedianINC_2 => low 38K? 60K - 74K range (13700)
	SQFT - sqft_2 => low 99? => except for low seems legit
	VALUE - value_2 => low 1? => except for low seems legit

	Other Info
	NbhdRating => Seeing "0" when scale is 1-10
	bed => Seeing "0" possibly missing
	bath => Seeing "0" possibly missing

*** New Columns ***

| **column** | **original format** | **new format** | **column** |
|-|-|-|-|
| ``age`` | character, nominal | numeric, continuous | ``age_2`` |
| ``gender`` | numeric, continuous | numeric, nominal | ``gender_2`` |
| ``married`` | numeric, continuous | numeric, nominal | ``married_2`` |
| ``nkid`` | numeric, continuous | no change | ``nkid_2`` |
| ``nativity`` | character, nominal | numeric, nominal | ``natvty_2`` |
| ``race`` | numeric, continuous | numeric, nominal | ``race_2`` |
| ``span`` | character, nominal | numeric, nominal | ``span_2`` |
| ``cars`` | numeric, continuous | no change | ``cars_2`` |
| ``prevhome`` | character, nominal | no change | ``prevhome_2`` |
| ``region`` | numeric, continuous | numeric, nominal | ``region_2`` |
| ``UnitRating`` | numeric, continuous | numeric, ordinal | ``UnitRating_2`` |
| ``NbhdRating`` | numeric, continuous | numeric, ordinal | ``NbhdRating_2`` |
| ``VeryLoINC`` | numeric, continuous | no change | ``VeryLoINC_2`` |
| ``LoINC`` | numeric, continuous | no change | ``LoINC_2`` |
| ``MedianLoINC`` | numeric, continuous | no change | ``MedianLoINC`` | 
| ``bath`` | numeric, continuous | no change | ''bath_2 |
| ``bed`` | numeric, continuous | no change | ''bed_2'' |
| ``built`` | numeric, continuous | numeric, ordinal | ``built_2`` |
| ``condo`` | numeric, continuous | numeric, nominal | ``condo_2`` |
| ``floors`` | numeric, continuous | no change | ''floors_2'' |
| ``garage`` | numeric, continuous | numeric, nominal | ``garage_2` |
| ``lot`` | numeric, continuous | no change | ''lot_2"" |
| ``psewer`` | numeric, continuous | numeric, nominal | ``psewer_2`` |
| ``rooms`` | numeric, continuous | no change | ``rooms_2`` |
| ``sqft`` | character, nominal | numeric, continuous | ``sqft_2`` |
| ``value`` | character, nominal | numeric, continuous | ``value_2`` |
| ``downpct`` | character, nominal | no change | ``downpct_2`` |
| ``downpay`` | character, nominal | no change | ``downpay_2`` |
| ``helc`` | numeric, continuous | numeric, nominal | ``helc_2`` |
| ``helump`` | numeric, continuous | numeric, nominal | ``helump_2`` |
| ``purchdate`` | numeric, continuous | numeric, ordinal | ``purchdate_2`` |
| ``HiEducInc`` | numeric, continuous | numeric, nominal | ``HiEducInc_2`` |

#########################
#### Column Viewer 2 ####
#########################

Cols => Columns Viewer => Select All Columns, Check Show Quartiles, Show Summary

- age_2 - date caculation for new age value

| **new column** | **original value** | **new value** |
|-|-|-|
| ``age_2`` | 1980 | 39 |
| ``age_2`` | 1977 | 42 |
| ``age_2`` | 1972 | 47 |
| ``age_2`` | 1966 | 53 |
| ``age_2`` | 1965 | 54 |
| ``age_2`` | 1948 | 71 |
| ``age_2`` | 1944 | 75 |
| ``age_2`` | 1941 | 78 |
| ``age_2`` | 1935 | 84 |

- NdhdRating_2 - Scale is 1-10, see 0s and additional variables suggest missing values

| **new column** | **original value** | **new value** |
|-|-|-|
| ``NdhdRating_2`` | 0 | Missing Value Code | 

- bath_2 - Where do they use bathroom without one and additional variables suggest missing values

| **new column** | **original value** | **new value** |
|-|-|-|
| ``bath_2`` | 0 | Missing Value Code 

- bed_2 - Where do they sleep without a bed and additional variables suggest missing values

| **new column** | **original value** | **new value** |
|-|-|-|
| ``bed_2`` | 0 | Missing Value Code | 

	VeryLoINC - VeryLoINC_2 => max 70K? 24K - 34K range (9200)
	LoINC - LoINC_2 => max 114K? 39K - 53K range (13600)
	MedianINC - MedianINC_2 => low 38K? 60K - 74K range (13700)
	SQFT - sqft_2 => low 99? => except for low seems legit
	VALUE - value_2 => low 1? => except for low seems legit

############################################################
################   Data Screening   ########################
############################################################


################
### Outliers ###
################

Analyze -> Screening -> Explore Outliers -> Quantile Range Outliers

###########################
#a. Quantile Range Outliers - inital change for normal distribution analysis
###########################

Tail Quantile - Change to .25
Q - Change to 1.5
		
Reviewed Data and increase Q up to 24 when I noticed lot_2 has 158 outliers of 999998

###########################
#b. Change Outliers Missing
###########################	

- lot_2 - After increasing Q length to 24 99998(158) cases appeared and change to missing

| **new column** | **original value** | **new value** |
|-|-|-|
| ``lot_2`` | 999998 | Missing Value Code | 

####################
### Missing Data ###
####################

First review the new data in column viewer to determine the missing conintuous variables

*** Continuous Variables of question ***

| **new_column** | **N** | **N Missing** |
|-|-|-|
| ``age_2``   |  9,723 | 277 |
| ``bath_2``  |  9,986 |  14 |
| ``bed_2``   |  9,992 |   8 |
| ``lot_2``   |  9,842 | 158 |
| ``sqft_2``  |  9,938 |  62 |
| ``value_2`` |  9,940 |  60 |

# Create new rows for imputation calculation #
# Only looking at specifc columns such as missing continuous data for imput

Analyze -> Screening -> Explore Missing Values -> Multivariate Normal Imputation

	accept skrinkage

| **new_column** |
|-|
| ``age_imputed``   |
| ``bath_imputed``  |
| ``bed_imputed``   |
| ``lot_imputed``   |
| ``sqft_imputed``  |
| ``value_imputed`` |

Tables -> Missing Data Pattern

# select all columns that were missing data from original set

| **column** | **N** | **N Missing** |
|-|-|-|
| ``age_2``        |  9,723 | 277 |
| ``lot_2``        |  9,842 | 158 |
| ``span_2``       |  9,857 | 143 |
| ``natvty_2``     |  9,879 | 121 |
| ``sqft_2``       |  9,938 |  62 |
| ``value_2``      |  9,940 |  60 |
| ``bath_2``	   |  9,986 |  14 |
| ``bed_2``        |  9,992 |   8 |
| ``NbhdRating_2`` |  9,998 |   2 |

# Pattern review suggests that some of the data isn't missing at random

| **column** | **N** | **N Missing** |
|-|-|-|
| ``age_2``        |  9,723 | 277 |
| ``lot_2``        |  9,842 | 158 |
| ``span_2``       |  9,857 | 143 |
| ``natvty_2``     |  9,879 | 121 |
| ``sqft_2``       |  9,938 |  62 |
| ``value_2``      |  9,940 |  60 |
| ``bath_2``	   |  9,986 |  14 |
| ``bed_2``        |  9,992 |   8 |
| ``NbhdRating_2`` |  9,998 |   2 |




























## Missing Values

Right now, we’re in your first GitHub **repository**. A repository is like a folder or storage space for your project. Your project's repository contains all its files such as code, documentation, images, and more. It also tracks every change that you—or your collaborators—make to each file, so you can always go back to previous versions of your project if you make any mistakes.

This repository contains three important files: The HTML code for your first website on GitHub, the CSS stylesheet that decorates your website with colors and fonts, and the **README** file. It also contains an image folder, with one image file.

## Demension Reduction (Multicollinearity)

You are currently viewing your project's **README** file. **_README_** files are like cover pages or elevator pitches for your project. They are written in plain text or [Markdown language](https://guides.github.com/features/mastering-markdown/), and usually include a paragraph describing the project, directions on how to use it, who authored it, and more.

[Learn more about READMEs](https://help.github.com/en/articles/about-readmes)

## Your first website

**GitHub Pages** is a free and easy way to create a website using the code that lives in your GitHub repositories. You can use GitHub Pages to build a portfolio of your work, create a personal website, or share a fun project that you coded with the world. GitHub Pages is automatically enabled in this repository, but when you create new repositories in the future, the steps to launch a GitHub Pages website will be slightly different.

[Learn more about GitHub Pages](https://pages.github.com/)

## Rename this repository to publish your site

We've already set-up a GitHub Pages website for you, based on your personal username. This repository is called `hello-world`, but you'll rename it to: `username.github.io`, to match your website's URL address. If the first part of the repository doesn’t exactly match your username, it won’t work, so make sure to get it right.

Let's get started! To update this repository’s name, click the `Settings` tab on this page. This will take you to your repository’s settings page. 

![repo-settings-image](https://user-images.githubusercontent.com/18093541/63130482-99e6ad80-bf88-11e9-99a1-d3cf1660b47e.png)

Under the **Repository Name** heading, type: `username.github.io`, where username is your username on GitHub. Then click **Rename**—and that’s it. When you’re done, click your repository name or browser’s back button to return to this page.

<img width="1039" alt="rename_screenshot" src="https://user-images.githubusercontent.com/18093541/63129466-956cc580-bf85-11e9-92d8-b028dd483fa5.png">

Once you click **Rename**, your website will automatically be published at: https://your-username.github.io/. The HTML file—called `index.html`—is rendered as the home page and you'll be making changes to this file in the next step.

Congratulations! You just launched your first GitHub Pages website. It's now live to share with the entire world

## Making your first edit

When you make any change to any file in your project, you’re making a **commit**. If you fix a typo, update a filename, or edit your code, you can add it to GitHub as a commit. Your commits represent your project’s entire history—and they’re all saved in your project’s repository.

With each commit, you have the opportunity to write a **commit message**, a short, meaningful comment describing the change you’re making to a file. So you always know exactly what changed, no matter when you return to a commit.

## Practice: Customize your first GitHub website by writing HTML code

Want to edit the site you just published? Let’s practice commits by introducing yourself in your `index.html` file. Don’t worry about getting it right the first time—you can always build on your introduction later.

Let’s start with this template:

```
<p>Hello World! I’m [username]. This is my website!</p>
```

To add your introduction, copy our template and click the edit pencil icon at the top right hand corner of the `index.html` file.

<img width="997" alt="edit-this-file" src="https://user-images.githubusercontent.com/18093541/63131820-0794d880-bf8d-11e9-8b3d-c096355e9389.png">


Delete this placeholder line:

```
<p>Welcome to your first GitHub Pages website!</p>
```

Then, paste the template to line 15 and fill in the blanks.

<img width="1032" alt="edit-githuboctocat-index" src="https://user-images.githubusercontent.com/18093541/63132339-c3a2d300-bf8e-11e9-8222-59c2702f6c42.png">


When you’re done, scroll down to the `Commit changes` section near the bottom of the edit page. Add a short message explaining your change, like "Add my introduction", then click `Commit changes`.


<img width="1030" alt="add-my-username" src="https://user-images.githubusercontent.com/18093541/63131801-efbd5480-bf8c-11e9-9806-89273f027d16.png">

Once you click `Commit changes`, your changes will automatically be published on your GitHub Pages website. Refresh the page to see your new changes live in action.

:tada: You just made your first commit! :tada:

## Extra Credit: Keep on building!

Change the placeholder Octocat gif on your GitHub Pages website by [creating your own personal Octocat emoji](https://myoctocat.com/build-your-octocat/) or [choose a different Octocat gif from our logo library here](https://octodex.github.com/). Add that image to line 12 of your `index.html` file, in place of the `<img src=` link.

Want to add even more code and fun styles to your GitHub Pages website? [Follow these instructions](https://github.com/github/personal-website) to build a fully-fledged static website.

![octocat](./images/create-octocat.png)

## Everything you need to know about GitHub

Getting started is the hardest part. If there’s anything you’d like to know as you get started with GitHub, try searching [GitHub Help](https://help.github.com). Our documentation has tutorials on everything from changing your repository settings to configuring GitHub from your command line.
