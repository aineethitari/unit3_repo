# Quiz 38

## Code

```.py
import random
from matplotlib import pyplot as plt

class Coordinate:
    def __init__(self,x:int, y:int):
        self.x:int = x
        self.y:int = y

    def __repr__(self)->str:
        return f"[Coordinate] x={self.x} y={self.y}"
class City:
    def __init__(self,name:str,location:Coordinate):
        self.name = name
        self.location = location

    def __repr__(self):
        return f"[City class] A {self.name} located at {self.location}"

    def distance(self,cityB):
        xa, ya = self.location.x, self.location.y
        xb, yb = cityB.location.x, cityB.location.y
        d = ((xa-xb)**2 + (ya-yb)**2 )**(1/2)
        return round(d,2)


class Country:
    def __init__(self, name:str):
        self.cities = []
        self.name = name

    def add_city(self, new_city:City):
        if isinstance(new_city, City):
            self.cities.append(new_city)
        else:
            raise ValueError("City must be a city object")

    def __repr__(self):
        return f"[Country object]Country"


thailand = Country(name="Thailand")

cities = ["Bangkok", "Chiangmai", "Phuket", "Nan", "Huahin", "Krabi", "Samui", "Ayutthaya", "Chiangrai", "Loei"]
for city in cities:
    match = Coordinate(x=random.randint(1,100), y=random.randint(1,100))
    cty = City(city, match)
    thailand.add_city(cty)
    plt.scatter(match.x,match.y,s=100) #quiz38 show graph sale map
    plt.text(match.x,match.y,f"{cty.name}")
    plt.xlabel("Latitude (km)")
    plt.ylabel("Longitude (km)")

for i in range(0,len(thailand.cities)-1):
    start_city = thailand.cities[i]
    end_city = thailand.cities[i+1]
    x = [start_city.location.x, end_city.location.x]
    y = [start_city.location.y, end_city.location.y]
    plt.plot(x,y, color="pink")
    print(f"Connecting city {start_city.name} to {end_city.name} : {start_city.distance(end_city)} km")

print("The total distance for this solution of the Saleman's problem is ")
plt.show()
```

## Result

<img width="628" alt="quiz 38 travelling salesman" src="https://user-images.githubusercontent.com/112055062/216755721-3d76395f-e3f4-48b7-b1cb-1e56d3815be3.png">
