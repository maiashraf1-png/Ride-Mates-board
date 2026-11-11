# Commuter Carpool Board — User Stories

**Team:** RideMates  
**Members:** Malak Mohamed | Mai Ashraf | Gana Ahmed | Menna Allah Mostafa | Maram Moustafa  
**Week:** 4 Deliverable

## 1. Product Overview

**Problem:** Many students and staff drive alone to campus while others spend long hours on public transport.

**Users:** Driver · Passenger · Admin

**Estimation Scale:** Fibonacci (1, 2, 3, 5, 8). See `estimation.md`.

## 2. Key Business Rules

| ID | Rule | Enforced in |
|---|---|---|
| BR-1 | Free seats can never drop below zero. | US-11, US-13 |
| BR-2 | A driver cannot book their own ride. | US-12 |
| BR-3 | Phone numbers are visible to the other party only after booking confirmation. | US-18 |

## 3. Story Summary

| ID | Epic | Story | Role | Points | Priority |
|---|---|---|---|---:|---|
| US-01 | Account | Register and log in | All | 5 | MVP |
| US-02 | Offer a Ride | Offer a ride | Driver | 3 | MVP |
| US-03 | Offer a Ride | View my offered rides | Driver | 2 | MVP |
| US-04 | Offer a Ride | See who booked my seats | Driver | 2 | MVP |
| US-05 | Offer a Ride | Cancel a ride | Driver | 3 | MVP |
| SP-01 | Match Riders | Spike: matching approach | Team | 2 | MVP |
| US-06 | Match Riders | Search rides by area | Passenger | 3 | MVP |
| US-07 | Match Riders | Search rides by arrival time | Passenger | 3 | MVP |
| US-08 | Match Riders | Combine area and time search | Passenger | 2 | MVP |
| US-09 | Match Riders | View ride details | Passenger | 2 | MVP |
| US-10 | Booking | Request a seat | Passenger | 5 | MVP |
| US-11 | Booking | Prevent seats below zero | System | 3 | MVP |
| US-12 | Booking | Block drivers from booking their own rides | System | 2 | MVP |
| US-13 | Booking | Confirm a booking | Driver | 3 | MVP |
| US-14 | Booking | Reject a booking | Driver | 2 | MVP |
| US-15 | Booking | Cancel my booking | Passenger | 3 | MVP |
| US-16 | Notifications & Safety | Notify on confirmation or rejection | Passenger | 3 | MVP |
| US-17 | Notifications & Safety | Notify on cancellations | User | 3 | MVP |
| US-18 | Notifications & Safety | Show phone numbers only after confirmation | Both parties | 3 | MVP |
| US-19 | Admin | Remove inappropriate rides | Admin | 3 | MVP |
| US-20 | Stretch | Rate a ride | Passenger | 5 | Stretch |
| US-21 | Stretch | Recurring weekly rides | Driver | 8 | Stretch |
| US-22 | Stretch | Preference filters (e.g., same-gender) | Passenger | 5 | Stretch |

**MVP total: 57 points (19 User Stories + 1 Spike).**  
**Stretch total: 18 points (3 User Stories).**

---

## 4. Epic: Account

### US-01 — Register and Log In (5 pts)

As a **user**, I want to register and log in so that I can offer or book rides under my own identity.

**Acceptance Criteria**

AC1 – Successful Registration
- Given a user is not registered in the system.
- When the user enters a valid name, email, phone number, password, and role, and clicks Register.
- Then the system creates a new account and displays a success confirmation.
  
AC2 – Duplicate Email
- Given an account already exists with the same email address.
- When the user attempts to register using that email address.
- Then the system rejects the registration and displays an error message indicating that the email is already registered.
  
AC3 – Required Fields Validation
- Given a user is on the registration page.
- When the user submits the registration form with one or more required fields empty.
- Then the system prevents registration and displays validation messages for the missing fields.
  
AC4 – Invalid Email Format
- Given a user is on the registration page.
- When the user enters an invalid email format.
- Then the system rejects the input and displays an appropriate validation message.
  
AC5 – Successful Login
- Given a user has an existing registered account.
- When the user enters the correct email and password and clicks Login.
- Then the system authenticates the user and redirects them to their dashboard.
  
AC6 – Invalid Login Credentials
- Given a user has an existing registered account.
- When the user enters an incorrect email or password.
- Then the system denies access and displays an appropriate error message.
  
AC7 – Unregistered Email
- Given no account exists with the entered email address.
- When the user attempts to log in.
- Then the system denies access and displays an error message
---

## 5. Epic: Offer a Ride

### US-02 — Offer a Ride (3 pts)

As a **driver**, I want to offer a ride by entering my area, departure time, estimated arrival time, and free seats so that passengers can find my ride.

