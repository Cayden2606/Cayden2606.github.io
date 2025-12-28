---
title: FlightOps Airport Database CLI Simulator
summary: A terminal-based airport operations database system featuring role-based access control, schema-driven CRUD workflows, and full audit logging for accountability.
date: 2025-08-10

image:
  caption: 'Image credit: **Me**'

authors:
  - admin

tags:
  - Python
  - MySQL
  - Database Design
  - CLI Application
  - Role-Based Access Control
  - Audit Logging
---

{{< toc mobile_only=true is_open=true >}}

<a href="GITHUB_REPO_URL" style="display:flex;align-items:center;gap:10px;" target="_blank" rel="noopener">
  <img src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png" alt="GitHub Logo" style="width:28px;height:28px;" loading="lazy" style="margin: 0 0 0 0 !important">
  GitHub Repository
</a>

---

## **Overview**
**FlightOps Manager** is a **Python + MySQL CLI system** designed to simulate core airport operational workflows in a realistic aviation domain.

Built for **Database Design & Applications (EGE311)**, it demonstrates **3NF relational modelling**, enforced integrity constraints, and a production-inspired operational layer with:

- **Role-based access control** (Front Desk / Admin / Superadmin)  
- **Schema-driven CRUD workflows** across operational tables  
- **Full audit logging** (CREATE / READ / UPDATE / DELETE) for accountability  
- A polished **Rich-powered terminal UI** with guided input + validation guardrails  

---

## **Problem**
Airport operations contain tightly linked data: **flights, aircraft assignment, crew scheduling, passenger identity, bookings, and movement records (arrivals/departures)**.  

Spreadsheet workflows struggle with:
- **Integrity** (invalid references, duplicated IDs, broken relationships)  
- **Security** (everyone can edit everything)  
- **Traceability** (no accountability of who changed what and when)

FlightOps solves this by combining a **normalized MySQL schema**, **referential constraints**, **role separation**, and **audit trails** in a structured CLI workflow.

---

## **Database Design (Normalisation → 3NF)**

### **Before vs After ERD**
The project begins with an unnormalized/early-stage ERD and progresses to a fully normalized 3NF schema.

<div class="flex flex-col gap-6 mt-2 mb-6">
  <div class="flex flex-col items-center">
    <img src="Media/erd_before_normalisation_1nf.png" alt="ERD Before Normalisation (1NF)" class="w-full max-w-xs h-auto rounded-xl shadow-md" loading="lazy" style="margin: 0 0 0 0 !important">
    <div class="text-sm text-gray-600 dark:text-gray-300 mt-1">Figure: ERD before normalisation (1NF stage)</div>
  </div>
  <div class="flex flex-col items-center">
    <img src="Media/erd_after_normalisation_3nf.png" alt="Normalised ERD (3NF)" class="w-full max-w-lg h-auto rounded-xl shadow-md" loading="lazy" style="margin: 0 0 0 0 !important">
    <div class="text-sm text-gray-600 dark:text-gray-300 mt-1">Figure: Normalised ERD (3NF)</div>
  </div>
</div>

### **Core Entities & Relationships (Logical Schema)**
**Tables (11 total):**  
`Airports, Planes, Flights, Arrivals, Departures, Employees, Passengers, Bookings, FlightCrew, AdminUsers, AuditLog`

**Key relationships implemented via FK constraints (from `database.sql`):**
- **Airports (1) → Planes (M)** via `Planes.BaseAirportCode → Airports.AirportCode`
- **Planes (1) → Flights (M)** via `Flights.AircraftID → Planes.AircraftID`
- **Flights (1) → Arrivals / Departures (M)** via `Arrivals.FlightID`, `Departures.FlightID`
- **Flights (M) ↔ Employees (M)** via junction table **FlightCrew**
  - **Composite PK:** (`FlightID`, `EmployeeID`)
- **Passengers (1) → Bookings (M)** via `Bookings.PassengerID → Passengers.PassengerID`
- **AuditLog** references users with `ON DELETE SET NULL` to preserve logs even after user removal.

---

## **Key Features (with Screenshots)**

### **1) Role-Based Access Control (RBAC)**
- **Front Desk:** view-only access to limited operational tables  
- **Admin:** CRUD on operational tables  
- **Superadmin:** full control, including **AdminUsers** and **AuditLog**

