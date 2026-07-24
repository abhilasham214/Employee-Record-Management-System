# 🏢 Employee Record Management System

A real-time full-stack web application for managing employee records, featuring user authentication, role management, live WebSocket updates, and MongoDB persistence.

---

## 📌 Features

- **🔐 User Authentication**: Secure login and registration with hashed password storage.
- **⚡ Real-Time Synchronization**: Live updates powered by WebSocket (`ws`) so changes reflect immediately across all connected client dashboards.
- **📋 Complete CRUD Operations**: Add, view, update, and delete employee records dynamically.
- **🖥️ Responsive Interface**: Dynamic EJS templates rendered cleanly with styled forms and user dashboards.

---

## 🛠️ Project Structure

```text
Employee-Record-Management-System/
├── app.js                 # Primary Express server setup & WebSocket initialization
├── employeeRoutes.js       # Express routing endpoints for Employee CRUD actions
├── Employee.js            # Mongoose Schema for Employee records
├── User.js                # Mongoose Schema for User authentication
├── hash.js                # Password hashing utility functions
├── login.ejs              # Login page view
├── register.ejs           # User registration view
├── dashboard.ejs          # Main dashboard view displaying employee records
├── employee-form.ejs      # Form view for adding/editing employee records
├── style.html             # UI styling file / template stylesheet
├── package.json           # Node.js project manifest & dependencies
└── README.md              # Project documentation
```

---

## ⚙️ Tech Stack

- **Backend Framework**: Node.js & Express.js
- **Database**: MongoDB & Mongoose ORM
- **Real-Time Communication**: WebSocket (`ws`)
- **Template Engine**: EJS (Embedded JavaScript)
- **Styling**: HTML5, CSS3

---

## 🚀 Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/abhilasham214/Employee-Record-Management-System.git
cd Employee-Record-Management-System
```

### 2. Install dependencies
```bash
npm install
```

### 3. Configure Environment Variables
Create a `.env` file in the root directory:
```env
PORT=3000
MONGODB_URI=mongodb://localhost:27017/employee_db
SESSION_SECRET=your_secret_key
```

### 4. Start the Application
```bash
# Start server
node app.js
```
Open your browser and navigate to `http://localhost:3000`.

---

## 🔌 API & WebSocket Events

- `POST /register`: Registers a new user account.
- `POST /login`: Authenticates user credentials.
- `GET /employees`: Retrieves employee list.
- `POST /employees`: Adds a new employee record and broadcasts a WebSocket update event to all connected clients.
- `DELETE /employees/:id`: Deletes an employee record and triggers live broadcast.

---

## 🛡️ License

This project is licensed under the [MIT License](LICENSE).
