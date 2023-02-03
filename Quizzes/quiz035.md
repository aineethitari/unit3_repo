# Quiz 35

![2022  Quizzes (14)](https://user-images.githubusercontent.com/112055062/216630718-bf0817eb-8049-41f8-9464-27a03d4cb2fd.jpg)

## Code
```.py
import random
class Account:
    def __init__(self):
        self.balance = 0
        self.holder_name = ""
        self.holder_email = ""
        a = random.randint(100,1000)
        b = random.randint(10000,100000)
        c = random.randint(0,10)
        self.number = [a,b,c]
    def set_holder_name(self, name:str)->str:
        if not isinstance(name,str):
            raise ValueError("Error. The Name has to be a string")
        self.holder_name = name
        return f"Holder's name set to {self.holder_name}"
    def set_holder_email(self, email:str)->str:
        if email.count("@") != 1:
            raise ValueError("Error. Wrong email format")
        self.holder_email = email

        return f"Holder's email set to {self.holder_email}"
    def get_balance(self)->int:
        return self.balance
    def deposit(self,amount:int)->str:
        self.balance += amount
        return f"New balance: {self.balance} USD"
    def get_account_no(self)->str:
        a, b, c = self.number
        return f"Holder's account number is {a}--{b}--{c}"
```

## Test

<img width="896" alt="test quiz 35" src="https://user-images.githubusercontent.com/112055062/216654498-76215aa0-fbcc-45c8-bd46-62831e2a7653.png">