<div class="grid grid-cols-1 sm:grid-cols-2 gap-6 mt-2 mb-6">
  <div class="flex flex-col items-center">
    <img src="Media/cli_role_selection.png" alt="Role selection screen" class="w-full max-w-lg h-auto rounded-xl shadow-md" loading="lazy" style="margin: 0 0 0 0 !important">
    <div class="text-sm text-gray-600 dark:text-gray-300 mt-1">Role selection + system entry</div>
  </div>
  <div class="flex flex-col items-center">
    <img src="Media/cli_frontdesk_dashboard.png" alt="Front Desk dashboard" class="w-full max-w-lg h-auto rounded-xl shadow-md" loading="lazy" style="margin: 0 0 0 0 !important">
    <div class="text-sm text-gray-600 dark:text-gray-300 mt-1">Front Desk menu (view-only)</div>
  </div>
</div>

<div class="grid grid-cols-1 sm:grid-cols-2 gap-6 mt-2 mb-6">
  <div class="flex flex-col items-center">
    <img src="Media/cli_admin_dashboard.png" alt="Admin dashboard" class="w-full max-w-lg h-auto rounded-xl shadow-md" loading="lazy" style="margin: 0 0 0 0 !important">
    <div class="text-sm text-gray-600 dark:text-gray-300 mt-1">Admin dashboard (CRUD access)</div>
  </div>
  <div class="flex flex-col items-center">
    <img src="Media/cli_superadmin_dashboard.png" alt="Superadmin dashboard" class="w-full max-w-lg h-auto rounded-xl shadow-md" loading="lazy" style="margin: 0 0 0 0 !important">
    <div class="text-sm text-gray-600 dark:text-gray-300 mt-1">Superadmin dashboard (AdminUsers + AuditLog)</div>
  </div>
</div>

---

### **2) Schema-Driven CRUD (Dynamic Prompts + Validation)**
The CLI introspects table structure at runtime using:
- `DESCRIBE <table>` for columns + PK detection  
- `information_schema.KEY_COLUMN_USAGE` for FK references  
This enables generic CRUD workflows across many entities without hardcoding forms.

<div class="flex flex-col gap-8 mt-2 mb-6">

  <!-- CRUD Menu -->
  <div>
    <h3 class="text-lg font-semibold text-gray-800 dark:text-gray-100 mb-3">CRUD Menu</h3>
    <div class="flex flex-col items-center">
      <img src="Media/cli_manage_airports_menu.png" alt="Manage table menu" class="w-full max-w-xs h-auto rounded-xl shadow-md" loading="lazy" style="margin: 0 0 0 0 !important">
      <div class="text-sm text-gray-600 dark:text-gray-300 mt-1">CRUD menu for an entity (e.g., Airports)</div>
    </div>
  </div>

  <!-- ADD (Create) -->
  <div>
    <h3 class="text-lg font-semibold text-gray-800 dark:text-gray-100 mb-3">ADD (Create)</h3>
    <div class="flex flex-col items-center">
      <img src="Media/cli_dynamic_prompts_add_airports.png" alt="Dynamic prompts for adding a record" class="w-full max-w-lg h-auto rounded-xl shadow-md" loading="lazy" style="margin: 0 0 0 0 !important">
      <div class="text-sm text-gray-600 dark:text-gray-300 mt-1">Schema-driven prompts with datatype constraints</div>
    </div>
  </div>
  <div class="flex flex-col items-center">
    <img src="Media/cli_insert_confirmation.png" alt="Insert confirmation table" class="w-full max-w-lg h-auto rounded-xl shadow-md" loading="lazy" style="margin: 0 0 0 0 !important">
    <div class="text-sm text-gray-600 dark:text-gray-300 mt-1">ADD: Preview + confirmation before commit</div>
  </div>

  <!-- VIEW (Read) -->
  <div>
    <h3 class="text-lg font-semibold text-gray-800 dark:text-gray-100 mb-3">VIEW (Read)</h3>
    <div class="flex flex-col items-center">
      <img src="Media/cli_view_table_legend.png" alt="View records output with legend" class="w-full max-w-lg h-auto rounded-xl shadow-md" loading="lazy" style="margin: 0 0 0 0 !important">
      <div class="text-sm text-gray-600 dark:text-gray-300 mt-1">Rich table output with PK/FK visual legend</div>
    </div>
  </div>

  <!-- UPDATE -->
  <div>
    <h3 class="text-lg font-semibold text-gray-800 dark:text-gray-100 mb-3">UPDATE</h3>
    <div class="flex flex-col items-center">
      <img src="Media/cli_update_prompts.png" alt="Update prompts table" class="w-full max-w-lg h-auto rounded-xl shadow-md" loading="lazy" style="margin: 0 0 0 0 !important">
      <div class="text-sm text-gray-600 dark:text-gray-300 mt-1">Schema-driven prompts with datatype constraints</div>
    </div>
  </div>
  <div class="flex flex-col items-center">
    <img src="Media/cli_update_confirmation.png" alt="Update confirmation table" class="w-full max-w-lg h-auto rounded-xl shadow-md" loading="lazy" style="margin: 0 0 0 0 !important">
    <div class="text-sm text-gray-600 dark:text-gray-300 mt-1">UPDATE: Preview + confirmation before commit</div>
  </div>

  <!-- DELETE -->
  <div>
    <h3 class="text-lg font-semibold text-gray-800 dark:text-gray-100 mb-3">DELETE</h3>
    <div class="flex flex-col items-center">
      <img src="Media/cli_delete_prompts.png" alt="Delete prompts table" class="w-full max-w-lg h-auto rounded-xl shadow-md" loading="lazy" style="margin: 0 0 0 0 !important">
      <div class="text-sm text-gray-600 dark:text-gray-300 mt-1">Schema-driven prompts with datatype constraints</div>
    </div>
  </div>
  <div class="flex flex-col items-center">
    <img src="Media/cli_delete_confirmation.png" alt="Delete confirmation table" class="w-full max-w-lg h-auto rounded-xl shadow-md" loading="lazy" style="margin: 0 0 0 0 !important">
    <div class="text-sm text-gray-600 dark:text-gray-300 mt-1">DELETE: Preview + confirmation before commit</div>
  </div>
