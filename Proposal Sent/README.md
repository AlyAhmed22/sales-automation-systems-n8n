## Proposal Sent Workflow

This workflow automates the process of marking a proposal as sent after confirmation from the salesperson, while keeping the CRM accurate and the system resilient to human input errors.

### Workflow Overview

The workflow is triggered manually by the salesperson via Telegram after sending a proposal to a client.

### Step-by-Step Flow

1. **Telegram Trigger**
   - The salesperson sends a message to the bot confirming that a proposal has been sent.
   - The message typically contains the client’s email.

2. **LLM Parsing (Email Extraction)**
   - An LLM chain analyzes the Telegram message.
   - The client email is extracted from free-text input.

3. **CRM Lookup**
   - The workflow queries the CRM to retrieve the client record using the extracted email.
   - Client data is fetched to verify existence and retrieve identifiers.

4. **Validation (IF Condition)**
   - The workflow checks whether a valid `client_id` exists.

5. **CRM Update (Success Path)**
   - If the client exists:
     - The CRM deal/contact status is updated to **“Proposal Sent”**
     - The sales pipeline remains synchronized with real actions.

6. **Sales Notification (Failure Path)**
   - If the client does not exist:
     - A Telegram message is sent back to the salesperson
     - The message requests correcting or re-sending the client email

This ensures that CRM data reflects real sales activity while keeping the salesperson in the loop.

---

## Proposal Sent & Error Handling

To prevent workflow interruptions caused by invalid or mistyped client emails, the CRM **Get Client** node is intentionally configured to always return data instead of throwing a hard error.

### Why This Matters

- Human input (Telegram messages) is inherently error-prone
- Stopping the workflow on missing data would reduce reliability
- Sales automation should fail **gracefully**, not technically

### Implementation Strategy

- The CRM GET node is allowed to return empty or partial results
- No execution-level error is thrown if the email is invalid
- Business logic handles validation instead of system errors

### Logic Flow

- **If `client_id` exists**
  - Update CRM status to **Proposal Sent**
- **If `client_id` does NOT exist**
  - Send a Telegram message to the salesperson requesting email correction

### Result

This approach transforms technical failures into business decisions, ensuring:
- High workflow stability
- Better human–automation collaboration
- Zero workflow crashes due to simple input mistakes

