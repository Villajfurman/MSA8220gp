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

Part 1 - 

	- Submit one column with "best" predictions for each of the 10k households.
	- Indicate whether each is or is NOT a "warm lead".

Part 2 - 

	- Add part 2 notes here
	
Part 3 - 

	- Add part 2 notes here

---## I. Data Overview

### *Variable Definitions*


## I. Data Overview

### *Variable Definitions*


Demographic data for head of household:

	1. age: age in years
	2. gender: gender (1=male, 2=female)
	3. married: marital status (1=married with spouse present, 2=married with spouse absent, 3=widowed, 4=divorced, 5=separated, 6=never married)
	4. nkid: number of children (any age)
	5. natvty: country of birth (57=US, 72=Puerto Rico, 109=France, 110=Germany,…)
	6. race: race (letting W=White, B=Black, I=American Indian, A=Asian, and H=Hawaiian: 1=W only, 2=B only, 3=I only, 4=A only, 5=H only, 6=W/B, 7=W/I, 8=W/A, 9=W/H, 10= B/I, 11=B/A, 12=B/H, 13= I/A, 14=A/H, 15=W/B/I, 16=W/B/A, 17=W/I/A, 18=W/A/H, 19=W/I/A, 21= other combination of 4 or 5 races)
	7. span: spanish origin (1=yes, 2=no)
	8. cars: number of cars kept for use by household
	9 .prevhome: whether the occupant ever owned a home before (1=yes, 2=no, D= don’t know, R=not answered)

Location data:

	10. region: geographic location of household relative to school (1=north, 2=east, 3=south, 4=west)
	11. UnitRating: rating of unit as a place to live (10= best, 1=worst)
	12. NbhdRating: rating of neighborhood as place to live (10= best, 1=worst)
	13. VeryLoINC: limit on what constitutes “very low income” for the surrounding region
	14. LoINC: limit on what constitutes “low income” for the surrounding region
	15. MedianINC: median income for the surrounding region

Dwelling data:

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

Mortgage data:

	27. downpct: down payment percentage (0=none, 1=0-2%, 2=3-5%, 3=6-10%, 4=11-15%, 5=16-20%, 6=21-40%, 7=41-99%, 8=100%, B=not applicable, D= don’t know)
	28. dwnpay: main source of down payment (1=sale of previous home, 2=savings, 3=sale of other investment, 4=borrowing, 5=gift, 6=land used for financing, 7=other 8=none, B=not applicable, D= don’t know, R=not answered)
	29. helc: has a home equity line of credit (1=yes, 2=no)
	30. helump: has a lump sum home equity loan (1=yes, 2=no)
	31. purchdate: year unit bought/obtained/received

Dependent variable
 
	32. HiEducInc: household with college educated parent(s), income over $100K, and at least one child under 18 years old (0=no, 1=yes)

#### *Column Viewer*

JMP:

	Cols => Columns Viewer => Select All Columns => Check Show Quartiles => Show Summary

*Variables of question*

| *column* | **N** | **N Missing** | **N Categories** | **Suspect** |
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

Notes:

	- New Column maybe Income?
	- low  - 0 - 34,000
	- med  - >34,000 - 55,000
	- high - >55,000

Check Values

	- AGE - age_2              => See date year format
	- VeryLoINC - VeryLoINC_2  => max 70K? 24K - 34K range (9200)
	- LoINC - LoINC_2          => max 114K? 39K - 53K range (13600)
	- MedianINC - MedianINC_2  => low 38K? 60K - 74K range (13700)
	- SQFT - sqft_2            => low 99?  => except for low seems legit
	- VALUE - value_2          => low 1?   => except for low seems legit

Other Info:

	- NbhdRating  => Seeing "0" when scale is 1-10
	- bed         => Seeing "0" possibly missing
	- bath        => Seeing "0" possibly missing

*New Columns*