</div>

---

### **3) Composite Primary Key Handling (FlightCrew)**
For junction tables like **FlightCrew**, the system:
- detects composite PK columns  
- forces user to input the full PK combination  
- validates uniqueness before insert/update

*(Composite PK support is explicitly noted in project specs and implemented in code via PK column detection + uniqueness checks.)*

---

### **4) Sorting / Record Viewing Controls**
Records can be displayed as:
- all rows  
- top 10  
- custom N  
and optionally sorted by the appropriate timestamp column:
- `CreatedAt` for most operational tables  
- `AdminCreatedAt` for AdminUsers  
- `Timestamp` for AuditLog  

<div class="grid grid-cols-1 sm:grid-cols-2 gap-6 mt-2 mb-6">
  <div class="flex flex-col items-center">
    <img src="Media/cli_view_options.png" alt="View options menu" class="w-full max-w-lg h-auto rounded-xl shadow-md" loading="lazy" style="margin: 0 0 0 0 !important">
    <div class="text-sm text-gray-600 dark:text-gray-300 mt-1">View mode selection (All / Top 10 / Custom)</div>
  </div>
  <div class="flex flex-col items-center">
    <img src="Media/cli_sort_menu.png" alt="Sort options menu" class="w-full max-w-lg h-auto rounded-xl shadow-md" loading="lazy" style="margin: 0 0 0 0 !important">
    <div class="text-sm text-gray-600 dark:text-gray-300 mt-1">Sorting options (default / ASC / DESC by timestamp)</div>
  </div>
</div>

---

### **5) Audit Logging (Accountability by Design)**
Every action generates an audit record containing:
- `Username`, `TableName`, `ActionType`, `Details`, `Timestamp`  
AuditLog is viewable only by Superadmin and cannot be modified through normal workflows.

<div class="grid grid-cols-1 sm:grid-cols-2 gap-6 mt-2 mb-6">
  <div class="flex flex-col items-center">
    <img src="Media/cli_audit_log_rich.png" alt="Audit log table (Rich output)" class="w-full max-w-lg h-auto rounded-xl shadow-md" loading="lazy" style="margin: 0 0 0 0 !important">
    <div class="text-sm text-gray-600 dark:text-gray-300 mt-1">AuditLog output showing CRUD actions with timestamps</div>
  </div>
  <div class="flex flex-col items-center">
    <img src="Media/cli_adminusers_table.png" alt="AdminUsers table view" class="w-full max-w-lg h-auto rounded-xl shadow-md" loading="lazy" style="margin: 0 0 0 0 !important">
    <div class="text-sm text-gray-600 dark:text-gray-300 mt-1">AdminUsers table (hashed passwords + role column)</div>
  </div>
