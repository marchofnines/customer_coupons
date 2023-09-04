# Will the Customer Accept the Coupon?
[Link to customer_coupons.ipynb Jupyter Notebook](https://github.com/marchofnines/customer_coupons/blob/main/customer_coupons.ipynb)

## PART I - General Analysis
### Dataset cleaning and preparing
 - Dropped Duplicates
 - Dropped car column since it had 99% nulls
 - Dropped other null rows since they had 1-2% nulls
 - Combined columns without loss of information:
    - Combined toCoupon_GEQ5min, toCoupon_GEQ15min, toCoupon_GEQ25min into one column venueDistance which expressed in minutes the distance from the venue.  
    - Combined direction_same and direction_opp into one column called direction which had two values 'Same' and 'Opposite'.  
- Defined order of values in most columns for easier plotting

### Answers to questions 
1. What proportion of bar coupons were accepted?
    - The proportion of total observations who chose to accept the coupon isis : 56.84%

### Observations from histogram to visualize the temperature column
- The most overall coupons are distributed to drivers when temperatures are at 80 degrees and those coupons also have the highest acceptance rate.


## PART II - Bar Coupon Questions
#### What proportion of bar coupons were accepted?
    - The proportion of bar coupons that were accepted is : 41.19%
#### Compare the acceptance rate between those who went to a bar 3 or fewer times a month to those who went more.
    - The acceptance rate for drivers who went to a bar 3 or fewer times a month is 37.24%
    - The acceptance rate for drivers who went to a bar more than 3 times a months is 76.17%
    - Drivers who went to a bar more than 3 times a months are 2.05 more likely to accept the coupon than drivers who went to a bar 3 or fewer times a month
#### Compare the acceptance rate between drivers who go to a bar more than once a month and are over the age of 25 to the all others. Is there a difference?
    - The acceptance rate for Drivers who go to a bar more than once a month and age > 25 is 69.41%
    - The acceptance rate for all others is 35.06%
    - Drivers who go to a bar more than once a month and age > 25 are 1.98 more likely to accept the coupon than all others
#### Use the same process to compare the acceptance rate between drivers who go to bars more than once a month and had passengers that were not a kid and had occupations other than farming, fishing, or forestry.
    - The acceptance rate for Drivers who go to bars more than once a month and had passengers that were not a kid and had occupations other than farming, fishing, or forestry is 70.94%
    - The acceptance rate for all others is 29.72%
    - Drivers who go to bars more than once a month and had passengers that were not a kid and had occupations other than farming, fishing, or forestry are 2.39 more likely to accept the coupon than all others

#### Compare the acceptance rates between those drivers who: go to bars more than once a month, had passengers that were not a kid, and were not widowed OR go to bars more than once a month and are under the age of 30 OR go to cheap restaurants more than 4 times a month and income is less than 50K.
    - The acceptance rate for drivers who go to bars more than once a month, had passengers that were not a kid, and were not widowed is 70.94%
    - The acceptance rate for all others is 29.72%
    - Drivers who go to bars more than once a month, had passengers that were not a kid, and were not widowed are 2.39 more likely to accept the coupon than all others
    - The acceptance rate for drivers who go to bars more than once a month and are under the age of 30 is 72.96%
    - The acceptance rate for all others is 34.82%
    - Drivers who go to bars more than once a month and are under the age of 30 are 2.10 more likely to accept the coupon than all others
    - The acceptance rate for drivers who go to cheap restaurants more than 4 times a month and income is less than 50K. is 45.65%
    - The acceptance rate for all others is 40.24%
    - drivers who go to cheap restaurants more than 4 times a month and income is less than 50K. are 1.13 more likely to accept the coupon than all others

#### Based on these observations, what do you hypothesize about drivers who accepted the bar coupons?
    - We see a high acceptance rate amongst drivers who have characteristics of being younger and single.  For instance, younger people typically frequent cheap restaurants, go out a lot to both bars and restaurants, have lower incomes and are less likely to have kids.  Therefore I hypothesized that acceptance rates are higher for drivers who are young and single.  
    - I confirmed this using barplots of the Acceptance Rate by Age and the Acceptance Rate by Marital Status.


## PART III - Business Question / Problem Statement
- List distinctions between customers who accept a Coffee House coupon versus those who do not in terms of: 
    - User attributes
    - Contextual attributes
    - Coupon attributes
    - Lifestyle attributes (frequency of going out)
    - Occupation, Education and Income 

### Note: All questions and answers below relate only to the coffee coupon
----

### For what combination of contextual attributes did drivers have the highest acceptance rate?
    - Drivers going No Urgent Place at 10AM with kids when the venue is only 5 mins away in the opposite direction and it is 55 degrees and rainy outside had the highest acceptance rate (100%)
### For what combination of contextual attributes did drivers have the lowest acceptance rate?
    - Drivers going home at 10PM alone when the venue is 15 mins away in the opposite direction and it is 30 degrees and snow outside had the lowest acceptance rate (17.5%)
### What is the ratio between both groups (All contextual attributes)?
    - The ratio between the group with the highest acceptance rate to the group with the lowest acceptance rate is 5.71
### For what combination of destination and time did drivers have the highest acceptance rate?
    - Drivers going No Urgent Place at 10PM (68.69%)
### For what combination of destination and time did drivers have the lowest acceptance rate?
    - Drivers going home at 10PM accepted the coupon (28.96%)
### What is the ratio between both groups (Destination and Time)?
    - The ratio between the group with the highest acceptance rate to the group with the lowest acceptance rate is 2.37
### For what combinations of contextual attributes were no coupons given?
    - We see 3201 combinations of contextual attributes for which no coupons were given.  For instance we see from the graphs that amongst people going to work, coupons were only given at 7AM
### Hypothesis from plotting acceptance rate and count by destination and distance
    - We note that surprisingly, the acceptance rate for drivers going to work when the venue is 25 mins away is 0.43. This seems high.  One possible explanation is that even though the venue is  25 mins away, it is probably near the work place for these drivers
### Interesting observations from plotting acceptance rate and count by destination and passengers
    - Among drivers going home, the acceptance rate is much higher when the partner is riding with the driver - although we also note that the sample size is very small for drivers going home with their partner.
### How does the expiration of the coupon impact acceptance rate? 
    - For all types of passengers except for partner, the acceptance rate for coupons that expire after 1 day is higher than the acceptance rate for coupons that expire after 2h
    - For all destination types, the acceptance rate for coupons that expire after 1 day is higher than the acceptance rate for coupons that expire after 2h
    - The overall ratio between acceptance rates for 1d coupons vs 2h coupons is 1.35
### Compare the acceptance rate of drivers going No Urgent Place at 10AM, are 5 mins away from venue while riding with kids or friends (group with highest acceptance rates from question 1) against all other drivers.
    - The acceptance rate for Drivers going No Urgent Place at 10AM, are 5 mins away from venue while riding with kids or friends is 71.84%
    - The acceptance rate for all others is 48.29%
    - Drivers going No Urgent Place at 10AM, are 5 mins away from venue while riding with kids or friends are 1.49 more likely to accept the coupon than all others
### Observations from countplots (Marketing perspective)
    - The highest coupon counts are:
        - Destination Vs. Time: No Urgent Place at 10AM and Work at 7AM 
        - Destination Vs Venue Distance: No Urgent Place for 5 and 15 min drives to the venue
        - Destination Vs. Direction:  No Urgent Place, opposite direction
        - Destination Vs. Passengers: No Urgent Place with Friends
        - Destination Vs. Weather: No Urgent Place, Sunny
        - Destination Vs. Temperature: No Urgent Place 80 Degrees
    - Some of the lowest coupon counts are: 
        - Destination Vs. Time: 
            - Coupons were only given for work at 7am, home at 6pm and 10pm.  
            - Coupons were not given for No Urgent Place at 7am
        - Destination Vs Venue Distance: No Urgent Place for 25 min drives
        - Destination Vs. Direction:  No Urgent Place, same direction
        - Destination Vs. Passengers: No coupons given for passsengers not riding alone for work 
            - That's probably because most commuters drive to work alone anyway
        - Destination Vs. Weather: In general few coupons were given for rainy and snowy weather regardless of destination
        - Destination Vs. Temperature: Few coupons given at 30 degrees for No Urgent Place but also not many given for other destinations either 
    - Additional Insights
        - Most of the drivers going home do so at 6PM and most ride alone
        - The lowest amount of coupons given for coffee is at 10PM
        - Marketers of the coupons heavily targeted drivers going no urgent place
        - They only gave out coupons for 25 min drives for those going home or to work. Perhaps marketers are targeting drivers who live or work near the venues that are 25 mins away.  We will look at acceptance rates and see if they are high
        - They did not give any coupons for those going no urgent place and in the same direction because that would be like giving free money. 
### Plot bar plots of contextual attributes and provide observations and insights
    - Highest Acceptance Rates by Destination and Time: 
        - Surprisingly it is 10PM going to No Urgent Place despite low coupon count we saw from question 1
        - Secondly 10AM going to No Urgent Place

    - Lowest Acceptance Rates by Destination and Time: 
        - 10PM and 6PM while going home
        - Going Home Alone
        - Have Kids and going home or to work
        - Going home and are within 25 miles from the venue
        - Going home or to work and are headed in the opposite direction
    - Notable impacts to the rates by Distance to the Venue
        - Drivers Going No Urgent Place accept ~55-60% of coupons for 5 and 15 min drives 
        - For drives 5 mins away, drivers going to work have similar acceptance rate as those going No Urgent Place
        - Going home, the more the travel time to venue the less likely drivers are to accept coupons
        - Going to work we surprisingly see an acceptance rate of over 40% for 25 min drives
        
    - Notable impacts to the rates by Direction
        - Acceptance rate is close to 60% for those going to No Urgent Place and needing to change direction 
        
    - Notable impacts to the rates by Passengers
        - Passengers with kids going No Urgent Place have a lower acceptance rate than all others 

    - Notable impacts from temperature and weather
        - Highest acceptance is rates is for snowy 30 degree weather while commuting to work
        - Weather and temperature are not big deterrents for drivers going No Urgent Place

    - Notable impacts to the rates by coupon expiration time
        - Acceptance rate are lowest for drivers going home
        - Acceptance rates for coupons expiring in 1 day tend to be higher than coupons expiring in 2h
    - Additional Observations
        - Most of the drivers going home do so at 6PM and most ride alone
        - The lowest amount of coupons given for coffee is at 10PM
 ###  For what combination of demographic attributes did drivers have the highest acceptance rate?
    -  The highest acceptance rates (100%) are found among:
        - Females of ages 36 and 41 that are unmarried partners with children
        - Males of age 31 that are unmarried partners with no children
        - Males of age 46 that are married with no chlidren 
    - The lowest acceptance rates (0%) are found among:
        - Females of age 21 that are unmarried partners with children 
    - What is the ratio between both groups?
        - Undefined since we cannot divide by 0
    - We note that no coupons are distributed to drivers below 21 or above 50
### For what combination of education and occupation did drivers have the highest acceptance rate?
    - Highest (100%) acceptance rates are found among:
        - Drivers with some college/no degree who work in Farming, Fishing and Forestry
        - Drivers with a Bachelor, or a high school degree or some high school that work in Installation Maintenance & Repair
### For what combination of education and occupation did drivers have the lowest acceptance rate?
    - High School graduates in Arts Design Entertainment Sports & Media and Production Occupations (0%)
    - Associates degree students in Farmish, Fishing and Forestry, Food Preparation & Serving Related as well as Installation Maintenance & Repair (0%)
### Analysze the lifestyle attributes (frequency of going out to different establishments) and plot graphs as needed
    - The main thing that stands out from the plots and groupby operations is that regarding the going out habits, those who never go to the coffee house have the lowest acceptance rate for the coffee coupons. This makes sense.  
### Plot countplots and bar plots of the occupation, education and income and list your observations
    - The highest acceptance rates are for: 
        - occupation: 
            - healthcare practicioners (perhaps working late shifts)
        - education: 
            - Some High School 
        - income: 
            - Again we find some of the highest accetpance rates among lower income drivers
### Compare acceptance rate of drivers who make less than 25k and are students or unemployed vs. all others
    - The acceptance rate for drivers who make 25k or less and are students or unemployed is 58.68%
    - The acceptance rate for all others is 48.56%
    - Drivers who make 25k or less and are students or unemployed are 1.21 more likely to accept the coupon than all others
### Additional General Observation
    - We already saw that when coupon = Coffee House the overall acceptance rate is around 50% vs. 56.76% for all coupon types combined.  This is interesting because it may indicate that the price of coffee is low enough that overall people are less incentivized to accept a coupon.  

### Part IV - Next Steps 
    - There are many combinations of features for which drivers did not receive coupons or had very few coupons distributed.  We would recommend distributing additional coupons to cover all combinations of attributes so that a full representative analysis can be performed. 
    - Compare acceptance rates by looking at additional combinations of features