| **column** | **original format** | **new format** | **column** |
|-|-|-|-|
| ``age`` 	  | character, nominal  | numeric, continuous | ``age_2``	 |
| ``gender`` 	  | numeric, continuous | numeric, nominal    | ``gender_2``	 |
| ``married``     | numeric, continuous | numeric, nominal    | ``married_2``	 |
| ``nkid`` 	  | numeric, continuous | no change 	      | ``nkid_2``	 |
| ``nativity``    | character, nominal  | numeric, nominal    | ``natvty_2`` 	 |
| ``race`` 	  | numeric, continuous | numeric, nominal    | ``race_2`` 	 |
| ``span`` 	  | character, nominal  | numeric, nominal    | ``span_2`` 	 |
| ``cars`` 	  | numeric, continuous | no change 	      | ``cars_2`` 	 |
| ``prevhome`` 	  | character, nominal  | no change 	      | ``prevhome_2`` 	 |
| ``region`` 	  | numeric, continuous | numeric, nominal    | ``region_2`` 	 |
| ``UnitRating``  | numeric, continuous | numeric, ordinal    | ``UnitRating_2`` |
| ``NbhdRating``  | numeric, continuous | numeric, ordinal    | ``NbhdRating_2`` |
| ``VeryLoINC``   | numeric, continuous | no change 	      | ``VeryLoINC_2``  |
| ``LoINC`` 	  | numeric, continuous | no change 	      | ``LoINC_2`` 	 |
| ``MedianLoINC`` | numeric, continuous | no change 	      | ``MedianLoINC``  | 
| ``bath`` 	  | numeric, continuous | no change 	      | ''bath_2 	 |
| ``bed`` 	  | numeric, continuous | no change 	      | ''bed_2'' 	 |
| ``built`` 	  | numeric, continuous | numeric, ordinal    | ``built_2`` 	 |
| ``condo`` 	  | numeric, continuous | numeric, nominal    | ``condo_2`` 	 |
| ``floors`` 	  | numeric, continuous | no change 	      | ''floors_2'' 	 |
| ``garage`` 	  | numeric, continuous | numeric, nominal    | ``garage_2` 	 |
| ``lot`` 	  | numeric, continuous | no change	      | ''lot_2"" 	 |
| ``psewer`` 	  | numeric, continuous | numeric, nominal    | ``psewer_2`` 	 |
| ``rooms`` 	  | numeric, continuous | no change 	      | ``rooms_2``  	 |
| ``sqft`` 	  | character, nominal  | numeric, continuous | ``sqft_2``  	 |
| ``value`` 	  | character, nominal  | numeric, continuous | ``value_2``  	 |
| ``downpct`` 	  | character, nominal  | no change 	      | ``downpct_2`` 	 |
| ``downpay`` 	  | character, nominal  | no change	      | ``downpay_2`` 	 |
| ``helc`` 	  | numeric, continuous | numeric, nominal    | ``helc_2``  	 |
| ``helump`` 	  | numeric, continuous | numeric, nominal    | ``helump_2`` 	 |
| ``purchdate``   | numeric, continuous | numeric, ordinal    | ``purchdate_2``  |
| ``HiEducInc``   | numeric, continuous | numeric, nominal    | ``HiEducInc_2``  |

#### *Column Viewer 2*

JMP:

	Cols => Columns Viewer => Select All Columns => Check Show Quartiles => Show Summary

Notes:

	- VeryLoINC - VeryLoINC_2 => max 70K? 24K - 34K range (9200)
	- LoINC - LoINC_2 	  => max 114K? 39K - 53K range (13600)
	- MedianINC - MedianINC_2 => low 38K? 60K - 74K range (13700)
	- SQFT - sqft_2 	  => low 99? => except for low seems legit
	- VALUE - value_2 	  => low 1? => except for low seems legit

Check Values

	- age_2	     => receiving dates instead of continuous values.
	- NdhdRating => Scale is 1-10, see 0s and additional variables suggest missing values0 value is considered a missing value
	- bath_2     => Where do they use bathroom without one and additional variables suggest missing values.
	- bed_2	     => Where do they sleep without a bed and additional variables suggest missing values.

Value Changes:

	- age_2		=> date calculation for new age value
	- NdhdRating_2  => 0 value is considered a missing value
	- bath_2        => 0 value is considered a missing value
	- bed_2	        => 0 value is considered a missing value

| **column** | **original value** | **new value** |
|-|-|-|
| ``age_2`` 	   | 1980 | 		    39 |
| ``age_2`` 	   | 1977 | 		    42 |
| ``age_2`` 	   | 1972 | 		    47 |
| ``age_2`` 	   | 1966 | 	 	    53 |
| ``age_2`` 	   | 1965 | 		    54 |
| ``age_2`` 	   | 1948 | 		    71 |
| ``age_2`` 	   | 1944 |  		    75 |
| ``age_2`` 	   | 1941 | 		    78 |
| ``age_2`` 	   | 1935 | 		    84 |
| ``NdhdRating_2`` |    0 | Missing Value Code | 
| ``bath_2`` 	   |    0 | Missing Value Code | 
| ``bed_2`` 	   |    0 | Missing Value Code | 

---

## II. Data Screening

### *Outliers*

#### *A. Quantile Range Outliers* - inital change for normal distribution

JMP:

	Analyze => Screening => Explore Outliers => Quantile Range Outliers

	Tail Quantile => .1 => .25
	Q             =>  3 => 24

Notes

	Increasing Q to 24 identified 158 outliers for lot_2 => 158 => 99998

| **column** | **original value** | **new value** |
|-|-|-|
| ``lot_2`` | 999998 | Missing Value Code | 

#### *B. Change Outliers Missing* - After increasing Q length to 24 99998(158) cases appeared and change to missing

JMP:

	Analyze => Screening => Explore Outliers => Quantile Range Outliers => Change to Missing
	
### *Missing Data*

#### *Column Viewer 3*

JMP:

	Cols => Columns Viewer => Select All Columns => Check Show Quartiles => Show Summary

Notes:

	- Identify all the **CONTINUOUS** variables with missing data except add age_2.
	- List out below (Create a new column for these as the imputation will replace values)

| **column** | **N** | **N Missing** |
|-|-|-|
| ``age_2``   |  9,723 | 277 |
| ``bath_2``  |  9,986 |  14 |
| ``bed_2``   |  9,992 |   8 |
| ``lot_2``   |  9,842 | 158 |
| ``sqft_2``  |  9,938 |  62 |
| ``value_2`` |  9,940 |  60 |

Add New Column Info:

	- Create new rows for imputation calculation.
	- List on new columns below.

| **imputed_column** |
|-|
| ``age_imputed``   |
| ``bath_imputed``  |
| ``bed_imputed``   |
| ``lot_imputed``   |
| ``sqft_imputed``  |
| ``value_imputed`` |

JMP:

	Analyze => Screening => Explore Missing Values => Select "New Columns" => Multivariate Normal Imputation => Accept Skrinkage => Yes

Note:

	- Probably should be done first prior to imputation but seeing there was new column created for these they can be removed if needed.

#### *Column Viewer 4*

JMP:

	Cols => Columns Viewer => Select All Columns => Check Show Quartiles => Show Summary

Notes:

	- Identify all the variables with missing data not just continuous.
	- List out below (Remember to create a new column for these as the imputation will replace values)


*Missing Data Variables_2*
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

#### *Identify Missing Data Patterns*

JMP:	

	Tables => Missing Data Pattern => Select "Select Columns"

Notes:

	- Pattern review suggests that some of the data isn't missing at random.
	- It is possible span_2 nativity_2 have a pattern suggesting not random.
	- It is possible that sqft_2 & value_2 have a pattern suggesting not random
	- Will review the correlation table for further info.

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

#### *Multicollinearity*

JMP:

	Analyze -> Multivariate Methods -> Multivariate (all missing cont. vars)

Notes:

	- Identify correlations between columns to determine imputation.
	- sqft_2 correlates with rooms_2 moderately
	- value_2 correlates with VeryLoINC_2, MedianINC_2, bath_2, rooms_2
	- bath_2 correlates with bed_2, rooms_2, value_2
	- bed_2 correlates with VeryLoINC_2, bath_2, rooms_2, value_2
	
| **column1** | **column2** | **Correlation_Value** |
|-|-|-|
| ``car_2``       |  ``VeryLoINC_2`` | .3092 |
| ``car_2``       |  ``LoINC_2``     | .3215 |
| ``VeryLoINC_2`` |  ``LoINC_2``     | .9786 |
| ``VeryLoINC_2`` |  ``MedianINC_2`` | .7215 |
| ``VeryLoINC_2`` |  ``bed_2``       | .2591 |
| ``VeryLoINC_2`` |  ``value_2``     | .3320 |
| ``LoINC_2``     |  ``MedianINC_2`` | .3144 |
| ``MedianINC_2`` |  ``value_2``     | .3084 |
| ``bath_2``      |  ``bed_2``       | .4920 |
| ``bath_2``      |  ``rooms_2``     | .5442 |
| ``bath_2``      |  ``value_2'`     | .3858 |
| ``bed_2``       |  ``rooms_2``     | .7633 |
| ``bed_2``	  |  ``value_2``     | .2702 |
| ``rooms_2``     |  ``sqft_2``      | .2552 |
| ``rooms_2``     |  ``value_2``     | .3431 |
	