</div>

---

### **6) ASCII Animation Splash Screen (Intro Sequence)**
To enhance UX, the program plays an **animated ASCII splash** at startup (purely cosmetic).  
The CLI loads pre-generated ASCII frames from a text file (e.g., `frames.txt`) and renders them in sequence in the terminal.

- The animation **does not affect** database functionality or CRUD logic  
- Frames are stored as **newline-separated blocks**, making them easy to parse and play  
- Frames were generated using a separate utility tool (see Appendix A)

---

## **Security & Access Control**
- Admin authentication uses **SHA-256 hashing** (`hashlib.sha256`)  
- **LastLogin timestamp** is updated on successful login  
- Front Desk mode is accessible as a **restricted view-only role**  
- SQL injection is avoided via parameterized queries (`Cursor.execute(SQL, params)`)

---

## **Tech Stack**
- **Language:** Python 3  
- **Database:** MySQL 8.0 (`sg_airport_database`)  
- **Connector:** `mysql-connector-python`  
- **Terminal UI:** `rich` (tables, panels, prompts, styling)  
- **Schema Modelling:** MySQL Workbench (`database.mwb`)  

---

## **My Role**
I designed and implemented the project end-to-end:
- ER modelling and normalization to **3NF**
- Building the MySQL schema with FK constraints and timestamp columns
- Implementing a generic CLI CRUD engine driven by schema introspection
- Implementing composite PK workflows (FlightCrew)
- Audit log architecture + enforcement of privileged access
- UI/UX polish with Rich

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
4. **Configure Connection:** edit credentials in `startup()` inside `database_cli.py`
5. **Run:**

   ```bash
   python database_cli.py
   ```

---

## **Project Structure**

```text
├── database_cli.py                       # Main CLI application
├── database.sql                          # Schema + sample data
├── database.mwb                          # MySQL Workbench model
└── frames.txt  # ASCII intro frames file (used by intro_sequence())
```

---

## **Outcome**

This project demonstrates strong competency in:

* **Relational DB design:** normalization, referential integrity, junction tables, composite keys
* **Software engineering:** modular CLI design, reusable CRUD engine via schema introspection
* **Security:** hashed credentials + role separation + last login tracking
* **Auditability:** structured logging of operational changes with timestamps + attribution
* **UX polish:** a readable, guided terminal workflow built with Rich

---

## **Appendix A — ASCII Animation Splash Screen**

To enhance user experience, an ASCII animation is played at the start of the program (referenced under **Special Features → Intro Sequence** in the report).
This animation was generated using a separate Python utility hosted here:

<a href="https://github.com/Cayden2606/gif-2-ascii" target="_blank" rel="noopener">
  https://github.com/Cayden2606/gif-2-ascii
</a>

The tool converts a `.gif` into ASCII frames stored in a `frames.txt` file (or equivalent frames file).
The animation is **purely cosmetic** and does not affect the functionality of the database application.

<details>
  <summary><b>Supporting Tool: GIF → ASCII Animation Converter (Overview)</b></summary>

  <br>

  <div class="text-sm text-gray-700 dark:text-gray-300">
    A lightweight Python utility that converts animated <code>.gif</code> files into animated ASCII art for terminal display.
    It can output frames to <code>frames.txt</code> and includes a simple terminal player.
  </div>

  <br>

<b>Key capabilities</b>

  <ul>
    <li>Converts GIFs to ASCII while preserving aspect ratio</li>
    <li>Supports standard and multithreaded conversion modes</li>
    <li>Outputs to <code>frames.txt</code> and optionally copies to clipboard</li>
    <li>Includes a terminal animation player (<code>ascii_player.py</code>)</li>
  </ul>

<b>How frames are stored</b>

  <ul>
    <li>Each ASCII frame is separated by <b>two newlines</b> (<code>\n\n</code>)</li>
    <li>This makes parsing trivial: split by double-newline and render sequentially</li>
  </ul>

<b>Quickstart (tool repo)</b>

  <pre><code class="language-bash">pip install pillow pyperclip
python3 converter.py
python3 ascii_player.py</code></pre>

</details>
