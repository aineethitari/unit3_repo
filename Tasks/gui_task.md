# GUI Building Task
## Example 1
### Python
```.py
from kivymd.app import MDApp

class example1(MDApp):
    def build(self):
        return

test = example1()
test.run()
```
### Kivy
```.kv
Screen:
    size: 500, 500

    MDLabel:
        text: "Hello World"
        halign: "center"
        font_size: "34pt"
```

<img width="1056" alt="Code" src="https://user-images.githubusercontent.com/112055062/215322319-14d59532-f41b-4aa6-84ff-1d56971b07a9.png">

<img width="798" alt="Helllo World" src="https://user-images.githubusercontent.com/112055062/215322240-d16b8a7e-2735-4213-96e5-2ecc035bad9d.png">

## Example 2
### Python
```.py
from kivymd.app import MDApp

class example2(MDApp):
    def build(self):
        return
    def close(self):
        exit()

test = example2()
test.run()
```
### Kivy
```.kv
Screen:
    size: 500,500
    MDBoxLayout:
        pos_hint: {"center_x":0.5}
        size_hint: .7,.7
        md_bg_color: "#fdfcdc"
        orientation: "vertical"

        MDLabel:
            text: "Hello World"
            halign: "center"
            font_size: "34pt"

        MDRaisedButton:
            text: "Close"
            size_hint: .5, 1
            font_size: "34pt"
            md_bg_color: "#f07167"
            pos_hint: {"center_x":0.5}
            on_press:
                app.close()
```
<img width="1070" alt="Example2" src="https://user-images.githubusercontent.com/112055062/215323031-aface0a9-d09e-4e66-9928-995b8f5b3d64.png">

<img width="798" alt="Example 2 run" src="https://user-images.githubusercontent.com/112055062/215323045-1b8c31c1-a9ef-4524-8d76-8ca7a717986a.png">

## Example 3
### Python
```.py
from kivymd.app import MDApp

class example3(MDApp):
    def build(self):
        return
    def change_author(self,name):
        self.root.ids.title.text = f"Author{name}"

test = example3()
test.run()
```
### Kivy
```.kv
Screen:
    size: 500, 500
    MDLabel:
        id: title
        text: ""
        font_style: "H1"
        pos_hint: {"center_y":.8}
        halign: "center"

    MDBoxLayout:
        pos_hint: {"center_x":.5,"center_y":.5}
        size_hint: .7, .2
        orientation: "horizontal"

        MDChip:
            text: "Author A"
            pos_hint: {"center_y": .5}
            icon_right: "close-circle-outline"
            md_bg_color: "#003049"
            text_color: "#FFFFFF"
            on_press: app.change_author("A")

        MDChip:
            text: "Author B"
            pos_hint: {"center_y": .5}
            icon_right: "close-circle-outline"
            md_bg_color: "#D62828"
            on_press: app.change_author("B")

        MDChip:
            text: "Author C"
            pos_hint: {"center_y":.5}
            icon_right: "close-circle-outline"
            md_bg_color: "#F77F00"
            on_press: app.change_author("C")

        MDChip:
            text: "Author D"
            pos_hint: {"center_y":.5}
            icon_right: "close-circle-outline"
            md_bg_color: "#FCBF49"
            on_press: app.change_author("D")

        MDChip:
            text: "Author E"
            pos_hint: {"center_y":.5}
            icon_right: "close-circle-outline"
            md_bg_color: "#EAE2B7"
            on_press: app.change_author("E")
```

<img width="1066" alt="code example 3" src="https://user-images.githubusercontent.com/112055062/215324089-20df4d81-ae3d-4122-8441-ad2e645605dd.png">

<img width="790" alt="example 3 run" src="https://user-images.githubusercontent.com/112055062/215324115-4c7b5fe7-4060-4da6-9a31-0043b4e6a6ce.png">

## Task 1
### Python

```.py
from kivymd.app import MDApp

class CurrencyConverter(MDApp):
    def __init__(self, **kwargs):
        super().__init__(**kwargs)
        self.thai = 0
        self.final = 0

    def build(self):
        pass # You should add the code to build the user interface here.

    def convert(self, currency:str):
        if self.root.ids.amount_thai.text.isdigit():
            if currency == "JPY":
                self.final = float(int(self.root.ids.amount_thai.text)) * 0.25
            if currency == "USD":
                self.final = float(int(self.root.ids.amount_thai.text)) * 32.78

            self.root.ids.converted_value.text = f"The converted value is {self.final:.2f} {currency}"
        else:
            self.root.ids.amount_thai.text = f"ERROR. Please enter numbers"


CurrencyConverter().run()
```

### Kivy
```.kv
Screen:
    size: 500, 500
    MDLabel:
        id: title
        text: "Currency Converter"
        font_style: "H1"
        pos_hint: {"center_y":.8}
        halign: "center"
        font_size: "38pt"

    MDTextField:
        id: amount_thai
        hint_text: "Enter amount in THB"
        mode: "fill"
        size_hint: .80,.15
        pos_hint: {"center_y":.5,"center_x":.5}
        halign: "center"

    MDBoxLayout:
        id: button
        orientation: "horizontal"
        size_hint: .4,.3
        pos_hint:  {"center_y":.2,"center_x":.5}

        MDChip:
            text: "JPY"
            pos_hint: {"center_y":.5, "center_x":.5}
            md_bg_color: "#D62828"
            on_press: app.convert("JPY")

        MDChip:
            text: "USD"
            pos_hint: {"center_y":.5, "center_x":.5}
            md_bg_color: "#F77F00"
            on_press: app.convert("USD")

    MDLabel:
        id: converted_value
        text: ""
        font_style: "H1"
        font_size: "34pt"
        pos_hint: {"center_y":.33}
        halign: "center"
```

<img width="795" alt="currencyconverter run" src="https://user-images.githubusercontent.com/112055062/215503962-d1159aa8-06a1-41c3-a503-7727b6e606b6.png">

<img width="798" alt="currency converter validat" src="https://user-images.githubusercontent.com/112055062/215511647-49d92d9b-637d-4d6f-b8fd-2549265ed658.png">

## Task 2