Column Changes:

	- age_2, lot_2 do not show any correlation and excluded from imputation.
	- remove age_imputed and lot_imputed from data set. 

#### *Missing Interpretation*

Modeling Missing Values:

	- starting with age_2 and then lot_2 values.

JMP:

	Right Click => Column Header => New Formula Column => Distributional => Informative Missing

Notes:

	- See right away that IsMissing(column_2) is one column with binary values "Is Missing"
	- The other is informative{column_2}


Column Changes:

	- new column - *IsMissing[age_2]*
	- new column - *IsMissing[lot_2]*

*Create a Validation Column*

Review:

	- Missing Validation Column in data set so need to create a new one

JMP

	Right of last column => Right Click empty column => New Column

New Column Info:

	Column Name - Validation
	Modeling Type - Nominal
	Initalize Data - Random
	Random Indicator - Values => 0,1,2 => Proportions => .4, .3, .3

*Predict Age & Lot Missing Values*

Notes:

	- Build model for each new column with variables
	- Use Bootstrap to build model
	- Repeat process for *Age_Completed* & *Lot_Completed*
	- Use imputed columns instead of original_2 columns for this process.

JMP

	Analyze => Predictive => Bootstrap Forest => Use indepenent variables to predict each column
	Supress Multithreading => Set random seed to 123 => ok
	Red Triangle => Save Columns => Saved Predicitives

