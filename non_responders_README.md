# Non-responders with valid emails

`non_responders_valid_email.csv` — leads from three completed Sendkit campaigns
that received the full email sequence but **never replied**, and whose email is
valid (delivered, non-bounced, well-formed).

## Columns
`email, first_name, last_name, company_name, source_campaign`

## Source campaigns (completed/sent versions)
| Source campaign | Campaign ID | Non-responders |
|---|---|---|
| Sendkit Duplicate - EB | `69b8053798a4a5530c704157` | 617 |
| SL users list - | `69c19143394b226b571f7923` | 1,207 |
| inboxkit leadlist - discolike agencies | `69c4e37020f11141c75797a6` | 1,681 |
| **Total** | | **3,505** |

## Methodology
For each completed campaign, every lead resolves to exactly one outcome:
`replied`, `bounced` (undeliverable), `unsubscribed`, or `completed` (finished the
sequence — delivered fine, never replied). We exported leads with
`status = completed`, which are precisely the **non-responders with a valid,
deliverable email**. Repliers, bounces (invalid emails), unsubscribes, and
never-contacted leads were excluded. One record with a stray leading-colon email
artifact was normalized; one `completed` record flagged as replied was dropped.
