## Proposal Sent & Error Handling 

To prevent workflow interruptions caused by invalid or mistyped client emails, the CRM "Get Client" node is configured to always return data instead of throwing an error.

### Why this matters
- Human input (Telegram messages) is inherently error-prone
- Stopping the workflow on missing data would reduce reliability
- Sales automation should fail gracefully, not technically

### Implementation
- The CRM GET node is allowed to return empty or partial data
- An IF condition checks whether a valid `client_id` exists

### Logic Flow
- If `client_id` exists → Update CRM status to **Proposal Sent**
- If `client_id` does NOT exist → Notify salesperson via Telegram to correct the email

This approach transforms technical errors into business logic decisions, ensuring high workflow stability and better human–automation collaboration.
