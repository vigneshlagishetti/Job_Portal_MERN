# Job Application Portal (MERN Stack)

A comprehensive job portal application built with MongoDB, Express.js, React.js, and Node.js. This platform allows recruiters to post job listings and manage applications, while applicants can browse jobs, apply, and track their applications.

## 🚀 Features

### 👤 User Management

- **User Registration & Authentication**: Secure registration for both Applicants and Recruiters
- **Role-based Access**: Different interfaces and permissions for Applicants and Recruiters
- **Profile Management**: Users can update their profiles, education, skills, and contact information
- **JWT Authentication**: Secure token-based authentication system

### 👔 For Recruiters

- **Job Listing Management**:
  - Create new job listings with details (title, requirements, salary, duration, etc.)
  - Edit existing job listings (max applicants, max positions, deadline)
  - Delete job listings
  - View all posted jobs
- **Application Management**:
  - View all applications for each job listing
  - Accept or reject applications
  - Automatic email notifications to accepted candidates
  - Track number of accepted candidates
- **Employee Management**:
  - View all employees/accepted candidates
  - Rate employees
  - Manage employee information

### 🎯 For Applicants

- **Job Search & Application**:
  - Browse all available job listings
  - Apply for jobs with Statement of Purpose (SOP)
  - Track application status (Applied, Accepted, Rejected)
  - View application history
- **Profile Features**:
  - Update personal information and skills
  - Add education details
  - Rate completed jobs

### 🔧 Technical Features

- **Input Validation**: Comprehensive form validation for all user inputs
- **Email Notifications**: Automated email system for job acceptance notifications
- **Rating System**: Two-way rating system for jobs and employees
- **Responsive Design**: Material-UI components for modern, responsive interface
- **Real-time Updates**: Dynamic status updates for applications
- **Search & Filter**: Job filtering and sorting capabilities
- **Security**: Password hashing with bcrypt, JWT tokens, and protected routes

## 🛠️ Tech Stack

**Frontend:**

- React.js
- Material-UI (@material-ui/core, @material-ui/icons)
- React Router DOM
- Axios for API calls
- Bootstrap
- React Redux
- JWT Decode

**Backend:**

- Node.js
- Express.js
- MongoDB with Mongoose
- JWT for authentication
- Bcrypt.js for password hashing
- Nodemailer for email notifications
- Multer for file uploads
- CORS enabled

## 📦 Installation & Setup

### Prerequisites

- Node.js (v12 or higher)
- MongoDB (local or cloud instance)
- Git

### Backend Setup

```bash
cd backend/
npm install
```

Create a `config/keys.js` file with your configuration:

```javascript
module.exports = {
    mongoURI: "your_mongodb_connection_string",
    secretOrKey: "your_jwt_secret_key",
    orgmail: "your_email@gmail.com",
    orgpass: "your_email_password"
};
```

Start the backend server:

```bash
npm start
```

Server runs on http://localhost:4000

### Frontend Setup

```bash
cd frontend/
npm install
npm start
```

Frontend runs on http://localhost:3000

## 🗂️ Project Structure

```
mern_job_portal/
├── backend/
│   ├── config/
│   │   └── keys.js              # Database & email configuration
│   ├── middleware/
│   │   └── auth.js              # JWT authentication middleware
│   ├── models/
│   │   ├── Users.js             # User schema (Applicants & Recruiters)
│   │   └── Jobs.js              # Job listings schema
│   ├── routes/
│   │   ├── Users.js             # User-related API endpoints
│   │   ├── Jobs.js              # Job-related API endpoints
│   │   └── testAPI.js           # Test endpoint
│   ├── acceptance.js            # Email template for job acceptance
│   ├── email.js                 # Email service configuration
│   ├── validation.js            # Input validation functions
│   └── server.js                # Main server file
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   │   ├── Applicants/      # Applicant-related components
│   │   │   ├── Recruiters/      # Recruiter-related components
│   │   │   ├── Common/          # Shared components
│   │   │   └── templates/       # Navigation templates
│   │   ├── context/             # Authentication context
│   │   ├── util/                # Route protection utilities
│   │   └── App.js               # Main app component
│   └── package.json
└── README.md
```

## 🔐 API Endpoints

### User Routes (`/user`)

- `POST /register` - User registration
- `POST /login` - User login
- `GET /me` - Get current user profile
- `POST /editUser/:id` - Update user profile
- `POST /addJob/:id` - Add job to user's applied jobs
- `GET /getApp/:id` - Get applicant details
- `POST /getApps` - Get multiple applicants

### Job Routes (`/job`)

- `GET /` - Get all job listings
- `POST /register` - Create new job listing
- `POST /addApp/:id` - Add application to job
- `POST /updateStatus/:id` - Update application status
- `POST /editJob/:id` - Edit job details
- `POST /deleteJob/:id` - Delete job listing
- `GET /getJob/:id` - Get specific job details
- `GET /checkAccepted/:id` - Check if user is accepted
- `POST /getJobs` - Get multiple jobs

## 🚦 Usage

1. **Registration**: Choose between Applicant or Recruiter role
2. **For Recruiters**:
   - Create job listings from the dashboard
   - Manage applications and accept/reject candidates
   - View and rate employees
3. **For Applicants**:
   - Browse available job listings
   - Apply with a Statement of Purpose
   - Track application status
   - Rate completed jobs

## 🔒 Security Features

- Password hashing using bcrypt
- JWT token-based authentication
- Protected routes based on user roles
- Input validation and sanitization
- CORS enabled for cross-origin requests

## 📧 Email Notifications

Automated email notifications are sent to applicants when their job applications are accepted, using a professionally designed HTML email template.

## 🎨 UI/UX Features

- Responsive design with Material-UI components
- Role-based navigation menus
- Dynamic status updates
- Professional styling with Bootstrap
- User-friendly forms with validation feedback

Navigate to [http://localhost:3000/](http://localhost:3000/) in your browser to access the application.
