# 🚗 Ride Booking Backend API

This backend provides authentication, captain management, ride services, and map utilities for a ride-booking application. All protected routes require a valid JWT token.

---

## Base URL

```
http://localhost:<PORT>
```

---

## Authentication

Protected routes require the following header:

```
Authorization: Bearer <token>
```

---

# User APIs

## 1. Register User

**POST** `/users/register`

Creates a new user account.

### Request Body

```json
{
  "fullname": {
    "firstname": "Soumya",
    "lastname": "Madishetti"
  },
  "email": "soumya@example.com",
  "password": "123456"
}
```

### Response

```json
{
  "user": {
    "fullname": {
      "firstname": "Soumya",
      "lastname": "Madishetti"
    },
    "email": "soumya@example.com"
  },
  "token": "JWT_TOKEN"
}
```

---

## 2. Login User

**POST** `/users/login`

Authenticates user and returns JWT token.

### Request Body

```json
{
  "email": "soumya@example.com",
  "password": "123456"
}
```

---

## 3. Get User Profile

**GET** `/users/profile`
Requires authentication.

Returns current logged-in user details.

---

## 4. Logout User

**GET** `/users/logout`
Requires authentication.

Invalidates the current session token.

---

# Captain APIs

## 1. Register Captain

**POST** `/captains/register`

Creates a captain account with vehicle details.

### Request Body

```json
{
  "fullname": {
    "firstname": "Ravi",
    "lastname": "Kumar"
  },
  "email": "ravi@example.com",
  "password": "123456",
  "vehicle": {
    "color": "White",
    "plate": "TS09AB1234",
    "capacity": 4,
    "vehicleType": "car"
  }
}
```

### Response

```json
{
  "captain": {
    "fullname": {
      "firstname": "Ravi",
      "lastname": "Kumar"
    },
    "email": "ravi@example.com",
    "vehicle": {
      "color": "White",
      "plate": "TS09AB1234",
      "capacity": 4,
      "vehicleType": "car"
    }
  },
  "token": "JWT_TOKEN"
}
```

---

## 2. Login Captain

**POST** `/captains/login`

Authenticates captain and returns JWT token.

---

## 3. Captain Profile

**GET** `/captains/profile`
Requires authentication.

Returns captain profile details.

---

## 4. Logout Captain

**GET** `/captains/logout`
Requires authentication.

Returns:

```json
{
  "message": "Logout successful"
}
```

---

# Maps APIs

## 1. Get Coordinates

**GET**
`/maps/get-coordinates?address=<address>`

Returns latitude and longitude for a given address.

### Response

```json
{
  "lat": 17.3850,
  "lng": 78.4867
}
```

---

## 2. Get Distance and Duration

**GET**
`/maps/get-distance-time?origin=<origin>&destination=<destination>`

Returns travel distance and estimated time.

---

## 3. Location Suggestions

**GET**
`/maps/get-suggestions?input=<text>`

Returns autocomplete location suggestions.

---

# Ride APIs

## 1. Create Ride

**POST** `/rides/create`
Requires authentication.

### Request Body

```json
{
  "pickup": "Hitech City",
  "destination": "Secunderabad",
  "vehicleType": "car"
}
```

### Response

```json
{
  "ride": {
    "pickup": "Hitech City",
    "destination": "Secunderabad",
    "fare": 120,
    "status": "pending",
    "distance": 5000,
    "duration": 900,
    "otp": "4321"
  }
}
```

---

## 2. Get Fare Estimate

**GET**
`/rides/get-fare?pickup=<pickup>&destination=<destination>`

### Response

```json
{
  "auto": 60,
  "car": 100,
  "moto": 40
}
```

---

# Error Handling

| Status Code | Description                   |
| ----------- | ----------------------------- |
| 400         | Invalid or missing parameters |
| 401         | Unauthorized / Invalid token  |
| 404         | Resource not found            |
| 500         | Internal server error         |

---

# Validation Rules

* First name must be at least **3 characters**
* Password must be at least **6 characters**
* Vehicle capacity must be **minimum 1**
* Supported vehicle types: `car`, `auto`, `motorcycle`

---

# Tech Stack

* Node.js
* Express.js
* MongoDB
* JWT Authentication
* Map Service API (Google Maps or similar)

---

# Author

Soumya Madishetti
