# Classroom Management System

A comprehensive, full-stack classroom management system built with Django, Python, and modern web technologies. This application provides role-based access for students, teachers, and administrators to manage classroom activities efficiently.

## Tech Stack

**Backend:**
- Python with Django framework
- Django ORM with SQLite/PostgreSQL database
- JSON Web Tokens (JWT) for authentication
- Django Channels with WebSockets for real-time communication
- Django's built-in password hashing for security
- Field-level encryption for sensitive data protection
- Django REST Framework for API endpoints

**Frontend:**
- HTML5
- CSS3
- JavaScript
- Bootstrap for responsive design
- Django Templates

## Features

### Authentication & Security
- Secure user registration and login system with JWT
- Password hashing and field encryption for data protection
- Role-based access control (RBAC) for different user types

### Role-Based Access Control
**Students:**
- View marks and grades given by teachers
- Download assignments posted by teachers
- Submit assignment solutions (one-time submission)
- View announcements and notices from teachers
- Message teachers directly
- View and edit personal profile
- Search functionality for teachers list

**Teachers:**
- Add and manage students in their classes
- Create, edit, and grade student assignments
- Post notices and announcements to class students
- View and manage student marks through detailed profiles
- Access student submissions and provide feedback
- Receive and respond to student messages in inbox
- Upload and manage assignment files
- Search functionality for student lists

**Administrators:**
- Oversee user registration and management
- Manage class scheduling and assignments
- Full system access and user role management

### Core Functionalities
- **Assignment Management:** Teachers post assignments, students submit solutions
- **Grade Management:** Secure storage of student marks with easy editing capabilities
- **Real-time Messaging:** Direct communication between students and teachers
- **File Upload System:** Support for assignment submissions and profile pictures
- **Notice System:** Broadcast announcements to class members
- **Profile Management:** User profile customization with photo uploads
- **Search System:** Quick user discovery and filtering

## Project Structure

```
classmanager/
├── classroom/
│   ├── migrations/
│   ├── templates/
│   │   └── classroom/
│   │       ├── add_marks.html
│   │       ├── assignment_list.html
│   │       ├── base.html
│   │       ├── login.html
│   │       ├── profile.html
│   │       └── ...
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── forms.py
│   ├── models.py
│   ├── tests.py
│   ├── urls.py
│   └── views.py
├── classmanager/
│   ├── __init__.py
│   ├── asgi.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── media/
│   └── uploads/
├── static/
│   ├── css/
│   ├── js/
│   └── images/
├── manage.py
└── requirements.txt
```

## Setup and Installation

To run this project locally on Windows, follow these steps:

1. **Clone the repository:**
   ```cmd
   git clone https://github.com/YOUR_USERNAME/classroom-management-system.git
   cd classroom-management-system\classmanager
   ```

2. **Create and activate virtual environment:**
   ```cmd
   python -m venv venv
   venv\Scripts\activate
   ```

3. **Install dependencies:**
   ```cmd
   pip install django
   pip install djangorestframework
   pip install djangorestframework-simplejwt
   pip install django-channels
   pip install pillow
   ```

4. **Set up environment variables:**
   Create a `.env` file in the project root and add:
   ```
   SECRET_KEY=your_django_secret_key
   DEBUG=True
   DATABASE_URL=sqlite:///db.sqlite3
   JWT_SECRET=your_jwt_secret_key
   ```

5. **Run database migrations:**
   ```cmd
   python manage.py makemigrations
   python manage.py migrate
   ```

6. **Create a superuser (admin):**
   ```cmd
   python manage.py createsuperuser
   ```

7. **Start the development server:**
   ```cmd
   python manage.py runserver
   ```

8. **Access the application:**
   Open your web browser and navigate to `http://127.0.0.1:8000`

## How to Use

1. **Register Users:** Create accounts for students and teachers through the registration page
2. **Admin Setup:** Use the superuser account to access Django admin panel at `/admin/`
3. **Teacher Workflow:** 
   - Log in as teacher
   - Add students to your class
   - Post assignments and notices
   - Grade submissions and manage marks
4. **Student Workflow:**
   - Log in as student
   - View assignments and download materials
   - Submit completed work
   - Check grades and communicate with teachers
5. **Explore Features:** Navigate through different sections to explore messaging, profile management, and search functionalities

## Screenshots

### Home Page
![classmanager](https://user-images.githubusercontent.com/59278577/85334196-73729680-b4f8-11ea-90b6-a42336e1d7dd.PNG)
![classmanager-homepage](https://user-images.githubusercontent.com/59278577/85334362-c2203080-b4f8-11ea-973c-e9ff6b481810.PNG)
![classmanager-homepage1](https://user-images.githubusercontent.com/59278577/85334481-f398fc00-b4f8-11ea-88fc-ba3371076930.PNG)

### Login Page
![classmanager-loginpage](https://user-images.githubusercontent.com/59278577/85334573-1deab980-b4f9-11ea-86b9-4e1367e78057.PNG)

### Options Available for Teachers
![classmanager-teacheroptions](https://user-images.githubusercontent.com/59278577/85334843-8cc81280-b4f9-11ea-8162-2ac5756f3884.PNG)

### Options Available for Students
![classmanager-studentsoptionlist](https://user-images.githubusercontent.com/59278577/85336072-ac603a80-b4fb-11ea-87b5-a942ce294a2b.PNG)

### Profile Page
User can edit their profile by clicking on Edit profile
![classmanager-profilepic](https://user-images.githubusercontent.com/59278577/85335035-f34d3080-b4f9-11ea-9478-bc4632798eef.PNG)

### Marks Given by Teacher
Here, teachers can see all the marks given by them to a particular student of their class and can update them.
![classroom-marksgiven](https://user-images.githubusercontent.com/59278577/85335383-8d14dd80-b4fa-11ea-8257-797c5a0fe52a.PNG)

### Marks List Obtained by Student
![classmanager-marksobtained](https://user-images.githubusercontent.com/59278577/85335564-d6fdc380-b4fa-11ea-8219-09d40f96f8e7.PNG)

### Assignments Uploaded by Teacher
Students can download assignments given by their teacher and can submit their work too.
![classmanager-assignmentpage](https://user-images.githubusercontent.com/59278577/85335929-6c995300-b4fb-11ea-883d-48ab096dd89a.PNG)

### Assignment Submission by Students
Teacher can check submissions made by their students and can give them marks for that.
![classmanager-submissionlist](https://user-images.githubusercontent.com/59278577/85335777-2e039880-b4fb-11ea-8d7d-0edc517ac11e.PNG)

## Key Highlights

- **Multi-user Architecture:** Leverages Django's robust user system with custom role implementations
- **Secure Data Handling:** Implements encryption for sensitive information and secure file uploads
- **Real-time Communication:** WebSocket integration for instant messaging capabilities
- **Responsive Design:** Mobile-friendly interface for accessibility across devices
- **Scalable Architecture:** Built with Django best practices for easy maintenance and expansion

Class Manager uses the multi-user concept of Django where student and teacher are different types of user and have different functionalities. Also adding features like notice, messages, assignment, adding students to the class etc. requires a lot of Django concepts. Projects like Class Manager is a great choice to practice your Django skills and test yourself.

This Classroom Management System demonstrates advanced Django concepts including custom user models, file handling, real-time features, and comprehensive CRUD operations, making it an excellent project for learning full-stack web development.
