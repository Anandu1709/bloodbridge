# bloodbridge
# Blood Donation Management Platform

A comprehensive Flask-based web application for managing blood donation activities with role-based access control.

## Features

### Multi-Role System
- **Donors**: Register, manage profiles, track donation history
- **Hospitals**: Request blood, manage urgent needs
- **Organizations**: Organize donation events, manage donor networks
- **Admins**: System administration and user management

### Core Functionality
- Secure user authentication and authorization
- Blood type compatibility matching
- Search and filtering system for donors
- Emergency blood request system
- Responsive design for mobile and desktop
- Real-time notifications and alerts

## Technologies Used

*   **Backend:** Python, Flask, SQLAlchemy, WTForms
*   **Frontend:** HTML, CSS (with custom styles), JavaScript
*   **Database:** PostgreSQL (recommended for production), SQLite (for development)
*   **WSGI Server:** Gunicorn (recommended for production)

## Quick Setup

### Prerequisites
- Python 3.11+
- PostgreSQL database (optional - SQLite included for development)

### Installation

1. **Extract the source code**
   ```bash
   unzip blood_donation_platform_source.zip
   cd blood_donation_platform
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   # or if using uv:
   uv sync
   ```

3. **Set environment variables**
   ```bash
   export SESSION_SECRET="your-secret-key-here"
   export DATABASE_URL="sqlite:///instance/blood_donation.db"
   ```

4. **Run the application**
   ```bash
   python main.py
   # or with gunicorn:
   gunicorn --bind 0.0.0.0:5000 main:app
   ```

5. **Access the application**
   Open your browser and navigate to `http://localhost:5000`

## Project Structure

```
blood_donation_platform/
├── app.py              # Flask application setup
├── models.py           # Database models
├── routes.py           # Application routes
├── forms.py            # WTForms definitions
├── utils.py            # Helper functions
├── main.py             # Application entry point
├── static/
│   ├── css/
│   │   └── styles.css  # Custom styling
│   └── js/
│       └── main.js     # Frontend functionality
└── templates/          # HTML templates
    ├── auth/           # Authentication pages
    ├── donor/          # Donor dashboard and forms
    ├── hospital/       # Hospital dashboard and forms
    ├── organization/   # Organization dashboard and forms
    ├── admin/          # Admin dashboard
    └── search/         # Search functionality
```

## User Roles & Access

### Donor Features
- Complete profile with blood type and medical information
- View donation eligibility status
- Respond to blood requests
- Track donation history

### Hospital Features
- Create urgent blood requests
- Specify blood type requirements and urgency levels
- View donor responses
- Manage hospital profile information

### Organization Features
- Organize donation events
- Manage donor networks
- Track organization activities
- Coordinate with hospitals

### Admin Features
- User management and moderation
- System oversight and configuration
- Analytics and reporting
- Platform administration

## Security Features

- Password hashing with Werkzeug
- Session-based authentication
- Role-based access control
- Form validation and CSRF protection
- Input sanitization

## Development

### Database Models
- **User**: Base user authentication
- **DonorProfile**: Donor-specific information
- **HospitalProfile**: Hospital details
- **OrganizationProfile**: Organization information
- **BloodRequest**: Hospital blood requests
- **Donation**: Donation records
- **DonationEvent**: Organized events

### API Endpoints
- Authentication: `/login`, `/register`, `/logout`
- Dashboards: `/dashboard`, `/donor/dashboard`, `/hospital/dashboard`
- Profiles: `/donor/profile`, `/hospital/profile`, `/organization/profile`
- Search: `/search/donors`
- Requests: `/hospital/request-blood`

## Production Deployment

1. Set secure environment variables
2. Configure PostgreSQL database
3. Use production WSGI server (gunicorn recommended)
4. Enable HTTPS and security headers
5. Set up monitoring and logging

## Support

This platform provides a complete foundation for blood donation management. All core features are implemented and ready for production use with proper security configurations.
