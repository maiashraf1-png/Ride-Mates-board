# Ride-Mates-Board — User Stories

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

AC1 – View Booked Passengers
- Given a driver has offered a ride with one or more bookings.
- When the driver opens the ride details.
- Then the system displays all passengers who have booked seats on that ride, including each passenger's name and booking status.
  
AC2 – Display Pending Booking Status
- Given a passenger has booked a seat and the booking has not yet been confirmed.
- When the driver views the passenger list.
- Then the system displays the booking status as "Pending".
  
AC3 – Display Confirmed Booking Status
- Given a passenger's booking has been confirmed.
- When the driver views the passenger list.
- Then the system displays the booking status as "Confirmed".
  
AC4 – No Bookings
- Given a driver has offered a ride with no bookings.
- When the driver opens the ride details.
- Then the system displays an empty-state message indicating that no passengers have booked the ride yet.

### US-05 — Cancel a Ride (3 pts)

As a **driver**, I want to cancel my ride so that passengers know the trip will not happen.

**Acceptance Criteria**

AC1 – Successfully Cancel a Ride
- Given a driver is logged in and has an active ride.
- When the driver selects "Cancel Ride" and confirms the cancellation.
- Then the system changes the ride status to "Cancelled" and removes the ride from the search results.
  
AC2 – Notify Booked Passengers
- Given an active ride has one or more confirmed or pending bookings.
- When the driver successfully cancels the ride.
- Then the system sends a cancellation notification to all booked passengers (see US-17).
  
AC3 – Prevent Booking on Cancelled Ride
- Given a ride has been cancelled.
- When a passenger attempts to book a seat on that ride.
- Then the system prevents the booking and displays a message indicating that the ride is no longer available.
  
AC4 – Confirm Cancellation
- Given a driver selects "Cancel Ride".
- When the cancellation confirmation prompt is displayed.
- Then the system allows the driver to confirm or go back without cancelling the ride.

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

AC1 – Time-Boxed Research
- Given the team needs to investigate ride-matching approaches.
- When the team starts the research.
- Then the investigation must be completed within one working day.
  
AC2 – Area Selection Decision
- Given the team is comparing different area-selection approaches.
- When the team evaluates a predefined area list and free-text input.
- Then the team documents the advantages and disadvantages of both approaches and selects one.
  
AC3 – Arrival-Time Range Decision
- Given the team needs to define arrival-time matching logic.
- When the team investigates possible arrival-time ranges.
- Then the team documents the selected matching range and its justification.
  
AC4 – Research Documentation
- Given the research is completed.
- When the team reviews the findings.
- Then a short written decision is provided covering the selected area approach and arrival-time matching logic

### US-06 — Search Rides by Area (3 pts)

As a **passenger**, I want to search rides by area so that I can find a convenient pickup location.

**Acceptance Criteria**

AC1 – Search Rides by Area
- Given one or more rides are available in the selected area.
- When a passenger searches for that area.
- Then the system displays only rides that match the selected area.
  
AC2 – No Matching Rides
- Given no available rides exist in the selected area.
- When a passenger searches for that area.
- Then the system displays a "No rides found" message.
  
AC3 – Display Available Rides Only
- Given rides exist in the selected area with different statuses.
- When a passenger searches for that area.
- Then the system displays only active rides that are available for booking.
  
AC4 – Empty Search Input
- Given a passenger is on the ride search page.
- When the passenger submits the search without selecting an area.
- Then the system displays a validation message asking the passenger to select an area.
  
### US-07 — Search Rides by Arrival Time (3 pts)

As a **passenger**, I want to find rides arriving before a chosen time (e.g., 9:00) so that I reach my first lecture on time.

**Acceptance Criteria**

AC1 – Search by Arrival Time
- Given a passenger is on the ride search page.
- When the passenger selects an arrival time of 09:00 using the "Arrive Before" option.
- Then the system displays only rides with an estimated arrival time at or before 09:00.
  
AC2 – Sort Search Results
- Given multiple rides match the selected arrival time.
- When the search results are displayed.
- Then the system sorts the rides by estimated arrival time in ascending order (earliest arrival first).
  
AC3 – No Matching Rides
- Given no rides have an estimated arrival time at or before the selected time.
- When the passenger searches using the "Arrive Before" option.
- Then the system displays a "No rides found" message.
  
