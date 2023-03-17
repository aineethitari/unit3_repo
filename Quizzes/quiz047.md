# Quiz 47
## Code
```.py
import sqlite3

from kivymd.app import MDApp
from security import encrypt_password

class database_worker:
    def __init__(self, name):
        self.connection = sqlite3.connect(name)
        self.cursor = self.connection.cursor()

    def search(self, query):
        result = self.cursor.execute(query).fetchall()
        return result

    def run_save(self, query):
        self.cursor.execute(query)
        self.connection.commit()

    def close(self):
        self.connection.close()


class quiz047(MDApp):
    def __init__(self, **kwargs):
        super().__init__(**kwargs)
        self.components = {"basic":0}

    def build(self):
        return

    def save(self):
        pass

    def update(self):
        #This function updates all the labels in the form using the base salary and the percentage
        # Pseudocode
        # 1- get the base salary from the GUI
        base = self.root.ids.base.text
        # 2- if base salary define total=int(base) and an empty string to store build a hash (for_hash="") if no base then end the function
        if base == "":
            return

        # 3- for Each TextField with ids: "inhabitant","income_tax","pension","health" get the text property
        inhabitant = self.root.ids.inhabitant.text
        health = self.root.ids.health.text
        pension = self.root.ids.pension.text
        income_tax = self.root.ids.income_tax.text

        # 4- if the TextField.text has a number (value), calculate the equation new_value="(base*int(value)//100) JPY" and subbctract the equation to the total
        taxes = [health, pension, income_tax, inhabitant]
        taxes_labels = ["health", "pension", "income_tax", "inhabitant"]
        new_value = int(base)

        x = 0
        for tax in taxes:
            if tax != "":
                new_value -= (int(base) * int(tax)) // 100
                self.root.ids[taxes_labels[x] + "_label"].text = f"{new_value} JPY" #number 6 set labels
                x += 1
                print(tax)
        # 5- if no: then new_value = " JPY"
            else:
                new_value = ""

        # 6- set the label next to the TextField (inhabitant_label, income_tax_label, etc) to the variable new_value
        # 7- concatenate to the hash variable the f"{id}{value}"
        hash = encrypt_password(base, inhabitant, income_tax, pension, health, new_value)
        # 8- set the text of the element id=total to the total with the JPY symbol
        self.root.ids.salary_label.text = f"{new_value}"
        # 9- encrypt the hash and change the text of the label with id=hash to the last 50 characters of the hash
        self.root.ids.hash.text = hash[-50:]

        #calculate total
        ids = ["inhabitant", "income_tax", "pension", "health"]

        # update the percentage

    def save(self):
        #repeat the algorithm in update but create variables to save the amount of each item:
        #base = int(base)
        #inhabitant = amount in JPY to remove from base for inhabitant tax
        #income_tax = amount in JPY to remove from base for income tax
        #pension = amount in JPY to remove from base for pension tax
        #health = amount in JPY to remove from base for health tax
        #total = total net salary
        #hahs = hash of the calcualtions in the format
        #inhabitant4,income_tax3,pension2,health1,total1103  (here the numbers next to the category are percentages)
        base = []
        inhabitant = []
        income_tax = []
        pension = []
        health = []
        salary = []
        hash = []

        x = 0
        variables = ["base", "inhabitant", "income_tax", "pension", "health", "salary", "hash"]
        variables_labels = ["base", "inhabitant", "income_tax", "pension", "health", "salary_label", "hash"]
        for variable in variables:
            variable = self.root.ids[variables_labels[x] + "_label"].text
            variable = variable[:-4]
            x += 1

        # query = f"""INSERT into payments
        query = f"""INSERT into payments (base, inhabitant, income_tax, pension, health, total, hash) VALUES ({base}, {inhabitant}, {income_tax}, {pension}, {health}, {salary}, '{hash}')"""
        db = database_worker("payments.db")
        db.run_save(query)
        db.close()

        self.root.ids.hash.text = f"Payment saved"

    def clear(self):
        for label in ["base", "inhabitant","income_tax","pension","health"]:
            self.root.ids[label].text = ""
            self.root.ids[label+"_label"].text = " JPY"

        self.root.ids["salary_label"].text = " JPY"
        self.root.ids.hash.text = "----"


test = quiz047()
create = """CREATE TABLE if not exists payments(
id PRIMARY KEY, 
base INTEGER,
inhabitant INTEGER,
income_tax INTEGER,
pension INTEGER,
health INTEGER,
total INTEGER,
hash TEXT)
"""

db = database_worker("payments.db")
db.run_save(create)
db.close()
test.run()
```

## Result

