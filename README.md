# used-products-ecommerce-
E-commerce marketplace for used products in Cameroon
A MERN-stack web app for buying and selling second-hand products within Cameroon.
#FRONT-END STACK

React JS (Vite)

Tailwind CSS

React Router

Axios

Context API / Zustand (for auth state)
#BACK-END STACK
Node.js

Express.js

MongoDB + Mongoose

JWT Authentication
#Project architecture
Frontend (React + Vite + Tailwind)
        ↓
REST API (Express.js)
        ↓
MongoDB (Mongoose ODM)

#PROJECT FOLDER STRUCTURE

cameroon-used-products-ecommerce/
│
├── README.md
├── .gitignore
│
├── frontend/                  # React + Vite + Tailwind
│   ├── public/
│   ├── src/
│   │   ├── assets/
│   │   ├── components/
│   │   │   ├── Navbar.jsx
│   │   │   ├── Footer.jsx
│   │   │   └── ProductCard.jsx
│   │   │
│   │   ├── pages/
│   │   │   ├── Home.jsx
│   │   │   ├── Login.jsx
│   │   │   ├── Register.jsx
│   │   │   ├── ProductDetails.jsx
│   │   │   ├── AddProduct.jsx
│   │   │   ├── Dashboard.jsx
│   │   │   └── AdminPanel.jsx
│   │   │
│   │   ├── context/
│   │   │   └── AuthContext.jsx
│   │   │
│   │   ├── services/
│   │   │   ├── api.js
│   │   │   └── authService.js
│   │   │
│   │   ├── utils/
│   │   │   └── formatDate.js
│   │   │
│   │   ├── App.jsx
│   │   ├── main.jsx
│   │   └── index.css
│   │
│   ├── postcss.config.js
│   ├── vite.config.js
│   ├── .env
│   └── package.json
│
│
├── backend/                   # Node.js + Express + MongoDB
│   ├── src/
│   │   ├── config/
│   │   │   └── db.js
│   │   ├── controllers/
│   │   ├── middleware/
│   │   ├── models/
│   │   ├── routes/
│   │   ├── utils/
│   │   ├── app.js
│   │   └── server.js
│   ├── .env
│   └── package.json
│
└── docs/
    ├── SRS.pdf
    ├── API_Documentation.md
    └── Architecture_Diagram.png

1. Authentication Routes (auth.routes.js)
    | Method | Endpoint         | Description       |
| ------ | ---------------- | ----------------- |
| POST   | `/auth/register` | Register new user |
| POST   | `/auth/login`    | Login user        |
| GET    | `/auth/profile`  | Get user profile  |
| PUT    | `/auth/profile`  | Update profile    |
| POST   | `/auth/logout`   | Logout            |

2. Product Routes (product.routes.js)
   | Method | Endpoint                    | Description              |
| ------ | --------------------------- | ------------------------ |
| POST   | `/products`                 | Create a product listing |
| GET    | `/products`                 | Get all products         |
| GET    | `/products/:id`             | Get product by ID        |
| PUT    | `/products/:id`             | Update product listing   |
| DELETE | `/products/:id`             | Delete product           |
| GET    | `/products/category/:catId` | Filter by category       |
| GET    | `/products/user/:userId`    | List user’s products     |

3. Messaging Routes (message.routes.js)
   | Method | Endpoint               | Description          |
| ------ | ---------------------- | -------------------- |
| POST   | `/messages`            | Send message         |
| GET    | `/messages/:userId`    | Show user's messages |
| GET    | `/messages/thread/:id` | Conversation thread  |
4. Category Routes (category.routes.js)
   | Method | Endpoint      | Description          |
| ------ | ------------- | -------------------- |
| POST   | `/categories` | Create category      |
| GET    | `/categories` | Fetch all categories |
5. Admin Routes (admin.routes.js)
   | Method | Endpoint                    | Description         |
| ------ | --------------------------- | ------------------- |
| GET    | `/admin/users`              | Get all users       |
| GET    | `/admin/products`           | Get all products    |
| PUT    | `/admin/block-user/:id`     | Block user          |
| DELETE | `/admin/remove-product/:id` | Remove product      |
| GET    | `/admin/stats`              | Platform statistics |


    
#INSTALLATION GUIDE

Clone project
git clone https://github.com/<user>/used-products-ecommerce.git
cd used-products-ecommerce

#INSTALL FRONT-END
cd frontend
npm install
RUN:
npm run dev
CREATE .env:
VITE_API_URL=http://localhost:5000/api/v1

#INSTALL BACK-END

cd backend
npm install

CREATE .env:
PORT=5000
MONGO_URI=<your mongo uri>
JWT_SECRET=<your secret key>
CLIENT_URL=http://localhost:5173

RUN:
npm run dev

#API Routes Overview
Auth
POST    /auth/register
POST    /auth/login
GET     /auth/profile

Products
GET     /products
POST    /products
GET     /products/:id
PUT     /products/:id
DELETE  /products/:id

👥 WORKFLOW CONTRIBUTION (FOR TEAM MEMBERS)

Pull updates

git pull


Create branch

git checkout -b feature-name


Commit your changes

Push branch

Create Pull Request

Team reviews and merges to main

🔐 Environment Variables

Never push .env files.
Add inside .gitignore.
