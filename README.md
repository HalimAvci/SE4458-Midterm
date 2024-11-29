# Presentation Link

https://www.youtube.com/watch?v=DEZL8IXbr28

**Note:** The audio recording is missing due to issues with finding a suitable microphone.

# ER Diagram

![ER Diagram](https://github.com/user-attachments/assets/89e47832-605a-407d-a112-4f86b8c8335b)

**!!!** For a detailed explanation of the data model used in this project, please refer to the Data Model section at the end of this document.


# SE4458 Midterm Project
This is a web-based ticket management system designed for airline flight bookings and check-ins. The application allows users to:
- Search for available flights based on date, origin, and destination.
- Book tickets for available flights.
- Perform check-ins for booked tickets.
- Manage flight data with an admin interface.

# Features
- • **User Features:**
- **Flight Search:** Search available flights based on date, origin, and destination.
- **Ticket Booking:** Book tickets for flights and generate booking details.
- **Check-In:** Passengers can check in for their flights once a ticket is purchased.

- • **Admin Features:**
- **Add Flights:** Admin users can add new flights with details like date, origin, destination, available seats, and price.
- **Report Flights:** Admin users can generate reports of flights based on various filters like date, available seats, and price.

  # Technologies Used
  - **ASP.NET Core:** Backend framework for building RESTful APIs.
  - **Entity Framework Core:** ORM for database interactions.
  - **JWT Authentication:** secures API endpoints using JSON Web Tokens (JWT).
  - **Microsoft SQL Server:** Database used to store flight and ticket data.

  # API Endpoints
  **Authentication**
  - **GET/Authentication/Values:** Authenticate admin users and get a JWT token.
    
  **Flights**
  - **POST/Admin/Insert flight:** Add a new flight.
  - **POST/Admin/Report flight:** Generate a report of flights based on filters.

  **Ticketing**
  - **GET/Mobile app/Query:** Query available flights.
  - **POST/Mobile app/Buy:** Book a ticket.
  - **POST/Mobile app/Check-in:** Check in for a flight.

  # Security
  This project uses JWT-based authentication. To access protected endpoints (such as adding flights or querying the flight report), an admin user needs to authenticate and receive a token. This token must be 
  included in the Authorization header as a Bearer token.

  ```bash
  Authorization: Bearer <your_token_here>
  ```

  # Data Models
  
  **Flights**
  - ID: int (Primary key)
  - Date: date
  - FlightNumber: varchar
  - FromLoc: varchar
  - ToLoc: varchar
  - AvailableSeats: int
  - Price: decimal

  **Tickets**
  - ID: int (Primary key)
  - Date: date
  - FlightNumber: varchar (Foreign key to flights)
  - FromLoc: varchar
  - ToLoc: varchar
  - PassName: varchar
  - NoOfPeople: int
  - IsCheckedIn: bit
  
