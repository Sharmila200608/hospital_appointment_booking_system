<div align="center">

# 🏥 Hospital Appointment Booking System

A full-stack web application for booking, managing, and tracking hospital appointments — built with plain **HTML, CSS, JavaScript, PHP, and SQLite** (no frameworks required).

![PHP](https://img.shields.io/badge/PHP-8.x-777BB4?style=flat-square&logo=php&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-3-003B57?style=flat-square&logo=sqlite&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML-5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS-3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)

</div>

---

## 📖 Overview

The **Hospital Appointment Booking System** lets patients browse doctors, book appointments online, and track or cancel their bookings — while giving hospital staff an admin panel to manage doctors and appointments in real time.

It's built entirely on **PHP + MySQL**, so it runs anywhere PHP runs, with zero external services, no build step, and no database server to install.

---

## ✨ Features

**Patient side**
- Browse doctors by department, experience, and availability
- Book an appointment with client-side **and** server-side validation
- Instant booking confirmation with a unique Appointment ID
- Look up and cancel appointments using a phone number (no account needed)

**Admin side**
- Secure login (hashed passwords, session-based auth)
- Dashboard with live stats (total doctors, total appointments, today's appointments, cancellations)
- Add / remove doctors
- Search, update status, or delete any appointment

**Engineering**
- Client-side validation (JS) for instant feedback + server-side re-validation (PHP) for real security
- Prepared statements throughout (SQL-injection safe)
- Output escaping throughout (XSS safe)
- Double-booking prevention (same doctor, same date & time slot)
- Auto-provisioning database — schema and seed data are created on first run, no manual SQL required

---

## 🛠️ Tech Stack

| Layer | Technology | Purpose |
|---|---|---|
| Structure | HTML5 | Page markup |
| Styling | CSS3 | Layout, theming, animations |
| Interactivity | Vanilla JavaScript | Form validation, UI animation |
| Backend | PHP 8 | Server logic, routing, sessions |
| Database | SQLite 3 (via PDO) | Persistent storage in a single file |

---

## 🏗️ Architecture

```
Browser (HTML/CSS/JS)
        │  form submit
        ▼
   book.php  ──────────────►  database/connect.php (PDO)
        │  validate + insert            │
        ▼                               ▼
confirmation.php               hospital.db (SQLite)
```

- **`includes/header.php` & `includes/footer.php`** — shared layout, included on every page so nav/footer changes happen in one place.
- **`database/connect.php`** — the single gatekeeper to the database; creates tables and seed data automatically if they don't exist.
- **Patients** are identified by phone number lookup (no login required).
- **Admins** authenticate via PHP sessions, guarded by `admin/auth.php` on every protected page.

### Database schema (SQLite)

```
doctors                    patients                    appointments
────────────────           ────────────────            ─────────────────────
doctor_id (PK)              patient_id (PK)             appointment_id (PK)
name                        name                         patient_id (FK)
department                  age                          doctor_id (FK)
qualification                gender                       appointment_date
experience                  phone                        appointment_time
phone                        email                        reason
email                                                    status
available_days                                            created_at
available_time
```

One doctor → many appointments. One patient → many appointments.

---

## 📂 Project Structure

```
HospitalAppointmentSystem/
├── admin/                  # Admin login, dashboard, doctor & appointment management
│   ├── auth.php            # Session guard included on every protected admin page
│   ├── login.php / logout.php
│   ├── dashboard.php
│   ├── doctors.php / add_doctor.php
│   └── appointments.php
├── patient/                 # Patient appointment lookup & cancellation
│   ├── dashboard.php
│   └── cancel.php
├── database/
│   ├── connect.php          # PDO connection + schema + seed data (auto-run)
│   └── hospital.db          # Generated on first run — not committed to git
├── includes/
│   ├── header.php
│   └── footer.php
├── css/style.css
├── js/
│   ├── validation.js        # Client-side form validation
│   └── animations.js        # Scroll-reveal, ripple, counters (purely visual)
├── index.php / doctors.php / appointment.php / book.php
├── confirmation.php / about.php / contact.php
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites
- PHP 8.x with the `pdo_sqlite` extension enabled (bundled by default in most PHP installs and in XAMPP/WAMP/MAMP)

### Option A — PHP's built-in server (fastest)
```bash
git clone https://github.com/Snehar273/hospital-appointment-system.git
cd hospital-appointment-system
php -S localhost:8000
```
Visit **http://localhost:8000**

### Option B — XAMPP / WAMP / MAMP
1. Copy the project folder into `htdocs` (XAMPP) or `www` (WAMP).
2. Start Apache from the control panel.
3. Visit `http://localhost/hospital-appointment-system/`

No manual database setup is needed — `database/connect.php` creates `hospital.db`, its tables, 6 sample doctors, and a default admin account automatically the first time any page loads.

### Default admin login
```
Username: admin
Password: admin123
```
> ⚠️ Change this before deploying anywhere public — see [Security Notes](#-security-notes).

---

## 🧭 Usage Walkthrough

1. **Home → Book Appointment** — fill in patient details, pick a doctor, date, and time slot.
2. Submit — you'll land on a **Confirmation** page with your Appointment ID.
3. **My Appointments** — look up your booking using the phone number you registered with, and cancel it if needed.
4. **Admin → Login** — view live stats, add/remove doctors, and manage all appointments (search by name, update status, delete).

---

## 🔒 Security Notes

- Passwords are hashed with `password_hash()` — never stored in plain text.
- All database queries use **PDO prepared statements** to prevent SQL injection.
- All output is passed through `htmlspecialchars()` to prevent XSS.
- Before deploying publicly:
  - Change the default admin password.
  - Block direct access to `database/hospital.db` (e.g. an `.htaccess` with `Deny from all` inside the `database/` folder).
  - Serve over HTTPS.

---

## 🌐 Deployment

Works on any standard PHP shared host (cPanel, etc.) or a VPS with Apache/Nginx + PHP.

> **Note:** Platforms with an ephemeral filesystem (e.g. free tiers of Render/Railway/Heroku) will **wipe `hospital.db` on every restart or redeploy**. For persistent data, use standard PHP hosting, a VPS, or attach a persistent volume.

---

## 🗺️ Roadmap / Possible Extensions

- [ ] Email/SMS appointment reminders
- [ ] Patient accounts with authentication
- [ ] Doctor-side portal for viewing their own schedule
- [ ] Calendar view for admins
- [ ] Migrate to MySQL/PostgreSQL for multi-server deployments

---

## 📄 License

This project is open-sourced under the [MIT License](LICENSE).

---

## 🙋 Author

Built as a full-stack development project.
Feel free to fork, adapt, and extend it for your own use case.
