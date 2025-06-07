Features
Secure Teacher Login: Teachers can log in using their credentials.

Student Listing: Displays a clear list of students with their Name, Subject, and Marks.

Inline Student Editing: Allows teachers to directly edit student details ( Marks) within the table.

Student Deletion: Provides functionality to remove student records.

Add New Student: A modal/pop-up form to easily add new student details.

Includes logic to prevent duplicate student (name + subject) entries.

Responsive UI: Designed to be usable across different devices (desktop, tablet, mobile).

Modern Aesthetics: Features an attractive, dark-themed user interface inspired by streaming services.

Getting Started
Follow these instructions to get a copy of the project up and running on your local machine for development and testing purposes.

Prerequisites
Before you begin, ensure you have the following installed:

Python 3.x: Download from python.org

pip: Python's package installer (usually comes with Python).

Git: Download from git-scm.com

Installation
Clone the Repository:
Open your terminal or command prompt and navigate to the directory where you want to store your project. Then, clone your repository:


Example: git clone https://github.com/VDeepakro/teacherportal.git



cd YOUR_REPOSITORY_NAME
# Example: cd teacherportal


Create and Activate a Python Virtual Environment:
It's best practice to use a virtual environment to manage project dependencies.

python -m venv venv


This creates a folder named venv in your project directory.

Activate the virtual environment:

On Windows:

.\venv\Scripts\activate


Your terminal prompt should now show (venv) at the beginning, indicating the virtual environment is active.

Install Project Dependencies:
Install Django, which is the primary dependency for this project.

pip install Django


Running the Application
Apply Database Migrations:
Django uses migrations to set up your database tables based on the models defined in the application.

python manage.py migrate


This will create the necessary database tables (by default, Django uses SQLite, which is a file-based database).

Create a Superuser (Admin Account):
You'll need a teacher account to log in to the portal. Create one using the command below and follow the prompts for username, email (optional), and password. Remember these credentials!

python manage.py createsuperuser


Run the Django Development Server:
Start the local web server to run your application.

python manage.py runserver


You should see output indicating the server is running, usually at http://127.0.0.1:8000/.

Access the Application:
Open your web browser and go to http://127.0.0.1:8000/. You should be redirected to the login page (/login/). Use the superuser credentials you created in the previous step to log in.

Project Structure
teacherporta/
├── core/
│   ├── migrations/
│   ├── static/
│   │   ├── style.css
│   │   ├── script.js
│   │   └── login_style.css
│   ├── templates/
│   │   ├── home.html
│   │   └── login.html
│   ├── admin.py
│   ├── apps.py
│   ├── models.py
│   ├── tests.py
│   ├── urls.py
│   └── views.py
├── teacherporta/
│   ├── __init__.py
│   ├── asgi.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── manage.py
├── db.sqlite3  # Database file (ignored by .gitignore)


Database Details
The project uses Django's default SQLite database (db.sqlite3) for simplicity in a development environment.
For creating the teachers signup go to this route http://127.0.0.1:8000/admin/login/?next=/admin/ and i will share my Username and password via mail id

Teacher Model: Stores teacher credentials for login.

Student Model: Stores student name, subject, and marks.

Authentication
The portal implements a basic teacher login system.

Login Page: /login/

Upon successful login, the teacher's username is stored in the session.

The home view (/home/) requires an active teacher session.
