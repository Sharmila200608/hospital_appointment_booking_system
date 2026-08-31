<div align="center">

# 🏥 Hospital Appointment Booking System

### A Complete Web-Based Hospital Appointment Management System

<p>
  <b>Book Appointments • Manage Doctors • Track Appointments • Admin Dashboard</b>
</p>

<br>

<img src="https://img.shields.io/badge/PHP-8.x-777BB4?style=for-the-badge&logo=php&logoColor=white">
<img src="https://img.shields.io/badge/MySQL-8.x-4479A1?style=for-the-badge&logo=mysql&logoColor=white">
<img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white">
<img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white">
<img src="https://img.shields.io/badge/JavaScript-ES6-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black">

<br><br>

<img src="https://img.shields.io/badge/License-MIT-green?style=for-the-badge">

</div>

---

## 📖 About The Project

The **Hospital Appointment Booking System** is a full-stack web application developed to simplify and manage hospital appointment scheduling.

The system allows patients to browse doctors, select their preferred doctor, choose an available date and time, and book appointments online.

An **Admin Dashboard** is also provided to manage doctors and appointments efficiently.

This project is built using **PHP, MySQL, HTML5, CSS3, and Vanilla JavaScript**, making it simple to understand, run, and maintain.

---

## 🎯 Project Objectives

The main objectives of this project are:

* 🏥 Digitize the hospital appointment booking process
* 👨‍⚕️ Make doctor information easily accessible
* 📅 Simplify appointment scheduling
* 👤 Manage patient appointment information
* 👨‍💼 Provide an admin panel for hospital staff
* 🔒 Implement secure authentication and database operations
* ⚡ Reduce manual appointment management

---

# ✨ Features

## 👤 Patient Features

* 🏠 User-friendly home page
* 👨‍⚕️ Browse available doctors
* 🏥 View doctors by department
* 📋 View doctor details and experience
* 📅 Select appointment date
* ⏰ Select appointment time
* 📝 Enter patient details
* ✅ Book appointments online
* 🎫 Generate unique Appointment ID
* 🔍 Search existing appointments
* 📱 Search appointments using phone number
* ❌ Cancel appointments
* ✔️ Client-side form validation
* ✔️ Server-side form validation

---

## 👨‍💼 Admin Features

* 🔐 Secure Admin Login
* 📊 Admin Dashboard
* 📈 View appointment statistics
* 👨‍⚕️ Add new doctors
* 🗑️ Delete doctors
* 📋 View all appointments
* 🔍 Search appointments
* 🔄 Update appointment status
* ❌ Delete appointments
* 📅 View today's appointments
* 📊 Monitor cancelled appointments

---

# 🛠️ Technology Stack

| Technology           | Usage                                   |
| -------------------- | --------------------------------------- |
| 🐘 **PHP 8.x**       | Backend development                     |
| 🗄️ **MySQL**        | Database management                     |
| 🌐 **HTML5**         | Website structure                       |
| 🎨 **CSS3**          | Styling and responsive design           |
| ⚡ **JavaScript ES6** | Client-side validation and interactions |
| 🔌 **PDO / MySQL**   | Database connectivity                   |
| 🔐 **PHP Sessions**  | Admin authentication                    |
| 🖥️ **XAMPP**        | Local development environment           |
| 💻 **VS Code**       | Development environment                 |

---

# 🏗️ System Architecture

```text
                    ┌─────────────────────┐
                    │       PATIENT       │
                    │      Web Browser    │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   HTML / CSS / JS   │
                    │      Frontend       │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │        PHP          │
                    │       Backend       │
                    │ Validation & Logic  │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │       MySQL         │
                    │      Database       │
                    └─────────────────────┘
```

---

# 🗃️ Database Design

The system uses **MySQL** to store and manage application data.

### 👨‍⚕️ Doctors Table

```text
doctors
────────────────────────────
doctor_id        PRIMARY KEY
name
department
qualification
experience
phone
email
available_days
available_time
```

### 👤 Patients Table

```text
patients
────────────────────────────
patient_id       PRIMARY KEY
name
age
gender
phone
email
```

### 📅 Appointments Table

