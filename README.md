Project: Module 5 Practical Application Example 1
===

# Author: Vijay Chaganti

Dataset information
---

*Imagine driving through town and a coupon is delivered to your cell phone for a restaurant near where you are driving. Would you accept that coupon and take a short detour to the restaurant? Would you accept the coupon but use it on a subsequent trip? Would you ignore the coupon entirely? What if the coupon was for a bar instead of a restaurant? What about a coffee house? Would you accept a bar coupon with a minor passenger in the car? What about if it was just you and your partner in the car? Would weather impact the rate of acceptance? What about the time of day?*

*Given dataset has 12684 entries with 26 columns*
*Data Source: https://github.com/chagantvj/PracticalApplicationM5/blob/main/coupons.csv*

**Date Understanding and Cleaning**
---
*Total entries for each column of the data frame is 12684.*

*There is some data missing for Columsn car, Bar, CoffeeHouse, CarryAway, RestaurantLessThan20 and Restaurant20To50.*

| Column    | non-null-entries |
| --------- | ------- |
| car       |  108 (almost all entries null and can be ignored )     |
| Bar       |  12577 (null data is filled with the mode() of this column)      |
| CoffeeHouse          | 12467 (null data is filled with the mode() of this column)       |
| CarryAway          | 12533 (null data is filled with the mode() of this column)       |
| RestaurantLessThan20          | 12554 (null data is filled with the mode() of this column)       |
| Restaurant20To50          | 12495 (null data is filled with the mode() of this column)       |


## Used below code to cleanup and process data
 ```
 data['Bar'].replace('', np.nan, inplace=True)
data['CoffeeHouse'].replace('', np.nan, inplace=True)
data['CarryAway'].replace('', np.nan, inplace=True)
data['RestaurantLessThan20'].replace('', np.nan, inplace=True)
data['Restaurant20To50'].replace('', np.nan, inplace=True)

Bar_mode_value = data['Bar'].mode()[0]
CoffeeHouse_mode_value = data['CoffeeHouse'].mode()[0]
CarryAway_mode_value = data['CarryAway'].mode()[0]
RestaurantLessThan20_mode_value = data['RestaurantLessThan20'].mode()[0]
Restaurant20To50_mode_value = data['Restaurant20To50'].mode()[0]

data['Bar'].fillna(data['Bar'].mode()[0], inplace=True)
data['CoffeeHouse'].fillna(data['CoffeeHouse'].mode()[0], inplace=True)
data['CarryAway'].fillna(data['CarryAway'].mode()[0], inplace=True)
data['RestaurantLessThan20'].fillna(data['RestaurantLessThan20'].mode()[0], inplace=True)
data['Restaurant20To50'].fillna(data['Restaurant20To50'].mode()[0], inplace=True)
```
<br/>
<br/>
 
**Coupons Accepted vs Rejected from the entire data set**
---
![image](https://github.com/user-attachments/assets/a603ddec-97bc-43ff-afdd-3b0ec7f80ff6)

<br/>
<br/>


**Type of Coupons**
---
*Total 2017 Bar Coupons are present in dataset*

![image](https://github.com/user-attachments/assets/47fbac40-b0b5-411e-8685-b67a3f245b18)


<br/>
<br/>

**Total Bar coupons Accepted vs Rejected**
---
*Total 817 Bar Coupons are Accepted which is approximately 41% as shown in below pie chart*
![image](https://github.com/user-attachments/assets/fd1d8a52-4282-4a81-bba4-9c438f4d2db8)

<br/>
<br/>

**Accepted drivers went to Bar**
---

**Drivers who never whent to Bar and who went less than 3 times have accepeted coupons compared to rest who went more than 3 times per month**

![image](https://github.com/user-attachments/assets/b3b7d0fa-c737-4baf-86cc-195f11003400)

*never -- 0 times to bar*

*less1 -- Not gone to Bar*

*1~3   -- Going to bar more than 1 and lessthan 3*

*4~8  -- Going to bar more than 4 and lessthan 8*

*gt8  -- Going to bar more than 8*

<br/>
<br/>

**Drivers went to Bar more than once a month based on Age**
---
![image](https://github.com/user-attachments/assets/3247942a-b120-4f1f-9596-9be815b2ff67)

*Acceptance ratio is more for age group os less than 21 years compared to higher age group*

<br/>
<br/>


**Drivers with no kids as passenger & Occupation other than farming,fishing,or forestry VS All Others**
---

*Acceptance rate between drivers who go to bars more than once a month and had passengers that were not a kid and had occupations other than farming, fishing, or forestry to all others (added this last statement "to all others" for clarity)*

![image](https://github.com/user-attachments/assets/d8131851-a7a5-4ffd-a69f-f6a1777a6a8d)

*Drivers with no kids as passengers and whose occupation is not farming, fishing and forestry has almost equal acceptance ratio compared to all other categories of occupation together and all categories of passengers except kids.*


<br/>
<br/>

**Acceptance Rate for different categories of Drivers**
---
*Compare the acceptance rates between those drivers who:*

*Cat1 - go to bars more than once a month, had passengers that were not a kid, and were not widowed*

*Cat2 - go to bars more than once a month and are under the age of 30*

*Cat3 - go to cheap restaurants more than 4 times a month and income is less than 50K*


![image](https://github.com/user-attachments/assets/4eca5fde-21a6-430d-bbca-3042f4b2cfed)


<br/>
<br/>