**Acceptance Criteria**

AC1 – Successful Ride Publication
- Given a driver is logged in and all required ride details are valid.
- When the driver enters the departure area, departure time, estimated arrival time, and number of free seats, then submits the form.
- Then the system publishes the ride and makes it available in search results.
  
AC2 – Invalid Number of Free Seats
- Given a driver is creating a new ride.
- When the driver enters a number of free seats less than 1.
- Then the system rejects the ride and displays an appropriate validation message.
  
AC3 – Past Departure Time
- Given a driver is creating a new ride.
- When the driver enters a departure time earlier than the current date and time.
- Then the system rejects the ride and displays an error message indicating that the departure time must be in the future.
  
AC4 – Invalid Arrival Time
- Given a driver is creating a new ride.
- When the driver enters an estimated arrival time earlier than the departure time.
- Then the system rejects the ride and displays an error message indicating that the arrival time must be after the departure time.
  
AC5 – Store Estimated Arrival Time
- Given a driver submits a ride with valid departure and estimated arrival times.
- When the ride is successfully published.
- Then the system stores the estimated arrival time and uses it when passengers search for rides by arrival time.

### US-03 — View My Offered Rides (2 pts)

As a **driver**, I want to view my offered rides so that I can manage them.

**Acceptance Criteria**

AC1 – View Offered Rides
- Given a driver is logged in and has one or more offered rides.
- When the driver opens the "My Rides" page.
- Then the system displays all rides offered by that driver, including the departure area, departure time, estimated arrival time, and remaining seats.
  
AC2 – Empty Rides List
- Given a driver is logged in and has not offered any rides.
- When the driver opens the "My Rides" page.
- Then the system displays an empty-state message indicating that no rides have been offered yet.
  
AC3 – Display Only Driver's Own Rides
- Given multiple drivers have offered rides in the system.
- When a driver opens the "My Rides" page.
- Then the system displays only the rides offered by the currently logged-in driver.
  
AC4 – Updated Ride Information
- Given a driver's offered rides have been updated.
- When the driver opens or refreshes the "My Rides" page.
- Then the system displays the latest available ride information.

### US-04 — See Who Booked My Seats (2 pts)

As a **driver**, I want to see who booked my seats so that I know whom to pick up.

**Acceptance Criteria**

- Given a ride with bookings, when I open it, then I see each passenger's name and booking status.
- Given a booking is not yet confirmed, then it is labelled "Pending".

### US-05 — Cancel a Ride (3 pts)

As a **driver**, I want to cancel my ride so that passengers know the trip will not happen.

**Acceptance Criteria**

- Given an active ride, when I cancel it, then its status becomes "Cancelled" and it disappears from search.
- Given the ride had bookings, then all booked passengers are notified (see US-17).

---

## 6. Epic: Match Riders (Split Using SPIDR)

"Match riders" is too large for one sprint, so it was split using SPIDR:

| Letter | Technique | Result |
|---|---|---|
| S — Spike | Time-boxed research on how to match area and time | SP-01 |
| P — Paths | Separate paths: by area, by arrival time, and combined | US-06, US-07, US-08 |
| I — Interfaces | Results list and ride details screen | US-09 |
| D — Data | Area, departure time, estimated arrival time, and free seats | US-06 to US-09 |
| R — Rules | Seat limits and own-ride rule | US-11, US-12 |

### SP-01 — Spike: Matching Approach (2 pts)

As the **team**, we want to investigate how to match rides by area and time so that we choose a simple, reliable approach before building search.

**Acceptance Criteria**

- Time-boxed to 1 working day.
- Output: a short written decision covering area selection (area list vs. free text) and arrival-time range logic.

### US-06 — Search Rides by Area (3 pts)

As a **passenger**, I want to search rides by area so that I can find a convenient pickup location.

**Acceptance Criteria**

- Given rides exist in "Nasr City", when I search that area, then only matching rides are listed.
- Given no matches, then a "No rides found" message is shown.

### US-07 — Search Rides by Arrival Time (3 pts)

As a **passenger**, I want to find rides arriving before a chosen time (e.g., 9:00) so that I reach my first lecture on time.

**Acceptance Criteria**

- Given I set "arrive before 09:00", then only rides with an estimated arrival time at or before 09:00 are shown.
- Results are sorted by earliest estimated arrival time.

### US-08 — Combine Area and Time Search (2 pts)

As a **passenger**, I want to search by area and arrival time together so that I see only the most relevant rides.

**Acceptance Criteria**

- Given both filters, then results satisfy both the selected area and arrival-time conditions.
- Given only one filter, then the search still works.

### US-09 — View Ride Details (2 pts)

As a **passenger**, I want to view ride details and available seats so that I can decide whether to book.

