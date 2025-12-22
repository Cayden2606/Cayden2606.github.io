---
title: Singapore Airport Database CLI
summary: A terminal-based airport operations database system featuring role-based access control, CRUD workflows, and audit logging.
date: 2025-07-04

image:
  caption: 'Image credit: **Cayden Miguel Theseira**'

authors:
  - admin

tags:
  - Python
  - MySQL
  - Database Design
  - CLI Application
  - Role-Based Access Control
---

{{< toc mobile_only=true is_open=true >}}

<a href="GITHUB_REPO_URL" style="display:flex;align-items:center;gap:10px;" target="_blank" rel="noopener">
  <img src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png" alt="GitHub Logo" style="width:28px;height:28px;">
  GitHub Repository
</a>

---

## **Overview**
**FlightOps Manager** is a command-line interface (CLI) application for managing airport operations data. Built as a database design project, it applies relational modelling and real-world aviation workflows to manage **airports, aircraft, flights, arrivals/departures, employees, passengers, bookings, and crew assignments**, with **role-based access** and **audit logging** for accountability.

---

## **Problem**
Airport operations involve complex relationships across flights, passengers, aircraft, and staffing. Spreadsheet-based tracking struggles with **data integrity**, **access control**, and **traceability** of changes. This project addresses these issues with a normalized MySQL schema, enforced referential constraints, role-based permissions, and a structured audit trail of user actions.

---

## **Key Features**

### **Role-Based Access Control**
- Three roles: **Superadmin**, **Admin**, **Front Desk (view-only)**
- Secure authentication for admin accounts using **SHA-256 password hashing**
- **Last login** tracking for admin accounts

### **CRUD Workflows Across Core Tables**
- Create, Read, Update, Delete operations for operational entities (e.g., Airports, Planes, Flights, Arrivals, Departures, Employees, Passengers, Bookings, FlightCrew)
- **AdminUsers management** available to Superadmin
- **AuditLog view** available to Superadmin (read-only)

### **Dynamic Schema-Driven Forms**
- Runtime schema introspection using `DESCRIBE` to generate prompts dynamically
- Validates common MySQL types (e.g., `CHAR`, `VARCHAR`, `INT`, `DATE`, `DATETIME`, `ENUM`)
- Enforces **primary key uniqueness** at input time (including **composite keys** for junction tables)

### **Foreign Key Validation with Suggestions**
- Detects foreign key constraints via MySQL metadata
- Displays **allowed referenced values** to guide correct input and prevent referential integrity errors

### **Audit Logging**
- Logs CREATE / READ / UPDATE / DELETE actions for operational tables
- Records **username**, **table**, **action type**, **details**, and **timestamp** for traceability
- Audit logging is restricted from being modified directly (view-only access via Superadmin)

### **Polished Terminal UI**
- Built with **Rich** for styled panels, prompts, and formatted tables
- Visual distinction for **primary keys**, **foreign keys**, and regular columns
- Optional intro experience using ASCII frame animation

---

## **Tech Stack**
- **Language:** Python 3
- **Database:** MySQL 8.0 (schema: `sg_airport_database`)
- **Connector:** `mysql-connector-python`
- **Terminal UI:** `rich`
- **Security:** SHA-256 hashing via `hashlib`
- **Schema Modelling:** MySQL Workbench (`database.mwb`)

---

## **My Role**
I designed and implemented the project end-to-end, including:
- Database modelling and schema design (11 tables, including AdminUsers + AuditLog)
- CLI architecture and role-based access flows
- Schema-driven CRUD form generation and validation logic
- Audit logging design and implementation
- UI/UX polish using Rich tables and panels

---

## **Getting Started**
1. **Prerequisites:** Python 3.8+, MySQL 8.0  
2. **Database Setup:**
   ```bash
   mysql -u root -p < database.sql
   ```

3. **Install Dependencies:**

   ```bash
   pip install mysql-connector-python rich
   ```
4. **Configure Connection:** Update MySQL credentials in `database_cli.py` (inside `startup()`)
5. **Run Application:**

   ```bash
   python database_cli.py
   ```

---

## **Project Structure**

```text
├── database_cli.py    # Main CLI application (1369 lines)
├── database.sql       # Full MySQL schema + sample data
├── database.mwb       # MySQL Workbench model file
└── frames.txt         # ASCII animation frames (intro)
```

---

## **Outcome**

This project demonstrates proficiency in:

* **Relational Database Design:** normalization, referential integrity, composite keys, and junction tables
* **Backend Development:** Python CLI architecture, validation, and modular CRUD workflows
* **Security & Access Control:** hashed credentials, role-based permissions, and restricted admin/audit access
* **Auditability:** structured logging for operational table actions with user attribution and timestamps
* **User Experience:** readable terminal UI with strong feedback, guardrails, and guided input

