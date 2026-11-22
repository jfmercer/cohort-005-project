# Cadence

An online course platform where Learners buy courses from Instructors, and the platform's staff look after money and accounts.

## Language

### Refunds

**Refund Request**:
A Learner's ask to have their money back for a course they bought, with their reason in their own words.
_Avoid_: Chargeback, Reversal, cancellation, cancel my purchase

**Refund**:
The money that goes back to the Learner when a Refund Request is approved. A declined Refund Request produces no Refund.
_Avoid_: Chargeback, Reversal

**Refund Amount**:
What the Learner actually paid for the purchase. A Refund is always the full Refund Amount; there are no partial Refunds.
_Avoid_: list price, refundable amount

**Pending**:
The state of a Refund Request that has not yet been approved or declined.
_Avoid_: Requested, open, waiting

**Approved**:
The state of a Refund Request an Admin has accepted. It produces a Refund and ends the Learner's access to the course.

**Declined**:
The state of a Refund Request an Admin has turned down. No money moves.
_Avoid_: Rejected, denied

A Refund Request is always exactly one of Pending, Approved, or Declined. A Learner cannot withdraw one.

**Refund Window**:
The 14 calendar days after a purchase during which a Learner may make a Refund Request. It includes the whole of the fourteenth day.
_Avoid_: cancel window, cancellation period

**Refund Eligibility**:
Whether a Learner may make a Refund Request at all. It requires being inside the Refund Window, staying under the watch-time and completion limits, and not holding a claimed team seat.

**Chargeback**:
A dispute the cardholder raises through their bank, which forces the money back. This is not a Refund Request, and the platform does not model it today.

### People

**Learner**:
A person who buys or is enrolled in a course.

**Admin**:
Platform staff. Admins review Refund Requests. Instructors never review Refund Requests for their own courses.
