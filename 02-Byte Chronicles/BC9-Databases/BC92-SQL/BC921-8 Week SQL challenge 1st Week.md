---
index: BC921
tags: 8-week-sql-challenge, sql, practice
status: Completed
created: 2023-05-06 14:45
updated: <%+ tp.file.last_modified_date() %>
author: sarwesh maharjan
---
Related: [[BC922-8 Week SQL Challenge 2nd Week]], [[BC923-8 Week SQL Challenge 3rd Week]]
URL: [link](https://8weeksqlchallenge.com/case-study-1/)

---


What is the total amount each customer spent at the restaurant?
```sql
SELECT dannys_diner.sales.customer_id, sum(dannys_diner.menu.price) FROM dannys_diner.menu INNER JOIN dannys_diner.sales ON dannys_diner.menu.product_id = dannys_diner.sales.product_id GROUP BY dannys_diner.sales.customer_id;
```


How many days has each customer visited the restaurant?
```sql
SELECT dannys_diner.sales.customer_id, count(DISTINCT dannys_diner.sales.order_date) FROM dannys_diner.menu INNER JOIN dannys_diner.sales ON dannys_diner.menu.product_id = dannys_diner.sales.product_id GROUP BY dannys_diner.sales.customer_id;
```

What was the first item from the menu purchased by each customer?
```sql
SELECT dannys_diner.sales.customer_id, MIN(dannys_diner.menu.price), MIN(dannys_diner.sales.order_date) FROM dannys_diner.menu INNER JOIN dannys_diner.sales ON dannys_diner.menu.product_id = dannys_diner.sales.product_id GROUP BY dannys_diner.sales.customer_id ORDER BY dannys_diner.sales.customer_id;
```

What is the most purchased item on the menu and how many times was it purchased by all customers?
```sql
SELECT COUNT(dannys_diner.sales.customer_id) as count, dannys_diner.menu.product_name FROM dannys_diner.menu INNER JOIN dannys_diner.sales ON dannys_diner.menu.product_id = dannys_diner.sales.product_id GROUP BY dannys_diner.menu.product_name ORDER BY count DESC LIMIT 1;
```

Which item was the most popular for each customer?
```sql
 SELECT popular_table.cid, MAX(popular_table.popular) FROM ( SELECT dannys_diner.sales.customer_id as cid, COUNT(*) as popular, dannys_diner.menu.product_name as menu FROM dannys_diner.menu INNER JOIN dannys_diner.sales ON dannys_diner.menu.product_id = dannys_diner.sales.product_id GROUP BY dannys_diner.sales.customer_id, dannys_diner.menu.product_name ORDER BY dannys_diner.sales.customer_id, popular DESC) AS popular_table GROUP BY popular_table.cid;
```

Which item was purchased first by the customer after they became a member?
```sql
SELECT dannys_diner.sales.customer_id as cid,MIN(dannys_diner.sales.order_date) FROM dannys_diner.sales INNER JOIN dannys_diner.members ON dannys_diner.sales.customer_id = dannys_diner.members.customer_id WHERE dannys_diner.sales.order_date > dannys_diner.members.join_date GROUP BY cid;
```

Which item was purchased just before the customer became a member?
```sql
SELECT dannys_diner.sales.customer_id as cid,MAX(dannys_diner.sales.order_date) FROM dannys_diner.sales INNER JOIN dannys_diner.members ON dannys_diner.sales.customer_id = dannys_diner.members.customer_id WHERE dannys_diner.sales.order_date < dannys_diner.members.join_date GROUP BY cid;
```

What is the total items and amount spent for each member before they became a member?
```sql
SELECT t.cid, SUM(t.amount), COUNT(t.item) FROM (SELECT dannys_diner.menu.price as amount, dannys_diner.sales.customer_id as cid, dannys_diner.members.join_date as jdate, dannys_diner.menu.product_name as item, dannys_diner.sales.order_date as odate FROM dannys_diner.sales LEFT JOIN dannys_diner.members ON dannys_diner.sales.customer_id = dannys_diner.members.customer_id LEFT JOIN dannys_diner.menu ON dannys_diner.sales.product_id = dannys_diner.menu.product_id) as t WHERE jdate < odate GROUP BY t.cid;
```

If each $1 spent equates to 10 points and sushi has a 2x points multiplier - how many points would each customer have?
```sql
 SELECT t.cid, SUM( CASE WHEN t.menu <> 'sushi' THEN t.total*2 ELSE t.total END ) FROM ( SELECT popular_table.cid, popular_table.total, popular_table.menu FROM ( SELECT dannys_diner.sales.customer_id as cid, SUM(dannys_diner.menu.price) as total, dannys_diner.menu.product_name as menu FROM dannys_diner.menu INNER JOIN dannys_diner.sales ON dannys_diner.menu.product_id = dannys_diner.sales.product_id GROUP BY dannys_diner.sales.customer_id, dannys_diner.menu.product_name ORDER BY dannys_diner.sales.customer_id, total DESC) AS popular_table) AS t GROUP BY t.cid;
```

In the first week after a customer joins the program (including their join date) they earn 2x points on all items, not just sushi - how many points do customer A and B have at the end of January?
```sql
SELECT t.cid, SUM( CASE WHEN DATE_PART('week',t.jdate) = 1 AND DATE_PART('year', t.jdate) = 2022 THEN t.amount*2 else t.amount END ) FROM (SELECT dannys_diner.menu.price as amount, dannys_diner.sales.customer_id as cid, dannys_diner.members.join_date as jdate, dannys_diner.menu.product_name as item, dannys_diner.sales.order_date as odate FROM dannys_diner.sales LEFT JOIN dannys_diner.members ON dannys_diner.sales.customer_id = dannys_diner.members.customer_id LEFT JOIN dannys_diner.menu ON dannys_diner.sales.product_id = dannys_diner.menu.product_id) as t GROUP BY t.cid;
```