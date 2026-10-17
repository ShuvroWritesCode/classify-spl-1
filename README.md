# Classify — All-in-One Class Management Platform

![PHP](https://img.shields.io/badge/PHP-777BB4?style=flat&logo=php&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat&logo=mysql&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS3/SCSS](https://img.shields.io/badge/CSS3%2FSCSS-1572B6?style=flat&logo=css3&logoColor=white)
![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)

**Classify** is a web-based class management system that brings a university class's day-to-day essentials — routines, class work, announcements, academic resources, and room availability — into one place. It was built for students of the CSE department at the Islamic University of Technology (IUT), who otherwise had to track this information across scattered chats, drives, and notice boards.

---

## Overview

Students juggle many disconnected sources: Google Classroom for assignments, messenger groups for Class Representative (CR) notices, shared drives for notes, and printed routines for schedules. Finding a free classroom for a group study session usually means walking the halls.

Classify gives each student a single authenticated dashboard that pulls these together and adds a database-backed **Vacant Room Finder** that answers "which classroom is free right now?" in one query.

## Key Features

- **Secure user accounts** — Sign-up and login with session-based authentication. Passwords are hashed with PHP's `password_hash()` / `password_verify()`, and registration validates email format, username uniqueness, and password strength (minimum 8 characters with uppercase, lowercase, digit, and special character).
- **Vacant Room Finder** — Students select a day and class period; the app queries the routine database and returns every classroom that is free in that slot.
- **Section-wise class routines** — Quick access to Section A and Section B schedules.
- **CR Announcements feed** — A live announcement board (powered by a Google Apps Script web app) where Class Representatives post updates for the whole class.
- **Class Work hub** — Central links to Google Classroom and other course platforms.
- **Essentials & Resources** — Curated administrative links, academic resources, a seniors' shared drive, the class's own drive, and recommended learning material.
- **Profile management & contact page** — Update profile details, end the session safely, send a message to the team, and browse an FAQ section.
- **Responsive UI** — Mobile-friendly layout with a collapsible navigation bar, Swiper.js hero slider, and searchable dropdowns (Chosen.js).

## Tech Stack

| Layer      | Technologies                                               |
| ---------- | ---------------------------------------------------------- |
| Frontend   | HTML5, CSS3, SCSS, JavaScript, jQuery, Swiper.js, Chosen.js, Font Awesome |
| Backend    | PHP (procedural, session-based auth)                       |
| Database   | MySQL (via `mysqli`)                                       |
| Integrations | Google Apps Script (announcements), Google Classroom, Google Drive |

## Project Structure

```
├── login.php        # Login page and authentication
├── Register.php     # Account registration with input validation
├── home.php         # Dashboard: routines, class work, CR announcements
├── course.php       # Essentials, resources, and Vacant Room Finder
├── contact.php      # Contact form and FAQ
├── connection.php   # MySQL connection configuration
├── functions.php    # Session/login helper (check_login)
├── css/             # Stylesheets (SCSS source + compiled CSS)
├── js/script.js     # Navbar, forms, and slider interactions
└── images/          # Static assets
```

## Getting Started

### Prerequisites

- PHP 7.4+
- MySQL / MariaDB
- A local server stack such as [XAMPP](https://www.apachefriends.org/), MAMP, or WAMP

### Installation

1. Clone the repository into your web server's document root (e.g. `htdocs/`):
   ```bash
   git clone https://github.com/ShuvroWritesCode/Software-Project-Lab-01.git
   ```
2. Create a MySQL database named `login_sample_db` with two tables:
   - `student` — `id`, `e_mail`, `username`, `password`
   - `routine` — `room_no`, `day`, `time`, `vacant`
3. Update the credentials in `connection.php` if they differ from the defaults (`root` with no password on `localhost`).
4. Start Apache and MySQL, then open `http://localhost/Software-Project-Lab-01/login.php`.

## About the Course

Classify was developed for **Software Project Lab-01**, a 1.5-credit project course at IUT. Teams of up to three students design and deliver a complete web or app project over one semester under a faculty supervisor. A faculty committee then evaluates the final product, and each member is assessed on their individual contribution.

## Team

| Member                     |
| -------------------------- |
| Iftekharul Haque Shuvro    |
| Chowdhury Ashfaq           |
| Tasrefee Mahmud Ridun      |

## License

This project is licensed under the [MIT License](LICENSE).
