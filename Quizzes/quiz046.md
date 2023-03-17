# Quiz 46
## Code
```.py
import sqlite3

haiku = """Code flows like a stream
 Algarithms guide its way
 In silence, it solves"""
class database_handler():
    def __init__(self, namedb: str):
        self.connection = sqlite3.connect(namedb)
        self.cursor = self.connection.cursor()

    def create_table(self):
        query = f"""CREATE TABLE if not exists words(
            id INTEGER PRIMARY KEY not NULL,
            word text not NULL,
            length int not NULL
            )"""
        self.run_query(query)

    def run_query(self, query: str):
        self.cursor.execute(query)
        self.connection.commit()

    def close(self):
        self.connection.close()

db = database_handler(namedb = "quiz045.db")
db.create_table()

for word in haiku.split():#insert every word and length in database
    query = f"INSERT into words (word,length) VALUES ('{word}',{len(word)})"
    db.run_query(query)

#query the average of length

query = f"SELECT avg(length) from words as 'average_len'"
db.run_query(query)
print(db.cursor.fetchone())

db.close()
```

## Result

<img width="303" alt="quiz 46 result" src="https://user-images.githubusercontent.com/112055062/225957706-422fbc3f-f954-4577-bcb7-e2cd22c28aae.png">