AC4 – Exclude Cancelled Rides
- Given some rides matching the selected arrival time have been cancelled.
- When the passenger performs the search.
- Then the system excludes all cancelled rides from the search results.

### US-08 — Combine Area and Time Search (2 pts)

As a **passenger**, I want to search by area and arrival time together so that I see only the most relevant rides.

**Acceptance Criteria**

AC1 – Search Using Both Filters
- Given a passenger selects a departure area and an arrival time.
- When the passenger submits the search.
- Then the system displays only rides that match both the selected area and the arrival-time condition.
  
AC2 – Search Using Area Filter Only
- Given a passenger selects a departure area without specifying an arrival time.
- When the passenger submits the search.
- Then the system displays all available rides matching the selected area.
  
AC3 – Search Using Arrival-Time Filter Only
- Given a passenger specifies an arrival time without selecting a departure area.
- When the passenger submits the search.
- Then the system displays all available rides matching the arrival-time condition.
  
AC4 – No Matching Rides
- Given no rides match the selected search criteria.
- When the passenger submits the search.
- Then the system displays a "No rides found" message.

### US-09 — View Ride Details (2 pts)

As a **passenger**, I want to view ride details and available seats so that I can decide whether to book.

**Acceptance Criteria**

AC1 – Display Ride Details
- Given a passenger selects an available ride from the search results.
- When the passenger opens the ride details page.
- Then the system displays the departure area, departure time, estimated arrival time, number of available seats, and driver's name.
  
AC2 – Hide Driver's Phone Number Before Confirmation
- Given a passenger opens the details of a ride without a confirmed booking.
- When the ride details are displayed.
- Then the system does not show the driver's phone number.
  
AC3 – Display Driver's Phone Number After Booking Confirmation
- Given a passenger has a confirmed booking for a ride.
- When the passenger views the ride details.
- Then the system displays the driver's phone number (see US-18).
  
AC4 – Updated Available Seats
- Given the number of available seats on a ride has changed.
- When a passenger opens or refreshes the ride details page.
- Then the system displays the current number of available seats.

---

## 7. Epic: Booking

### US-10 — Request a Seat (5 pts)

As a **passenger**, I want to request a seat so that I can travel with a driver.

**Acceptance Criteria**

AC1 – Successful Seat Request
- Given a passenger is logged in and selects a ride with one or more available seats.
- When the passenger requests a seat.
- Then the system creates a new booking with the status "Pending".
  
AC2 – Prevent Duplicate Booking
- Given a passenger already has an active booking on the selected ride.
- When the passenger attempts to request another seat on the same ride.
- Then the system prevents the duplicate booking and displays an appropriate error message.
  
AC3 – Notify Driver of New Booking
- Given a passenger successfully requests a seat.
- When the booking is created.
- Then the system sends a notification to the driver informing them of the new booking request.
  
AC4 – No Available Seats
- Given a ride has zero available seats.
- When a passenger attempts to request a seat.
- Then the system rejects the booking request and displays a message indicating that no seats are available.
  
AC5 – Booking on Cancelled Ride
- Given a ride has been cancelled.
- When a passenger attempts to request a seat.
- Then the system prevents the booking and displays a message indicating that the ride is no longer available.
  
### US-11 — Prevent Seats Below Zero (3 pts) — BR-1

As the **system**, I want free seats never to drop below zero so that rides are never overbooked.

**Acceptance Criteria**

AC1 – Prevent Booking When No Seats Are Available
- Given a ride has zero free seats.
- When a passenger requests a seat.
- Then the system blocks the booking request and displays a message indicating that no seats are available.
  
AC2 – Prevent Overbooking During Simultaneous Confirmations
- Given a ride has only one free seat and two passengers have pending booking requests.
- When the driver confirms both booking requests at the same time.
- Then the system allows only one booking to be confirmed and rejects the other request because no seats are available.
  
AC3 – Maintain Non-Negative Seat Count
- Given a ride has a specific number of free seats.
- When a booking is confirmed.
- Then the system decreases the free-seat count by one without allowing it to become less than zero.
  
