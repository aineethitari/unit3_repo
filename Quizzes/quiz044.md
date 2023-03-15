# Quiz 44
## Solve these questions
1. How many tables are there in the database?
```
SELECT count(*) from sqlite_master WHERE type is 'table';
```
![quiz 44 q1](https://user-images.githubusercontent.com/112055062/225382589-c3c5776b-898b-4398-9168-a62103057489.png)

ANS: 3 Tables

2. How many Male inhabitants are Friendly?
```
SELECT count(*) from INHABITANT WHERE gender is 'Male' and state is 'Friendly';
```
![quiz44 q1](https://user-images.githubusercontent.com/112055062/225381981-e42058c9-af4b-4242-a26a-a9312a3a57d0.png)
ANS: 4 inhabitants

3. What is the average gold by village?

```
SELECT avg(gold), villageid from INHABITANT GROUP BY villageid;
```

![quiz44 q3](https://user-images.githubusercontent.com/112055062/225384245-8232b3dc-9afb-49da-bf8c-f325324ee76b.png)

4. How many items are there that start with the letter “A”

```
SELECT count(*) from ITEM where item like 'A%';
```

![quiz44 q4](https://user-images.githubusercontent.com/112055062/225385113-c6420f3a-fb79-475a-bed3-01824fd7859c.png)

ANS: 3 items

8. How many different jobs are there? 
9. What are the items owned by the herbalists?
