# Quiz 45
## Create the UML Diagram

![UML diagram check fraud](https://user-images.githubusercontent.com/112055062/225951820-67d7abeb-b115-47a2-a574-ab5ec64a3f29.jpeg)


## Create the SQL queries to find the responsible for the fraudulent transaction.
```.sql
SELECT account_id, sum(amount) as total_deposit FROM transactions where transaction_type = 'deposit' GROUP BY account_id; total deposit
SELECT account_id, sum(amount) as total_withdraw FROM transactions where transaction_type = 'withdraw' GROUP BY account_id; total withdraw
SELECT CASE WHEN total_deposit - total_withdraw != balance THEN 'wrong' ELSE 'good'
END AS 'Check', total_deposit, total_withdraw, balance, account_id
FROM (SELECT sum(amount) as total_deposit, account_id as 'account_deposit' FROM transactions where transaction_type = 'deposit' GROUP BY account_id ),
     (SELECT sum(amount) as total_withdraw, account_id as 'account_withdraw' FROM transactions where transaction_type = 'withdraw' GROUP BY account_id),
     accounts WHERE account_deposit = account_withdraw and account_deposit = accounts.account_id;
```

<img width="862" alt="check fraud" src="https://user-images.githubusercontent.com/112055062/225944040-8068fdb7-abfa-4439-99f3-384937203c57.png">

## What is the name of the customer and the problem that resulted in the bankruptcy of the bank?
```.sql
SELECT customer_id, first_name, last_name from customers WHERE customer_id in (12,13,15,17,19)
```
<img width="533" alt="fraud customers" src="https://user-images.githubusercontent.com/112055062/225945212-f72d0230-2f7e-4b37-b90d-da67d8dea68e.png">
The total balance does not match the deposited and withdraw amount.

