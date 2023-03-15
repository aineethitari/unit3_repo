# Quiz 42 Mystery Page
## Python Code
```.py
from kivymd.app import MDApp
from kivymd.uix.screen import MDScreen

class MysteryPageA(MDScreen):
    def message1(self):
        self.ids.PageA.text = "This is mystery page A you pressed the button"
        print(f"This is mystery page A you pressed the button")


class MysteryPageB(MDScreen):
    def message2(self):
        print("This is mystery page B you pressed the button")
        self.ids.PageB.text = "This is mystery page B you pressed the button"


class quiz042(MDApp):
    def build(self):
        return

test = quiz042()
test.run()
```
## Kivy Code
```.kv
ScreenManager:
    MysteryPageA:
        name: "MysteryPageA"

    MysteryPageB:
        name: "MysteryPageB"

<MysteryPageA>:
    name: "MysteryPageA"
    MDBoxLayout:
        size_hint: 1,1
        pos_hint: {"center_x":.5, "center_y":.5}
        orientation: "vertical"
        spacing: dp(10)
        padding: dp(10)

        MDBoxLayout:
            size_hint: 1,.5
            pos_hint: {"center_x":.5, "center_y":.5}


            MDLabel:
                id: PageA
                text: "Press the button"
                size_hint: 1,1
                halign: "center"
                valign: "center"

        MDRaisedButton:
            size_hint: 1,.5
            text: "Go to Page B"
            pos_hint: {"center_x":.5, "center_y":.5}
            on_press: root.message1()
            on_press: app.root.current = "MysteryPageB"



<MysteryPageB>:
    name: "MysteryPageB"
    MDBoxLayout:
        size_hint: 1,1
        pos_hint: {"center_x":.5, "center_y":.5}
        orientation: "vertical"
        spacing: dp(10)
        padding: dp(10)

        MDBoxLayout:
            size_hint: 1,.5
            pos_hint: {"center_x":.5, "center_y":.5}



            MDLabel:
                id: PageB
                text: "This is mystery page B you pressed the button"
                size_hint: 1,1
                halign: "center"
                valign: "center"

        MDRaisedButton:
            size_hint: 1,.5
            text: "Go to Page A"
            pos_hint: {"center_x":.5, "center_y":.5}
            on_press: root.message2()
            on_press: app.root.current = "MysteryPageA"

```

## Result

video: https://youtu.be/h1SHVF3hjEM

