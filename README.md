# Django Authentication Project

A comprehensive Django-based authentication system with user registration, login, password reset, and profile management features.

## Features

- **User Registration**: New users can create accounts with email verification
- **User Login**: Secure authentication with session management
- **Password Reset**: Forgot password functionality via email
- **User Profile**: View and manage user profile information
- **JWT Authentication**: Token-based authentication for API endpoints
- **Responsive Design**: Clean, mobile-friendly interface
- **REST API**: RESTful API endpoints for authentication operations

## Tech Stack

- **Backend**: Django 4.2+
- **API**: Django REST Framework
- **Authentication**: JWT (JSON Web Tokens)
- **Frontend**: HTML5, CSS3, Bootstrap
- **Database**: SQLite (development)

## Installation

### Prerequisites

- Python 3.8+
- pip (Python package manager)

### Local Development Setup

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd auth_project
   ```

2. **Create virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Run migrations**
   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```

5. **Create superuser (admin)**
   ```bash
   python manage.py createsuperuser
   ```

6. **Run development server**
   ```bash
   python manage.py runserver
   ```

7. **Access the application**
   - Main site: http://localhost:8000
   - Admin panel: http://localhost:8000/admin

## Project Structure

```
auth_project/
├── accounts/                 # User authentication app
│   ├── migrations/          # Database migrations
│   ├── serializers.py       # REST API serializers
│   ├── urls.py             # URL patterns for accounts
│   └── views.py            # View logic for authentication
├── auth_project/           # Main Django project
│   ├── settings.py         # Project settings
│   ├── urls.py            # Root URL configuration
│   └── wsgi.py            # WSGI configuration
├── templates/             # HTML templates
│   ├── base.html          # Base template
│   ├── login.html         # Login page
│   ├── register.html      # Registration page
│   ├── profile.html       # User profile page
│   └── password_reset*.html # Password reset templates
├── requirements.txt       # Python dependencies
└── manage.py            # Django management script
```

## API Endpoints

### Authentication Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/auth/register/` | User registration |
| POST | `/api/auth/login/` | User login |
| POST | `/api/auth/logout/` | User logout |
| POST | `/api/auth/password/reset/` | Request password reset |
| POST | `/api/auth/password/reset/confirm/` | Confirm password reset |
| GET | `/api/auth/user/` | Get current user info |
| PUT | `/api/auth/user/` | Update user info |

### Template URLs

| URL | Description |
|-----|-------------|
| `/` | Home page |
| `/login/` | Login page |
| `/register/` | Registration page |
| `/profile/` | User profile page |
| `/password-reset/` | Password reset request page |
| `/password-reset-done/` | Password reset confirmation page |

## Usage

### User Registration
1. Navigate to `/register/`
2. Fill in username, email, and password
3. Submit the form to create a new account

### User Login
1. Navigate to `/login/`
2. Enter username and password
3. Click login to access your account

### Password Reset
1. Navigate to `/password-reset/`
2. Enter your email address
3. Check your email for reset instructions
4. Follow the link to reset your password

### Profile Management
1. Login to your account
2. Navigate to `/profile/`
3. Update your profile information as needed

## Configuration

### Email Settings
For password reset functionality, configure email settings in `settings.py`:

```python
EMAIL_BACKEND = 'django.core.mail.backends.smtp.EmailBackend'
EMAIL_HOST = 'smtp.gmail.com'
EMAIL_PORT = 587
EMAIL_USE_TLS = True
EMAIL_HOST_USER = 'your-email@gmail.com'
EMAIL_HOST_PASSWORD = 'your-app-password'
```

### JWT Settings
JWT configuration is handled by `djangorestframework-simplejwt`. Default settings are:
- Access token lifetime: 5 minutes
- Refresh token lifetime: 1 day

## Development

### Running Tests
```bash
python manage.py test
```

### Code Style
- Follow PEP 8 style guidelines
- Use meaningful variable and function names
- Add docstrings to all functions and classes

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Django documentation
- Django REST Framework documentation
- Simple JWT documentation
