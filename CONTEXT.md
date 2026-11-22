# Domain glossary

Use these terms in code, UI copy, emails, and error messages. If a word is in the **Avoid** column, don't use it for that concept.

## Refunds

| Term | Definition | Avoid | Code |
| --- | --- | --- | --- |
| **Refund** | A learner asks for, and may get back, the amount paid for a purchase. | Chargeback, Reversal, Cancellation, "cancel my purchase" | `refunds` table, `RefundStatus`, `/courses/:slug/refund` |
| **Refund request** | A refund that is open, with status **Requested**. Users see "Refund requested". One purchase can have at most one open refund request. | Pending, pending chargeback, "raised", "waiting on us" | `RefundStatus.Requested` |
| **Approved** | End state: the refund is granted and the refund amount is returned to the card the learner paid with. | "done" | `RefundStatus.Approved`, `amountRefunded`, `resolvedAt` |
| **Declined** | End state: the refund is not granted. Nothing is returned. | "rejected", "done" | `RefundStatus.Declined`, `resolvedAt` |
| **Resolve** | An **Admin** moves a refund request to Approved or Declined. Today nothing in the app does this; it happens outside the app. Copy says "our team". | "someone" | `resolvedByUserId`, `UserRole.Admin` |
| **Refund amount** | Always the **amount paid** for the purchase, never the list price. | — | `purchases.amountPaid` |
| **Refund window** | The purchase day plus 14 calendar days, counted in whole days. A purchase made at 23:00 still gets its full 14th day. | cancel window | `REFUND_WINDOW_DAYS` |
| **Refund eligibility** | A purchase can be refunded only when all of these are true: it is inside the refund window, the learner has watched under 2 hours, under 50% of lessons are completed, it is not a claimed team seat, and it has no open refund request. The server checks all of them, not just the UI. | — | — |
| **Chargeback** | A dispute the cardholder files through their bank or card issuer. The app does not model chargebacks. **Never use this word for a refund.** | — | — |

## Neighbouring terms

| Term | Definition | Avoid | Code |
| --- | --- | --- | --- |
| **Learner** | The person who bought or is taking a course. Use this word in copy. | "user" (in copy), "customer" | `users` with `UserRole.Student` |
| **Purchase** | A learner buying a course once. The thing a refund applies to. | order | `purchases` |
| **Amount paid** | What the learner was actually charged for a purchase. | — | `purchases.amountPaid` |
| **List price** | The course's standard price before any discount. | — | `courses.price` |
| **PPP price** | A purchasing-power-parity discounted price, based on the learner's country. | — | `getDiscountForCountry` |
| **Team seat** | A course licence bought by a team and handed out as a coupon. | — | `coupons.purchaseId` |
| **Claimed seat** | A team seat whose coupon has been redeemed. It belongs to the team, so the learner can't refund it. | — | `coupons.redeemedAt` |
