## Contract Creation & Sending Automation

### Overview
This workflow automates the creation, preparation, and delivery of client contracts after a proposal reaches the accepted stage.  
It ensures that contracts are generated only for qualified leads, uses AI to structure contract data, and keeps humans in control before final sending.

The workflow is designed with strong validation, error handling, and human-in-the-loop checkpoints to prevent costly sales mistakes.

---

### Business Goals
- Prevent contract creation for unqualified leads  
- Eliminate manual contract drafting  
- Ensure CRM data accuracy  
- Maintain legal document consistency  
- Keep full sales control before sending contracts  

---

### Workflow Trigger

#### Sales Form Submission
The workflow starts when a salesperson submits a contract request form.  
The form typically includes:
- Client email or identifier  
- Contract-related details  
- Project and pricing information  

---

### Workflow Steps

#### 1. CRM Lookup with Error Handling
The workflow retrieves client data from the CRM:
- The CRM GET node is configured **not to fail**, even if the email is incorrect  
- This prevents workflow interruption due to human input errors  

---

#### 2. Client Validation (IF Node)
An IF condition checks:
- Whether a valid `client_id` exists  

**Logic:**
- If `client_id` exists → Continue workflow  
- If `client_id` does NOT exist →  
  - Notify the salesperson via Telegram  
  - Ask them to enter correct client information  

This transforms technical errors into business validation logic.

---

#### 3. Sales Stage Qualification (Second IF Node)
This step ensures contracts are created only for eligible clients:
- Confirms the client status is **Proposal Sent** or **Proposal Accepted**  

**Logic:**
- If status is valid → Continue  
- If status is invalid →  
  - Notify the salesperson that the selected client is not eligible for a contract  
  - Prevents contracts being created for proposal-stage leads  

---

#### 4. CRM Status Update
Once validation passes:
- The CRM record is updated to reflect contract initiation  
- Ensures full pipeline visibility and accurate reporting  

---

#### 5. AI Contract Data Generation (LLM Chain)
An LLM Chain generates a **structured JSON object** used to populate the contract.

**Key characteristics:**
- Outputs JSON only (no text, no markdown)  
- Strict schema enforcement  
- Missing values default safely  

**Generated data includes:**
- Project name  
- Client legal details  
- Contract dates  
- Service descriptions  
- Pricing items and totals  
- Payment terms  
- Signature information  

This JSON is later injected directly into the contract template.

---

#### 6. Contract Document Preparation
The workflow automates document handling:
- Copies the contract template file from Drive  
- Replaces placeholders `[ ]` with AI-generated data  
- Preserves formatting and legal structure  
- Downloads the finalized contract if needed  

---

#### 7. Draft Email Creation (Human-in-the-Loop)
A contract email draft is created:
- Final contract attached  
- Saved as a draft (not auto-sent)  

This ensures:
- Manual review  
- Legal and commercial verification  
- Full sales control before sending  

---

#### 8. CRM Final Update
After contract preparation:
- CRM status is updated  
- Contract activity is logged  
- Ensures pipeline accuracy  

---

#### 9. Sales Notification
A final notification is sent to the salesperson:
- Contract is ready  
- Email draft created  
- Awaiting review and manual sending  

Notifications are typically delivered via Telegram or internal messaging tools.

---

### Human-in-the-Loop Design
This workflow intentionally includes manual checkpoints:
- Contract emails are never auto-sent  
- Sales reviews contract content before delivery  
- Prevents legal, pricing, or client mismatch errors  

---

### Tools & Technologies Used
- n8n (Workflow Automation)  
- CRM Integration  
- LLM / AI JSON Generation  
- Google Drive & Document Templates  
- Email Draft APIs (e.g., Gmail)  
- Telegram Notifications  

---

### Use Cases
Ideal for:
- B2B sales teams  
- Agencies handling service contracts  
- Freelancers and consultants  
- Sales pipelines requiring strict qualification rules  

This workflow is a core component of a **full Sales Automation System** that includes:
lead generation, follow-ups, proposals, contracts, and onboarding.
