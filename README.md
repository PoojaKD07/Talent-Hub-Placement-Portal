# Talent Hub – Student Placement & Recruitment Portal

A full-stack campus placement and recruitment management application developed using **Node.js, Express.js, MySQL, HTML, CSS and JavaScript**.

Talent Hub connects students, companies and placement administrators through a centralized recruitment platform.

## 1. Project Overview

Talent Hub is designed to simplify and manage the campus placement process. It provides separate functionalities for students, companies and administrators.

Students can explore job opportunities, check eligibility and apply for jobs. Companies can publish job openings, review applications and manage interviews. Administrators can monitor placement activities through a centralized dashboard.

## 2. Project Objectives

- Develop a centralized campus placement platform.
- Provide separate access for students, companies and administrators.
- Automate job eligibility checking.
- Simplify job applications and application tracking.
- Support interview scheduling and offer management.
- Maintain structured placement information using MySQL.

## 3. Key Features

### Student Module
- Student registration and login.
- Create and update academic profiles.
- Browse and search job opportunities.
- Check eligibility based on department, CGPA and backlogs.
- Apply for eligible jobs.
- Track application status.
- View interview schedules and offers.
- Accept or decline placement offers.
- View notifications.

### Company Module
- Company registration and login.
- Create job and internship postings.
- Specify eligibility requirements.
- Review student applications.
- Shortlist or reject applicants.
- Create interview availability slots.
- Schedule interviews through the API.
- Publish placement offers.

### Administrator Module
- Administrator authentication.
- View student statistics.
- View company statistics.
- Monitor job postings and applications.
- View accepted offer statistics.

## 4. Eligibility Checking

The application checks student eligibility before accepting a job application.

| Eligibility criterion | Description |
|---|---|
| Department | Checks whether the student's department is allowed |
| Minimum CGPA | Checks the student's CGPA against the job requirement |
| Active backlogs | Checks the number of pending backlogs |
| Total backlogs | Checks the total number of backlogs, including cleared ones |

The application performs these checks on the backend before creating an application.

## 5. Technologies Used

| Technology | Purpose |
|---|---|
| Node.js | JavaScript runtime |
| Express.js | Backend framework |
| MySQL | Relational database |
| mysql2 | MySQL database connectivity |
| HTML | Frontend structure |
| CSS | Interface styling |
| JavaScript | Frontend interactions |
| bcryptjs | Password hashing |
| JSON Web Token | Authentication |
| dotenv | Environment configuration |

## 6. Project Structure

```text
Talent-Hub-Placement-Portal/
│
├── database/
│   ├── schema.sql
│   └── migration_eligibility.sql
│
├── docs/
│   └── PROJECT_OVERVIEW.md
│
├── frontend/
│   ├── index.html
│   ├── app.js
│   └── styles.css
│
├── .env.example
├── .gitignore
├── package.json
├── server.js
└── README.md
```

## 7. Installation Requirements

Install the following software before running the application:

- Node.js LTS
- npm
- MySQL Server 8.x or compatible version
- A modern web browser
- MySQL Workbench (optional)

Check Node.js and npm installation:

```bash
node -v
npm -v
```

## 8. Installation and Execution

### Step 1: Clone the Repository

```bash
git clone https://github.com/YOUR-USERNAME/Talent-Hub-Placement-Portal.git
cd Talent-Hub-Placement-Portal
```

Replace `YOUR-USERNAME` with your GitHub username.

### Step 2: Create the MySQL Database

For a fresh installation, execute:

```bash
mysql -u root -p < database/schema.sql
```

Alternatively, open `database/schema.sql` in MySQL Workbench and execute the script.

### Step 3: Configure Environment Variables

Copy `.env.example` to a new file named `.env` in the project root.

Update the configuration with your own database credentials and secure secrets:

```env
PORT=5000
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=your_actual_mysql_password
DB_NAME=talent_hub
JWT_SECRET=your_unique_secret_key
ADMIN_EMAIL=your_admin_email
ADMIN_PASSWORD=your_strong_admin_password
```

Use your actual local MySQL password and a strong, unique JWT secret and administrator password.

**Important:** Never upload `.env` to GitHub. Only `.env.example` should be included in the repository.

### Step 4: Install Dependencies

```bash
npm install
```

### Step 5: Start the Application

```bash
npm start
```

### Step 6: Open the Application

Open a web browser and visit:

```text
http://localhost:5000
```

Register student and company accounts to explore the application.

Use the administrator credentials configured in your local `.env` file for administrator access.

## 9. Database Information

The project uses MySQL as its relational database.

The database schema includes tables for:

1. Students
2. Companies
3. Job Listings
4. Job Eligible Departments
5. Applications
6. Interview Slots
7. Interviews
8. Offers
9. Skills
10. Student Skills
11. Notifications

Foreign keys and constraints help maintain relationships between the records.

### Database Migration

The project also includes:

`database/migration_eligibility.sql`

This migration is intended for an existing database created using the earlier schema. For a fresh installation, use `database/schema.sql` instead. Do not run the migration repeatedly.

## 10. Important API Endpoints

| Method | Endpoint | Function |
|---|---|---|
| POST | `/api/auth/register/student` | Register student |
| POST | `/api/auth/register/company` | Register company |
| POST | `/api/auth/login` | User login |
| GET | `/api/health` | Check server/database |
| GET | `/api/departments` | View departments |
| GET | `/api/jobs` | Browse job listings |
| POST | `/api/jobs` | Create a job |
| GET / PUT | `/api/students/me` | View/update student profile |
| POST | `/api/applications` | Apply for a job |
| GET | `/api/applications/mine` | View own applications |
| GET | `/api/company/applications` | View company applications |
| PATCH | `/api/applications/:id/status` | Update application status |
| POST | `/api/interview-slots` | Create interview slot |
| POST | `/api/interviews` | Schedule interview |
| GET | `/api/interviews/mine` | View student interviews |
| POST | `/api/offers` | Publish an offer |
| GET | `/api/offers/mine` | View student offers |
| PATCH | `/api/offers/:id/respond` | Respond to an offer |
| GET | `/api/notifications` | View notifications |
| GET | `/api/admin/summary` | View administrator summary |

## 11. Security Features

- Password hashing using bcryptjs.
- JWT-based authentication.
- Role-based access control.
- Parameterized SQL queries.
- Backend eligibility verification.
- Environment-based configuration for secrets.

## 12. Conclusion

Talent Hub demonstrates the use of full-stack web development, REST API design, relational database management, authentication and authorization, and recruitment workflow automation.

The project provides a centralized platform for managing important campus placement activities and improving communication between students, companies and placement administrators.

---

**Talent Hub – Connecting Students, Companies and Career Opportunities.**
