# 🚗 RTO Management System

A complete **RTO Management System** built using **Spring Boot**, **Java**, **Maven**, and **MySQL**, featuring RESTful APIs for backend management and a basic HTML/CSS/JavaScript frontend. The system allows efficient handling of vehicle registrations, driver licensing, payments, and appointments.

---

## 📌 Features

- ✅ Vehicle Registration Management  
- ✅ Driving License Issuance & Renewal  
- ✅ Learner License Management  
- ✅ Driving Test Appointments Scheduling  
- ✅ Payments & Fee Management  
- ✅ Insurance Records  
- ✅ Admin and User Roles  
- ✅ REST APIs with JSON Responses  

---

## 🧰 Tech Stack

| Layer             | Technology                            |
|-------------------|---------------------------------------|
| Backend           | Java, Spring Boot                     |
| Dependency Mgmt   | Maven                                  |
| Frontend          | HTML, CSS, JavaScript *(or React)*     |
| Database          | MySQL                                  |
| ORM               | Spring Data JPA                        |
| Security          | Spring Security *(Basic Auth/JWT)*     |
| Tools             | Postman, Swagger                       |

---

## 🗃️ Database Design

Below are the main tables and their fields:

---

### 🧑‍💼 User Management

**Users**
- `user_id` (Primary Key)
- `first_name`, `middle_name`, `last_name`
- `email`, `phone_number`, `address`
- `username`, `password`
- `status` *(active/inactive)*

**Profile_Update**
- `user_id` (Primary Key)
- `first_name`, `middle_name`, `last_name`
- `dob` (Date of Birth)
- `address`, `phone_number`, `email`
- `blood_group`, `photo`
- `license_status` *(active/inactive)*

---

### 🪪 License & Driver Management

**Driving_Licenses**
- `license_id` (PK)
- `user_id` (FK)
- `license_type` (Private, Commercial, etc.)
- `issue_date`, `expiry_date`
- `license_number`, `vehicle_type`
- `status`

**Learner_Licenses**
- `learner_id` (PK)
- `user_id` (FK)
- `issue_date`, `expiry_date`
- `status`

---

### 🚗 Vehicle Registration

**Vehicle_Registrations**
- `registration_id` (PK)
- `vehicle_id` (FK)
- `user_id` (FK)
- `registration_date`, `expiry_date`
- `registration_number`
- `status`

---

### 💳 Fees & Payments

**Payments**
- `payment_id` (PK)
- `user_id` (FK)
- `payment_amount`, `payment_date`
- `payment_method` (Cash, Card, Online)
- `transaction_id`
- `payment_status`

**Fee_Schedules**
- `fee_id` (PK)
- `service_name` (License Renewal, Vehicle Registration, etc.)
- `fee_amount`
- `service_category`

---

### 🛡️ Insurance

**Insurance**
- `insurance_id` (PK)
- `vehicle_id` (FK)
- `insurance_company`
- `policy_number`
- `expiry_date`
- `premium_amount`

---

### 📝 Driving Test Appointments

**Driving_Test_Appointment**
- `appointment_id` (PK)
- `driver_id` (FK)
- `test_date`, `test_time`
- `test_type` (Written, Practical, etc.)
- `location`
- `instructor_id` (FK)
- `status` (Scheduled, Completed, Cancelled)

---

### ♻️ License Renewal

**License_Renewal**
- `renewal_id` (PK)
- `driver_id` (FK)
- `license_id` (FK)
- `renewal_date`, `expiry_date`
- `status` (Pending, Approved, Rejected)
- `payment_id` (FK)

---

## 🚀 How to Run

### 📦 Backend Setup

```bash
git clone https://github.com/VISHAKHADAC/rto-management-system.git
cd rto-management-system
mvn clean install
```

### ⚙️ Start the Application

```bash
./mvnw spring-boot:run
```

### 🌐 Frontend Access

- Open `src/main/resources/static/index.html` in your browser  
- *(Optional)* Deploy React frontend separately

---

## 📁 API Endpoints (Sample)

| Method | Endpoint                      | Description                        |
|--------|-------------------------------|------------------------------------|
| GET    | `/api/vehicles`               | Get all vehicles                   |
| POST   | `/api/vehicles/register`      | Register new vehicle               |
| POST   | `/api/licenses/apply`         | Apply for driving license          |
| GET    | `/api/users/{id}`             | Retrieve user details              |
| POST   | `/api/license-renewal`        | Renew driving license              |
| POST   | `/api/driving-test/schedule`  | Schedule driving test appointment  |

---

## 🔒 Authentication

- Spring Security with basic login credentials  
- *(Optional)* JWT authentication can be implemented for REST APIs

---

## 👩‍💻 Author

- **Vishakha Huse**
- [GitHub Profile](https://github.com/VISHAKHADAC)

---

## 📝 License

This project is licensed under the MIT License.
