# Forecast – Commuter Carpool Board

**Team Name:** RideMates  
**Members:** Malak Mohamed | Mai Ashraf | Gana Ahmed | Menna Allah Mostafa | Maram Moustafa  
**Week:** 4 Deliverable

## 1. Forecast Inputs

- Total MVP scope: 57 Story Points
- Stretch scope: 18 Story Points
- Sprint length: 2 weeks
- Planned velocity: 19 Story Points per Sprint
- Conservative velocity: 15 Story Points per Sprint

The estimates are based on the team's current planning assumptions and the story points in `estimation.md`.

The team has no completed sprints yet, so both planned and conservative velocities are initial planning assumptions, not measured team performance. They will be reviewed after Sprint 1.

## 2. Forecast Calculation

**Planned Scenario:**

57 Story Points / 19 points per Sprint = 3 Sprints

3 Sprints × 2 weeks = 6 weeks

**Conservative Scenario:**

57 Story Points / 15 points per Sprint = 3.8 Sprints

We round up to 4 Sprints.

4 Sprints × 2 weeks = 8 weeks

| Scenario | Velocity | Estimated Sprints | Estimated Duration |
|---|---:|---:|---:|
| Planned | 19 points | 3 | 6 weeks |
| Conservative | 15 points | 4 | 8 weeks |

## 3. Proposed MVP Sprint Plan

| Sprint | Stories | Total Points |
|---|---|---:|
| Sprint 1 | US-01, US-02, US-03, SP-01, US-06, US-07 | 18 |
| Sprint 2 | US-09, US-10, US-11, US-12, US-13, US-14, US-16 | 20 |
| Sprint 3 | US-04, US-05, US-08, US-15, US-17, US-18, US-19 | 19 |
| **Total** | **MVP Scope** | **57** |

### Sprint 1 – Basic Setup and Ride Search

Focus: Account setup, offering rides, and basic ride search.

The team will work on registration/login, creating rides, viewing offered rides, and searching by area and estimated arrival time. The Match Riders spike will help investigate the matching approach.

### Sprint 2 – Booking and Booking Rules

Focus: Booking functionality and business rules.

The team will implement ride details, seat requests, seat availability validation, preventing drivers from booking their own rides, booking confirmation/rejection, and confirmation/rejection notifications.

Sprint 2 contains 20 points, which is slightly above the planned velocity of 19 points. The team will review capacity during sprint planning and may move US-14 to a later sprint if necessary, updating the remaining sprint plan accordingly.

### Sprint 3 – Cancellations, Privacy, Admin, and Combined Search

Focus: Completing the remaining MVP features.

The team will implement viewing who booked seats, cancelling rides and bookings, combining area and arrival-time search, cancellation notifications, phone-number privacy rules, and admin ride moderation.

The team will also verify that the business rules are respected across the main user flows.

## 4. Stretch Scope

The following stories are not included in the MVP forecast:

| Story ID | Feature | Story Points |
|---|---|---:|
| US-20 | Rate a Ride | 5 |
| US-21 | Recurring Weekly Rides | 8 |
| US-22 | Preference Filters | 5 |
| **Total** | **Stretch Scope** | **18** |

These features may be considered after the MVP is completed, depending on the team's remaining capacity.

US-21 should be split into smaller stories before scheduling it.

## 5. Risks and Assumptions

- The planned and conservative velocities are assumptions because the team has not completed a sprint yet.
- Sprint 2 is one point above the planned velocity, so the team may need to adjust its scope based on actual capacity.
- If a story is moved between sprints, the team will review dependencies and rebalance the remaining backlog instead of simply adding extra points to another sprint.
- Booking and seat availability rules require careful testing, especially when multiple passengers request the last available seat.
- Notifications and phone-number privacy are important requirements and should be tested carefully.
- Team availability and workload may affect the actual delivery time.
- The forecast will be updated after Sprint 1 using the team's actual velocity.

## 6. Conclusion

Based on the current estimates, the MVP is expected to take:

- **Planned scenario:** 3 Sprints (6 weeks).
- **Conservative scenario:** 4 Sprints (8 weeks).

The forecast is an initial plan and may change as the team completes sprints and learns its actual delivery capacity.
