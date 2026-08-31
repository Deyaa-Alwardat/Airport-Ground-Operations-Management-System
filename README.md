# Airport Ground Operations Management System

A C# console application developed as **Assignment 2** for managing the ground operations of a single airport terminal.

## Project Overview

The system is designed for airport ground staff, gate agents, and operations supervisors to manage flights, gates, passengers, boarding, baggage, bookings, standby passengers, and ground staff assignments during a working shift.

The application enforces business rules to prevent invalid or conflicting operations.

## Features

### Flight & Gate Management

* Register domestic and international flights.
* Store scheduled arrival and departure times.
* Store seat capacity and flight status.
* Assign flights to gates.
* Prevent gate assignment conflicts during overlapping time windows.
* Prevent international flights from being assigned to gates that do not support international operations.
* Update flight status:

  * Scheduled
  * Delayed
  * Boarding
  * Departed
  * Cancelled

### Passenger Management

* Register passengers with:

  * Passenger ID
  * Name
  * Category
* Supported passenger categories:

  * Standard
  * VIP
  * Reduced Mobility
* Support optional connecting-flight information.

### Boarding

* Check whether a passenger has a confirmed booking.
* Prevent boarding on cancelled or departed flights.
* Allow boarding only when the flight status is `Boarding`.
* Verify minimum connection time for connecting passengers.
* Display a specific reason when boarding is denied.

### Baggage Management

* Register multiple bags for the same passenger and flight.
* Track cumulative baggage weight.
* Apply baggage allowances by passenger category.
* Prevent a new bag from exceeding the passenger's total baggage allowance.
* Apply a maximum single-bag weight.
* Prevent baggage registration for departed or cancelled flights.

### Booking & Standby

* Register passengers separately from flight bookings.
* Confirm a booking when seats are available.
* Automatically place passengers on standby when the confirmed seat capacity is reached.
* Maintain a FIFO standby list.
* Limit the standby list capacity.
* Automatically promote the earliest standby passenger when a confirmed booking is cancelled.
* Prevent duplicate active bookings for the same passenger and flight.

### Ground Staff Management

* Assign staff members to flights or gates/facilities.
* Track cumulative duty hours during the session.
* Prevent overlapping staff assignments.
* Prevent assignments that exceed the maximum allowed duty hours.

## Design Decisions

The assignment leaves several values open for the developer to choose. The following values were selected:

| Rule                               |        Value |
| ---------------------------------- | -----------: |
| Minimum connection time            |   45 minutes |
| Maximum standby list size          | 5 passengers |
| Maximum staff duty hours per shift |      8 hours |
| Standard baggage allowance         |        30 kg |
| VIP baggage allowance              |        40 kg |
| Reduced Mobility baggage allowance |        30 kg |
| Maximum single bag weight          |        23 kg |

### Gate Occupancy Window

A flight occupies its assigned gate from its **scheduled arrival time until its scheduled departure time**.

Two flights cannot use the same gate when their occupancy windows overlap.

## OOP & Design

The project applies C# Object-Oriented Programming concepts including:

* Classes and objects
* Encapsulation
* Enums
* Interfaces
* Generics
* LINQ
* Dependency Injection
* Separation of responsibilities

The project also applies Clean Code and SOLID principles where appropriate to keep the implementation readable, maintainable, and extensible.

## Data Storage

The system uses **session-only in-memory storage**.

No database or external persistence is used.

All data is lost when the application is closed, according to the assignment requirements.

## Main Operations

The application supports:

1. Register Flight
2. Assign Flight to Gate
3. Update Flight Status
4. Register Passenger
5. Check Boarding Eligibility
6. Process Boarding
7. Register Baggage
8. View Passenger Cumulative Baggage
9. Book Passenger / Confirm or Standby
10. Cancel Confirmed Booking
11. View Flight Standby List
12. Assign Ground Staff
13. View Staff Duty Hours
14. View Gates
15. View Flights
16. View Passengers
17. View Bookings
18. Exit

## Error Handling

The system provides specific feedback for invalid operations, including:

* Invalid numeric input
* Duplicate flight registration
* Non-existing flights, gates, or passengers
* Gate schedule conflicts
* Invalid international gate assignments
* Insufficient connection time
* Missing confirmed booking
* Exceeding baggage allowance
* Full standby list
* Duplicate booking
* Overlapping staff assignments
* Exceeding staff duty-hour limits
* Boarding a departed or cancelled flight
* Registering baggage for a departed or cancelled flight

## How to Run

1. Open the Visual Studio solution.
2. Build the project using **Build > Build Solution**.
3. Run the application using **Ctrl + F5** or the Start button.
4. Use the console menu to perform the required airport ground operations.

## Technologies

* C#
* .NET
* Visual Studio
* Object-Oriented Programming
* LINQ
* Interfaces
* Generics
* Dependency Injection

## Assignment

**Airport Ground Operations Management System — Assignment 2**

Developed as a console-based implementation of the requirements provided by the training assignment.
