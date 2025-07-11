# Job Portal - Symfony Application

## 📋 Project Overview

This is a comprehensive job portal web application built with **Symfony 4.4** that connects job seekers with employers. The platform provides a complete ecosystem for job posting, application management, user profiles, and communication between users.

## 🚀 Features

### For Job Seekers
- **User Registration & Profile Management**: Complete user profiles with CV/resume uploads
- **Job Search**: Browse and search through available job postings
- **Application System**: Apply to jobs with detailed application tracking
- **Profile Dashboard**: Manage personal information, work experience, and qualifications
- **Messaging System**: Communicate with employers and other users
- **Friends System**: Connect with other professionals
- **Interview Management**: Schedule and manage interviews

### For Employers
- **Job Posting**: Create and manage detailed job announcements
- **Candidate Management**: Review applications and manage candidates
- **Dashboard**: Comprehensive employer dashboard for job management
- **Communication Tools**: Direct messaging with candidates
- **Application Tracking**: Monitor and manage job applications

### Administrative Features
- **Admin Dashboard**: Complete administrative control panel using EasyAdmin
- **User Management**: Manage all users (job seekers and employers)
- **Content Moderation**: Moderate job postings and user content
- **System Monitoring**: Track platform usage and statistics

## 🛠 Technology Stack

### Backend
- **PHP 7.1.3+**
- **Symfony 4.4** - Full-stack PHP framework
- **Doctrine ORM** - Database abstraction layer
- **EasyAdmin Bundle** - Admin interface
- **Security Bundle** - Authentication and authorization
- **Mailer Bundle** - Email functionality
- **Twilio SDK** - SMS/communication integration

### Frontend
- **Twig Templates** - Template engine
- **Bootstrap 5** - CSS framework
- **FontAwesome** - Icons
- **FullCalendar** - Calendar functionality
- **jQuery** - JavaScript library
- **Custom CSS/JS** - Custom styling and interactions

### Database
- **MySQL/PostgreSQL** - Database (configurable via DATABASE_URL)
- **Doctrine Migrations** - Database versioning

### Additional Features
- **File Upload** - Image and document uploads
- **QR Code Generation** - QR code functionality
- **Pagination** - Content pagination
- **Image Processing** - Image manipulation and optimization
- **CKEditor** - Rich text editing
- **Calendar Integration** - Event scheduling

## 📁 Project Structure

```
WebSymfony/
├── src/
│   ├── Controller/           # Application controllers
│   │   ├── Admin/           # Admin panel controllers
│   │   ├── UserController.php
│   │   ├── AnnonceController.php
│   │   ├── DemandeController.php
│   │   └── ...
│   ├── Entity/              # Database entities
│   │   ├── User.php         # User management
│   │   ├── Annonce.php      # Job postings
│   │   ├── Demande.php      # Job requests
│   │   ├── Apply.php        # Job applications
│   │   └── ...
│   ├── Repository/          # Database queries
│   ├── Form/               # Form types
│   ├── Security/           # Authentication
│   └── EventSubscriber/    # Event handling
├── templates/              # Twig templates
│   ├── admin/             # Admin panel templates
│   ├── user/              # User templates
│   ├── annonce/           # Job posting templates
│   └── ...
├── config/                # Configuration files
├── public/               # Web root
│   ├── build/            # Compiled assets
│   ├── uploads/          # Uploaded files
│   └── images/           # Static images
├── migrations/           # Database migrations
├── tests/               # Unit tests
└── vendor/              # Dependencies
```

## 🗄 Database Schema

### Core Entities

#### User
- Personal information (name, email, phone, etc.)
- Professional details (job, experience, qualifications)
- Profile image and CV uploads
- Role-based access (ROLE_USER, ROLE_EMPLOYEUR, ROLE_ADMIN)
- Relationships with jobs, applications, and messages

#### Annonce (Job Posting)
- Job title, description, requirements
- Salary range, location, experience level
- Company information and contact details
- Application deadline and status
- Relationship with employer and applications

#### Demande (Job Request)
- Job seeker's requirements and preferences
- Desired salary, location, experience
- Professional qualifications and skills
- Relationship with job seeker and applications

