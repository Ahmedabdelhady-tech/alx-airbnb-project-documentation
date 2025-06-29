# 🏠 ALX Airbnb Project – Backend Requirements

## 📜 Overview

This document defines the **functional and technical requirements** for key backend features of the Airbnb-like system. It covers API endpoints, input/output specifications, validation rules, and performance standards.

---

## 1️⃣ User Authentication

### ✅ Functional Requirements

- Users can register an account.
- Users can log in to get an access token.
- Users can log out to invalidate the session.
- Only authenticated users can access protected resources.

### 🔗 API Endpoints

| Method | Endpoint        | Description                  |
|--------|-----------------|------------------------------|
| POST   | `/api/register` | Register a new user          |
| POST   | `/api/login`    | Authenticate user credentials|
| POST   | `/api/logout`   | Logout user session          |

### 📥 Input / 📤 Output

- **Register**
  - **Input:** `{first_name, last_name, email, password, phone_number (optional)}`
  - **Output:** `201 Created` or error (`409` if email exists)

- **Login**
  - **Input:** `{email, password}`
  - **Output:** `200 OK` with JWT token or `401 Unauthorized`

- **Logout**
  - **Input:** JWT token in header
  - **Output:** `200 OK`

### 🔍 Validation Rules

- Email must be unique and valid.
- Password minimum length: 8 characters.
- Phone number is optional but validated if present.

### 🚀 Performance

- Response time < 500ms.
- Rate limiting for login attempts (e.g. 5 per minute).

---

## 2️⃣ Property Management

### ✅ Functional Requirements

- Hosts can create, update, delete, and view properties.
- Guests can browse properties.

### 🔗 API Endpoints

| Method | Endpoint               | Description                       |
|--------|------------------------|-----------------------------------|
| POST   | `/api/properties`      | Create property (Host)            |
| GET    | `/api/properties`      | List all properties               |
| GET    | `/api/properties/:id`  | Retrieve property details         |
| PUT    | `/api/properties/:id`  | Update property (Host)            |
| DELETE | `/api/properties/:id`  | Delete property (Host/Admin)      |

### 📥 Input / 📤 Output

- **Create Property**
  - **Input:** `{name, description, location, price_per_night}`
  - **Output:** `201 Created` with property info

- **Get Properties**
  - **Output:** List of properties with pagination support

### 🔍 Validation Rules

- `name`, `description`, `location` cannot be empty.
- `price_per_night` must be a positive decimal.
- Only the host who owns the property can update/delete it.

### 🚀 Performance

- API must support filtering by location, price, etc.
- Query responses < 700ms for up to 1000 properties.

---

## 3️⃣ Booking System

### ✅ Functional Requirements

- Users can create and cancel bookings.
- Hosts can view bookings related to their properties.

### 🔗 API Endpoints

| Method | Endpoint                    | Description                     |
|--------|-----------------------------|---------------------------------|
| POST   | `/api/bookings`             | Create a booking                |
| GET    | `/api/bookings`             | List user bookings              |
| GET    | `/api/bookings/:id`         | Retrieve booking details        |
| DELETE | `/api/bookings/:id/cancel`  | Cancel a booking                |

### 📥 Input / 📤 Output

- **Create Booking**
  - **Input:** `{property_id, start_date, end_date}`
  - **Output:** `201 Created` with booking info or error

- **Cancel Booking**
  - **Output:** `200 OK` with cancellation confirmation

### 🔍 Validation Rules

- Dates cannot overlap with existing bookings.
- `start_date` must be before `end_date`.
- Status must be `pending`, `confirmed`, or `cancelled`.

### 🚀 Performance

- Booking confirmation within 700ms.
- Availability checks handle concurrent requests safely.

---

## 4️⃣ Payment Processing

### ✅ Functional Requirements

- Users can make payments for bookings.
- Payment status is tracked.

### 🔗 API Endpoints

| Method | Endpoint                  | Description                  |
|--------|---------------------------|------------------------------|
| POST   | `/api/payments`           | Make a payment for a booking |
| GET    | `/api/payments/:id`       | Retrieve payment details     |

### 📥 Input / 📤 Output

- **Payment**
  - **Input:** `{booking_id, amount, payment_method}`
  - **Output:** `201 Created` or error

### 🔍 Validation Rules

- `amount` must equal the total booking price.
- `payment_method` in {credit_card, paypal, stripe}.

---

## 5️⃣ Reviews & Messaging

### ✅ Functional Requirements

- Users can leave reviews after a stay.
- Users can send messages to each other.

### 🔗 API Endpoints

| Method | Endpoint               | Description                    |
|--------|------------------------|--------------------------------|
| POST   | `/api/reviews`         | Submit a property review       |
| GET    | `/api/reviews/:id`     | Get property reviews           |
| POST   | `/api/messages`        | Send a message                 |
| GET    | `/api/messages`        | Retrieve messages              |

### 🔍 Validation Rules

- Rating between 1 to 5.
- Comments cannot be empty.

---

## 🔐 Security Requirements

- Authentication with JWT.
- Role-based access control:
  - **Guest:** Browse, book, review.
  - **Host:** Manage properties, view bookings.
  - **Admin:** Manage all.

## ⚙️ Performance & Scalability

- Indexing on `email`, `property_id`, `booking_id`.
- All APIs are stateless and scalable.
- Error handling with standardized JSON error responses.

---

## 📂 File Structure
