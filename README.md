# Ex02 Django Polls
## Date: 04-11-2024

## AIM
To develop a Django application to implement polls.


## DESIGN STEPS

### STEP 1:
Clone the problem from GitHub

### STEP 2:
Create a new app in Django project

### STEP 3:
Enter the code for admin.py and models.py

### STEP 4:
Execute Django admin and create details for polls.

## PROGRAM:
admin.py
```
admin.py
admin.py
admin.py
from django.contrib import admin
from .models import Question, Choice
   
  
  admin.site.register(Question)
  admin.site.register(Choice)
  ```
  model.py
  ```
  model.py
models.py:
import datetime
 from django.db import models
 from django.utils import timezone
 
 
 class Question(models.Model):
     question_text = models.CharField(max_length=200)
     pub_date = models.DateTimeField("date published")
 
    def __str__(self):
        return self.question_text  # Makes the object readable when printed

    def was_published_recently(self):
        return self.pub_date >= timezone.now() - datetime.timedelta(days=1)


class Choice(models.Model):
    question = models.ForeignKey(Question, on_delete=models.CASCADE)
    choice_text = models.CharField(max_length=200)
    votes = models.IntegerField(default=0)

    def __str__(self):
        return self.choice_text  # Makes the object readable when printed

```
## OUTPUT
![alt text](<Screenshot 2024-11-04 142511.png>)
![alt text](<Screenshot 2024-11-04 142525.png>) 
![alt text](<Screenshot (5).png>) 
## COURSERA GRADE
![alt text](<Screenshot (4).png>) 
## RESULT
Thus the program for creating a polls using Django has been executed successfully.
