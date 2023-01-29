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