New Column Info:

	Column Name - age_2 Predicted
	Column Name - lot_2 Predicted

*Create Completed Columns*

Notes:

	- Insert new column for each new set (Age_Completed & Lot_Completed)

JMP

	Right click on new column => Formula => Conditional - if => Comparison - Is Missing  "age_2 to age_predicted, otherwise age_2"
	Repeat steps for lot_completed

New Column Info

	Column Name - Age_Completed
	Column Name - Lot_Completed

*Compare Complete to Is Missing Columns*

JMP

	Y by X => Y=Is Misssing X=Complete Column

Notes:

	Repeat for each "Completed Column"
	Check p-values

Results

	Age_Completed - missing at random
	Lot_Completed - Higher the lot size more likely its missing

*Response Screening Investigation*

JMP

	Analyze => Screening => Response Screening => Choose Values => ok

Notes:

	- Drop both Is Missing in Y
	- Throw in independent variables in X
	- Lot_2 is not missing at random and the values in the chart below suggest just that.
	- There were quite a few more but just hit on pain points.

| **column** | **FDR_Value** |
|-|-|
| ``psewer_2``      | 67.99 |
| ``Lot_Completed`` | 11.60 |
| ``MedianINC_2``   |  8.01 |
	
*Results*

Conclusion:

	Use informative missing for Lot_2.
	We could use Age_Completed as missing completely as random.

