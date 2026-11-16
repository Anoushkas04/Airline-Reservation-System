# Airline Reservation System

A JavaFX desktop app for booking flights and managing an airline schedule. It was built to practise object-oriented design, multithreading and reactive UI in Java.

**Stack:** Java · JavaFX

## Features

**Traveller**
- Search the flight schedule by origin, destination or date.
- Book seats from a seat-map grid. Booked seats are disabled in real time.
- Demand-based pricing: each successful booking raises that flight's seat price by 10%.
- Add-ons: Wi-Fi, lounge access, catering and extra luggage.
- An invoice listing booked seats, booking times, add-ons and the total cost.

**Manager** (password-protected)
- Add and delete flights, and mark flights as departed.
- Reports: most frequent destination, busiest departure period, and busiest booking day, month and year.
- A searchable log of departed flights.

## Implementation notes

- **Concurrent bookings:** each booking request runs on its own thread, and `Seat.book()` is `synchronized`, so two travellers can't book the same seat. To show this, a second "traveller" books from the console on a separate thread while the GUI is in use. Whoever gets the seat first wins, and the other is told it's taken.
- **Reactive UI:** seat state, booked counts and price are JavaFX properties. The seat buttons and price label are bound to them, and a custom `BooleanBinding` detects when a flight is fully booked.
- **Search:** `FilteredList` over observable lists for the schedule and the departed-flight log.
- **Custom data structure:** a generic `Stack<T>` holds the departed-flight log that the reports read from.
- **Custom exception:** `AllSeatsBooked`.

## Running

Requires a JDK and the JavaFX SDK.

```bash
javac --module-path $PATH_TO_FX --add-modules javafx.controls Demo.java
java  --module-path $PATH_TO_FX --add-modules javafx.controls Demo
```

All data is in memory. Flights added during a session aren't saved.
