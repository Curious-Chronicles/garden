---
index: BC923
tags: 8-week-sql-challenge, sql, practice
status: Todo
created: 2023-05-06 14:45
updated: <%+ tp.file.last_modified_date() %>
author: sarwesh maharjan
---
Related: [[BC922-8 Week SQL Challenge 2nd Week]], [[BC921-8 Week SQL challenge 1st Week]]
URL: [link](https://8weeksqlchallenge.com/case-study-3/)

---
# General Knowledge

1. What is churn?
  - Churn means that customer has cancelled his/her subscription however, the subscription stores itself until its the end period of subscription. 

2. How plans changes for trial user to other subscription options? 
  - It goes as following 
  | Plans Start | Change to | Type |
  | --- | --- | --- | 
  | 7 days free trial| Pro monthly |  Automatic |
  | 7 days free trail | Basic or Pro anually | Manually | 
  | Plan cancel | Churn period | price = null but not disabled | 
  
# **A. Customer Journey**

Based off the 8 sample customers provided in the sample from the subscriptions table, write a brief description about each customer’s onboarding journey. Try to keep it as short as possible - you may also want to run some sort of join to make your explanations a bit easier!

Summarized version of the plan changes that occurred for the first 8 customers.  

|Customer| Journey Started | Journey Ended | Within Trial Period| Churn After Period| New Plan Period|
| --- | --- | --- | --- | --- | --- |
| 1 | trial | basic monthly | no | - | - |
| 2| trial | pro annual | no | - | - |
|3| trial | basic monthly | no | - | - |
|4| trial | basic monthly | no | After 3 months |  - |
|5| trial | basic monthly | no | - | - |
|6| trial | basic monthly | no | After 2 months | - |
|7| trial | basic monthly | no | - | pro monthly (After 3 months) |
|8| basic monthly | pro monthly (After 2 months) |  -  | - | - |


Below SQL queries can provide more in-depth information. 
```sql
SELECT s.customer_id, s.plan_id, p.plan_name, p.price, s.start_date  
FROM foodie_fi.plans as p
INNER JOIN foodie_fi.subscriptions as s ON p.plan_id = s.plan_id
Where s.customer_id IN (1,2,3,4,5,6,7,8)
ORDER BY s.customer_id, s.plan_id;
```

# **B. Data Analysis Questions**
_**Please note that the answer given below refers to data present at the date 2023-05-02. If you are looking over the data in the future, please run the attached sql queries to get the latest set of data. If you only want historical data upto the mentioned date than it is correct.**_

How many customers has Foodie-Fi ever had?
- Total number of customer in the Foodie-Fi currently is: 1000. 
  ```sql
SELECT COUNT(DISTINCT s.customer_id) as total_customer
FROM foodie_fi.subscriptions as s;
  ```
  
What is the monthly distribution of trial plan start_date values for our dataset - use the start of the month as the group by value
  ```sql
SELECT DATE_TRUNC('month',  s.start_date) AS start_month, COUNT(*) AS count  
FROM foodie_fi.plans as p
INNER JOIN foodie_fi.subscriptions as s ON p.plan_id = s.plan_id
Where p.plan_name = 'trial'
GROUP BY start_month;
```

What plan start_date values occur after the year 2020 for our dataset? Show the breakdown by count of events for each plan_name
- According to data, pro annual has 63. churn is 71, pro monthly is 60 and basic monthly is 8. 
```sql
SELECT p.plan_name, COUNT(*) AS count
FROM foodie_fi.subscriptions AS s
INNER JOIN foodie_fi.plans AS p ON s.plan_id = p.plan_id
WHERE s.start_date > '2020-12-31'
GROUP BY p.plan_name;
```

What is the customer count and percentage of customers who have churned rounded to 1 decimal place?
-  According to the data. 30.7% of the user have churned. 
```sql
SELECT 
  COUNT(DISTINCT s.customer_id) AS customer_count,
  ROUND(COUNT(DISTINCT CASE WHEN p.price IS NULL THEN s.customer_id END) * 100.0 / COUNT(DISTINCT s.customer_id), 1) AS churn_percentage
FROM foodie_fi.subscriptions AS s
INNER JOIN foodie_fi.plans AS p ON s.plan_id = p.plan_id;
```

How many customers have churned straight after their initial free trial - what percentage is this rounded to the nearest whole number?
- According to the data only 9.2% of user churn right after ending their trial period.
```sql
SELECT
  COUNT(DISTINCT s.customer_id) AS churned_count,
  COUNT(DISTINCT t.customer_id) AS trial_count,
  ROUND(COUNT(
  	CASE
    	WHEN s.plan_id = '4' then s.customer_id
    END
  ) * 100.0 / COUNT(DISTINCT t.customer_id),0) AS churned_percentage
FROM foodie_fi.subscriptions AS s
INNER JOIN (
  SELECT customer_id, start_date + INTERVAL '7' DAY AS end_date
  FROM foodie_fi.subscriptions
  WHERE plan_id = '0'
) AS t ON s.customer_id = t.customer_id
WHERE t.end_date = s.start_date;
```

What is the number and percentage of customer plans after their initial free trial?
- 908 customer continue on with the plan with 90.8 percentage of trial count.
```sql
SELECT
  COUNT(DISTINCT s.customer_id) AS customer_count,
  COUNT(DISTINCT CASE WHEN s.plan_id <> '0' and s.plan_id <> '4' THEN s.customer_id END) AS plan_count,
  ROUND(COUNT(DISTINCT CASE WHEN s.plan_id <> '0' and s.plan_id <> '4' THEN s.customer_id END) * 100.0 / COUNT(DISTINCT s.customer_id), 1) AS plan_percentage
FROM foodie_fi.subscriptions AS s
INNER JOIN (
  SELECT customer_id
  FROM foodie_fi.subscriptions
  WHERE plan_id = '0'
) AS t ON s.customer_id = t.customer_id;
```

What is the customer count and percentage breakdown of all 5 plan_name values at 2020-12-31?
- Only churn with 1 customer was present at the specify date.
```sql
SELECT p.plan_name, COUNT(*) AS count
FROM foodie_fi.subscriptions AS s
INNER JOIN foodie_fi.plans AS p ON s.plan_id = p.plan_id
WHERE s.start_date = '2020-12-31'
GROUP BY p.plan_name;
```

How many customers have upgraded to an annual plan in 2020?
- the total customer were 195 in the year 2020
```sql
SELECT p.plan_name, COUNT(*) AS count
FROM foodie_fi.subscriptions AS s
INNER JOIN foodie_fi.plans AS p ON s.plan_id = p.plan_id
WHERE EXTRACT(YEAR FROM s.start_date) = 2020 and p.plan_name='pro annual'
GROUP BY p.plan_name;
```

How many days on average does it take for a customer to an annual plan from the day they join Foodie-Fi?
- In average it took customer 101 days before they went to pro annual
```sql
SELECT
  ROUND(AVG(a.switch_date - s.start_date),1) AS average_days_to_annual_plan
FROM foodie_fi.subscriptions AS s
INNER JOIN (
  SELECT customer_id, MIN(start_date) AS switch_date
  FROM foodie_fi.subscriptions
  WHERE plan_id = '3'
  GROUP BY customer_id
) AS a ON s.customer_id = a.customer_id
WHERE s.plan_id <> '3';
```

Can you further breakdown this average value into 30 day periods (i.e. 0-30 days, 31-60 days etc)
```sql
SELECT
  CASE
    WHEN days <= 30 THEN '0-30 days'
    WHEN days <= 60 THEN '31-60 days'
    WHEN days <= 90 THEN '61-90 days'
    ELSE 'More than 90 days'
  END AS period,
  COUNT(*) AS count
FROM (
  SELECT
    s.customer_id,
    ROUND(a.switch_date - s.start_date,1) AS  days
  FROM foodie_fi.subscriptions AS s
  INNER JOIN (
    SELECT customer_id, MIN(start_date) AS switch_date
    FROM foodie_fi.subscriptions
    WHERE plan_id = 3
    GROUP BY customer_id
  ) AS a ON s.customer_id = a.customer_id
  WHERE s.plan_id <> 3
) AS subquery
GROUP BY period
ORDER BY MIN(days);
```

How many customers downgraded from a pro monthly to a basic monthly plan in 2020?
```sql

```

# **C. Challenge Payment Question**

The Foodie-Fi team wants you to create a new payments table for the year 2020 that includes amounts paid by each customer in the subscriptions table with the following requirements:

- Monthly payments always occur on the same day of month as the original start_date of any monthly paid plan
- Upgrades from basic to monthly or pro plans are reduced by the current paid amount in that month and start immediately
- Upgrades from pro monthly to pro annual are paid at the end of the current billing period and also starts at the end of the month period
- Once a customer churns they will no longer make payments

Example outputs for this table might look like the following:
![](https://i.imgur.com/Ny16ESX.png)


# **D. Outside The Box Questions**

The following are open ended questions which might be asked during a technical interview for this case study - there are no right or wrong answers, but answers that make sense from both a technical and a business perspective make an amazing impression!

How would you calculate the rate of growth for Foodie-Fi?

What key metrics would you recommend Foodie-Fi management to track over time to assess performance of their overall business?

What are some key customer journeys or experiences that you would analyse further to improve customer retention?

If the Foodie-Fi team were to create an exit survey shown to customers who wish to cancel their subscription, what questions would you include in the survey?

What business levers could the Foodie-Fi team use to reduce the customer churn rate? How would you validate the effectiveness of your ideas?