```text
appointments
────────────────────────────
appointment_id      PRIMARY KEY
patient_id          FOREIGN KEY
doctor_id           FOREIGN KEY
appointment_date
appointment_time
reason
status
created_at
```

### 🔗 Relationships

```text
             ┌─────────────┐
             │   DOCTORS   │
             └──────┬──────┘
                    │
                    │ 1
                    │
                    │ Many
                    ▼
             ┌─────────────┐
             │APPOINTMENTS │
             └──────┬──────┘
                    ▲
                    │ Many
                    │
                    │ 1
             ┌──────┴──────┐
             │   PATIENTS  │
             └─────────────┘
```

* One doctor can have multiple appointments.
* One patient can have multiple appointments.
* Each appointment belongs to one doctor and one patient.

---

# 📂 Project Structure

```text
Hospital_Booking_System/
│
├── 📁 admin/
│   ├── auth.php
│   ├── login.php
│   ├── logout.php
│   ├── dashboard.php
│   ├── doctors.php
│   ├── add_doctor.php
│   └── appointments.php
│
├── 📁 patient/
│   ├── dashboard.php
│   └── cancel.php
│
├── 📁 database/
│   └── connect.php
│
├── 📁 includes/
│   ├── header.php
│   └── footer.php
│
├── 📁 css/
│   └── style.css
│
├── 📁 js/
│   ├── validation.js
│   └── animations.js
│
├── index.php
├── doctors.php
├── appointment.php
├── book.php
├── confirmation.php
├── about.php
├── contact.php
└── README.md
```

---

# 🚀 Installation & Setup

Follow the steps below to run the project on your local system.

## 1️⃣ Requirements

Before running the project, install:

* **XAMPP**
* **PHP 8.x**
* **MySQL**
* **Git**
* **VS Code**

---

## 2️⃣ Clone the Repository

Open the VS Code terminal and run:

```bash
git clone https://github.com/Sharmila200608/hospital_appointment_booking_system.git
```

Navigate to the project:

```bash
cd hospital_appointment_booking_system
```

---

# 🐘 PHP Setup

If PHP is already configured in your system, check the PHP version using:

```bash
php -v
```

If PHP is not available directly through the terminal, use the XAMPP PHP executable.

### First time only

Run:

```powershell
C:\xampp\php\php.exe -v
```

This confirms that PHP is installed correctly through XAMPP.

---

# 🗄️ MySQL Setup

### Step 1 — Start XAMPP

Open **XAMPP Control Panel**.

Start:

```text
MySQL  → Start
```

You do not need to start Apache if you are running the project using PHP's built-in development server.

---

### Step 2 — Create Database

Open:

```text
http://localhost/phpmyadmin
```

Create a new database named:

```text
hospital_booking_system
```

Import or create the required tables using the SQL file provided with the project, if available.

---

### Step 3 — Configure Database Connection

Open:

```text
database/connect.php
```

Configure your MySQL connection.

Example:

```php
<?php

$host = "localhost";
$dbname = "hospital_booking_system";
$username = "root";
$password = "";

$conn = new PDO(
    "mysql:host=$host;dbname=$dbname;charset=utf8mb4",
    $username,
    $password
);

$conn->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);

?>
```

> **Note:** Change the username and password if your MySQL configuration is different.

---

# ▶️ Run the Application

After configuring MySQL, open the VS Code terminal.

Go to the project directory:

```powershell
cd C:\Hospital_Booking_System\hbs
```

Then start the PHP development server:

```powershell
php -S localhost:8000
```

If the `php` command is not recognized, use:

```powershell
C:\xampp\php\php.exe -S localhost:8000
```

You should see:

```text
Development Server (http://localhost:8000) started
```

Now open your browser:

```text
http://localhost:8000
```

🎉 **The Hospital Appointment Booking System is now running!**

---

# 🔄 How To Run The Project Every Time

After the initial PHP setup, you only need to follow these steps:

```text
1. Open XAMPP
        ↓
2. Start MySQL
        ↓
3. Open VS Code
        ↓
4. Open the project folder
        ↓
5. Open VS Code Terminal
        ↓
6. Run:
   php -S localhost:8000
        ↓
7. Open:
   http://localhost:8000
```

### 💡 Important

The command:

```powershell
C:\xampp\php\php.exe -v
```

is mainly for **checking PHP for the first time**.

