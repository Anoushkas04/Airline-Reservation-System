# Airline Reservation System (ARS)

A comprehensive **JavaFX-based Airline Reservation System** designed for efficient flight management and booking. This application simulates a real-world airline operations environment with features for both travellers and managers.

## 🚀 Key Features

### 👤 Traveller Portal
*   **Interactive Booking:** Search for flights by origin, destination, or date and book seats via an interactive grid-based seat map.
*   **Dynamic Pricing:** Implements a demand-based pricing model where seat prices increase by 10% after each successful booking.
*   **Add-on Services:** Purchase extras like in-flight meals, Wi-Fi access, lounge entry, and extra luggage.
*   **Automated Invoicing:** Generates detailed invoices including seat details, add-ons, and total costs.

### 🛠️ Manager Dashboard
*   **Flight Management:** Add new flights, delete existing ones, or mark flights as departed.
*   **Advanced Reporting:** Analyze system performance with automated reports on frequent destinations, busiest booking months, and departed flight logs.
*   **Secure Access:** Password-protected administrative interface.

## 💻 Technical Highlights
*   **Concurrency:** Utilizes Java multithreading and `synchronized` methods to handle concurrent booking requests safely, preventing race conditions.
*   **Reactive UI:** Built with JavaFX `Properties` and `Bindings` for real-time interface updates (e.g., immediate disabling of booked seats).
*   **Data Structures:** Custom generic `Stack` implementation used for flight logging and analytics.
*   **Search Engine:** Advanced filtering system for flight schedules using `FilteredList`.

## 🛠️ Requirements
*   Java 8 or higher
*   JavaFX SDK

---
*Created as part of a Cognitive Assessment project.*
