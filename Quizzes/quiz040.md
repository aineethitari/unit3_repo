# Quiz 40

![2022  Quizzes (18)](https://user-images.githubusercontent.com/112055062/216755836-3a730c16-78dc-4e0c-b3d7-eca5bf1c6fec.jpg)

## Code
```.py
from kivymd.app import MDApp

class quiz040(MDApp):
    def __init__(self, **kwargs):
        super().__init__(**kwargs)


    def build(self):
        return

    def changebg(self,choice):
        if choice == "bright":
            self.root.ids.button.text = "Dark Mode"
            self.root.ids.word.color = "#000000"
            self.root.ids.box.md_bg_color = "#FFFFFF"
            self.root.ids.button.md_bg_color = "#73c5ff"

        elif choice == "dark":
            self.root.ids.button.text = "Bright Mode"
            self.root.ids.word.color = "#FFFFFF"
            self.root.ids.box.md_bg_color = "#000000"
            self.root.ids.button.md_bg_color = "#FF69B4"


test = quiz040()
test.run()
```

## Results

<img width="794" alt="quiz040 result bright" src="https://user-images.githubusercontent.com/112055062/216758611-2c254c80-4f22-48d8-a8fc-8cfec84b4557.png">

<img width="795" alt="quiz040 dark result" src="https://user-images.githubusercontent.com/112055062/216758616-f0b70320-3898-4a80-8ade-d2ef9b616609.png">
