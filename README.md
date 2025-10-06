# ⚙️ MERN + MySQL CRUD Application

A full-stack **MERN** (MongoDB, Express, React, Node.js) style CRUD app, but using **MySQL** as the database.  
This app allows users to **Create, Read, Update, and Delete** records stored in a MySQL table, with a **unique email constraint** and **CORS-enabled** backend API.

---

## 🚀 Features

- ✅ Add, Edit, Delete users  
- 📋 Display data in a **table format**
- 🧠 Email field is **unique** (no duplicate emails)
- 🔒 Handles duplicate email errors gracefully
- 🔄 Auto-refresh after each operation
- 🌐 CORS enabled for secure frontend-backend communication

---

## 🧩 Tech Stack

| Layer | Technology |
|--------|-------------|
| **Frontend** | React (Create React App), Axios |
| **Backend** | Node.js, Express.js |
| **Database** | MySQL with mysql2 driver |
| **Environment** | dotenv |
| **Security** | CORS middleware |

---

## 📁 Folder Structure

mern-mysql-crud/
│
├── backend/
│ ├── server.js
│ ├── .env
│ ├── package.json
│
└── frontend/
├── src/
│ ├── App.js
│ └── index.js
├── public/
├── package.json
│
└── README.md

yaml
Copy code

---

## ⚙️ Setup Instructions

### 1️⃣ Clone the Project
```bash
git clone https://github.com/yourusername/mern-mysql-crud.git
cd mern-mysql-crud
2️⃣ Setup MySQL Database
Make sure MySQL server is running.
Then, create the database manually:

sql
Copy code
CREATE DATABASE mern_crud;
USE mern_crud;
You don’t need to manually create the table — it’s auto-created by the backend:

sql
Copy code
CREATE TABLE IF NOT EXISTS users (
  id INT AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(100) NOT NULL,
  email VARCHAR(191) UNIQUE NOT NULL
);
3️⃣ Setup Backend
bash
Copy code
cd backend
npm install
Create a .env file inside backend/:

ini
Copy code
DB_HOST=localhost
DB_USER=root
DB_PASS=
DB_NAME=mern_crud
PORT=5000
Then run the server:

bash
Copy code
node server.js
If successful:

arduino
Copy code
✅ MySQL Connected
🚀 Server running on port 5000
4️⃣ Setup Frontend
bash
Copy code
cd ../frontend
npm install
npm start
The frontend will start on:
👉 http://localhost:3000

🔗 API Routes
Method	Endpoint	Description
GET	/items	Get all users
POST	/items	Add a new user
PUT	/items/:id	Update user by ID
DELETE	/items/:id	Delete user by ID

🌐 About CORS
CORS (Cross-Origin Resource Sharing) is used to allow your React frontend (port 3000) to call your Express backend (port 5000).

Enabled via:

javascript
Copy code
const cors = require("cors");
app.use(cors());
For production, you can restrict origins:

javascript
Copy code
app.use(cors({ origin: "https://your-frontend-domain.com" }));
🧠 How It Works
Frontend (React) sends REST API requests via Axios

Backend (Express) receives them and performs SQL queries using mysql2

Database (MySQL) stores user records with a unique email constraint

Responses are sent back and displayed dynamically in a React table

📸 Sample Output
sql
Copy code
| No | Name        | Email               | Actions         |
|----|--------------|---------------------|-----------------|
| 1  | John Doe     | john@example.com    | [Edit] [Delete] |
| 2  | Jane Smith   | jane@example.com    | [Edit] [Delete] |
⚠️ Common Errors
Error	Fix
Specified key was too long; max key length is 1000 bytes	Use VARCHAR(191) for unique email field
Access-Control-Allow-Origin	Make sure cors is used in backend
ECONNREFUSED	Check if MySQL service is running and credentials are correct
Email already exists!	Email must be unique in database

🧱 Future Improvements
✅ Add form validation and success notifications

✅ Use Sequelize ORM for advanced MySQL handling

✅ Add search & pagination

✅ Deploy backend to Render/Heroku and frontend to Netlify/Vercel

👨‍💻 Author
Your Name
📧 satyasrinath6@gmail.com
🌐 GitHub: yourusername

🪪 License
This project is licensed under the MIT License — free to use, modify, and distribute.









10000 chars



