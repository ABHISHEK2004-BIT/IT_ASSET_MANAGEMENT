# NTPC IT Asset Management System

A web-based asset management application for tracking IT assets, employees, maintenance records, disposal logs, and pending recovery actions for an organization. This project combines a static front-end interface with an Express.js backend and Microsoft SQL Server database.

## Overview

This system is designed to manage the lifecycle of IT assets used by an organization such as NTPC. It includes:

- Asset registration and inventory tracking
- Employee and department master data
- Maintenance and repair records
- Disposal / scrap logging
- Dues and pending recovery tracking
- Reporting pages for operational visibility
- Secure login entry point for the application

## Tech Stack

- Frontend: HTML, CSS, JavaScript
- Backend: Node.js + Express.js
- Database: Microsoft SQL Server (local SQL Express instance)
- Database driver: `mssql`

## Project Structure

```text
.
├── server.js                  # Express server and API routes
├── package.json              # Node dependencies and scripts
├── database_backup.sql       # SQL Server backup for the application database
├── login.html                # Login page
├── home.html                 # Main dashboard
├── master*.html              # Asset/employee master forms and pages
├── transaction*.html          # Asset transactions and logs
├── report*.html              # Reports and dashboard pages
├── *.css                     # Styling files
├── *.js                      # Client-side JavaScript
├── *.pdf, *.jpg, *.png, *.avif, *.webp
└── ...
```

## Features

### Asset Management
- Register and track assets in the master ledger
- Maintain asset type, status, and created record information
- Update and review asset lifecycle status

### Employee/Department Management
- Register employee records and master details
- Link employees to departments and asset responsibilities

### Maintenance Tracking
- Record hardware issues and repair details
- Track service vendors, repair cost, and expected return date

### Disposal / Scrap Workflow
- Log disposed or obsolete assets
- Record reasons and recovery values
- Review disposal history from the reports module

### Reports and Recovery Monitoring
- Display active pending dues and asset recovery tasks
- Show maintenance and disposal summaries in report pages
- Provide a working dashboard for operational follow-up

## Prerequisites

Before running this project, make sure you have:

- Node.js installed
- npm installed
- Microsoft SQL Server Express (or another local SQL Server instance)
- SQL Server Management Studio or SQL command tools to restore/import the database backup

## Database Setup

This application expects a database named `IT_Asset_Management` and points to a local SQL Server instance using the configuration in `server.js`.

Current configuration in the project:

- Server: `localhost`
- Instance: `SQLEXPRESS`
- Database: `IT_Asset_Management`
- User: `saa`
- Password: `Shikha@08`

Use the provided `database_backup.sql` file to restore or recreate the database.

Important:
- If your local SQL Server setup is different, update the `dbConfig` section in `server.js`.
- For production use, avoid hardcoding database credentials directly in source files.

## Installation

1. Open a terminal in the project root.
2. Install dependencies:

```bash
npm install
```

3. Restore the database from `database_backup.sql` in SQL Server.
4. Update the database connection settings in `server.js` if needed.

## Run the Application

Start the server:

```bash
node server.js
```

Then open the application in a browser:

```text
http://localhost:5000
```

The root route redirects to the login page.

## Default Application Behavior

- The app serves static HTML pages from the project directory.
- The backend exposes REST APIs under routes such as `/api/...`.
- The server listens on port `5000`.

## Notes

- The project is a local/in-house asset management system and is not a full production-ready SaaS application.
- The front end is mostly HTML/CSS/JS and the APIs are server-driven using SQL queries.
- Some pages and API routes appear to have been built for specific operational workflows rather than a generalized framework.

## License

This project is currently licensed under the ISC license as defined in `package.json`.

## Suggested Improvements

For future enhancement, consider:

- Replacing hardcoded database credentials with environment variables
- Adding authentication and authorization for users and roles
- Improving validation and input sanitization
- Migrating to a modular backend structure
- Adding automated tests and deployment scripts
