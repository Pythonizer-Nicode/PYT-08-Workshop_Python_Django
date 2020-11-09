
# (◉ ͜ʖ◉))ﾉ彡 PYTHON WORKSHOP - DJANGO ✧٩(•́⌄•́๑)
>   Part of Team Workshop dedicated to Python


### Description 
> Start 09-11-2020


###  Index

-   [STEP 1 - Starting Project](#step_1_-_starting_project)
-   [STEP 2 - Creating App](#step_1_-_creating_app)
-   [STEP 3 - Models](#step_1_-_models)

---

### STEP 1 - Starting Project

-   Navigate to your working directory
-   On Windows: ```python -m venv virenv```
-   On Mac / Linux: ```python3 -m venv virenv```
-   Run environment :
    -   On Windows: ```virenv\scripts\activate```
    -   On Mac/Linux: ```source virenv/bin/activate```
    -   (Leave environment: ```deactivate```)
-   ```pip install pip --upgrade```
-   ```pip install django``` or ```pip install "django>=3.0,<4"```for specific version
-   Starting a project: ```django-admin startproject workshop```
-   (```python manage.py makemigrations```)
-   ```python manage.py migrate```
-   Run your development version: ```python manage.py runserver```
-   Visit: ```http://127.0.0.1:80000```
-   You should see the Django's rocket 
-   ```python manage.py createsuperuser```
-   Fill in the different fields

---

### STEP 2 - Creating App

-   Create app: ```$ python manage.py startapp events```
-   Open **settings.py**
-   Add ```'events.apps.EventsConfig',``` within **INSTALLED_APPS** array

---

### STEP 3 - Models

-   In your **events** app folder open **models.py**
-   Add :   
    class Event(models.Model):  
        name = models.CharField('Event Name', max_length=120)   
        event_date = models.DateTimeField('Event Date') 
        venue = models.CharField(max_length=120)    
        manager = models.CharField(max_length=60)   
        description = models.TextField(blank=True)  
-   ```python manage.py makemigrations```
-   ```python manage.py migrate```
-   ```python manage.py sqlmigrate events 0001_initial``` to view automatic SQL request
-   Add this function to class **Event** in your **events models.py** file:
     def __str__(self):  
        return self.name   
- Modify the content of your **events models.py** file: 

    from django.db import models
    
    
    class Venue(models.Model):
        name = models.CharField('Venue Name', max_length=120)
        address = models.CharField(max_length=300)
        zip_code = models.CharField('Post Code', max_length=12)
        phone = models.CharField('Contact Phone', max_length=20)
        web = models.URLField('Web Address')
        email_address = models.EmailField('Email Address')

        def __str__(self):
            return.self.name


    class MyClubUser(models.Model):
        first_name = models.CharField(max_length=30)
        last_name = models.CharField(max_length=30)
        email = models.EmailField('User Email')

        def __str__(self):
            return self.first_name + " " + self.last_name


    class Event(models.Model):
        name = models.CharField('Event Name', max_length=120)
        event_date = models.DateTimeField('Event Date')
        venue = models.ForeignKey(Venue, blank=True, null=True, on_delete=models.CASCADE)
        manager = models.CharField(max_length=60)
        attendees = models.ManyToManyField(MyClubUser, blank=True)
        description = models.TextField(blank=True)
    
        def __str__(self):
            return self.name
-   (```python manage.py check```)
-   ```python manage.py makemigrations```
-   ```python manage.py migrate```
-   ```python manage.py sqlmigrate events 0002_xxx``` to view automatic SQL request


---

### BeCode Intensive Bootcamp

In ten months, you have a wonderful opportunity to become a great Junior App & Web Developer. We are motivated by inclusion and the spirit of sharing!
The bootcamp aims at acquiring self-learning skills and mastering a junior web developer path, both frontend and backend. Support is provided by a team of great coaches who will guide you and help you overcome the various peaks of difficulty encountered.

Give maximum to get maximum 🚀

### COLLABORATION

Hello, I'm [Nicolas](https://www.linkedin.com/in/nicolas-denoel/), a computer science enthusiast who is in the middle of his reconversion as a developer. After 15 years in the commercial sector as a manager and director, I decided to put this career on hold to devote myself fully to development.  
After an intensive 7 month bootcamp at Becode where I was able to acquire the superpowers of a junior developer, I am now constantly exploring the challenges that the various companies and associations active in the field can offer me.  
Positive spirit, with an unquenchable thirst for learning, committed and structured, I like to take up challenges and always progress by giving the best of myself. 
If you have a project, no matter how big or small, don't hesitate to share it, we always have to win by doing things alongside others.  

See you soon!  

### TIMELINE
[:calendar: Discover the great timeline of my adventure to become a developer. Want to write your company's name on it ? Let's meet !](https://timelines.gitkraken.com/timeline/2e12cc334eb0406b84bf7a6339e666c4?range=2020-05-26_2020-06-27)  

[![License](http://img.shields.io/:license-mit-blue.svg?style=flat-square)](http://badges.mit-license.org)


