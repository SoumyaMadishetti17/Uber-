<h1 align="center">🚖 UberX – Production-Grade Ride Booking Platform</h1>

<p align="center">
A scalable, real-time ride booking system built with <b>MERN Stack</b> and <b>Microservices Architecture</b>.
<br/>
Designed with industry-level system design, performance optimization, and real-world scalability in mind.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Frontend-React-blue" />
  <img src="https://img.shields.io/badge/Backend-Node.js-green" />
  <img src="https://img.shields.io/badge/Database-MongoDB-brightgreen" />
  <img src="https://img.shields.io/badge/Architecture-Microservices-orange" />
  <img src="https://img.shields.io/badge/RealTime-Socket.io-yellow" />
  <img src="https://img.shields.io/badge/Auth-JWT-red" />
</p>

---

## 🌟 Overview

**UberX** is a full-stack ride-booking platform that simulates real-world ride-hailing systems like Uber.
The application is designed with a strong focus on:

* Scalability
* Real-time communication
* Clean architecture
* Production-ready backend design
* Industry-level system structure

This project demonstrates strong capabilities in **Full Stack Development, Backend Engineering, and System Design**.

---

## 🚀 Key Highlights

* ⚡ Microservices-based backend architecture
* 📡 Real-time ride requests & driver updates using Socket.io
* 🔐 Secure JWT authentication with role-based access
* 🧩 API Gateway for centralized request handling
* 📈 Scalable MongoDB schema design
* 🧱 Modular and maintainable codebase
* 🏗 Designed for high scalability and fault isolation

---

## 🏗 System Architecture

```
Client (React)
      │
      ▼
  API Gateway
      │
 ┌───────────────┬───────────────┬───────────────┐
 │ User Service  │ Ride Service  │ Driver Service│
 └───────────────┴───────────────┴───────────────┘
      │
      ▼
    MongoDB
```

### Why Microservices?

* Independent scaling of services
* Fault isolation
* Faster development & deployment
* Industry-standard backend architecture

---

## ⚡ Real-Time Workflow

1. User books a ride
2. Ride request is emitted via Socket.io
3. Nearby drivers receive request instantly
4. Driver accepts the ride
5. Live ride status updates in real-time
6. Ride completion & database persistence

---

## 🧩 Features

### Rider

* Register/Login
* Book rides with pickup & destination
* Fare estimation
* Live ride tracking
* Ride history

### Driver

* Driver authentication
* Accept/Reject rides
* Live location sharing
* Earnings tracking

### Admin

* Monitor active rides
* Manage users and drivers
* System overview

---

## 🛠 Tech Stack

### Frontend

* React.js
* Axios
* Context API / Redux
* Tailwind CSS / CSS
* Google Maps API

### Backend

* Node.js
* Express.js
* MongoDB
* Mongoose

### Architecture & Tools

* Microservices
* API Gateway
* Socket.io
* JWT Authentication
* REST APIs

---

## 📂 Project Structure

```
uberx/
│
├── client/                # React Frontend
├── gateway/               # API Gateway
├── services/
│   ├── user-service/
│   ├── driver-service/
│   ├── ride-service/
│
├── shared/
├── config/
└── README.md
```

---

## 🔐 Security

* JWT-based authentication
* Role-based authorization (User / Driver / Admin)
* Protected API routes
* Environment-based configuration

---

## ⚙️ Setup & Installation

### Clone Repository

```
git clone https://github.com/your-username/uberx.git
cd uberx
```

### Frontend

```
cd client
npm install
npm start
```

### Backend (Run each service)

```
cd services/service-name
npm install
npm run dev
```

---

## 🌍 Environment Variables

Create `.env` file:

```
PORT=5000
MONGO_URI=your_mongodb_url
JWT_SECRET=your_secret
GOOGLE_MAP_API_KEY=your_key
```

---

## 📈 Engineering Focus

This project demonstrates:

* Scalable backend architecture
* Real-time system design
* API design best practices
* Production-level project structuring
* Separation of concerns
* Clean and modular code

---

## 🔮 Future Enhancements

* Docker & Kubernetes deployment
* Redis caching
* Payment integration (Stripe/Razorpay)
* Notification service
* CI/CD pipeline
* Rate limiting & monitoring

---

## 👩‍💻 Author

**Soumya Madishetti**
Full Stack Developer | MERN | Backend & System Design Enthusiast

GitHub: https://github.com/your-username
LinkedIn: (Add your link)

---

## ⭐ If this project helped you

Please consider giving it a **star ⭐** to support the project.