**Acceptance Criteria**

- Details show area, departure time, estimated arrival time, free seats, and driver name.
- The driver's phone number is not shown before booking confirmation (see US-18).

---

## 7. Epic: Booking

### US-10 — Request a Seat (5 pts)

As a **passenger**, I want to request a seat so that I can travel with a driver.

**Acceptance Criteria**

- Given a ride with free seats greater than zero, when I request a seat, then a booking is created as "Pending".
- Given I already have an active booking on this ride, then a duplicate is blocked.
- The driver is notified of the new request.

### US-11 — Prevent Seats Below Zero (3 pts) — BR-1

As the **system**, I want free seats never to drop below zero so that rides are never overbooked.

**Acceptance Criteria**

- Given zero free seats, when a passenger requests a seat, then the request is blocked with a message.
- Given two simultaneous confirmations for the last seat, then only one succeeds.

### US-12 — Block Drivers from Booking Their Own Ride (2 pts) — BR-2

As the **system**, I want to block drivers from booking their own rides so that bookings stay valid.

**Acceptance Criteria**

- Given I am the driver of a ride, when I try to book it, then the action is blocked with a message.
- The "Book" button is hidden or disabled on my own rides.

### US-13 — Confirm a Booking (3 pts)

As a **driver**, I want to confirm a booking request so that the passenger can reserve a seat.

**Acceptance Criteria**

- Given a "Pending" booking and at least one free seat, when I confirm, then its status becomes "Confirmed" and free seats decrease by 1.
- Given zero free seats, then confirmation is blocked.

### US-14 — Reject a Booking (2 pts)

As a **driver**, I want to reject a booking request so that I can manage my passengers.

**Acceptance Criteria**

- Given a "Pending" booking, when I reject, then its status becomes "Rejected" and free seats do not change.

### US-15 — Cancel My Booking (3 pts)

As a **passenger**, I want to cancel my booking so that the seat becomes available again.

**Acceptance Criteria**

- Given a Pending or Confirmed booking, when I cancel, then its status becomes "Cancelled".
- Given the booking was Confirmed, then free seats increase by 1 and the driver is notified (see US-17).

---

## 8. Epic: Notifications & Safety

### US-16 — Notify on Confirmation or Rejection (3 pts)

As a **passenger**, I want to be notified when my booking is confirmed or rejected so that I know my travel plan.

**Acceptance Criteria**

- Given the driver confirms or rejects, then I receive an in-app notification within seconds.
- The notification names the ride and the outcome.

### US-17 — Notify on Cancellations (3 pts)

As a **user**, I want to be notified when a ride or booking is cancelled so that I can adjust my plans.

**Acceptance Criteria**

- Given a driver cancels a ride, then every passenger with a booking on that ride is notified.
- Given a passenger cancels a booking, then the driver is notified.

### US-18 — Show Phone Numbers Only After Confirmation (3 pts) — BR-3

As a **confirmed driver or passenger**, I want to see the other party's phone number only after the booking is confirmed so that we can coordinate pickup while privacy is protected.

**Acceptance Criteria**

- Given a booking is Pending, Rejected, or Cancelled, then both parties' phone numbers are hidden from each other everywhere (UI and API).
- Given a booking is Confirmed, then the driver can see the confirmed passenger's phone number and the passenger can see the driver's phone number.
- Phone numbers must not be exposed through search results or ride details before confirmation.

---

## 9. Epic: Admin

### US-19 — Remove Inappropriate Rides (3 pts)

As an **admin**, I want to view and remove inappropriate rides so that the platform stays safe.

**Acceptance Criteria**

- Given I am an admin, then I can list all rides and remove one with a reason.
- Given a ride is removed, then it disappears from search and its passengers are notified.
- Non-admin users cannot access this function.

---

## 10. Stretch Stories (Outside MVP)

### US-20 — Rate a Ride (5 pts)

As a **passenger**, I want to rate a completed ride so that I can share my experience.

**Acceptance Criteria**

- Given a completed ride I took, I can give a rating from 1 to 5 stars once.

### US-21 — Recurring Weekly Rides (8 pts)

As a **driver**, I want to create recurring weekly rides so that I do not repost the same ride.

**Acceptance Criteria**

- Given a weekly schedule, rides are generated automatically and can be edited individually.

### US-22 — Preference Filters (5 pts)

As a **passenger**, I want to filter rides by preferences such as same-gender rides so that I find a suitable ride.

**Acceptance Criteria**

- Given a preference filter, only matching rides are shown.

---

## 11. Definition of Done

- Acceptance criteria are met and demonstrated.
- Code is reviewed and merged.
- Stories are tested (manually or automatically) with no open critical bugs.
- Business Rules BR-1 to BR-3 are not violated.
