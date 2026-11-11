# Estimation — Commuter Carpool Board

**Team:** RideMates  
**Members:** Malak Mohamed | Mai Ashraf | Gana Ahmed | Menna Allah Mostafa | Maram Moustafa  
**Week:** 4 Deliverable

## 1. Estimation Method

| Item | Choice |
|---|---|
| Technique | Planning Poker (team consensus) |
| Scale | Fibonacci: 1, 2, 3, 5, 8 |
| Unit | Story Points: relative size combining effort, complexity, and uncertainty (not hours) |
| Size limit | Any item larger than 8 points is split before entering a sprint |

### Process

1. The story and its acceptance criteria are read aloud.
2. Each member privately selects a card.
3. All cards are revealed at the same time.
4. Members with the highest and lowest votes explain their reasoning.
5. The team re-votes until it reaches consensus (usually within two rounds).

## 2. Reference Story

**US-06 — Search Rides by Area = 3 points**

**Why this story was chosen:**

- It is well understood by the whole team: one filter, one results list, and one empty state.
- It has a medium size, so smaller and larger stories can be compared to it easily.
- It involves no external dependencies or security concerns.

Every other story was compared to it with one question: *"Is this smaller than, similar to, or bigger than Search by Area?"*

| Compared to US-06 | Points |
|---|---:|
| Much smaller, mostly a simple view or status change | 2 |
| Similar size | 3 |
| Clearly bigger, with several parts or a central workflow | 5 |
| Very large, with scheduling or complex logic | 8 |

## 3. Estimates and Rationale

| ID | Story | Pts | Rationale |
|---|---|---:|---|
| US-01 | Register and log in | 5 | Authentication, validation, and account access across several screens, with security concerns. |
| US-02 | Offer a ride | 3 | One form with validation for area, departure time, estimated arrival time, and free seats. |
| US-03 | View my offered rides | 2 | Simple list with an empty state and basic ride information. |
| US-04 | See who booked my seats | 2 | Simple list of passengers and booking statuses. |
| US-05 | Cancel a ride | 3 | Ride status change and removal from search; cancellation notifications are handled in US-17. |
| SP-01 | Spike: matching approach | 2 | Time-boxed to one working day; produces a written decision, not a feature. |
| US-06 | Search rides by area | 3 | **Reference story.** One area filter, results list, and empty state. |
| US-07 | Search rides by arrival time | 3 | Filters using estimated arrival time and sorts matching rides. |
| US-08 | Combine area and time search | 2 | Reuses the area and arrival-time filters from US-06 and US-07. |
| US-09 | View ride details | 2 | Read-only screen showing ride information and available seats. |
| US-10 | Request a seat | 5 | Creates a booking, blocks duplicates, and notifies the driver; a central booking workflow. |
| US-11 | Prevent seats below zero | 3 | Enforces BR-1, including the simultaneous-confirmation edge case. |
| US-12 | Block drivers from booking their own rides | 2 | Enforces BR-2 with a simple ownership check in the UI and backend. |
| US-13 | Confirm a booking | 3 | Changes booking status and decreases free seats while enforcing BR-1. |
| US-14 | Reject a booking | 2 | Changes booking status; available seats remain unchanged. |
| US-15 | Cancel my booking | 3 | Changes booking status and restores a seat when the booking was confirmed. |
| US-16 | Notify on confirmation or rejection | 3 | Sends an in-app notification to the passenger after the driver's decision. |
| US-17 | Notify on cancellations | 3 | Sends cancellation notifications to the affected passengers or driver. |
| US-18 | Show phone numbers only after confirmation | 3 | Enforces BR-3 for both parties across the UI and API. |
| US-19 | Remove inappropriate rides | 3 | Requires an admin role check, ride removal with a reason, and passenger notification. |
| US-20 | Rate a ride | 5 | Requires a rating feature and a one-rating-per-completed-ride constraint. |
| US-21 | Recurring weekly rides | 8 | Requires scheduling logic and handling repeated rides; the largest and most uncertain item. |
| US-22 | Preference filters | 5 | Requires preference data and additional filtering logic. |

## 4. Points by Epic

| Epic | Items | Points |
|---|---:|---:|
| Account | 1 | 5 |
| Offer a Ride | 4 | 10 |
| Match Riders | 5 (including SP-01) | 12 |
| Booking | 6 | 18 |
| Notifications & Safety | 3 | 9 |
| Admin | 1 | 3 |
| **MVP total** | **20 (19 stories + 1 spike)** | **57** |
| Stretch | 3 | 18 |
| **All scope** | **23** | **75** |

## 5. Assumptions and Risks

- Estimates assume the team has basic experience with the chosen technology stack.
- Notifications are in-app only (no email or SMS) in the MVP.
- US-10 covers notifying the driver about a new booking request. US-16 covers confirmation or rejection notifications, while US-17 covers cancellation notifications.
- Ride search by arrival time depends on the estimated arrival time entered by the driver when offering a ride.
- Business Rules BR-1, BR-2, and BR-3 have dedicated stories to ensure they receive proper implementation and testing.
- US-21 (8 points) is the least certain item and will be split before it is scheduled.
- Estimates will be revisited after Sprint 1 using the team's actual velocity.

## 6. Conclusion

The MVP scope is estimated at **57 Story Points**, including 19 user stories and one research spike. The three Stretch stories are estimated separately at **18 Story Points**.

The team will use its actual sprint velocity to improve future estimates and planning.