AC4 – Keep Seat Count Unchanged for Pending Bookings
- Given a passenger has requested a seat and the booking status is "Pending".
- When the booking request is created.
- Then the system does not decrease the free-seat count until the driver confirms the booking.
  
### US-12 — Block Drivers from Booking Their Own Ride (2 pts) — BR-2

As the **system**, I want to block drivers from booking their own rides so that bookings stay valid.

**Acceptance Criteria**

- Given I am the driver of a ride, when I try to book it, then the action is blocked with a message.
- The "Book" button is hidden or disabled on my own rides.

### US-13 — Confirm a Booking (3 pts)

As a **driver**, I want to confirm a booking request so that the passenger can reserve a seat.

AC1 – Successfully Confirm a Booking
- Given a driver has a pending booking request for one of their rides.
- When the driver selects "Confirm" for that booking.
- Then the system changes the booking status to "Confirmed".
  
AC2 – Update Available Seats
- Given a ride has one or more available seats and a pending booking.
- When the driver confirms the booking.
- Then the system decreases the number of free seats by one.
  
AC3 – Prevent Confirmation When No Seats Are Available
- Given a ride has zero available seats.
- When the driver attempts to confirm a pending booking.
- Then the system rejects the confirmation and displays a message indicating that no seats are available.
  
AC4 – Prevent Unauthorized Confirmation
- Given a user is not the driver who offered the ride.
- When the user attempts to confirm or reject a booking for that ride.
- Then the system denies the action.
  
AC5 – Notify Passenger
- Given a driver's confirmation is successful.
- When the booking status changes to "Confirmed".
- Then the system sends an in-app notification to the passenger (see US-16)
  
### US-14 — Reject a Booking (2 pts)

As a **driver**, I want to reject a booking request so that I can manage my passengers.

**Acceptance Criteria**

AC1 – Successfully Reject a Booking
- Given a driver is logged in and has a booking request with the status "Pending" for one of their rides.
- When the driver selects "Reject" for that booking.
- Then the system changes the booking status to "Rejected".
  
AC2 – Maintain Free Seats
- Given a booking request has the status "Pending".
- When the driver rejects the booking.
- Then the system keeps the number of free seats unchanged.
  
AC3 – Prevent Rejecting Non-Pending Bookings
- Given a booking has already been confirmed or rejected.
- When the driver attempts to reject it again.
- Then the system prevents the action and displays an appropriate message.
  
AC4 – Notify Passenger
- Given a driver's booking rejection is successful.
- When the booking status changes to "Rejected".
- Then the system notifies the passenger that their booking request has been rejected.
  
### US-15 — Cancel My Booking (3 pts)

As a **passenger**, I want to cancel my booking so that the seat becomes available again.

**Acceptance Criteria**

AC1 – Successfully Cancel a Pending Booking
- Given a passenger is logged in and has a booking with the status "Pending".
- When the passenger cancels the booking.
- Then the system changes the booking status to "Cancelled".
  
AC2 – Successfully Cancel a Confirmed Booking
- Given a passenger is logged in and has a booking with the status "Confirmed".
- When the passenger cancels the booking.
- Then the system changes the booking status to "Cancelled".
  
AC3 – Restore Available Seat
- Given a passenger has a confirmed booking.
- When the passenger cancels the booking.
- Then the system increases the ride's free-seat count by one.
  
AC4 – Notify Driver
- Given a passenger has a confirmed booking.
- When the booking is successfully cancelled.
- Then the system sends a cancellation notification to the driver (see US-17).
  
AC5 – Prevent Cancelling Inactive Bookings
- Given a booking has already been cancelled or rejected.
- When the passenger attempts to cancel it again.
- Then the system prevents the action and displays an appropriate message.
---

## 8. Epic: Notifications & Safety

### US-16 — Notify on Confirmation or Rejection (3 pts)

As a **passenger**, I want to be notified when my booking is confirmed or rejected so that I know my travel plan.

**Acceptance Criteria**

AC1 – Notification on Booking Confirmation
- Given a passenger has a booking with the status "Pending".
- When the driver confirms the booking request.
- Then the system sends an in-app notification to the passenger within a few seconds, informing them that their booking has been confirmed.
  
AC2 – Notification on Booking Rejection
- Given a passenger has a booking with the status "Pending".
- When the driver rejects the booking request.
- Then the system sends an in-app notification to the passenger within a few seconds, informing them that their booking has been rejected.
  
