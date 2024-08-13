PROJECT CONTENTS
================
- prompt_acv1p0.ipynd: Jupyter file
- readme.md (this file): Project content description

GENERAL DESCRIPTION
===================
This project pertains a marketing effort to supply customers with promotional discount coupons to several types of commercial establishments.
The coupons are delivered wirelessly via phone to vehicle drivers. The goal is to gain insights into coupon acceptance patterns for several customer groups
based on data variables and associated attributes.
The project uses data contained in UC Irvine's Machine Learning reporsitory located at https://archive.ics.uci.edu/dataset/603/in+vehicle+coupon+recommendation

DETAILED DESCRIPTION
====================
We use information from thw UC Irvine repository to include descriptions of the data variables. Please go to the link above for a deeper discussion on data contents. 
"destination: No Urgent Place, Home, Work
passanger: Alone, Friend(s), Kid(s), Partner (who are the passengers in the car)
weather: Sunny, Rainy, Snowy
temperature:55, 80, 30
time: 2PM, 10AM, 6PM, 7AM, 10PM
coupon: Restaurant(<$20), Coffee House, Carry out & Take away, Bar, Restaurant($20-$50)
expiration: 1d, 2h (the coupon expires in 1 day or in 2 hours)
gender: Female, Male
age: 21, 46, 26, 31, 41, 50plus, 36, below21
maritalStatus: Unmarried partner, Single, Married partner, Divorced, Widowed
has_Children:1, 0
education: Some college - no degree, Bachelors degree, Associates degree, High School Graduate, Graduate degree (Masters or Doctorate), Some High School
occupation: Unemployed, Architecture & Engineering, Student, 
Education&Training&Library, Healthcare Support, 
Healthcare Practitioners & Technical, Sales & Related, Management, 
Arts Design Entertainment Sports & Media, Computer & Mathematical, 
Life Physical Social Science, Personal Care & Service, 
Community & Social Services, Office & Administrative Support, 
Construction & Extraction, Legal, Retired, 
Installation Maintenance & Repair, Transportation & Material Moving, 
Business & Financial, Protective Service, 
Food Preparation & Serving Related, Production Occupations, 
Building & Grounds Cleaning & Maintenance, Farming Fishing & Forestry
income: $37500 - $49999, $62500 - $74999, $12500 - $24999, $75000 - $87499, 
$50000 - $62499, $25000 - $37499, $100000 or More, $87500 - $99999, Less than $12500
Bar: never, less1, 1~3, gt8,  nan4~8 (feature meaning: how many times do you go to a bar every month?)
CoffeeHouse: never, less1, 4~8, 1~3, gt8,  nan (feature meaning: how many times do you go to a coffeehouse every month?)
CarryAway:n4~8, 1~3, gt8, less1, never (feature meaning: how many times do you get take-away food every month?)
RestaurantLessThan20: 4~8, 1~3, less1, gt8,  never (feature meaning: how many times do you go to a restaurant with an average expense per person of less than $20 every month?)
Restaurant20To50: 1~3, less1, never, gt8, 4~8,  nan (feature meaning: how many times do you go to a restaurant with average expense per person of $20 - $50 every month?)
toCoupon_GEQ15min:0,1 (feature meaning: driving distance to the restaurant/bar for using the coupon is greater than 15 minutes)
toCoupon_GEQ25min:0, 1 (feature meaning: driving distance to the restaurant/bar for using the coupon is greater than 25 minutes)
direction_same:0, 1 (feature meaning: whether the restaurant/bar is in the same direction as your current destination)
direction_opp:1, 0 (feature meaning: whether the restaurant/bar is in the same direction as your current destination)
Y:1, 0 (whether the coupon is accepted)"

ANALYSIS SCOPE
==============
The attached Jupyter notebook contains a detailed analysis of two types of coupons:
1) Bar coupons
2) CoffeHouse coupons

The influence of several data variables and attributes on coupon acceptance rates was examined.
Accompanying visaulizations were generated to support the initial conclusions of our analyses and are included in the notebook.

