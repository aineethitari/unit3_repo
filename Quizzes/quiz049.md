# Quiz 49
## Code
```.py
import sqlite3
from secure_password import check_password

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

x = database_worker("bitcoin_exchange.db")
query = "SELECT * from ledger"
result = x.search(query)
x.close()

amount_valid = 0
for item in result:
    id = item[0]
    sender_id = item[1]
    receiver_id = item[2]
    amount = item[3]
    string = f"id {id},sender_id {sender_id},receiver_id {receiver_id},amount {amount}"

    check = check_password(string,item[4])
    if check == True:
        amount_valid += amount

print(f"Total amount of bitcoins is {amount_valid}")
```

## Result

<img width="397" alt="quiz049 result" src="https://user-images.githubusercontent.com/112055062/221084053-c3f7af8c-d01c-40b9-9036-84b778bbd2cb.png">
