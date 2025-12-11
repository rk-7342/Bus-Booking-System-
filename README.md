# 🚌 Bus Ticket Booking System  
A full-stack bus ticket booking application built with **Node.js**, **Express**, **PostgreSQL**, and **React (TypeScript)**.  
Users can browse bus shows, select journey details, pick seats, add passenger information, make bookings, and proceed to payment.

---

## 🚀 Features

### 👤 User Features
- User Registration & Login (JWT Authentication)
- Select journey date, pickup, and destination
- View list of available bus shows
- View available & booked seats in real-time
- Select multiple seats
- Enter passenger details (name, age, gender, mobile)
- Booking confirmation summary
- Payment initiation (dummy for now)

### 🛠 Admin Features
- Create bus shows
- Manage routes (source ↔ destination)
- View all bookings
- Manage seat availability

### 🗄 Backend Features
- Express REST API
- PostgreSQL database integration
- Secure Authentication (JWT)
- Proper database schema with constraints
- Error handling & validation

### 🎨 Frontend Features
- React with TypeScript
- Fully component-based architecture
- Seat selection UI
- Protected routes (auth required)
- Axios-based API service layer

---

## 🧰 Tech Stack

### **Frontend**
- React (TypeScript)
- React Router
- Axios
- CSS Modules / Styled Components

### **Backend**
- Node.js
- Express.js
- PostgreSQL + pg library
- JWT Authentication
- Bcrypt password hashing

### **Dev Tools**
- Nodemon
- Concurrently
- VS Code
- pgAdmin4
- GitHub

---

## 📂 Folder Structure

```
bus-ticket-system/
│
├── backend/
│   ├── src/
│   │   ├── config/
│   │   ├── controllers/
│   │   ├── middlewares/
│   │   ├── routes/
│   │   ├── utils/
│   │   └── index.js
│   ├── package.json
│   └── .env
│
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── assets/
│   │   ├── components/
│   │   ├── context/
│   │   ├── pages/
│   │   ├── services/
│   │   ├── App.tsx
│   │   └── index.tsx
│   ├── package.json
│
└── README.md
```

---

## 🛢 Database Schema

### **routes**
| Column | Type | Description |
|--------|------|-------------|
| id | SERIAL PK | Route ID |
| source | VARCHAR | Starting location |
| destination | VARCHAR | Ending location |

### **shows**
| Column | Type |
|--------|------|
| id | SERIAL PK |
| route_id | INT FK |
| bus_name | VARCHAR |
| start_time | TIMESTAMP |
| total_seats | INT |

### **bookings**
| Column | Type |
|--------|------|
| id | SERIAL PK |
| user_id | INT FK |
| show_id | INT FK |
| seat_numbers | INTEGER[] |
| passengers | JSONB |
| status | VARCHAR |

---

## 🔑 Environment Variables

Create a file: `backend/.env`

```
PORT=3001
DATABASE_URL=postgres://username:password@localhost:5432/busdb
JWT_SECRET=your_jwt_secret
```

---

## ▶️ Running the Backend

```
cd backend
npm install
npm run dev
```

API will run at:  
**http://localhost:3001**

---

## ▶️ Running the Frontend

```
cd frontend
npm install
npm start
```

App will run at:  
**http://localhost:3000**

---

## 📡 API Endpoints Summary

### **Auth**
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | /api/auth/register | Register new user |
| POST | /api/auth/login | Login & get JWT |

### **Shows**
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | /api/shows | Create show (Admin) |
| GET | /api/shows | Get all shows |
| GET | /api/shows/:id/seats | Get booked seats for a show |

### **Bookings**
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | /api/bookings | Create booking |
| GET | /api/bookings/:id | Get booking details |

---

## 🌐 Deployment Guide

### **Backend (Render / Railway / Heroku)**
1. Push repo to GitHub  
2. Connect backend folder  
3. Add environment variables  
4. Deploy  

### **Frontend (Vercel / Netlify)**
1. Build the frontend  

```
npm run build
```

2. Deploy `/build` folder  

3. Update backend URL:

`frontend/src/services/api.ts`

```ts
baseURL: "https://your-backend-url/api"
```

---

## 🎯 Future Enhancements
- Razorpay / Stripe Payment Integration  
- Admin Dashboard (React UI)  
- Real-time seat lock using WebSockets  
- Ticket PDF generation  
- Email/SMS notifications  

---

## 🧑‍💻 Author
**Kota Sesha Sai Sanjeeva Rishi Vardhan**  
AI Engineering | Backend & Full Stack Developer

---

## ⭐ Contribute
Pull requests are welcome!  
If you like this project, give it a ⭐ on GitHub.