You do **not** need to run it every time.

---

# 🔐 Admin Login

Use the administrator credentials configured for the application:

```text
Username: admin
Password: admin123
```

> ⚠️ **Security:** Change the default admin password before using the application in a real production environment.

---

# 🧭 Application Workflow

## 👤 Patient Workflow

```text
🏠 Home
   │
   ▼
👨‍⚕️ Browse Doctors
   │
   ▼
🏥 Select Department
   │
   ▼
👨‍⚕️ Select Doctor
   │
   ▼
📅 Select Date & Time
   │
   ▼
📝 Enter Patient Details
   │
   ▼
✅ Book Appointment
   │
   ▼
🎫 Confirmation
   │
   ▼
🆔 Appointment ID
```

---

## 👨‍💼 Admin Workflow

```text
🔐 Admin Login
      │
      ▼
📊 Dashboard
      │
      ├──────────────► 👨‍⚕️ Manage Doctors
      │
      └──────────────► 📅 Manage Appointments
                              │
                              ▼
                       🔍 Search
                              │
                              ▼
                       🔄 Update Status
                              │
                              ▼
                       ❌ Delete
```

---

# 🔒 Security

The application includes several security practices.

### 🔐 Password Hashing

Admin passwords are protected using PHP password hashing:

```php
password_hash()
```

### 🛡️ SQL Injection Protection

Prepared statements are used for database queries.

Example:

```php
$stmt = $conn->prepare(
    "SELECT * FROM doctors WHERE doctor_id = ?"
);

$stmt->execute([$doctorId]);
```

### 🧹 XSS Protection

User-generated output is escaped using:

```php
htmlspecialchars($value)
```

### 🔑 Session Authentication

Admin pages are protected using PHP sessions.

### 🚫 Double Booking Prevention

The application checks the selected:

```text
Doctor + Appointment Date + Appointment Time
```

before creating a new appointment.

---

# 📊 Admin Dashboard

The admin dashboard provides an overview of the hospital appointment system.

It can display:

| Statistic                | Description                      |
| ------------------------ | -------------------------------- |
| 👨‍⚕️ Total Doctors      | Number of registered doctors     |
| 📅 Total Appointments    | Total appointments               |
| 📆 Today's Appointments  | Appointments scheduled for today |
| ❌ Cancelled Appointments | Number of cancelled bookings     |

---

# 🌟 Why This Project?

This project demonstrates practical full-stack web development concepts such as:

* Frontend development
* Backend development
* MySQL database integration
* CRUD operations
* Authentication
* Session management
* Form validation
* Secure database operations
* Appointment scheduling
* Admin dashboard development
* Responsive web design

---

# 🚀 Future Enhancements

The system can be extended with:

* [ ] 📧 Email appointment reminders
* [ ] 📱 SMS notifications
* [ ] 👤 Patient registration and login
* [ ] 👨‍⚕️ Doctor login portal
* [ ] 📅 Calendar-based scheduling
* [ ] 🔔 Real-time notifications
* [ ] 📊 Advanced analytics
* [ ] 💳 Online payment integration
* [ ] 🌍 Multi-language support
* [ ] ☁️ Cloud deployment
* [ ] 🏥 Multiple hospital support

---

# 🎓 Project Purpose

This project was developed as a **Full-Stack Web Development Project** to demonstrate the practical implementation of:

> **HTML + CSS + JavaScript + PHP + MySQL**

It provides hands-on experience with frontend development, backend programming, database management, authentication, CRUD operations, and real-world appointment scheduling.

---

# 📄 License

This project is licensed under the **MIT License**.

You are free to:

* Use the project
* Modify the project
* Extend the project
* Distribute the project

See the `LICENSE` file for complete license information.

---

# 👩‍💻 Author

<div align="center">

## **Sharmila R**

### 💻 Full-Stack Web Development Project

🏥 **Hospital Appointment Booking System**

<br>

⭐ If you find this project useful, please consider giving it a **Star**!

🍴 **Fork** • ⭐ **Star** • 💡 **Contribute**

</div>

---

<div align="center">

## 🏥 Hospital Appointment Booking System

### Making hospital appointment management simple, fast, and accessible.

**Built with ❤️ using PHP & MySQL**

</div>
