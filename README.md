 ## The Complete SQL Bootcamp (Udemy) -  Assessment Solutions 

🧠 Course Overview

This repository contains my hands-on solutions and query breakdowns from the The Complete SQL Bootcamp: Go from Zero to Hero course on Udemy, taught by Jose Portilla.

The course is designed to take learners from absolute beginners to intermediate-level SQL users by teaching real-world querying techniques using PostgreSQL. It covers topics such as filtering, joins, aggregation, subqueries, window functions, and more.

🗃️ Dataset Used
All exercises and assessments use a simulated DVD Rental database. This sample database includes tables like:

customer, payment, film, address, staff, and more, mimicking the structure of a real-world video rental store.

##  Assessment Test 1

---

### **1. Return the customer IDs of customers who have spent at least \$110 with the staff member who has an ID of 2.**


#### 💻 SQL Query:

```sql
SELECT customer_id, SUM(amount)
FROM payment
WHERE staff_id = 2
GROUP BY customer_id
HAVING SUM(amount) > 110;
```
🔍 Explanation:
- FROM payment: We're working with the payment table, which logs all transactions.
- WHERE staff_id = 2: Filters only transactions made by staff member with ID 2.
- GROUP BY customer_id: Groups the payments by each customer to calculate totals per customer.
- SUM(amount): Calculates the total amount each customer paid to staff member 2.
- HAVING SUM(amount) > 110: Returns only those customers whose total payments exceed $110.

#### 📸 Query Output:

<p align="center">
  <img src="https://i.imgur.com/R7pzFGC.png" height="60%" width="60%" alt="Replace"/>
</p>
<br />
<br />
---

### **2. How many films begin with the letter J?**

#### 💻 SQL Query:

```sql
SELECT COUNT(*) 
FROM film
WHERE title LIKE 'J%';
```
🔍 Explanation:
- FROM film: We are querying the film table, which holds movie records.
- WHERE title LIKE 'J%': Filters only the movies where the title starts with the letter 'J'.
- COUNT(*): Counts how many such titles exist.
-  % is a wildcard meaning "any number of characters," so 'J%' means any title starting with 'J'.

#### 📸 Query Output:
<p align="center">
  <img src="https://i.imgur.com/HflewIB.png" height="60%" width="60%" alt="Replace"/>
</p>
<br />
<br />
---

### **3. What customer has the highest customer ID number whose name starts with an 'E' and has an address ID lower than 500?**

#### 💻 SQL Query:

```sql
SELECT first_name, last_name 
FROM customer
WHERE first_name LIKE 'E%' 
  AND address_id < 500
ORDER BY customer_id DESC
LIMIT 1;
```
🔍 Explanation:
- FROM customer: We are working with the customer table.
- WHERE first_name LIKE 'E%': Filters customers whose first name starts with 'E'.
- AND address_id < 500: Only includes customers with an address ID less than 500.
- ORDER BY customer_id DESC: Sorts customers by customer ID in descending order (highest first).
- LIMIT 1: Returns only the top result, which will be the customer with the highest customer_id that matches the filters.

#### 📸 Query Output:

<p align="center">
  <img src="https://i.imgur.com/KX6du4h.png" height="60%" width="60%" alt="Replace"/>
</p>
<br />
<br />

---

More assessments to follow as I complete them. Stay tuned!

---
