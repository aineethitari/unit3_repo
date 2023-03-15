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

5. How many different jobs are there? 
```
SELECT count(distinct job) from  INHABITANT;
```
![quiz44 q5](https://user-images.githubusercontent.com/112055062/225385953-efe43b16-3444-48c8-b3e9-a088dce7bb0a.png)
 
 ANS: 15
 
9. What are the items owned by the herbalists?

```
SELECT personid from INHABITANT where job is 'Herbalist';
SELECT * from ITEM where owner is 4 or owner is 18;
```

![quiz 44 q 6 1](https://user-images.githubusercontent.com/112055062/225396708-0c0b34ba-ff41-4cd2-a52d-bd78add6fb62.png)

![quiz 44 q 6 2](https://user-images.githubusercontent.com/112055062/225396784-9261049e-ce72-4a93-ae58-1cc8f5c6103d.png)
