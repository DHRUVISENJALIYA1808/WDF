# 🌐 Web Development Framework (WDF) — Lab Practicals Repository

> **Academic Submission for Web Development Framework (WDF)**  
> **Student:** Dhruvi Senjaliya  
> **Email:** dhruvisenjaliya1808@gmail.com  
> **Repository:** [https://github.com/DHRUVISENJALIYA1808/WDF](https://github.com/DHRUVISENJALIYA1808/WDF)  
> **Institution:** Charusat University • Faculty of Technology  

---

## 📌 Project Overview & Attribution

This repository houses the complete series of laboratory practicals for the **Web Development Framework (WDF)** curriculum. The coursework culminates in **StudentHub**, an enterprise-grade academic web portal consolidating 15 laboratory modules into a unified campus management ecosystem with role-based access for enrolled students, campus administrators, and public visitors.

### 🤝 Academic Attribution & Source Reference
- **Reference Project (Source):** [hetbhimani5/StudentHub](https://github.com/hetbhimani5/StudentHub) by Het Bhimani.
- **Attribution Statement:** The foundational laboratory implementation, structural architecture, and practical modules are referenced and adapted from the StudentHub repository by Het Bhimani with full authorization from the author for college laboratory submission, coursework evaluation, and educational demonstration.
- **Licensing & Copyright:** Developed under the Web Development curriculum at CHARUSAT University. All original copyrights and university curriculum guidelines are acknowledged and preserved.

---

## 📂 Laboratory Practicals Index (Practicals 1 – 15)

The repository organizes all 15 practicals into distinct, modular folders to avoid name collisions and preserve individual laboratory integrity:

| Practical | Module Title | Directory | Key Technologies | Description & Highlights |
| :--- | :--- | :--- | :--- | :--- |
| **Practical 1** | Sitemap & Wireframing | [`Practical-1/`](Practical-1/) | XML / Draw.io | Information architecture, user navigation journeys, and Draw.io system wireframes. |
| **Practical 2** | UI Structure & HTML5 Templates | [`Practical-2/`](Practical-2/) | Semantic HTML5, PHP | Responsive views for Home, About, Events, Feedback, Dashboard, Edit, and Profile. |
| **Practical 3** | CSS3 Design System | [`Practical-3/`](Practical-3/) | Vanilla CSS3, Grid, Flexbox | Typography, Charusat brand identity colors, dark mode styling, and responsive UI components. |
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

## ⚡ Quick Start & Setup Guide

### 📋 Prerequisites
- **Web Server:** XAMPP, WAMP, or LAMP stack (Apache 2.4+).
- **PHP Version:** PHP 8.1+ with extensions: `pdo_mysql`, `mysqli`, `fileinfo`, `json`, `mbstring`.
- **Database:** MySQL / MariaDB 10.4+ (default ports `3306` or `3307`).

---

### 🚀 Step 1: Clone or Place into Local Web Server
Clone this repository into your local web server root directory (e.g., `htdocs` in XAMPP):
```bash
cd C:\xampp\htdocs
git clone https://github.com/DHRUVISENJALIYA1808/WDF.git
```

---

### 🗄️ Step 2: Database Setup & Seeding
The project features an automated, self-healing database seeder:
1. Ensure **Apache** and **MySQL** are running in the XAMPP Control Panel.
2. Open your browser and navigate to the database setup script:
   ```text
   http://localhost/WDF/Practical-15/setup_portal.php
   ```
   *Alternatively, import `Practical-15/portal_schema.sql` directly into phpMyAdmin.*
3. The installer automatically:
   - Detects MySQL running on port **3306** or **3307**.
   - Creates the `studenthub` database if missing.
   - Provisions all necessary tables (`students`, `events`, `registrations`, `auth_tokens`, `audit_logs`).
   - Seeds default test accounts and mock event fixtures.

---

### 🌐 Step 3: Accessing the Portal
You can run the portal either via localhost subfolder or as an Apache Virtual Host:

#### Option A: Localhost Subfolder (Default)
Navigate to:
```text
http://localhost/WDF/
```
The root `index.php` dispatcher will automatically route you to the home page or your role-specific dashboard.

#### Option B: Virtual Host Deployment (Optional)
1. Add to `C:\Windows\System32\drivers\etc\hosts`:
   ```text
   127.0.0.1    studenthub.local
   127.0.0.1    www.studenthub.local
   ```
2. Copy the configuration from `Practical-15/studenthub-vhost.conf` to your Apache `httpd-vhosts.conf` file.
3. Restart Apache and navigate to `http://studenthub.local/`.

---

### 🧪 Step 4: Automated System Diagnostic Suite
To verify navigation, responsiveness, authentication, database operations, security, and AJAX functionality, run:
```text
http://localhost/WDF/Practical-15/verify_portal.php
```

---

## 🔑 Test Credentials for Evaluation & Viva

| Account Role | University Email | Password | Primary Destination |
| :--- | :--- | :--- | :--- |
| **Administrator** | `admin@charusat.edu.in` | `Admin@123` | Admin Dashboard (`Practical-14`) |
| **Student (Demo 1)** | `25dce099@charusat.edu.in` | `Rohan@123` | Student Dashboard & Profile (`Practical-2`) |
| **Student (Demo 2)** | `25dce017@charusat.edu.in` | `Yaksh@123` | Student Dashboard & Profile (`Practical-2`) |

---

## 🛡️ Security Implementation Highlights

- **SQL Injection Prevention:** 100% prepared queries using parameterized statements (`?` or `:placeholder`) across PDO and MySQLi.
- **Cross-Site Scripting (XSS) Defense:** Strict `htmlspecialchars($data, ENT_QUOTES, 'UTF-8')` escaping on all user-supplied output.
- **Role-Based Access Control (RBAC):** Server-side enforcement with `requireAdmin()` gatekeeper returning HTTP `403 Forbidden` for unauthorized routes.
- **Session Security:** Session ID regeneration upon login, 15-minute inactivity timeout, and timing-attack immune remember-me split tokens (`selector` + `validator`).
- **File Upload Protection:** Server-side binary MIME verification via `finfo_file()` and strict $\le 2\text{ MB}$ file size enforcement.

---

## 📊 File & Practical Inventory

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
└── README.md                # Project Documentation & Practical Index
```
**Total Files Transferred & Verified:** 112 files across 12 practical folders.

---

## 📜 License & Acknowledgments

- **Curriculum:** Web Development Framework (WDF) Laboratory, CHARUSAT University.
- **Reference Work:** [StudentHub](https://github.com/hetbhimani5/StudentHub) by Het Bhimani.
- All rights reserved © 2026.
