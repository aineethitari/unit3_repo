# Quiz 37

![2022  Quizzes (16)](https://user-images.githubusercontent.com/112055062/216683776-62b0e4ac-eaf8-4ece-8ade-c7d926474b67.jpg)

## Code

```.py
class CompoundInterest:
    def __init__(self, principal, rate, year):
        self.principal = principal
        self.rate = rate
        self.years = year

class AccountingProgram:
    def __init__(self):
        self.data = CompoundInterest(principal=0,rate=0,year=0) #composition
    def set_principal(self,principal):
        if principal < 0:
            raise ValueError("Principal should be greater than zero")
        else:
            self.data.principal = principal
        return principal
    def set_rate(self,rate):
        if rate < 0:
            raise ValueError("Interest rate should be greater than zero")
        else:
            self.data.rate = rate
        return rate
    def set_years(self,year:int):
        if year < 0:
            raise ValueError("Years should be greater than zero")
        else:
            self.data.year = year
        return year
    def calculate_interest(self):
        interest = self.data.principal * (1+self.data.rate)**self.data.year
        interest = float("{:.2f}".format(interest))
        return interest
```

## Test

<img width="702" alt="quiz 37 test" src="https://user-images.githubusercontent.com/112055062/216754172-4996b962-0820-4398-8c96-cbe7a4d91876.png">
