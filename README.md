# Employee Record Management System

A full-stack web application for real-time employee record administration. Built on Node.js, Express, MongoDB, and WebSockets, the system delivers real-time multi-client synchronization for CRUD operations and authenticated user management.

## Architecture and Data Flow

`	ext
+----------------+      HTTP / WebSocket       +---------------------+
|                | <-------------------------> |                     |
|  Browser View  |                             |  Express.js Server  |
|  (EJS Views)   | --- WebSocket Broadcast --> |     (app.js)        |
|                |                             |                     |
+----------------+                             +---------------------+
                                                          |
                                           +--------------+--------------+
                                           |                             |
                                           v                             v
                                 +------------------+          +-------------------+
                                 |  Authentication  |          |  MongoDB Storage  |
                                 |   & Hash Logic   |          | (Employee & User) |
                                 +------------------+          +-------------------+
`

## Key Features

- User Authentication: Secure user registration and login endpoints utilizing cryptographic hashing.
- Real-Time WebSocket Synchronization: Instant multi-client updates broadcasting CRUD changes without manual page refreshes.
- Employee CRUD Pipeline: Endpoints to create, read, update, and delete employee records.
- Server-Side Templating: Dynamic EJS views rendered for authentication, dashboards, and employee management forms.
- Data Persistence: MongoDB connection via Mongoose models for structured schema validation.

## Repository Structure

`	ext
Employee-Record-Management-System/
├── app.js                 # Server entry point & WebSocket initialization
├── employeeRoutes.js       # Express router for employee endpoints
├── Employee.js            # Mongoose Schema for Employee entities
├── User.js                # Mongoose Schema for User entities
├── hash.js                # Cryptographic hashing module
├── login.ejs              # Authentication login template
├── register.ejs           # User registration template
├── dashboard.ejs          # Dashboard template displaying records
├── employee-form.ejs      # Form template for record management
├── style.html             # Interface styling definitions
├── package.json           # Application dependencies and scripts
└── README.md              # Project documentation
`

## Tech Stack

- Backend: Node.js, Express.js
- Database: MongoDB, Mongoose ORM
- Real-Time Communication: WebSocket (ws)
- Templating Engine: EJS
- Client Layer: HTML5, CSS3, JavaScript

## Local Setup and Installation

### Prerequisites

- Node.js (v14.0.0 or higher)
- npm (v6.0.0 or higher)
- MongoDB instance running locally on port 27017 or via a remote connection string.

### Setup Instructions

1. Clone the repository:
   `ash
   git clone https://github.com/abhilasham214/Employee-Record-Management-System.git
   cd Employee-Record-Management-System
   `

2. Install Node.js dependencies:
   `ash
   npm install
   `

3. Create a .env configuration file in the project root:
   `nv
   PORT=3000
   MONGODB_URI=mongodb://localhost:27017/employee_management
   SESSION_SECRET=your_production_secret_key
   `

4. Start the application server:
   `ash
   node app.js
   `

5. Access the application in your browser at http://localhost:3000.

## API Endpoints

- POST /register: Registers a new administrative user.
- POST /login: Authenticates credentials and opens a session.
- GET /employees: Fetches all employee records.
- POST /employees: Creates an employee record and triggers a WebSocket broadcast.
- DELETE /employees/:id: Removes an employee record and updates active clients.

## License

This software is licensed under standard open-source terms.
