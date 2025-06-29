Requirement Analysis in Software Development.

What is Requirement Analysis?
Requirement analysis is basically the process of figuring out what exactly needs to be built before you start developing software. It is almost like, “What do you want your house to look like?” before you even pick up a hammer. It’s about understanding the needs, goals, and expectations of the people who will use the software, and then putting all that into a clear plan. In software terms, that means sitting down with clients, users, or teams to find out what they want the software to do, why they want it, and how they expect it to behave. It’s one of the first and most important steps in the software development process.

Types of Requirements.
1. Functional Requirement:
      Functional requirements describe what the system should do — the core functions, features, and behaviors of the app that serve user needs directly.
   A. Hotel Management Service
      - Add/Update Hotel Information
         Example: Hotel managers should be able to add new hotels, update room availability, and change pricing through a portal.
      - Manage Room Details
         Example: Managers can update room types, features, images, and number of available rooms.
   B. Customer Service (Search + Booking)
      - Search Hotels
         Example: Users should be able to search for hotels by location, date, price range, and rating using Elasticsearch.
      - Make a Booking
         Example: Customers should be able to select a room, confirm booking dates, and submit a booking request.
      - Process Payments
        Example: The system must integrate with third-party payment services to allow customers to pay for their bookings.
   C. View Booking Service
      - View Current & Past Bookings
         Example: Customers and hotel managers can view booking history, statuses, and details.
      - Send Notifications
         Example: Notifications are sent when a booking is confirmed or an offer becomes available (via Kafka consumers).
2. Non-functional Requirements:
      Non-functional requirements describe how the system performs rather than what it does. These ensure the system runs smoothly, securely, and efficiently.
   A. Performance & Scalability
      - The system should support high user traffic using load balancers, CDNs, and microservices.
      - Booking data should load quickly using Redis caching to reduce response time.
   B. Reliability & Availability
      - Hotel and booking data must always be accessible, even under heavy traffic — supported by master-slave DB architecture and CDNs.
      - The system should sync updates in real-time, using message queues (Kafka) to handle asynchronous updates between services.
   C. Data Management
      - Booking and search data should be stored and retrieved efficiently, using Cassandra for archival and ElasticSearch for fast search.
      - Temporary booking data should be cached, using Redis to improve API speed and reduce DB load.
   D. Security
      - User data and payment details must be securely handled via third-party payment gateways and secured API endpoints.
   E. Maintainability & Modularity
      - The system should be easy to update or expand without downtime, achieved through microservices architecture where each service (e.g., search, booking, payment) works       independently.

Key Activities in Requirement Analysis.
1. Requirement Elicitation - Gathering requirements through:
    * Interviews, surveys, focus groups
    * Observation, document analysis
    * Prototyping or brainstorming
2. Requirement Documentation - Writing down requirements clearly in formats like:
    * Software Requirements Specification (SRS)
    * User stories or use cases
    * Process models or diagrams
3. Requirement Validation - Ensuring requirements are:
    * Accurate, complete, feasible, and unambiguous
    * Reviewed and approved by stakeholders
4. Requirement Analysis and Prioritization
    * Analyzing dependencies, conflicts, and priorities
    * Deciding what to build first and why

Why is Requirement Analysis Important?
1. Foundation for Design and Development: Requirement analysis acts as the blueprint for the entire development process. Without it, developers may build a product that doesn't solve the right problem.
2. Reduces Project Risk: Clear requirements prevent miscommunication, scope creep, and rework, which are often the cause of software failure or budget overruns.
3. Improves Stakeholder Satisfaction: By involving stakeholders early, requirement analysis ensures the final product aligns with actual business needs.
4. Facilitates Better Planning and Estimation: Well-defined requirements help project managers estimate time, cost, and resources more accurately.
5. Supports Testing and Validation: Requirements serve as the basis for creating test cases to verify that the software meets user expectations.

## 📌 Use Case Diagrams

### 🧾 What is a Use Case Diagram?

A Use Case Diagram is a visual representation of the system's functionality from the user's point of view. It shows the interactions between users (**actors**) and the system's key functions (**use cases**). These diagrams are commonly used in the Requirement Analysis phase to clarify how users engage with the system.

### ✅ Benefits of Use Case Diagrams

- Clearly defines system boundaries.
- Helps identify main functionalities and user interactions.
- Makes requirements easy to understand for technical and non-technical stakeholders.
- Aids in identifying and avoiding missing functionality early in the development process.

---

### 🏨 Use Case Diagram: Hotel Booking System

The following use case diagram models a hotel booking system like Airbnb or OYO. It includes two main actors:

- **Customer** – the end-user booking a hotel.
- **Hotel Manager** – the hotel owner/administrator managing listings and bookings.

### 📷 Diagram
[alx-booking-uc](https://github.com/user-attachments/assets/34b87386-58c6-4bff-a19a-1974392cb0bb)
alx-booking-uc.png

Acceptance Criteria
### 📌 What is Acceptance Criteria?
**Acceptance Criteria** are clear, specific conditions or requirements that a software feature must meet for it to be accepted by the end user, stakeholder, or product owner. They define the boundaries of a user story or feature and clarify what the software should do, helping both developers and testers understand when a task is “done.”
### 🎯 Importance of Acceptance Criteria in Requirement Analysis
- Ensures everyone has a shared understanding of the feature’s purpose and expected behavior.
- Acts as a guideline for developers to implement functionality that meets business needs.
- Helps QA testers create test cases and verify that all requirements are met.
- Reduces ambiguity and scope creep by clearly stating what is *in* and *out* of scope.
- Improves communication between business stakeholders and technical teams.

Example: Acceptance Criteria for **Checkout Feature**
**Feature:** Customer completes hotel booking with payment confirmation.
#### ✅ Acceptance Criteria:
1. The system must allow a logged-in user to initiate checkout after selecting a hotel room.
2. The user must be able to review booking details (hotel name, dates, price, taxes) before proceeding.
3. The user must select a payment method (e.g., debit/credit card, wallet).
4. The system must validate payment information and confirm successful transactions via the payment gateway.
5. A confirmation message must be displayed after a successful payment, along with a unique booking reference number.
6. A booking confirmation email must be sent to the user’s registered email within 1 minute.
7. The booking status in the system must update to “Confirmed” after successful checkout.
8. If payment fails, the system must notify the user and allow them to retry with a different method.
### ✅ Format Tip:
Acceptance criteria are often written using the **Given-When-Then** format. Here’s one rewritten in that format:
> **Given** the user is on the checkout page with a valid hotel selection,  
> **When** they enter valid payment information and click “Pay Now”,  
> **Then** the system should process the payment and display a booking confirmation screen with a unique reference.


