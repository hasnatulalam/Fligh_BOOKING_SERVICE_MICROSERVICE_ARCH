Sharing the progress we've made on the Flight Reservation System project 🛫✈️
Details of the project:

- REST API,
- MVC design pattern.
- Embracing the benefits of Microservices, we designed our system to be modular and loosely coupled, enabling independent development and deployment of various functionalities.
- For data storage and management, we utilized the reliable and widely supported MySQL database, leveraging the power of 'Sequelize' as our Object-Relational Mapping (ORM) tool.

💡 Key Project Challenges and Solutions:

✅ Same Seat Selection:
- Implemented a solution to handle simultaneous seat selection by multiple users.
- Prioritized the first booking request and blocked subsequent requests for a specified period to ensure fair booking practices and prevent double bookings.
✅ Concurrent Bookings for the Same Seat:
- Implemented restrictions to prevent multiple users from making concurrent bookings for the same seat.
- Ensured that each seat is allocated to only one passenger at a time, eliminating conflicts.
✅ Sequential Payment Requests:
- Developed a mechanism to handle payment requests from the same user for the same booking ID.
- Ensured sequential processing of payment requests to avoid conflicts and prevent double charging.

🔒 Concurrency and Security:
To address the concurrent seat booking issue, we utilized locks and transactions, enabling smooth and conflict-free booking experiences for our users. Additionally, we implemented the concept of "idempotency" to handle duplicate payment requests effectively.

⏰ Cron Jobs and Notifications:
In bookings service, we used scheduled CRONS to regularly check and cancel pending bookings. Developed a separate "Notification service" that utilized message queues, configured using RabbitMQ, to ensure reliable communication between services, following a pub-sub model. Implemented an email service that sends a confirmation email to users upon successful booking of a flight, providing them with important details and ensuring a seamless customer experience. 

🔐 Secure API Gateway:
In our API Gateway service, we focused on security and scalability, implementing essential features such as:
1️⃣ Authentication using JWT and Authorization
2️⃣ Rate limiter
3️⃣ Proxy server