AC3 – Include Ride Information
- Given a passenger receives a booking confirmation or rejection notification.
- When the passenger views the notification.
- Then the notification displays the ride details, including the ride name or departure area, and the booking outcome ("Confirmed" or "Rejected").
  
AC4 – Notification Delivery Time
- Given a booking status has been successfully changed to "Confirmed" or "Rejected".
- When the system generates the notification.
- Then the notification is delivered to the passenger within a few seconds of the status change.
  
### US-17 — Notify on Cancellations (3 pts)

As a **user**, I want to be notified when a ride or booking is cancelled so that I can adjust my plans.

**Acceptance Criteria**

AC1 – Notify Passengers When a Ride Is Cancelled
- Given a driver has an active ride with one or more pending or confirmed bookings.
- When the driver successfully cancels the ride.
- Then the system sends a cancellation notification to every passenger who has a booking on that ride.
  
AC2 – Notify Driver When a Booking Is Cancelled
- Given a passenger has a pending or confirmed booking.
- When the passenger successfully cancels the booking.
- Then the system sends a cancellation notification to the driver of that ride.
  
AC3 – Include Cancellation Details
- Given a user receives a cancellation notification.
- When the user views the notification.
- Then the notification displays the relevant ride information and indicates whether the ride or booking was cancelled.
  
AC4 – Notification Delivery Time
- Given a ride or booking has been successfully cancelled.
- When the system generates the cancellation notification.
- Then the notification is delivered to the relevant user within a few seconds of the cancellation.
  
### US-18 — Show Phone Numbers Only After Confirmation (3 pts) — BR-3

As a **confirmed driver or passenger**, I want to see the other party's phone number only after the booking is confirmed so that we can coordinate pickup while privacy is protected.

**Acceptance Criteria**

AC1 – Hide Phone Numbers for Pending Bookings
- Given a booking has the status "Pending".
- When the driver or passenger views the booking details.
- Then the system hides both parties' phone numbers from each other in the UI and API responses.
  
AC2 – Hide Phone Numbers for Rejected Bookings
- Given a booking has the status "Rejected".
- When the driver or passenger views the booking details.
- Then the system prevents both parties from accessing each other's phone numbers through the UI and API.
  
AC3 – Hide Phone Numbers for Cancelled Bookings
- Given a booking has the status "Cancelled".
- When the driver or passenger views the booking details.
- Then the system prevents both parties from accessing each other's phone numbers through the UI and API.
  
AC4 – Show Phone Numbers After Confirmation
- Given a booking has the status "Confirmed".
- When the driver views the confirmed booking details.
- Then the system displays the passenger's phone number to the driver, and the driver's phone number to the passenger.
  
AC5 – Protect Phone Numbers in Search Results
- Given a passenger searches for available rides or views ride details without a confirmed booking.
- When the system returns search results or ride details through the UI or API.
- Then the system does not expose the driver's phone number.
  
AC6 – Prevent Unauthorized Phone Number Access
- Given a user does not have a confirmed booking for a ride.
- When the user attempts to access the other party's phone number directly through an API request.
- Then the system denies access and does not return the phone number.

---

## 9. Epic: Admin

### US-19 — Remove Inappropriate Rides (3 pts)

As an **admin**, I want to view and remove inappropriate rides so that the platform stays safe.

**Acceptance Criteria**

AC1 – View All Rides
- Given a user is logged in with an admin role.
- When the admin opens the ride management page.
- Then the system displays a list of all rides on the platform, including their details and current status.
  
AC2 – Remove an Inappropriate Ride
- Given an admin is viewing the list of rides.
- When the admin selects a ride, provides a removal reason, and confirms the action.
- Then the system removes the selected ride and records the provided reason.
  
AC3 – Remove Ride from Search Results
- Given an admin has successfully removed a ride.
- When passengers search for available rides.
- Then the system excludes the removed ride from all search results.
  
AC4 – Notify Booked Passengers
- Given a removed ride has one or more pending or confirmed bookings.
- When the admin successfully removes the ride.
- Then the system sends a notification to all passengers who have bookings on that ride.
  
