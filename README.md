# HelpDeskHub

A role-based helpdesk ticketing system built with Flask. This project demonstrates authentication, ticket management, workflow control, and a structured support queue.

---

## Overview

HelpDeskHub is a web application that allows users to create and track support tickets while enabling support representatives and administrators to manage, update, and resolve those tickets through a controlled workflow.

---

## Key Features

* User authentication

  * Registration and login
  * Secure password hashing
  * Session management with Flask-Login

* Role-based access control

  * User: create and view own tickets
  * Representative: manage and update tickets
  * Admin: full system access

* Ticket management

  * Create new tickets with title, description, category, and priority
  * View ticket history
  * Assign tickets to support staff

* Ticket workflow system

  * Defined status lifecycle:

    * New
    * Open
    * In Progress
    * Waiting on User
    * Resolved
    * Closed
  * Enforced status transitions to prevent invalid updates

* Comment system

  * Add comments to tickets
  * Track communication between users and staff

* Queue system for staff

  * View unassigned tickets
  * View assigned tickets
  * View all tickets
  * Claim tickets directly

* Dashboard

  * Total ticket count
  * Open and in-progress tickets
  * Closed tickets
  * Breakdown by status
  * Breakdown by priority

---

## Technology Stack

* Backend

  * Flask
  * Flask-SQLAlchemy
  * Flask-Login
  * Flask-WTF / WTForms

* Frontend

  * Bootstrap 5
  * Jinja2 templates

* Database

  * SQLite

---

## Project Structure

```id="9xw2r1"
helpdeskhub/
- app.py
- models.py
- forms.py
- requirements.txt
- README.md
- templates/ (HTML files)
- static/ (CSS)
- instance/ (database)
```

---

## Installation

* Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/helpdeskhub.git
cd helpdeskhub
```

* Create a virtual environment

```bash
python -m venv venv
source venv/bin/activate
# Windows:
venv\Scripts\activate
```

* Install dependencies

```bash
pip install -r requirements.txt
```

* Run the application

```bash
python app.py
```

* Open in browser

```id="h2k8fd"
http://127.0.0.1:5000
```

---

## Database Initialization

* Navigate to:

```id="v8d3lx"
/init-db
```

* This will:

  * Create all database tables
  * Insert a default admin user

* Default admin credentials:

```id="b3f7mz"
Email: admin@example.com
Password: admin123
```

---

## User Roles and Permissions

* User

  * Create tickets
  * View own tickets
  * Comment on own tickets

* Representative

  * View all tickets
  * Claim unassigned tickets
  * Update ticket status
  * Comment on all tickets

* Admin

  * Full access to all features
  * Same capabilities as representative with elevated control

---

## Access Control Rules

* Users cannot access tickets created by others
* Only representatives and admins can:

  * Assign tickets
  * Change ticket status
* Status updates must follow predefined transitions
* Unauthorized access returns HTTP 403

---

## Running the Application

* Start the Flask development server
* Access the application through the browser
* Register a new account or use the default admin
* Create and manage tickets through the UI

---

## Future Improvements

* Email notifications for ticket updates
* File attachment support
* Search and filtering functionality
* Pagination for ticket lists
* REST API for external integrations
* Deployment configuration (Docker or cloud platforms)

---

## Notes

* The database file should not be committed to version control
* Update the secret key before deploying to production
* This project is intended for demonstration and educational use

---

## License

This project is licensed under the MIT License.
