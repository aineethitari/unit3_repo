# Quiz 34

![2022  Quizzes (13)](https://user-images.githubusercontent.com/112055062/216628877-5134b990-e853-48ba-8b6a-4f72288b0e85.jpg)

## Code
```.py
class to_roman:
    def __init__(self,num:int):
        if num < 101:
            self.num = num
        else:
            raise ValueError("Error number needs to be an integer")
    def solution(self):
        num = self.num
        roman = ""
        while num > 0:
            for item in [(100,"C"),(90,"XC"),(50,"L"),(40,"XL"),(10,"X"),(9,"IX"),(5,"V"),(4,"IV"),(1,"I")]:
                dec,rom = item
                if dec <= num:
                    num -= dec
                    roman += rom
                    break
        return roman
  ```
  ## Test
  
  <img width="661" alt="quiz 034 test" src="https://user-images.githubusercontent.com/112055062/216629849-b499955c-898b-4a19-bbdc-0a8681f485d8.png">
