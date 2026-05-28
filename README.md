# University Project Management System

## Overview
A comprehensive online university platform for managing 100+ courses across multiple departments with complete course catalogs, student enrollment, and video course materials.

## Features

- ✅ **100 Courses** across 10 departments
- ✅ **Complete Course Management** system
- ✅ **Student Enrollment** tracking
- ✅ **Video Scripts** with natural, humanized language
- ✅ **Course Scheduling** and capacity management
- ✅ **Department Organization** by academic discipline
- ✅ **RESTful API** for course operations
- ✅ **Database Models** for scalability

## Project Structure

```
pm_course/
├── README.md
├── courses/
│   ├── course_database.json          # Complete 100-course catalog
│   ├── course_categories.json        # Department/category definitions
│   └── video_scripts/
│       ├── core_courses/             # Video scripts for core courses
│       ├── advanced_courses/         # Video scripts for advanced courses
│       └── specialization_courses/   # Video scripts for specializations
├── backend/
│   ├── server.js                    # Express server
│   ├── routes/
│   │   ├── courses.js               # Course endpoints
│   │   ├── enrollment.js            # Enrollment endpoints
│   │   └── students.js              # Student endpoints
│   ├── models/
│   │   ├── Course.js                # Course model
│   │   ├── Student.js               # Student model
│   │   └── Enrollment.js            # Enrollment model
│   └── config/
│       └── database.js              # Database configuration
├── frontend/
│   ├── index.html                   # Main page
│   ├── styles/
│   │   └── main.css                 # Styling
│   └── js/
│       ├── app.js                   # Main application logic
│       └── api.js                   # API client
├── package.json                     # Node.js dependencies
└── .env.example                     # Environment variables template
```

## Department Breakdown (100 Courses)

1. **Business & Management** (12 courses)
2. **Computer Science & Technology** (15 courses)
3. **Data Science & Analytics** (12 courses)
4. **Engineering** (13 courses)
5. **Finance & Accounting** (10 courses)
6. **Marketing & Communications** (10 courses)
7. **Psychology & Behavioral Sciences** (12 courses)
8. **Health Sciences** (10 courses)
9. **Environmental Studies** (10 courses)
10. **Entrepreneurship & Innovation** (6 courses)

## Getting Started

### Prerequisites
- Node.js 14+
- npm or yarn
- Git

### Installation

```bash
# Clone the repository
git clone https://github.com/douglasverli/pm_course.git
cd pm_course

# Install dependencies
npm install

# Set up environment
cp .env.example .env

# Start the server
npm start
```

### API Endpoints

```
GET    /api/courses              # Get all courses
GET    /api/courses/:id          # Get course details
POST   /api/courses              # Create new course
PUT    /api/courses/:id          # Update course
DELETE /api/courses/:id          # Delete course

GET    /api/students             # Get all students
POST   /api/students             # Register new student

POST   /api/enroll               # Enroll student in course
GET    /api/enrollment/:studentId # Get student's enrollments
```

## Course Categories

### Beginner Courses
- Introduction to course topics
- Fundamentals and core concepts
- No prerequisites required

### Intermediate Courses
- Advanced techniques and applications
- Requires foundational knowledge
- Hands-on projects included

### Advanced Courses
- Specialized topics and research
- Advanced problem-solving
- Industry standards and best practices

## Video Scripts

Each course includes:
- **Natural, conversational scripts** for video lessons
- **Humanized language** that feels personal and engaging
- **Clear learning objectives** outlined at the start
- **Practical examples** relevant to each discipline
- **Discussion points** for engagement
- **Action items** for students

## Database Schema

### Courses Table
```sql
CREATE TABLE courses (
  id INT PRIMARY KEY AUTO_INCREMENT,
  code VARCHAR(20) UNIQUE,
  title VARCHAR(255),
  description TEXT,
  department VARCHAR(100),
  instructor VARCHAR(255),
  level ENUM('beginner', 'intermediate', 'advanced'),
  capacity INT,
  enrolled INT DEFAULT 0,
  schedule VARCHAR(255),
  duration INT,
  credits INT,
  prerequisites TEXT,
  video_scripts_path VARCHAR(255),
  created_at TIMESTAMP,
  updated_at TIMESTAMP
);
```

### Students Table
```sql
CREATE TABLE students (
  id INT PRIMARY KEY AUTO_INCREMENT,
  email VARCHAR(255) UNIQUE,
  first_name VARCHAR(100),
  last_name VARCHAR(100),
  enrollment_date TIMESTAMP,
  status ENUM('active', 'inactive', 'graduated')
);
```

### Enrollments Table
```sql
CREATE TABLE enrollments (
  id INT PRIMARY KEY AUTO_INCREMENT,
  student_id INT,
  course_id INT,
  enrollment_date TIMESTAMP,
  progress INT DEFAULT 0,
  status ENUM('enrolled', 'completed', 'dropped'),
  grade VARCHAR(2),
  FOREIGN KEY (student_id) REFERENCES students(id),
  FOREIGN KEY (course_id) REFERENCES courses(id)
);
```

## Features Implemented

### Course Management
- ✅ Full CRUD operations
- ✅ Course categorization by department
- ✅ Level-based organization (Beginner/Intermediate/Advanced)
- ✅ Capacity and enrollment tracking
- ✅ Instructor assignment
- ✅ Schedule management

### Student Management
- ✅ Student registration and profiles
- ✅ Enrollment tracking
- ✅ Progress monitoring
- ✅ Grade management
- ✅ Course prerequisites validation

### Video Content
- ✅ Organized video script library
- ✅ Natural language scripts for engagement
- ✅ Structured lesson format
- ✅ Learning objectives per video
- ✅ Discussion prompts

### Reporting
- ✅ Enrollment reports
- ✅ Course utilization
- ✅ Student progress tracking
- ✅ Department-level analytics

## Future Enhancements

- [ ] Live streaming integration
- [ ] Interactive quizzes and assessments
- [ ] Student discussion forums
- [ ] Grade automation
- [ ] Certificate generation
- [ ] Mobile app
- [ ] Analytics dashboard
- [ ] Email notifications

## Technology Stack

- **Backend**: Node.js, Express.js
- **Frontend**: HTML5, CSS3, Vanilla JavaScript
- **Database**: MySQL/PostgreSQL or MongoDB
- **API**: RESTful JSON API
- **Version Control**: Git & GitHub

## Contributing

1. Create a feature branch (`git checkout -b feature/amazing-feature`)
2. Commit your changes (`git commit -m 'Add amazing feature'`)
3. Push to the branch (`git push origin feature/amazing-feature`)
4. Open a Pull Request

## License

MIT License - See LICENSE file for details

## Support

For questions or issues, please open a GitHub issue or contact the development team.

## Author

**Douglas Verli** - Online University Platform Developer

---

**Last Updated**: May 28, 2026
