# Quiz 36

![2022  Quizzes (15)](https://user-images.githubusercontent.com/112055062/216655662-dab65e53-1234-4dae-9eed-9795748d8e27.jpg)

## Code

```.py
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def get_name(self):
        return self.name
    def get_age(self):
        return self.age

class Student(Person):
    def __init__(self, name, age, grade):
        super().__init__(name, age)
        self.grade = grade

    def get_grade(self):
        return self.grade

class Classroom:
    def __init__(self):
        self.students = []

    def add_student(self,student):
        self.students.append(student)

    def remove_student(self,student):
        if student not in self.students:
            raise ValueError
        else:
            self.students.remove(student)
    def get_average_score(self):
        if len(self.students) == 0:
            raise ValueError
        total = 0
        for student in self.students:
            total += student.get_grade()
        average = total/len(self.students)
        return average
  ```
  
  ## Test
  
<img width="688" alt="test 36" src="https://user-images.githubusercontent.com/112055062/216671523-0aacd761-3422-4049-b585-86c804335c9c.png">

## UML Diagram

<img width="459" alt="UML quiz 36" src="https://user-images.githubusercontent.com/112055062/216754943-108c82a7-f486-4b8b-99fa-4f8f6f19b137.png">


