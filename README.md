# 🎬 Movie Ticket Booking Management

A **Pega Platform project** for managing movie ticket booking requests. The application handles movie details, show availability, ticket cost calculation, booking approval, ticket execution, routing, SLA, and confirmation notification.

## 👨‍🎓 Student Details

| Field       | Details                                                     |
| ----------- | ----------------------------------------------------------- |
| **Name**    | Belleri Bharath                                             |
| **Email**   | [belleribharath@gmail.com](mailto:belleribharath@gmail.com) |
| **Phone**   | 8374966596                                                  |
| **College** | Teegala Krishna Reddy Engineering College                   |
| **Branch**  | Electronics and Communication Engineering (ECE)             |
| **State**   | Telangana                                                   |

## 📌 Project Information

* **Project Name:** Movie Ticket Booking
* **Pega Application:** `NIP-Movie Ticket Booking Management-Bharath`
* **Case Type:** `Movie Ticket Request`
* **Platform:** Pega Platform

## 🎯 Project Objective

The main objective of this project is to create a simple and organized movie ticket booking process using Pega. It allows customers to submit booking requests, checks seat availability, calculates ticket cost, obtains confirmation, processes the booking, and sends a confirmation notification.

## 🚀 Features

### 1. Submit Movie Ticket Request

* Captures customer and movie booking details.
* Includes movie name, show date, show time, show type, and number of tickets.
* Required-field validation is applied.

### 2. Check Show Availability

* Captures available seat count.
* Checks the seat availability status.
* Booking proceeds only when seats are available.

### 3. Calculate Booking Cost

* Automatically calculates the total booking cost.
* Uses the ticket price and number of tickets.

**Formula:**

```text
Total Cost = Ticket Price × Number of Tickets
```

### 4. Confirm Booking Request

* Customer reviews the booking information.
* Customer can confirm or cancel the booking.

### 5. Maintain Movie and Show Data

Two reusable data objects are used:

**Movie**

* Movie Name
* Genre

**Show**

* Show Date
* Show Time
* Seat Capacity

### 6. Review Booking Details

The confirmation screen displays:

* Movie Name
* Show Date
* Show Time
* Number of Tickets
* Total Cost

### 7. Process Ticket Booking

The booking execution stage maintains:

* Booking Confirmation Status
* Seat Numbers
* Ticket ID

### 8. Notify Booking Confirmation

A correspondence rule sends a booking confirmation email after successful case resolution.

The confirmation contains:

* Case ID
* Movie details
* Show date and time
* Number of tickets
* Seat numbers
* Total cost

### 9. Booking SLA

The application uses an SLA with:

* **Goal:** 1 day
* **Deadline:** 2 days
* **Priority:** Increased when the deadline is breached

### 10. Route by Show Type

Bookings are routed according to the selected show type.

```text
Premium Show
     ↓
PremiumShowQueue

Standard / Other Show
     ↓
StandardShowQueue
```

## 🔄 Case Lifecycle

```text
Request Submission
        ↓
Availability
        ↓
Approval
        ↓
Booking Execution
        ↓
Resolution
```

## 🧮 Business Rule

**Rule Name:** `CalculateTotalCost`

**Rule Type:** Declare Expression

**Properties Used:**

* Ticket Price
* Number of Tickets
* Total Cost

**Formula:**

```text
.TotalCost = .TicketPrice * .NumberOfTickets
```

## 👥 Personas

### Customer

* Submits the movie ticket request.
* Provides booking details.
* Confirms the booking.

### Booking Support

* Handles ticket booking activities.
* Processes the booking request.

## 📋 Work Queues

| Work Queue          | Purpose                                |
| ------------------- | -------------------------------------- |
| `PremiumShowQueue`  | Used for premium or special screenings |
| `StandardShowQueue` | Used for all other shows               |

## 🛠️ Technologies Used

* **Pega Platform**
* **Pega Case Management**
* **Declare Expression**
* **Business Rules**
* **Correspondence**
* **SLA**
* **Work Queues**
* **Data Objects**
* **Routing**

## 📈 Application Workflow

The customer first submits a movie ticket request with the required movie and show details. The system checks seat availability and calculates the total cost automatically. The booking is then reviewed and confirmed. Based on the show type, the case is routed to the appropriate work queue. During booking execution, seat numbers and the ticket ID are recorded. Finally, the case is resolved and a confirmation email is sent.

## 👨‍💻 Author

**Belleri Bharath**

B.Tech – Electronics and Communication Engineering (ECE)

Teegala Krishna Reddy Engineering College, Telangana