SUMMARY OF MAIN ACTIONS AND FINDINGS
====================================
- Data was explored for inconsistencies and missing values. Appropriate data cleaning actions were taken
- Found that the proportion of the total observations that chose to accept the coupon was 57.06 percent
- Coupon data for "Bar" and "CoffeeHouse" stores were analyzed
- Findings for Bar coupons
    - The proportion of bar coupons that were accepted was  41.19 percent
    - The acceptance rate for individuals who went to a bar 3 or fewer times a month was 33.86 percent
    - The acceptance rate for individuals who went to a bar more than 3 times a month was 76.29 percent
    - The acceptance rate for individuals who went to a bar more than once a month and who were over the age of 25 was 68.54 percent
    - The acceptance rate for all other individuals was 39.45 percent
    - The acceptance rate for individuals who went to a bar more than once a month was 68.54 percent
    - The acceptance rate for individuals who had passengers that were not a kid was 43.51 percent
    - The acceptance rate for individuals who had passengers that had occupations other than farming, fishing, or forestry was 41.18 percent
    - The acceptance rate for individuals who went to a bar more than once a month and had passengers that were not a kid was 70.96 percent
    - The acceptance rate for individuals who went to a bar more than once a month and had passengers that were not a kid and had occupations other than farming, fishing, or forestry was 70.96 percent
    - The acceptance rate for individuals who are under the age of 30 was 49.09 percent
    - The acceptance rate for individuals who went to a bar more than once a month and are under the age of 30 was 71.76 percent
    - We hypothesized that the group that accepts bar coupons the most is under 30 years and goes to bars more than once a month. This seems to be supported by the analyses and visualizations.
- Findings for Coffee House coupons
    - The proportion of coffee house coupons that were accepted was  50.04 percent
    - The acceptance rate for individuals who went to a Coffee House 3 or fewer times a month was 43.12 percent
    - The acceptance rate for individuals who went to a Coffee House more than once a month was 50.04 percent
    - The acceptance rate for individuals who went to a Coffee House more than 3 times a month was 67.50 percent
    - The acceptance rate for individuals who went to a CoffeeHouse more than 3 times a month was 67.50 percent.
    - The acceptance rate for individuals who went to a CoffeeHouse more than 3 times a month and are below the age of 25 was 74.90 percent
    - The acceptance rate for individuals who went to a CoffeeHouse more than 3 times a month and are age 26 and older was 67.50 percent
    - The acceptance rate for individuals who went to a CoffeeHouse more than 3 times a month and are age below 25 and 50plus was 72.71 percent
    - The acceptance rate for individuals who went to a CoffeeHouse more than 3 times a month and are below the age of 25 and male was 73.51 percent
    - The acceptance rate for individuals who went to a CoffeeHouse more than 3 times a month and are below the age of 25 and female was 76.79 percent
    - For the group who went to a CoffeeHouse more than 3 times a month and are below the age of 25:
        - The subgroups with the largest acceptance rates were individuals with incomes less than 12500, between 87500-99999 and between 62500-74999 dollars.
            - The largest number of coupons accepted were by the less than 12500 dollar income group
        - There were not significant (<10%) changes in acceptance rates when data was segmented by the individuals' educational level
        - Coupon acceptance rates are low late at night (10 PM) and peak at 10 AM and 2 PM. The largest number of coupons accepted was in the 21 year old group.
        - Coupon acceptance rates are influenced by the direction of driving. Acceptance rates are sginificantly higher when the individuals are driving in the direction of the coffee house
        - Coupons acceptance rates are higher when the driver is physically close to the coffee house.
            - Acceptance rate peaks when the driver is within 15 minutes of the store at the time the coupon is received
    - Based on the partial analyses performed, the customer who is the most likely to accept bar coupons has the following profile:
      - Visits coffee houses more than 3 times a month
      - It is under 25 years old
      - Female
      - Has an income less than $12500
      - The coupon is issued between the mid morning and the early afternoon (10AM to 2PM)
      - It is driving in the same direction as the coffee house is located
      - It is within 15 minutes of the store   

  NEXT STEPS AND RECOMMENDATIONS
  ==============================
  We have completed an initial analysis of two coupon types with a limited set of variables and data attributes.
  It would be good to expand the analysis to explore the possible influences of occupation, passanger type, marital status, family composition and weather among others.
  Also expand the analysis to look at other type of store coupons as well. 
