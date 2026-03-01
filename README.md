# 🚖 Uber Clone – Production-Ready Full Stack MERN Application

A production-level ride-booking platform inspired by Uber, built using the **MERN Stack**.
The application includes separate **User and Captain (Driver) systems**, secure authentication, Google Maps integration, real-time communication, and a complete ride lifecycle from booking to completion.

This project demonstrates real-world **full-stack development**, **system design**, and **scalable backend architecture** used in modern production applications.

---

## 🔥 Project Highlights

* Full-stack MERN architecture
* Separate User & Captain modules
* Real-time ride system using Socket.io
* Google Maps integration
* Secure JWT authentication
* Captain availability gateway
* Complete ride lifecycle management
* Production-ready backend structure
* Scalable system design concepts

---

## ✨ Features

### 👤 User Module

* User Registration & Login
* JWT Authentication
* Profile access
* Search pickup & destination
* Google Maps location suggestions
* Distance & fare estimation
* Create ride request
* Real-time ride status tracking

---

### 🚗 Captain (Driver) Module

* Captain Registration & Login
* Driver dashboard
* Receive ride requests in real-time
* Accept / Reject rides
* Start and complete rides
* Toggle Online / Offline availability
* View current ride details

---

### 🚕 Ride Lifecycle

Ride Status Flow:

Requested → Accepted → Ongoing → Completed

* Ride stored in MongoDB
* Fare calculated based on distance
* Real-time status updates for both User and Captain

---

## 🔁 Complete System Flow (User → Gateway → Captain)

### Step 1: User Creates Ride

1. User logs in
2. Enters pickup & destination
3. Frontend calls Maps APIs
4. User clicks **Book Ride**
5. Request sent to:

```
POST /api/ride/create
```

6. Backend:

* Creates ride in MongoDB
* Status = `requested`
* Sends event to available captains

---

### Step 2: Captain Gateway (Ride Distribution)

Backend:

* Finds captains where:

  * `isOnline = true`
  * Near pickup location
* Sends real-time event:

```
socket.emit("new-ride", rideData)
```

This layer works as the **Captain Gateway**.

---

### Step 3: Captain Accepts Ride

Request:

```
POST /api/ride/accept
```

Backend:

* Assigns captainId
* Updates status → `accepted`
* Notifies user via Socket

---

### Step 4: Ride Progress

| Action      | API          | Status    |
| ----------- | ------------ | --------- |
| Book Ride   | /ride/create | requested |
| Accept Ride | /ride/accept | accepted  |
| Start Ride  | /ride/start  | ongoing   |
| End Ride    | /ride/end    | completed |

Each step:

* Updates MongoDB
* Emits real-time event

---

## 🔴 Real-Time Communication

* Socket.io integration
* Live ride requests for captains
* Instant status updates for users
* Server acts as real-time gateway
* User ↔ Server ↔ Captain communication

---

## 🗺️ Maps & Location Services

* Google Maps JavaScript API
* Address autocomplete
* Address → Coordinates conversion
* Distance & duration calculation
* Route estimation

---

## 🔐 Security

* JWT Authentication
* Password hashing using bcrypt
* Protected routes middleware
* Token validation
* Logout functionality
* Environment-based configuration

---

## 🏗️ Tech Stack

### Frontend

* React (Vite)
* Axios
* Context API / State Management
* Tailwind CSS / CSS
* Google Maps JavaScript API
* Socket.io Client

### Backend

* Node.js
* Express.js
* MongoDB (Mongoose)
* JWT
* bcrypt
* Socket.io

---

## 📂 Project Structure

```
Uber-Clone/
│
├── client/                # React Frontend
│   ├── components
│   ├── pages
│   ├── context
│   ├── services
│   ├── hooks
│   └── App.jsx
│
├── server/                # Node Backend
│   ├── controllers
│   ├── models
│   ├── routes
│   ├── middlewares
│   ├── services
│   ├── config
│   └── server.js
│
└── README.md
```

---

## ⚙️ Installation & Setup

### 1. Clone Repository

```
git clone https://github.com/SoumyaMadishetti17/Uber-.git
cd Uber
```

---

## Backend Setup

```
cd server
npm install
```

Create `.env` inside **server**:

```
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
GOOGLE_MAPS_API_KEY=your_google_maps_key
```

Run backend:

```
npm run server
```

---

## Frontend Setup

```
cd client
npm install
```

Create `.env` inside **client**:

```
VITE_BASE_URL=http://localhost:5000
VITE_GOOGLE_MAPS_API_KEY=your_google_maps_key
```

Run frontend:

```
npm run dev
```

App runs at:

```
http://localhost:5173
```

---

## 📑 API Endpoints Overview

### Auth APIs

POST `/api/user/register`
POST `/api/user/login`
POST `/api/captain/register`
POST `/api/captain/login`

### Ride APIs

POST `/api/ride/create`
POST `/api/ride/accept`
POST `/api/ride/start`
POST `/api/ride/end`

### Maps APIs

GET `/api/maps/suggestions`
GET `/api/maps/distance-time`

---

## 🗃️ Database Models

### User

* Name
* Email
* Password
* Phone

### Captain

* Name
* Email
* Password
* Vehicle details
* Location
* isOnline status

### Ride

* UserId
* CaptainId
* Pickup & Destination coordinates
* Distance & Fare
* Ride status
* Timestamps

---

## ⚠️ Validation & Error Handling

* Request validation middleware
* Proper HTTP status codes
* Centralized error handling
* Input sanitization
* Authentication guards

---

## 🧠 System Architecture

```
User App (React)
        ↓
REST API (Node + Express)
        ↓
MongoDB Database
        ↓
Socket.io Gateway
        ↓
Captain App (React)
```

External Services:

* Google Maps API
* Socket.io

---

## ⚡ Performance Optimizations

* Efficient MongoDB queries
* Modular backend architecture
* JWT stateless authentication
* Lazy loading components
* Environment-based configuration

---

## 🌍 Deployment Ready

* CORS enabled
* Production build support
* Environment configuration
* Deployable on:

  * Render / Railway (Backend)
  * Vercel / Netlify (Frontend)
  * AWS / GCP

---

## 📸 Screenshots

(Add project screenshots here)

* User Ride Booking Screen
* Captain Dashboard
* Ride Tracking Page
* Map Integration View

---

## 🚀 Future Improvements

* Payment integration (Stripe / Razorpay)
* Push notifications
* Ride history analytics
* Admin dashboard
* Redis caching
* Microservices architecture
* Docker containerization
* CI/CD pipeline

---

## 💼 Resume Value

This project demonstrates:

* End-to-end MERN development
* Real-time system implementation
* Secure authentication architecture
* Third-party API integration
* System design understanding
* Production-level project structure

Suitable for **Full Stack / Backend roles (10–20+ LPA level)**.

---

## 🏷️ Tags

`#MERN` `#React` `#NodeJS` `#MongoDB` `#Express`
`#SocketIO` `#FullStack` `#Backend` `#GoogleMaps`
`#SystemDesign` `#JWT` `#RealTimeApp`

---

## 👨‍💻 Author

**Soumya Madishetti**
Full Stack Developer | MERN | Backend | System Design

---

## ⭐ Support

If you found this project helpful, please give it a ⭐ on GitHub!
