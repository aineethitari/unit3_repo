# Quiz 39
## Code
### Python

```.py
from kivymd.app import MDApp

class quiz039(MDApp):
    def __init__(self, **kwargs):
        super().__init__(**kwargs)
        self.count = 0

    def build(self):
        return

    def set_counter(self):
        #validate that it is a digit
        self.root.ids.count_label.text = f"Count {self.count}"

    def change(self, name:str):
        if 'up' in name:
            self.count += 1
        self.root.ids.count_label.text = f"Count {self.count}"

number_class = quiz039()
number_class.run()
```
### Kivy

```.kv
Screen:
    size: 500, 500

    MDBoxLayout:
        id: main_box
        orientation: "horizontal" #organized vertically
        size_hint: .7, .3
        md_bg_color: "#ccccff"
        pos_hint:{"center_x":.5, "center_y":.5}

        MDLabel:
            id: count_label
            font_style: "H3"
            halign: "center"
            font_size: '34pt'

        MDRaisedButton:
            id: add_btn
            text: "Add +1"
            on_press: app.change("up")
            size_hint: 1,1
            font_size: '34pt'
```
