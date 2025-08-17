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

## Key Highlights

- **Multi-user Architecture:** Leverages Django's robust user system with custom role implementations
- **Secure Data Handling:** Implements encryption for sensitive information and secure file uploads
- **Real-time Communication:** WebSocket integration for instant messaging capabilities
- **Responsive Design:** Mobile-friendly interface for accessibility across devices
- **Scalable Architecture:** Built with Django best practices for easy maintenance and expansion

Class Manager uses the multi-user concept of Django where student and teacher are different types of user and have different functionalities. Also adding features like notice, messages, assignment, adding students to the class etc. requires a lot of Django concepts. Projects like Class Manager is a great choice to practice your Django skills and test yourself.

This Classroom Management System demonstrates advanced Django concepts including custom user models, file handling, real-time features, and comprehensive CRUD operations, making it an excellent project for learning full-stack web development.
=======