#### Apply (Application)
- Job application details
- Cover letter and resume
- Application status and tracking
- Relationships with job and applicant

#### Messages
- User-to-user communication
- Conversation management
- Message history and threading

## 🚀 Installation & Setup

### Prerequisites
- PHP 7.1.3 or higher
- Composer
- MySQL/PostgreSQL database
- Web server (Apache/Nginx)

### Installation Steps

1. **Clone the repository**
   ```bash
   git clone [repository-url]
   cd WebSymfony
   ```

2. **Install dependencies**
   ```bash
   composer install
   ```

3. **Configure environment**
   ```bash
   # Copy .env.example to .env and configure:
   cp .env.example .env
   
   # Configure your database connection
   DATABASE_URL="mysql://username:password@localhost:3306/database_name"
   ```

4. **Create database and run migrations**
   ```bash
   php bin/console doctrine:database:create
   php bin/console doctrine:migrations:migrate
   ```

5. **Install assets**
   ```bash
   php bin/console assets:install
   ```

6. **Create admin user**
   ```bash
   php bin/console app:create-admin
   ```

7. **Start development server**
   ```bash
   php bin/console server:start
   ```

### Environment Configuration

Create a `.env` file with the following variables:
```env
DATABASE_URL="mysql://username:password@localhost:3306/job_portal"
MAILER_DSN=smtp://localhost
APP_ENV=dev
APP_SECRET=your-secret-key
```

## 👥 User Roles & Permissions

### ROLE_USER (Job Seeker)
- Browse job postings
- Apply to jobs
- Manage profile and CV
- Send messages to employers
- View application status

### ROLE_EMPLOYEUR (Employer)
- Post job announcements
- Manage job postings
- Review applications
- Communicate with candidates
- Access employer dashboard

### ROLE_ADMIN (Administrator)
- Full system access
- User management
- Content moderation
- System configuration
- Analytics and reporting

## 🔧 Key Features Implementation

### Job Search & Application
- Advanced search with filters (location, salary, experience)
- Application tracking system
- Email notifications for applications
- Interview scheduling

### User Management
- Complete user profiles with professional information
- CV/resume upload and management
- Profile verification system
- Professional networking features

### Communication System
- Real-time messaging between users
- Interview scheduling and management
- Email notifications
- SMS integration (Twilio)

### Admin Panel
- EasyAdmin integration for content management
- User moderation and management
- Job posting approval system
- Analytics and reporting

## 🎨 Frontend Features

- **Responsive Design**: Mobile-friendly interface
- **Modern UI**: Bootstrap 5 with custom styling
- **Interactive Elements**: AJAX-powered interactions
- **File Upload**: Drag-and-drop file uploads
- **Calendar Integration**: FullCalendar for scheduling
- **Rich Text Editing**: CKEditor for content creation

## 🔒 Security Features

- **User Authentication**: Symfony Security Bundle
- **Role-based Access Control**: Granular permissions
- **CSRF Protection**: Form security
- **Input Validation**: Comprehensive validation rules
- **File Upload Security**: Secure file handling
- **Password Reset**: Secure password recovery

## 📊 Performance & Optimization

- **Asset Optimization**: Compiled and minified assets
- **Database Optimization**: Efficient queries and indexing
- **Caching**: Symfony cache system
- **Image Processing**: Optimized image uploads
- **Pagination**: Efficient content loading

## 🧪 Testing

Run tests with PHPUnit:
```bash
php bin/phpunit
```

## 📝 API Documentation

The application provides RESTful endpoints for:
- User management
- Job posting and search
- Application processing
- Messaging system

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests for new functionality
5. Submit a pull request

## 📄 License

This project is proprietary software. All rights reserved.

## 🆘 Support

For support and questions:
- Create an issue in the repository
- Contact the development team
- Check the documentation

## 🔄 Version History

- **v1.0.0**: Initial release with core job portal functionality
- **v1.1.0**: Added messaging system and user profiles
- **v1.2.0**: Enhanced admin panel and security features
- **v1.3.0**: Mobile optimization and performance improvements

---

**Built with ❤️ using Symfony 4.4** 