# avengers-stage-2-backend
This project is a dockerized micro-service for authentication written in Django as a project by a group from #team-avengers in stage 2 of HNGi7

## Update: Pull requests will be accepted now.

## To contribute:

* Ensure you do not edit the .gitignore file for any reason. 
* The **authentify** app is the app that does all the job of extending the User model. No other app is to be created. Raise an issue if you thnk otherwise
* Whatever extension to the User model is done through a database relationship and not by OOP inheritance.
* Ensure code works before pushing. Don't push breaking code.
* Create branch for your own change with format: python/<your hng username>. Do not make pushes to the **python-branch** branch

#### Note: This README will be updated as often as possible to ensure we know how to set things up

## To set it all up for the first time.
* Fork the repo and then clone to your machine.
* cd into the project directory with `cd Authenticated`
* Install **pipenv** (We're using `pipenv` as our virtual environment)using `pip install pipenv`.
* Enable the virtual environment by typing `pipenv shell`.
* Install dependencies with `pipenv sync`

## To get Django part up and running if you just completed the above section
I am assuming you're in the outer **Authenticated** directory and you've enabled the virtual environment.
1. Proceed to the Django project directory by: `cd Authenticated`
1. Run `python manage.py migrate` to apply database changes
1. Run `python manage.py createsuperuser` to be able to access Django admin.(This command should be run only once throughout the lifetime of this project)
1. Run `gunicorn Authenticated.wsgi:application --bind 0.0.0.0:8000` to start the server. We're actually using Gunicorn instead of the default Python server(the `python manage.py runserver` version). If you use Gunicorn, static files won't load. When you visit the admin, you'll see pure HTML and no CSS. Use the default Django server to fix this.
1. Visit **localhost:8000/admin** or **127.0.0.1:8000/admin** to visit the admin panel.

## If you're resuming work on the project.
1. Ensure you're in the outer **Authenticated** directory by typing `pwd`. It should display `Authenticated, Pipfile Pipfile.lock` skip step 2. If you're seeing `Authenticated, README.md`, you're not yet there go to step 2.
1. Enter into the directory by `cd Authenticated`
1. Enable the virtual environment by typing `pipenv shell`.
1. Enter into the Django project directory with `cd Authenticated`
1. Go to step 2 of the previous heading (To get Django part up and running if you just completed the above section)
