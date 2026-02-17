# 🚖 Ride Booking Backend (Documentation)

A scalable backend system for a ride-booking platform that supports **User and Captain authentication**, **ride management**, and **map-based services**.
The system is built with a focus on clean architecture, security, and real-world production practices.

---

## Tech Stack & Dependencies

### Core Technologies
- Node.js
- Express.js
- MongoDB (Mongoose)
- JWT Authentication

### Main Dependencies

| Package | Purpose |
|---------|---------|
| express | Backend framework |
| mongoose | MongoDB object modeling |
| jsonwebtoken | JWT authentication |
| bcrypt | Password hashing |
| express-validator | Request validation |
| dotenv | Environment variable management |
| cors | Cross-origin resource sharing |
| cookie-parser | Cookie handling |
| axios | External API requests (Maps integration) |


---

## 📁 Project Structure

```
project-root
│
├── controllers
├── db
├── models
├── routes
├── middlewares
├── services
├── socket.js
├── app.js
├── package.json
├── package-lock.json
└── server.js


```

**Architecture Pattern:**
Controller → Service → Model

---

## ⚙️ Environment Variables

Create a `.env` file in the root:

```
PORT=5000
MONGO_URI=your_mongodb_connection
JWT_SECRET=your_secret_key
GOOGLE_MAPS_API_KEY=your_maps_key
```

---

## 🚀 How to Run Locally

```bash
# Clone repository
git clone https://github.com/SoumyaMadishetti17/Uber-.git

# Install dependencies
npm install

# Run server
npm start
```

Server will run at:

```
http://localhost:5000
```

---

# 🔐 Authentication

Protected routes require:

```
Authorization: Bearer <token>
```

Tokens are blacklisted on logout.

---

# 👤 User APIs

### Register

`POST /users/register`

Request:

```json
{
  "fullname": {
    "firstname": "Soumya",
    "lastname": "M"
  },
  "email": "user@example.com",
  "password": "123456"
}
```

Response:

* User object
* JWT Token

---

### Login

`POST /users/login`

---

### Profile

`GET /users/profile`

---

### Logout

`GET /users/logout`

---

# 🚗 Captain APIs

### Register

`POST /captains/register`

```json
{
  "fullname": {
    "firstname": "Raj"
  },
  "email": "captain@example.com",
  "password": "123456",
  "vehicle": {
    "color": "White",
    "plate": "TS09AB1234",
    "capacity": 4,
    "vehicleType": "car"
  }
}
```

---

### Login

`POST /captains/login`

---

### Profile

`GET /captains/profile`

---

### Logout

`GET /captains/logout`

---

# 🗺️ Maps APIs

### Get Coordinates

`GET /maps/get-coordinates?address=<address>`

Returns latitude and longitude.

---

### Get Distance & Duration

`GET /maps/get-distance-time?origin=<origin>&destination=<destination>`

---

### Get Suggestions

`GET /maps/get-suggestions?input=<text>`

---

# 🚕 Ride APIs

### Create Ride

`POST /rides/create`

Request:

```json
{
  "pickup": "Madhapur",
  "destination": "Gachibowli",
  "vehicleType": "car"
}
```

Response:

* Fare calculation
* Distance & duration
* Ride status
* OTP for ride verification

---

### Get Fare Estimate

`GET /rides/get-fare?pickup=<pickup>&destination=<destination>`

Response:

```json
{
  "auto": 50,
  "car": 80,
  "moto": 40
}
```

---

# 🛡️ Security Features

* JWT based authentication
* Password hashing (bcrypt)
* Token blacklisting on logout
* Input validation
* Role-based access control

---

# 📊 Key Features

* User & Captain role system
* Real-time fare calculation
* Map integration (coordinates, distance, autocomplete)
* Ride creation with OTP verification
* Clean scalable architecture

---

# 🧪 API Testing

You can test APIs using:

* Postman
* Thunder Client

---

# 📌 Future Improvements

* Real-time ride tracking (Socket.io)
* Payment integration
* Ride history & analytics
* Admin dashboard
* Docker deployment

---

# 👨‍💻 Author

**Soumya Madishetti**
MERN Stack Developer
Backend | System Design | API Development
