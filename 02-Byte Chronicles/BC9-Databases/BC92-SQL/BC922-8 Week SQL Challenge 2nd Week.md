---
index: BC922
tags: 8-week-sql-challenge, sql, practice
status: Completed
created: 2023-05-06 14:45
updated: <%+ tp.file.last_modified_date() %>
author: sarwesh maharjan
---
Related: [[BC923-8 Week SQL Challenge 3rd Week]], [[BC921-8 Week SQL challenge 1st Week]]
URL: [link](https://8weeksqlchallenge.com/case-study-2/)

---
# **A. Pizza Metrics**

How many pizzas were ordered?
```sql
SELECT COUNT(pizza_runner.customer_orders.pizza_id) as total_pizza FROM pizza_runner.customer_orders;
```

How many unique customer orders were made?
```sql
SELECT COUNT(DISTINCT pizza_runner.customer_orders.order_id) as total_pizza FROM pizza_runner.customer_orders;
```

How many successful orders were delivered by each runner?
```sql
SELECT pizza_runner.runner_orders.runner_id, COUNT(pizza_runner.runner_orders.order_id) AS Sucessful_delivery FROM pizza_runner.runner_orders WHERE pizza_runner.runner_orders.pickup_time <> 'null' GROUP BY pizza_runner.runner_orders.runner_id;
```

How many of each type of pizza was delivered?
```sql
SELECT pn.pizza_name, COUNT(*) as ordered FROM pizza_runner.customer_orders as co INNER JOIN pizza_runner.runner_orders as ro ON ro.order_id = co.order_id LEFT JOIN pizza_runner.pizza_names as pn ON co.pizza_id = pn.pizza_id WHERE ro.pickup_time <> 'null' GROUP BY pn.pizza_name;
```

How many Vegetarian and Meatlovers were ordered by each customer?
```sql
SELECT co.customer_id, pn.pizza_name, COUNT(*) FROM pizza_runner.customer_orders as co INNER JOIN pizza_runner.runner_orders as ro ON ro.order_id = co.order_id LEFT JOIN pizza_runner.pizza_names as pn ON co.pizza_id = pn.pizza_id GROUP BY co.customer_id, pn.pizza_name;
```

What was the maximum number of pizzas delivered in a single order?
```sql
SELECT co.order_id, count(pn.pizza_name) as order_delivered FROM pizza_runner.customer_orders as co INNER JOIN pizza_runner.runner_orders as ro ON ro.order_id = co.order_id LEFT JOIN pizza_runner.pizza_names as pn ON co.pizza_id = pn.pizza_id WHERE ro.pickup_time <> 'null' GROUP BY co.order_id ORDER BY order_delivered DESC LIMIT 1;
```

For each customer, how many delivered pizzas had at least 1 change and how many had no changes?
```sql
WITH CTE AS ( SELECT co.customer_id, (co.exclusions <> 'null' AND co.exclusions IS NOT NULL AND LENGTH(co.exclusions) > 0) as changes, (co.extras <> 'null' AND co.extras IS NOT NULL AND LENGTH(co.extras) > 0) as changes_extra FROM pizza_runner.customer_orders as co INNER JOIN pizza_runner.runner_orders as ro ON ro.order_id = co.order_id WHERE ro.pickup_time <> 'null') SELECT customer_id, COUNT(changes) FROM CTE WHERE changes = true OR changes_extra = true GROUP BY customer_id;
```

How many pizzas were delivered that had both exclusions and extras?
```sql
WITH CTE AS ( SELECT co.customer_id, co.exclusions, co.extras, (co.exclusions <> 'null' AND co.exclusions IS NOT NULL AND LENGTH(co.exclusions) > 0) AND (co.extras <> 'null' AND co.extras IS NOT NULL AND LENGTH(co.extras) > 0) as changes_extra FROM pizza_runner.customer_orders as co INNER JOIN pizza_runner.runner_orders as ro ON ro.order_id = co.order_id WHERE ro.pickup_time <> 'null') SELECT COUNT(*) as total_pizza_delivery FROM CTE WHERE changes_extra = true;
```

What was the total volume of pizzas ordered for each hour of the day?
```sql
SELECT DATE_PART('hour',co.order_time), COUNT(*) FROM pizza_runner.customer_orders as co GROUP BY DATE_PART('hour',co.order_time);
```

What was the volume of orders for each day of the week?
```sql
SELECT DATE_PART('dow',co.order_time), COUNT(*) FROM pizza_runner.customer_orders as co GROUP BY DATE_PART('dow',co.order_time);
```

# **B. Runner and Customer Experience**

How many runners signed up for each 1 week period? (i.e. week starts 2021-01-01)
        -   SELECT COUNT(*) as signed_up, DATE_TRUNC('week',r.registration_date) + INTERVAL '4' DAY as start_of_week FROM pizza_runner.runners as r GROUP BY start_of_week;

What was the average time in minutes it took for each runner to arrive at the Pizza Runner HQ to pickup the order?
        -   SELECT ro.runner_id, AVG(EXTRACT(minute FROM (ro.pickup_time::timestamp - co.order_time)))::integer FROM pizza_runner.runner_orders as ro INNER JOIN pizza_runner.customer_orders as co ON co.order_id = ro.order_id WHERE ro.pickup_time <> 'null' GROUP BY ro.runner_id;
Is there any relationship between the number of pizzas and how long the order takes to prepare?
```sql
WITH CTE AS ( SELECT ro.order_id,COUNT(co.pizza_id) as no_of_pizza, MAX(EXTRACT(minute FROM (ro.pickup_time::timestamp - co.order_time)))::integer as prep_time FROM pizza_runner.runner_orders as ro INNER JOIN pizza_runner.customer_orders as co ON co.order_id = ro.order_id WHERE ro.pickup_time <> 'null' GROUP BY ro.order_id) SELECT no_of_pizza, AVG(prep_time)::integer FROM CTE GROUP BY no_of_pizza ORDER BY no_of_pizza;
```

What was the average distance travelled for each customer?
```sql
SELECT co.customer_id, AVG(substring(ro.distance, '^[0-9]+')::integer)::integer as average_distance FROM pizza_runner.runner_orders as ro INNER JOIN pizza_runner.customer_orders as co ON co.order_id = ro.order_id GROUP BY co.customer_id;
```

What was the difference between the longest and shortest delivery times for all orders?
```sql
SELECT MAX(substring(ro.duration, '^[0-9]+')::integer)::integer - MIN(substring(ro.duration, '^[0-9]+')::integer)::integer as average_distance FROM pizza_runner.runner_orders as ro INNER JOIN pizza_runner.customer_orders as co ON co.order_id = ro.order_id WHERE ro.duration <> 'null';
```

What was the average speed for each runner for each delivery and do you notice any trend for these values?
```sql
SELECT ro.runner_id,AVG(substring(ro.distance, '^[0-9]+')::integer / (substring(ro.duration, '^[0-9]+')::integer / 60.0)) as avg_speed_travel FROM pizza_runner.runner_orders as ro INNER JOIN pizza_runner.customer_orders as co ON co.order_id = ro.order_id WHERE ro.duration <> 'null' GROUP BY ro.runner_id;
```

What is the successful delivery percentage for each runner?
```sql
SELECT ro.runner_id, SUM(CASE WHEN ro.pickup_time = 'null' THEN 0 ELSE 1 END) / COUNT(ro.order_id)::float as succesful_per_delivery FROM pizza_runner.runner_orders as ro GROUP BY ro.runner_id;
```

# **C. Ingredient Optimisation**

What are the standard ingredients for each pizza?
```sql
SELECT pt.topping_name FROM pizza_runner.pizza_recipes AS pr LEFT JOIN LATERAL unnest(string_to_array(pr.toppings, ',')) AS S(value) ON true INNER JOIN pizza_runner.pizza_toppings AS pt ON pt.topping_id = S.value::integer GROUP BY pt.topping_name HAVING COUNT(DISTINCT pr.pizza_id) = 2;
```

What was the most commonly added extra?
```sql
SELECT pt.topping_name, SUM(S.value::integer) as most_commonly FROM pizza_runner.customer_orders AS co LEFT JOIN LATERAL unnest(string_to_array(co.extras, ',')) AS S(value) ON true INNER JOIN pizza_runner.pizza_toppings as pt on pt.topping_id = S.value::integer WHERE S.value <> 'null' GROUP BY pt.topping_name ORDER BY most_commonly DESC LIMIT 1;
```

What was the most common exclusion?
```sql
SELECT pt.topping_name, SUM(S.value::integer) as most_commonly FROM pizza_runner.customer_orders AS co LEFT JOIN LATERAL unnest(string_to_array(co.exclusions, ',')) AS S(value) ON true INNER JOIN pizza_runner.pizza_toppings as pt on pt.topping_id = S.value::integer WHERE S.value <> 'null' GROUP BY pt.topping_name ORDER BY most_commonly DESC LIMIT 1;
```

Generate an order item for each record in the customers_orders table in the format of one of the following:
        -   Meat Lovers
        -   Meat Lovers - Exclude Beef
        -   Meat Lovers - Extra Bacon
        -   Meat Lovers - Exclude Cheese, Bacon - Extra Mushroom, Peppers
```sql
WITH EXTRA AS ( SELECT co.order_id, co.pizza_id, co.extras, STRING_AGG(DISTINCT pt.topping_name, ', ') as topping_extra FROM pizza_runner.customer_orders AS co LEFT JOIN LATERAL unnest(string_to_array(co.extras, ',')) AS S(value) ON true INNER JOIN pizza_runner.pizza_toppings as pt on pt.topping_id = S.value::integer WHERE S.value <> 'null' GROUP BY co.order_id, co.pizza_id, co.extras ), EXCLUSION AS ( SELECT co.order_id, co.pizza_id,co.exclusions, STRING_AGG(DISTINCT pt.topping_name, ', ') as topping_exclusion FROM pizza_runner.customer_orders AS co LEFT JOIN LATERAL unnest(string_to_array(co.exclusions, ',')) AS S(value) ON true INNER JOIN pizza_runner.pizza_toppings as pt on pt.topping_id = S.value::integer WHERE S.value <> 'null' GROUP BY co.order_id, co.pizza_id,co.exclusions ) SELECT co.order_id, pn.pizza_name, co.pizza_id, CONCAT (CASE When pn.pizza_name = 'Meatlovers' THEN 'Meat Lovers' ELSE pn.pizza_name END, COALESCE(' - Exclude ' || ex.topping_exclusion, '' ), COALESCE(' - Extra ' || et.topping_extra, '' ) )as added_extra FROM pizza_runner.customer_orders as co LEFT JOIN EXTRA as et ON et.order_id = co.order_id AND et.pizza_id = co.pizza_id AND et.extras = co.extras LEFT JOIN EXCLUSION as ex ON ex.order_id = co.order_id AND ex.pizza_id = co.pizza_id AND ex.exclusions = co.exclusions INNER JOIN pizza_runner.pizza_names as pn ON pn.pizza_id = co.pizza_id;
```

Generate an alphabetically ordered comma separated ingredient list for each pizza order from the customer_orders table and add a 2x in front of any relevant ingredients
        -   For example: "Meat Lovers: 2xBacon, Beef, ... , Salami"
```sql
WITH EXCLUSIONS AS ( SELECT co.order_id, co.pizza_id, S.value as topping_id FROM pizza_runner.customer_orders as co LEFT JOIN LATERAL unnest(string_to_array(co.exclusions, ',')) AS S(value) ON true WHERE LENGTH(value)>0 AND value<>'null' ), EXTRAS AS ( SELECT co.order_id, co.pizza_id, S.value as topping_id, T.topping_name FROM pizza_runner.customer_orders as co LEFT JOIN LATERAL unnest(string_to_array(co.extras, ',')) AS S(value) ON true INNER JOIN pizza_runner.pizza_toppings as T on t.topping_id = S.value::integer WHERE LENGTH(value)>0 AND value<>'null' ), ORDERS AS ( SELECT DISTINCT CO.order_id, CO.pizza_id, S.value as topping_id, T.topping_name FROM pizza_runner.customer_orders as CO INNER JOIN pizza_runner.pizza_recipes as PR on CO.pizza_id = PR.pizza_id LEFT JOIN LATERAL unnest(string_to_array(PR.toppings, ',')) AS S(value) ON true INNER JOIN pizza_runner.pizza_toppings as T on t.topping_id = S.value::integer ), ORDERS_WITH_EXTRAS_AND_EXCLUSIONS AS ( SELECT O.order_id, O.pizza_id, O.topping_id::int as topping_id, O.topping_name FROM ORDERS AS O LEFT JOIN EXCLUSIONS AS EXC ON EXC.order_id=O.order_id AND EXC.pizza_id=O.pizza_id AND EXC.topping_id=O.topping_id WHERE EXC.topping_id IS NULL UNION ALL SELECT ET.order_id, ET.pizza_id, ET.topping_id::int as topping_id, ET.topping_name FROM EXTRAS AS ET WHERE ET.topping_id<>'' ), TOPPING_COUNT AS ( SELECT O.order_id, O.pizza_id, O.topping_name, COUNT(*) as n FROM ORDERS_WITH_EXTRAS_AND_EXCLUSIONS as O GROUP BY O.order_id, O.pizza_id, O.topping_name ) SELECT TC.order_id, TC.pizza_id, STRING_AGG( CASE WHEN n>1 THEN n || 'x' || TC.topping_name ELSE TC.topping_name END,', ') as ingredient FROM TOPPING_COUNT AS TC GROUP BY TC.order_id, TC.pizza_id;WITH EXCLUSIONS AS ( SELECT co.order_id, co.pizza_id, S.value as topping_id FROM pizza_runner.customer_orders as co LEFT JOIN LATERAL unnest(string_to_array(co.exclusions, ',')) AS S(value) ON true WHERE LENGTH(value)>0 AND value<>'null' ), EXTRAS AS ( SELECT co.order_id, co.pizza_id, S.value as topping_id, T.topping_name FROM pizza_runner.customer_orders as co LEFT JOIN LATERAL unnest(string_to_array(co.extras, ',')) AS S(value) ON true INNER JOIN pizza_runner.pizza_toppings as T on t.topping_id = S.value::integer WHERE LENGTH(value)>0 AND value<>'null' ), ORDERS AS ( SELECT DISTINCT CO.order_id, CO.pizza_id, S.value as topping_id, T.topping_name FROM pizza_runner.customer_orders as CO INNER JOIN pizza_runner.pizza_recipes as PR on CO.pizza_id = PR.pizza_id LEFT JOIN LATERAL unnest(string_to_array(PR.toppings, ',')) AS S(value) ON true INNER JOIN pizza_runner.pizza_toppings as T on t.topping_id = S.value::integer )
```

What is the total quantity of each ingredient used in all delivered pizzas sorted by most frequent first?
```sql
WITH EXCLUSIONS AS ( SELECT co.order_id, co.pizza_id, S.value as topping_id FROM pizza_runner.customer_orders as co LEFT JOIN LATERAL unnest(string_to_array(co.exclusions, ',')) AS S(value) ON true WHERE LENGTH(value)>0 AND value<>'null' ), EXTRAS AS ( SELECT co.order_id, co.pizza_id, S.value as topping_id, T.topping_name FROM pizza_runner.customer_orders as co LEFT JOIN LATERAL unnest(string_to_array(co.extras, ',')) AS S(value) ON true INNER JOIN pizza_runner.pizza_toppings as T on t.topping_id = S.value::integer WHERE LENGTH(value)>0 AND value<>'null' ), ORDERS AS ( SELECT DISTINCT CO.order_id, CO.pizza_id, S.value as topping_id, T.topping_name FROM pizza_runner.customer_orders as CO INNER JOIN pizza_runner.pizza_recipes as PR on CO.pizza_id = PR.pizza_id LEFT JOIN LATERAL unnest(string_to_array(PR.toppings, ',')) AS S(value) ON true INNER JOIN pizza_runner.pizza_toppings as T on t.topping_id = S.value::integer ), ORDERS_WITH_EXTRAS_AND_EXCLUSIONS AS ( SELECT O.order_id, O.pizza_id, O.topping_id::int as topping_id, O.topping_name FROM ORDERS AS O LEFT JOIN EXCLUSIONS AS EXC ON EXC.order_id=O.order_id AND EXC.pizza_id=O.pizza_id AND EXC.topping_id=O.topping_id WHERE EXC.topping_id IS NULL UNION ALL SELECT ET.order_id, ET.pizza_id, ET.topping_id::int as topping_id, ET.topping_name FROM EXTRAS AS ET WHERE ET.topping_id<>'' ) SELECT O.topping_name, COUNT(O.pizza_id) as ingredient_count FROM ORDERS_WITH_EXTRAS_AND_EXCLUSIONS as O INNER JOIN pizza_runner.runner_orders as ro on O.order_id = ro.order_id WHERE ro.pickup_time<>'null' GROUP BY O.topping_name ORDER BY COUNT(O.pizza_id) DESC
```

# **D. Pricing and Ratings**

If a Meat Lovers pizza costs $12 and Vegetarian costs $10 and there were no charges for changes 

How much money has Pizza Runner made so far if there are no delivery fees?
```sql
SELECT SUM(CASE WHEN pn.pizza_name = 'Meatlovers' then 12 ElSE 10 END)as total_pizza_price FROM pizza_runner.customer_orders as co INNER JOIN pizza_runner.pizza_names as pn ON pn.pizza_id = co.pizza_id;
```

What if there was an additional $1 charge for any pizza extras?
        -   Add cheese is $1 extra
```sql
SELECT SUM(CASE WHEN pn.pizza_name = 'Meatlovers' AND pt.topping_name = 'Cheese' THEN 13 WHEN pn.pizza_name = 'Vegetarian' AND pt.topping_name = 'Cheese' THEN 11 WHEN pn.pizza_name = 'Meatlovers' THEN 12 WHEN pn.pizza_name = 'Vegetarian' THEN 10 END) as total_price FROM pizza_runner.customer_orders AS co LEFT JOIN LATERAL unnest(string_to_array(co.extras, ',')) AS S(value) ON S.value <> 'null' LEFT JOIN pizza_runner.pizza_toppings as pt on pt.topping_id = S.value::integer INNER JOIN pizza_runner.pizza_names as pn on pn.pizza_id = co.pizza_id;
```

The Pizza Runner team now wants to add an additional ratings system that allows customers to rate their runner, how would you design an additional table for this new dataset - generate a schema for this new table and insert your own data for ratings for each successful customer order between 1 to 5.
```sql
DROP TABLE IF EXISTS customer_ratings; CREATE TABLE pizza_runner.customer_ratings ( rating_id SERIAL PRIMARY KEY, order_id INT NOT NULL, customer_id INT NOT NULL, runner_id INT NOT NULL, rating INT NOT NULL, comment TEXT ); INSERT INTO pizza_runner.customer_ratings (order_id, customer_id, runner_id, rating, comment) VALUES (1, 1, 1, 4, 'Great service from the runner!'); INSERT INTO pizza_runner.customer_ratings (order_id, customer_id, runner_id, rating, comment) VALUES (2, 2, 2, 3, 'The runner was a bit late.'); INSERT INTO pizza_runner.customer_ratings (order_id, customer_id, runner_id, rating, comment) VALUES (3, 3, 1, 5, 'The runner was really friendly and arrived on time.'); INSERT INTO pizza_runner.customer_ratings (order_id, customer_id, runner_id, rating, comment) VALUES (4, 2, 3, 2, 'The runner forgot some of the items.'); INSERT INTO pizza_runner.customer_ratings (order_id, customer_id, runner_id, rating, comment) VALUES (5, 1, 2, 5, 'The runner was very fast and the pizza was still hot!'); INSERT INTO pizza_runner.customer_ratings (order_id, customer_id, runner_id, rating, comment) VALUES (6, 3, 3, 4, 'The runner communicated well and the delivery was smooth.');
```

 Using your newly generated table - can you join all of the information together to form a table which has the following information for successful deliveries?
        -   customer_id
        -   order_id
        -   runner_id
        -   rating
        -   order_time
        -   pickup_time
        -   Time between order and pickup
        -   Delivery duration
        -   Average speed
        -   Total number of pizzas
```sql
SELECT co.customer_id, co.order_id, ro.runner_id, cr.rating, co.order_time, ro.pickup_time, EXTRACT(minute FROM (ro.pickup_time::timestamp - co.order_time))::integer as time_between, ro.duration, ROUND(AVG(substring(ro.distance, '^[0-9]+')::integer / (substring(ro.duration, '^[0-9]+')::integer / 60.0)),2) as avg_speed, COUNT(co.pizza_id) as total_pizza FROM pizza_runner.customer_orders as co INNER JOIN pizza_runner.customer_ratings as cr ON cr.order_id = co.order_id INNER JOIN pizza_runner.runner_orders as ro ON ro.order_id = ro.order_id WHERE ro.pickup_time <> 'null' GROUP BY co.customer_id, co.order_id, ro.runner_id, cr.rating, co.order_time, ro.pickup_time, time_between, ro.duration;
```

If a Meat Lovers pizza was $12 and Vegetarian $10 fixed prices with no cost for extras and each runner is paid $0.30 per kilometre traveled - how much money does Pizza Runner have left over after these deliveries?
```sql
WITH CHARGE AS ( SELECT SUM(CASE WHEN pn.pizza_name = 'Meatlovers' then 12 ElSE 10 END)as total_pizza_price, SUM(substring(ro.distance, '^[0-9]+')::integer) * 0.30 as total_delivery_charge FROM pizza_runner.customer_orders as co INNER JOIN pizza_runner.pizza_names as pn ON pn.pizza_id = co.pizza_id INNER JOIN pizza_runner.runner_orders as ro ON ro.order_id = co.order_id) SELECT *, total_pizza_price - total_delivery_charge as profit FROM CHARGE;
```