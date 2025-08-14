# Mergington High School Activities API

A super simple FastAPI application that allows students to view and sign up for extracurricular activities.


## Features

- View all available extracurricular activities
- Sign up for activities
- User authentication (admin, staff, student)
- Login/logout endpoints
- Session-based user info endpoint

## Getting Started

1. Install the dependencies:

   ```
   pip install fastapi uvicorn
   ```

2. Run the application:

   ```
   python app.py
   ```

3. Open your browser and go to:
   - API documentation: http://localhost:8000/docs
   - Alternative documentation: http://localhost:8000/redoc


## API Endpoints

| Method | Endpoint                                                          | Description                                                         |
| ------ | ----------------------------------------------------------------- | ------------------------------------------------------------------- |
| GET    | `/activities`                                                     | Get all activities with their details and current participant count |
| POST   | `/activities/{activity_name}/signup?email=student@mergington.edu` | Sign up for an activity                                             |
| POST   | `/login`                                                          | Log in as a user (form: username, password)                         |
| POST   | `/logout`                                                         | Log out the current user                                            |
| GET    | `/me`                                                             | Get info about the current logged-in user                           |


## Data Model

The application uses a simple data model with meaningful identifiers:

1. **Users** - username, password, and role (admin, staff, student)
2. **Sessions** - session_id cookie maps to username
3. **Activities** - Uses activity name as identifier:
   - Description
   - Schedule
   - Maximum number of participants allowed
   - List of student emails who are signed up

All data is stored in memory, which means data will be reset when the server restarts.
