

# Learning Management System (LMS)

This Learning Management System (LMS) is a web-based application designed to help administrators and teachers manage students, teachers, and various academic data effectively. The application includes features for managing users, adding and viewing teachers, tracking statistics, and enabling students to view their academic results through a user-friendly dashboard. profuse

## Table of Contents
- [Project Overview](#project-overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Installation](#installation)
- [Usage](#usage)
- [Folder Structure](#folder-structure)
- [Database Structure](#database-structure)
- [Contributing](#contributing)
- [License](#license)

---

## Project Overview

The LMS provides a responsive and intuitive dashboard for Admin users to manage the essential components of a learning institution. Admins can:
- View statistics of registered teachers and students
- Add new teachers
- Manage user roles and permissions

Additionally, students can view their grades, subjects, and results once published by the teacher, enabling a transparent academic performance tracking system.

The system is developed using PHP for server-side logic, MySQL for database management, and Bootstrap for styling.

## Features

- **User Authentication**: Admin users can log in securely to access the admin dashboard.
- **Admin Dashboard**: Admin users can view key statistics and manage teachers and students.
- **Manage Teachers**: Admins can view, add, and edit teacher profiles.
- **View Pupils**: Admins can view and manage pupils.
- **Results Management**: Teachers can add grades for students, which students can then view in their profile once published.
- **Student Dashboard**: Students can view their grades, subjects, and results, including any recent updates to their academic records.
- **Charts and Analytics**: Pie charts show summaries for quick insights into the distribution of teachers and pupils.
- **Responsive Design**: Optimized layout for various screen sizes, enhancing user experience on both desktop and mobile devices.

## Tech Stack

- **Frontend**: HTML, CSS, Bootstrap, JavaScript
- **Backend**: PHP
- **Database**: MySQL
- **Libraries**: Chart.js for data visualization

---

## Installation

### Prerequisites
- **XAMPP/LAMP/WAMP Server**: For running PHP and MySQL
- **Composer**: For PHP dependency management (optional)
- **Git**: For version control

### Steps

1. **Clone the Repository**
   ```bash
   git clone https://github.com/your-username/lms-project.git
   cd lms-project
   ```

2. **Configure Database**
   - Create a MySQL database (e.g., `lms_db`).
   - Import the provided `lms_db.sql` file in the `database` folder into the database.
   - Update `db_connect.php` with your database credentials:
     ```php
     $servername = "localhost";
     $username = "your_db_username";
     $password = "your_db_password";
     $dbname = "lms_db";
     ```

3. **Run the Application**
   - Start your server (e.g., Apache and MySQL in XAMPP).
   - Access the application in the browser: `http://localhost/lms-project/`

---

## Usage

1. **Login**: Use the admin credentials to access the dashboard.
2. **Admin Dashboard**: 
   - View total number of teachers and pupils.
   - Access the `Manage Teachers` section to add, edit, or delete teachers.
3. **Student Dashboard**: 
   - Students can log in to view their grades, subjects, and results. Results are updated and visible once published by the teachers.
4. **Settings**: Customize additional settings (e.g., theme mode) through the settings page.
5. **Logout**: Securely end the session and return to the login page.

---

## Folder Structure

- **index.php**: Entry point for the dashboard.
- **db_connect.php**: Database connection configuration.
- **assets/**: Contains CSS, JavaScript, and images.
- **pages/**
  - `login.php`: Login page.
  - `view_teachers.php`: View all registered teachers.
  - `add_teacher.php`: Add a new teacher.
  - `student_dashboard.php`: Displays student's subjects, grades, and published results.
  - `settings.php`: Adjust settings such as theme mode.
- **partials/**: Contains reusable components like header, footer, and sidebar.
- **database/**: Contains database scripts for initial setup.

---

## Database Structure

The LMS database (`lms_db`) consists of the following tables:

1. **admin**: Stores administrator credentials.
   - `adminID`: INT, Primary Key
   - `adminName`: VARCHAR, Admin name
   - `email`: VARCHAR, Admin email
   - `password`: VARCHAR, Admin password (hashed)
   
2. **teacher**: Stores teacher profiles.
   - `teacherID`: INT, Primary Key
   - `first_name`: VARCHAR, Teacher first name
   - `last_name`: VARCHAR, Teacher last name
   - `email`: VARCHAR, Teacher email
   
3. **pupil**: Stores pupil profiles.
   - `pupilID`: INT, Primary Key
   - `first_name`: VARCHAR, Pupil first name
   - `last_name`: VARCHAR, Pupil last name
   - `class_id`: INT, Foreign key to `class`
   
4. **class**: Stores class details.
   - `classID`: INT, Primary Key
   - `name`: VARCHAR, Class name

5. **results**: Stores student grades and published results.
   - `resultID`: INT, Primary Key
   - `pupilID`: INT, Foreign Key to `pupil`
   - `subject`: VARCHAR, Name of the subject
   - `grade`: VARCHAR, Student’s grade for the subject
   - `published`: BOOLEAN, Flag indicating if the result is visible to students

---

## Contributing

Contributions are welcome! To contribute:
1. Fork the repository.
2. Create a new branch for your feature: `git checkout -b feature/feature-name`.
3. Commit changes: `git commit -m 'Add new feature'`.
4. Push to the branch: `git push origin feature/feature-name`.
5. Submit a pull request.

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Acknowledgments

Special thanks to the open-source libraries and tools that made this project possible:
- [Chart.js](https://www.chartjs.org/)
- [Bootstrap](https://getbootstrap.com/)
- [Font Awesome](https://fontawesome.com/)

---
