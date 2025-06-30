# grocery-web-app
📦 Grocery App Website
A full-stack web application for browsing and managing grocery items. Built with React.js, Node.js, Express, MongoDB, and SQL. Supports product browsing, user authentication, and shopping cart features.

✨ Features
🛒 Browse groceries by category

🔍 Search and filter items

🧾 Shopping cart system

🧑 User authentication (login/signup)

📊 Admin panel for managing inventory (MongoDB + SQL)

📱 Responsive UI with HTML/CSS

🛠️ Tech Stack
Frontend:

React.js

HTML5

CSS3

JavaScript

Backend:

Node.js

Express.js

Databases:

MongoDB (for products, categories)

SQL (PostgreSQL/MySQL) for user authentication and orders

📁 Project Structure
pgsql
Copy
Edit
grocery-app/
├── client/                 # React frontend
│   ├── public/
│   └── src/
│       ├── components/
│       ├── pages/
│       ├── App.js
│       └── index.js
├── server/                 # Node.js backend
│   ├── controllers/
│   ├── models/
│   ├── routes/
│   ├── sql/               # SQL scripts or integration
│   ├── mongodb/           # MongoDB models/schemas
│   └── server.js
├── .env
├── package.json
└── README.md
🚀 Getting Started
1. Clone the repo
bash
Copy
Edit
git clone https://github.com/yourusername/grocery-app.git
cd grocery-app
2. Setup Environment Variables
Create a .env file in the root and add:

env
Copy
Edit
PORT=5000
MONGO_URI=mongodb://localhost:27017/groceryDB
SQL_HOST=localhost
SQL_USER=your_user
SQL_PASSWORD=your_password
SQL_DATABASE=grocery_sql
JWT_SECRET=your_jwt_secret
3. Install Dependencies
Frontend:

bash
Copy
Edit
cd client
npm install
Backend:

bash
Copy
Edit
cd ../server
npm install
4. Run the App
Start Backend:

bash
Copy
Edit
cd server
npm run dev
Start Frontend:

bash
Copy
Edit
cd ../client
npm start
🧪 Sample SQL Schema
sql
Copy
Edit
CREATE TABLE users (
  id SERIAL PRIMARY KEY,
  username VARCHAR(50) NOT NULL UNIQUE,
  email VARCHAR(100) NOT NULL UNIQUE,
  password TEXT NOT NULL
);

CREATE TABLE orders (
  id SERIAL PRIMARY KEY,
  user_id INTEGER REFERENCES users(id),
  total NUMERIC,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
🧾 MongoDB Collections
json
Copy
Edit
{
  "products": [
    {
      "name": "Apples",
      "price": 2.99,
      "category": "Fruits",
      "inStock": true
    }
  ],
  "categories": [
    { "name": "Vegetables" },
    { "name": "Beverages" }
  ]
}
🔐 Auth Routes (JWT)
POST /api/auth/register

POST /api/auth/login

🧺 Grocery API Routes
GET /api/products

GET /api/products/:id

POST /api/cart

GET /api/cart

DELETE /api/cart/:id

✅ To-Do
 Stripe/PayPal integration

 Admin inventory dashboard

 Order history and receipts

 Image uploads for products
