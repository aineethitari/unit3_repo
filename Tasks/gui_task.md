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
