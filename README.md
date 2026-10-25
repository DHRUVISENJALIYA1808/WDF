# 🎓 Web Development Framework (WDF) — Laboratory Practicals

**Charusat University • Faculty of Technology**  
*Curriculum Laboratory Repository for Web Development Framework (WDF)*

---

## 📌 Project Overview

This repository contains the complete laboratory practicals for the **Web Development Framework (WDF)** coursework. The practicals culminate in **StudentHub**, a comprehensive academic web application designed to demonstrate both client-side and server-side web engineering principles.

The system integrates modern frontend design, structured JSON data bindings, MySQL database integration with PDO and MySQLi, session security, role-based access control (RBAC), asynchronous RESTful CRUD operations, and an automated deployment verification suite.

---

## 🛠️ Technologies & Tools

- **Frontend:** Semantic HTML5, CSS3 (Responsive Grid & Flexbox, Dark Mode), Modern JavaScript (ES6+, DOM Manipulation, Fetch API), Chart.js
- **Backend:** PHP 8.1+ (Object-Oriented & Procedural, PDO, MySQLi, Session Security, Server-Side MIME Verification)
- **Database:** MySQL / MariaDB 10.4+ (Prepared Statements, Bcrypt Password Hashing, Multi-Port Support for 3306 & 3307)
- **Architecture & Modeling:** Draw.io (Sitemap & Wireframe Models), JSON Schemas, Apache VirtualHost Configuration
- **Environment:** XAMPP / LAMP / WAMP Stack

---

## 📂 Laboratory Practicals Index (Practicals 1 – 15)

The repository organizes all 15 practicals into 12 dedicated folders to preserve modularity and avoid naming collisions across individual lab submissions:

| Practical | Module Title | Directory | Key Technologies | Description & Highlights |
| :--- | :--- | :--- | :--- | :--- |
| **Practical 1** | Sitemap & Wireframing | [`Practical-1/`](Practical-1/) | XML / Draw.io | Information architecture, user navigation journeys, and Draw.io system wireframes. |
| **Practical 2** | UI Structure & HTML5 Templates | [`Practical-2/`](Practical-2/) | Semantic HTML5, PHP | Responsive views for Home, About, Events, Feedback, Dashboard, Edit, and Profile. |
| **Practical 3** | CSS3 Design System | [`Practical-3/`](Practical-3/) | Vanilla CSS3, Grid, Flexbox | Typography, university brand colors, dark-mode styling, and responsive UI components. |
| **Practical 4 & 5** | JavaScript & Client-Side Validation | [`Practical-4&5/`](Practical-4&5/) | Modern JavaScript (ES6+) | Dynamic DOM manipulation, theme persistence via localStorage, regex form validation, and weather API. |
| **Practical 6** | Structured Data & JSON Schemas | [`Practical-6/`](Practical-6/) | JSON | Structured data fixtures for FAQs, event schedules, user registration, and system settings. |
| **Practical 7, 8 & 9** | Database Integration & Authentication | [`Practical-7&8&9/`](Practical-7&8&9/) | PHP, MySQL, PDO | MySQL PDO connection, bcrypt password hashing, active student sessions, and registration pipeline. |
| **Practical 10** | Advanced Session Security | [`Practical-10/`](Practical-10/) | PHP Sessions, Cookies | 15-minute inactivity session expiration, split remember-me tokens (`selector` + `validator`), and ID regeneration. |
| **Practical 11** | Student Management CRUD | [`Practical-11/`](Practical-11/) | MySQLi Prepared Statements | Prepared statements, multi-field search and pagination, soft-deletion, and CSV data export. |
| **Practical 12** | Event Management CRUD & File Upload | [`Practical-12/`](Practical-12/) | PHP File Handling, MIME Verification | Event administration with `finfo_file` MIME verification, strict 2MB poster limit, and audit trails. |
| **Practical 13** | REST API & Asynchronous CRUD | [`Practical-13/`](Practical-13/) | Fetch API, RESTful JSON | JavaScript Fetch API integration with zero page reloads, standard HTTP response codes, and JSON payloads. |
| **Practical 14** | Admin Dashboard & RBAC | [`Practical-14/`](Practical-14/) | PHP RBAC, Chart.js | Administrative console with Chart.js registration trends, role gatekeeper, and HTTP 403 access control. |
| **Practical 15** | Portal Integration & Deployment | [`Practical-15/`](Practical-15/) | Apache VHost, System Suite | Automated 7-pillar verification suite, Apache VirtualHost, unified database schema, and portal launcher. |

---

## 🗂️ Repository Structure

