# Quiz 41 Tic Tac Toe

## Python Code
```.py
from kivymd.app import MDApp

class quiz041(MDApp):

    def __init__(self,**kwargs):
        super().__init__(**kwargs)

    def build(self):
        return

    turn = "X"
    def change_turn(self,click):
        if self.turn == "X":
            click.text = "X"
            click.disabled = True
            click.md_bg_color_disabled = "ccfeff"
            self.root.ids.turn_text.text = "O's Turn"
            self.turn = "O"

        else:
            click.text = "O"
            click.disabled = True
            click.md_bg_color_disabled = "fdeaff"
            self.root.ids.turn_text.text = "X's Turn"
            self.turn = "X"


test = quiz041()
test.run()
```

## Kivy Code
```.kv
Screen:
    size: 500,500
    MDBoxLayout:
        id: full box
        orientation: "vertical"
        size_hint: 1,1
        pos_hint: {"center_x":.5, "center_y":.5}
        md_bg_color: "#9fc5e8" #blue
        spacing: dp(10)
        padding: dp(10)

        MDBoxLayout:
            id: title_box
            orientation: "vertical"
            pos_hint: {"center_x":.5, "center_y":.5}
            size_hint: 1, .15
            md_bg_color: "#ffb2d6" #pink

            MDLabel:
                id: title_text
                text: "Tic Tac Toe by Ainée"
                font_style: "H3"
                halign: "center"
                font_size: "27pt"

        MDBoxLayout:
            id: turn_box
            orientation: "vertical"
            pos_hint: {"center_x":.5, "center_y":.5}
            size_hint: 1, .15
            md_bg_color: "e0ff00" #lime

            MDLabel:
                id: turn_text
                text: "X's Turn"
                font_style: "H3"
                halign: "center"
                font_size: "27pt"

        MDBoxLayout:
            orientation: "vertical"
            size_hint: 1,1
            pos_hint: {"center_x":.5, "center_y":.5}
            md_bg_color: "#9fc5f5" #blue

            MDBoxLayout:#row1
                orientation: "horizontal"
                size_hint: .7,.8
                pos_hint: {"center_x":.5, "center_y":.5}
                md_bg_color: "9966cc" #purple
                spacing: dp(10)
                padding: dp(10)

                MDRaisedButton:
                    id: tile1_1
                    size_hint: 1,1
                    pos_hint: {"center_x":.5, "center_y":.5}
                    md_bg_color:"b9ff9c" #caramel
                    font_size: "65pt"
                    on_release: app.change_turn(tile1_1)

                MDRaisedButton:
                    id: tile1_2
                    size_hint: 1,1
                    pos_hint: {"center_x":.5, "center_y":.5}
                    md_bg_color:"b9ff9c" #caramel
                    font_size: "65pt"
                    on_release: app.change_turn(tile1_2)

                MDRaisedButton:
                    id: tile1_3
                    size_hint: 1,1
                    pos_hint: {"center_x":.5, "center_y":.5}
                    md_bg_color:"b9ff9c" #caramel
                    font_size: "65pt"
                    on_release: app.change_turn(tile1_3)

            MDBoxLayout:#row2
                orientation: "horizontal"
                size_hint: .7,.8
                pos_hint: {"center_x":.5, "center_y":.5}
                md_bg_color: "9966cc" #purple
                spacing: dp(10)
                padding: dp(10)

                MDRaisedButton:
                    id: tile2_1
                    size_hint: 1,1
                    pos_hint: {"center_x":.5, "center_y":.5}
                    md_bg_color:"b9ff9c" #caramel
                    font_size: "65pt"
                    on_release: app.change_turn(tile2_1)

                MDRaisedButton:
                    id: tile2_2
                    size_hint: 1,1
                    pos_hint: {"center_x":.5, "center_y":.5}
                    md_bg_color:"b9ff9c" #caramel
                    font_size: "65pt"
                    on_release: app.change_turn(tile2_2)

                MDRaisedButton:
                    id: tile2_3
                    size_hint: 1,1
                    pos_hint: {"center_x":.5, "center_y":.5}
                    md_bg_color:"b9ff9c" #caramel
                    font_size: "65pt"
                    on_release: app.change_turn(tile2_3)

            MDBoxLayout:#row3
                orientation: "horizontal"
                size_hint: .7,.8
                pos_hint: {"center_x":.5, "center_y":.5}
                md_bg_color: "9966cc" #purple
                spacing: dp(10)
                padding: dp(10)

                MDRaisedButton:
                    id: tile3_1
                    size_hint: 1,1
                    pos_hint: {"center_x":.5, "center_y":.5}
                    md_bg_color:"b9ff9c" #caramel
                    font_size: "65pt"
                    on_release: app.change_turn(tile3_1)

                MDRaisedButton:
                    id: tile3_2
                    size_hint: 1,1
                    pos_hint: {"center_x":.5, "center_y":.5}
                    md_bg_color:"b9ff9c" #caramel
                    font_size: "65pt"
                    on_release: app.change_turn(tile3_2)

                MDRaisedButton:
                    id: tile3_3
                    size_hint: 1,1
                    pos_hint: {"center_x":.5, "center_y":.5}
                    md_bg_color:"b9ff9c" #caramel
                    font_size: "65pt"
                    on_release: app.change_turn(tile3_3)
```

## Result
Video Test Run: https://youtu.be/2kn49_xvpBE

<img width="795" alt=" " src="https://user-images.githubusercontent.com/112055062/225324162-f53470cd-b9cc-45ed-8c05-741321f4464b.png">

<img width="793" alt="quiz041 pic" src="https://user-images.githubusercontent.com/112055062/225324187-6239b53a-4698-4bab-8f98-07489269240f.png">

<img width="800" alt="quiz041 pic 2" src="https://user-images.githubusercontent.com/112055062/225324214-8a3aa0d1-30e7-4327-9abf-14ef386a4ba1.png">