---

## III. Data Exploration


#### *A. Analyze* - Distribution, Fit Y by X, Tabulate, Multivariate

Notes:

	- Hide all the columns that are not going to used in the model so far
	- They still appear in the column selector for analysis

*Current Final Data Set*

| **column** |
|-|
| ``Age_Completed`` |
| ``gender_2``      |
| ``married_2``     |
| ``nkid_2``        |
| ``natvty_2``      |
| ``race_2``   	    |
| ``span_2``        |
| ``cars_2``        |
| ``prevhome_2``    |
| ``region_2``      |
| ``UnitRating_2``  |
| ``NbhdRating_2``  |
| ``VeryLoINC_2``   |
| ``LoINC_2``       |
| ``MedianINC_2``   |
| ``bath_imputed``  |
| ``bed_imputed``   |
| ``built_2``       |
| ``condo_2``       |
| ``floors_2``      |
| ``garage_2``      |
| ``lot_2``	    |
| ``psewer_2``      |
| ``rooms_2``       |
| ``sqft_imputed``  |
| ``value_imputed`` |
| ``downpct_2``     |
| ``dwnpay_2``      |
| ``helc_2``        |
| ``helump_2``      |
| ``purchdate_2``   |
| ``HiEduInc_2``    |


*1. Distribution*

JMP

	Analyze => Distribution

Notes:

	- Select all the columns for model.

Column Info:

	- Looking at our prediction variable "HiEducINC_2"
	- HiEducInc: household with college educated parent(s), income over $100K, and at least one child under 18 years old (0=no, 1=yes)
	- Value 0 => Count = 8859, Prob = .88950
	- Value 0 => Count = 1141, Prob = .11410

*2. Fit Y by X*

JMP

	Analyze => Fit X by Y
	
Notes:

	- Select all the columns for model.
	- This time use HiEduINC as the response variable

Column Info:
	
	- Review all the best fit
	- Review all the interesting relationships
  

*3. Tabulate*

JMP

	Analyze => Tabulate

Notes:

	- Hide all the columns that are not going to be used in the model so far
	- Select all the columns for model.

*4. Multivariate*

Notes:

	- Previously done

#### *B. Graph* - Graph Builder, Scatterplot, Scatterplot 3D

*1. Graph Builder*

JMP

	- Graph => Graph Builder => Drag columns of interest into appropriate columns.
	- Choose the options for visuals to look at relationships.

*1. Scatterplot*

JMP

	- Graph => Scatterplot Matrix => Drag columns of interest into appropriate columns.
	- Chose the options for visuals to look at relationships.

*1. Scatterplot*

JMP

	- Graph => Scatterplot Matrix => Drag columns of interest into appropriate columns.
	- Looking at relationships between sqft_2, value_2, bath_2, bed_2 * few others.

---

## IV. Predictive Modeling

Seed - 123

### *Partitioning*

JMP

	Analyze => predictive modeling => partition => select columns => Go


Columns:

	HiEduInc_2 as repsonse
	Below as the X Factors
	Validation as Validation
	Informative Missing
	Ordinal Restricts Order

* X Factors*
| **column** |
|-|
| ``Age_Completed`` |
| ``gender_2``      |
| ``married_2``     |
| ``nkid_2``        |
| ``natvty_2``      |
| ``race_2``   	    |
| ``span_2``        |
| ``cars_2``        |
| ``prevhome_2``    |
| ``region_2``      |
| ``UnitRating_2``  |
| ``NbhdRating_2``  |
| ``VeryLoINC_2``   |
| ``LoINC_2``       |
| ``MedianINC_2``   |
| ``bath_imputed``  |
| ``bed_imputed``   |
| ``built_2``       |
| ``condo_2``       |
| ``floors_2``      |
| ``garage_2``      |
| ``lot_2``	    |
| ``psewer_2``      |
| ``rooms_2``       |
| ``sqft_imputed``  |
| ``value_imputed`` |
| ``downpct_2``     |
| ``dwnpay_2``      |
| ``helc_2``        |
| ``helump_2``      |
| ``purchdate_2``   |