AC5 – Restrict Admin Access
- Given a user is logged in without an admin role.
- When the user attempts to access the ride management page or its related API endpoints.
- Then the system denies access and displays an appropriate authorization error message.

---

## 10. Stretch Stories (Outside MVP)

### US-20 — Rate a Ride (5 pts)

As a **passenger**, I want to rate a completed ride so that I can share my experience.

**Acceptance Criteria**

AC1 – Successfully Rate a Completed Ride
- Given a passenger has a confirmed booking for a completed ride.
- When the passenger submits a rating between 1 and 5 stars.
- Then the system saves the rating successfully.
  
AC2 – Prevent Multiple Ratings
- Given a passenger has already rated a completed ride.
- When the passenger attempts to submit another rating for the same ride.
- Then the system prevents the duplicate rating and displays an appropriate message.
  
AC3 – Rating Range Validation
- Given a passenger is rating a completed ride.
- When the passenger submits a rating below 1 or above 5 stars.
- Then the system rejects the rating and displays a validation message indicating that ratings must be between 1 and 5 stars.
  
AC4 – Prevent Rating Incomplete Rides
- Given a ride has not been completed yet.
- When a passenger attempts to submit a rating.
- Then the system prevents the rating and displays a message indicating that only completed rides can be rated.
  
AC5 – Restrict Rating to Passengers
- Given a user is not a passenger with a confirmed booking for the completed ride.
- When the user attempts to submit a rating.
- Then the system prevents the rating submission.

### US-21 — Recurring Weekly Rides (8 pts)

As a **driver**, I want to create recurring weekly rides so that I do not repost the same ride.

**Acceptance Criteria**

AC1 – Create Recurring Weekly Schedule
- Given a driver is logged in and enters valid ride details with a weekly recurring schedule.
- When the driver submits the recurring ride form.
- Then the system saves the weekly schedule successfully.
  
AC2 – Automatically Generate Weekly Rides
- Given a driver has created a valid weekly recurring schedule.
- When a scheduled recurrence date is reached.
- Then the system automatically generates a ride for that date using the saved ride details.
  
AC3 – Edit Individual Recurring Rides
- Given a driver has a recurring weekly schedule with multiple generated rides.
- When the driver selects and edits one generated ride.
- Then the system updates only that ride without affecting the remaining generated rides or the recurring schedule.
  
AC4 – Validate Recurring Ride Details
- Given a driver is creating a recurring weekly schedule.
- When the driver enters invalid ride details, such as zero free seats or an invalid time.
- Then the system rejects the schedule and displays appropriate validation messages.
  
AC5 – View Generated Recurring Rides
- Given a driver has an active recurring weekly schedule.
- When the driver opens "My Rides".
- Then the system displays all generated rides with their respective dates and details.
  
AC6 – Prevent Duplicate Ride Generation
- Given a recurring schedule already has a generated ride for a specific date and time.
- When the system processes the same recurrence again.
- Then the system prevents creating a duplicate ride.

### US-22 — Preference Filters (5 pts)

As a **passenger**, I want to filter rides by preferences such as same-gender rides so that I find a suitable ride.

**Acceptance Criteria**

AC1 – Filter Rides by Selected Preferences
- Given a passenger is on the ride search page and selects one or more preference filters.
- When the passenger applies the selected filters.
- Then the system displays only rides that match all selected preferences.
  
AC2 – Same-Gender Ride Filter
- Given a passenger selects the same-gender ride preference.
- When the passenger applies the filter.
- Then the system displays only rides that match the selected gender preference.
  
AC3 – Combine Preference Filters with Search Criteria
- Given a passenger selects preference filters along with area or arrival-time filters.
- When the passenger submits the search.
- Then the system displays only rides that satisfy all selected search criteria and preferences.
  
AC4 – No Matching Rides
- Given no available rides match the selected preferences.
- When the passenger applies the preference filters.
- Then the system displays a "No rides found" message.
  
AC5 – Clear Preference Filters
- Given a passenger has applied one or more preference filters.
- When the passenger clears the selected filters.
- Then the system displays all available rides that match the remaining search criteria.

---

## 11. Definition of Done

- Acceptance criteria are met and demonstrated.
- Code is reviewed and merged.
- Stories are tested (manually or automatically) with no open critical bugs.
- Business Rules BR-1 to BR-3 are not violated.