```text
WDF/
├── Practical-1/             # Sitemap & Wireframing (Draw.io architecture)
├── Practical-2/             # Semantic HTML5 Templates & PHP Views
├── Practical-3/             # CSS3 Design System & Theme Styles
├── Practical-4&5/           # JavaScript DOM Logic, Validation & Weather API
├── Practical-6/             # Structured JSON Data Schemas
├── Practical-7&8&9/         # Database Connection, Authentication & Sessions
├── Practical-10/            # Advanced Session Management & Security
├── Practical-11/            # Student Management CRUD & CSV Export
├── Practical-12/            # Event Management CRUD & File Uploads
│   └── uploads/posters/     # Upload directory with security headers
├── Practical-13/            # Asynchronous CRUD with RESTful Fetch API
├── Practical-14/            # Admin Dashboard, RBAC & Chart.js Analytics
├── Practical-15/            # System Verification Suite & Deployment Package
├── index.php                # Root Portal Dispatcher
├── README.md                # Project Documentation & Practical Index
└── .gitignore               # Ignored OS & Editor Artifacts
```

---

## ⚡ Quick Start & Setup Guide

### 📋 Prerequisites
- **Web Server:** XAMPP, WAMP, or LAMP stack with Apache 2.4+
- **PHP Version:** PHP 8.1+ with extensions enabled: `pdo_mysql`, `mysqli`, `fileinfo`, `json`, `mbstring`
- **Database:** MySQL / MariaDB 10.4+ (supports standard port `3306` and alternate port `3307`)

---

### 🚀 Step 1: Place Files in Local Web Server
Clone or copy this repository into your local web server root directory (e.g., `htdocs` in XAMPP):
```bash
cd C:\xampp\htdocs
git clone https://github.com/DHRUVISENJALIYA1808/WDF.git
```

---

### 🗄️ Step 2: Database Initialization & Seeding
The project features an automated, self-healing database seeder:
1. Start **Apache** and **MySQL** in the XAMPP Control Panel.
2. Open your browser and run the database setup script:
   ```text
   http://localhost/WDF/Practical-15/setup_portal.php
   ```
   *Alternatively, import `Practical-15/portal_schema.sql` directly via phpMyAdmin.*
3. The installer will automatically:
   - Auto-detect MySQL on port **3306** or **3307**.
   - Create the `studenthub` database if it does not already exist.
   - Provision all required tables (`students`, `events`, `registrations`, `auth_tokens`, `audit_logs`).
   - Seed default test accounts and sample event records.

---

### 🌐 Step 3: Accessing the Portal

#### Option A: Localhost Subfolder (Default)
Open in browser:
```text
http://localhost/WDF/
```
The root `index.php` dispatcher routes public visitors to the homepage and authenticated accounts to their respective dashboards.

#### Option B: Virtual Host Deployment (Optional)
1. Add to `C:\Windows\System32\drivers\etc\hosts`:
   ```text
   127.0.0.1    studenthub.local
   127.0.0.1    www.studenthub.local
   ```
2. Append the Virtual Host configuration from `Practical-15/studenthub-vhost.conf` to your Apache `httpd-vhosts.conf`.
3. Restart Apache and access `http://studenthub.local/`.

---

### 🧪 Step 4: Automated System Diagnostic Suite
To verify routes, responsiveness, authentication, database operations, security headers, and AJAX endpoints, visit:
```text
http://localhost/WDF/Practical-15/verify_portal.php
```

---

## 🔑 Test Credentials for Evaluation

| Account Role | University Email | Password | Primary Destination |
| :--- | :--- | :--- | :--- |
| **Administrator** | `admin@charusat.edu.in` | `Admin@123` | Admin Dashboard (`Practical-14`) |
| **Student (Demo 1)** | `25dce099@charusat.edu.in` | `Rohan@123` | Student Dashboard & Profile (`Practical-2`) |
| **Student (Demo 2)** | `25dce017@charusat.edu.in` | `Yaksh@123` | Student Dashboard & Profile (`Practical-2`) |

---

## 🛡️ Security Implementation Highlights

- **SQL Injection Prevention:** 100% prepared queries using parameterized statements (`?` or `:placeholder`) across PDO and MySQLi connections.
- **Cross-Site Scripting (XSS) Defense:** Strict `htmlspecialchars($data, ENT_QUOTES, 'UTF-8')` escaping on all user-rendered output.
- **Role-Based Access Control (RBAC):** Server-side route guarding with `requireAdmin()` returning HTTP `403 Forbidden` for unauthorized requests.
- **Session Security:** Immediate session ID regeneration upon login, 15-minute inactivity timeout, and timing-attack immune remember-me split tokens (`selector` + `validator`).
- **File Upload Protection:** Server-side binary MIME verification via `finfo_file()` with strict $\le 2\text{ MB}$ file size enforcement and directory access controls.

---

## 📜 License

Developed as part of the Web Development curriculum at **CHARUSAT University**. All Rights Reserved © 2026.