#### *Confusion Matrix*

JMP

	Red Triangle => Show Fit Details

Notes:

	Get the confusion matrix

JMP

	Red Triangle => Display Options => Show Split Prob

Notes:

	Get the confusion matrix
	Review the data

*Profit Matrix*

JMP

	Highlight HiEduINC => Right Click => Column Info => Column Properties => Profit Matrix	

| **Enrolled**   | ``0``      | ``1`` |
| `` 0`` 	 | **TN - 0** | **FP, -500** |
| `` 1`` 	 | **FN - 0** | **TP, 1000** |

JMP

	Analyze => Predictive Modeling => Partition => Recall
	Red Triangle => Save Prediction Formula

Notes:

	- Review output
	- Copy output to table 
	- Close output table
	- 8 New columns on table
	

Prob(HiEduInc_2==0)
Prob(HiEduInc_2==1)
Most Likely HiEduInc_2
Profit for 0
Profit for 1
Most Profitable Predition for HiEduInc_2
Expected Profit for HiEduInc_2
Actual Profit for HiEduInc_2

Notes:

	Profit for 0

	Profit for 1

### *Decision Tree*

Notes:

	run decision tree (default)
	record in models down below

### *Bootstrap Forest*

Notes:

	rerun but for boostrap (default)

### *Boosted Tree*

Notes:
	rerun but boosted (default)

## Models 

| Model ID | Model Type | Parameter | test decision matrix | Profit | MsClass Rate |
| 1  | decision | default           |2414 275 | 92500 | .0893 |
| -  | - | -		            |  81 230 |

| Model ID | Model Type | Parameter | test decision matrix | Profit | MsClass Rate |
| 2  | bootstrap | default          |2516 173 | 132500 | .0824 |
| -  | - | -		            |  92 219 |

| Model ID | Model Type | Parameter | test decision matrix | Profit | MsClass Rate |
| 3  | boosted | default            |2489 200 | 129000 | .0767 |
| -  | - | -			    |  82 229 |


## Models Averaging

	Analyze => Predictive Modeling => Model Comparison => red triangle => model averaging

	Columns to select
	prob(HiEduInc_2== 1)
	Prob(HiEduInc_2== 1)2
	Prob(HiEduInc_2== 1)3

	new columns to table

	Partition  | .0893 | 3000 | 32.167 |
	Bootstrap Forest | .08924 | 2984 | 43.063 |
	Boosted Tree | .1151 | 3000 | 43 |
	Model Avg | .1197 | 2984 | 39.042 |

Profit Matrix 

	| 0 | -500 |
	| 0 | 1000 |

## V. Model Selection

## Models Averaging

	Analyze => Predictive Modeling => Model Comparison => red triangle => model averaging

	Columns to select
	prob(HiEduInc_2== 1)
	Prob(HiEduInc_2== 1)2
	Prob(HiEduInc_2== 1)3
	HiEduInc_2 1 Avg Predictor
	
	By Validation

Model Comparison Validation=2 Test
	
Round 1	Winner - Bootsrap Forest

| Model ID | Model Type | Parameter | test decision matrix | Profit | MsClass Rate |
| 2  | bootstrap | default          |2516 173 | 132500 | .0824 |
| -  | - | -		            |  92 219 | - |
	
Expected Profit = 173(-500)+219(1000) = 132500
Expected Profit = 43.063(2984) = 128500

## training model round 2

Round 2 Winner - Boosted

| Model ID | Model Type | Parameter | test decision matrix | Profit | MsClass Rate |
| 2  | boosted | Num of layers = 1000 |2502 187 | 134500 | .0900 |
| -  | -       | -		      |  80 231 | - | - |


## VI. Making Predictions


