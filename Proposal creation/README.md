
## Proposal Creation & Sending Automation

### Overview
This workflow automates the creation, preparation, and delivery of sales proposals once a lead reaches the proposal stage.  
It combines CRM data, AI-generated content, document templates, and a human-in-the-loop approval process to ensure high-quality proposals with minimal manual effort.

### Business Goals
- Save time in proposal creation  
- Maintain proposal consistency and quality  
- Reduce manual document handling  
- Keep CRM data always up to date  
- Ensure full sales team control before sending proposals  

---

### Workflow Trigger

#### Form Submission Trigger
The workflow starts when a proposal request form is submitted.  
The form typically includes:
- Lead identifier  
- Project requirements  
- Proposal context or internal notes  

---

### Workflow Steps

#### 1. CRM Lookup (Get Lead Data)
The workflow retrieves the lead record from the CRM to:
- Confirm the lead exists  
- Fetch client name, email, and deal details  
- Ensure the proposal is linked to the correct CRM record  

---

#### 2. Validation (IF Node)
A validation check is performed to confirm:
- Required data is present  
- The lead is eligible for proposal creation  

If validation fails:
- The workflow stops  
- A notification is sent to the sales team for manual review  

---

#### 3. Stage Routing (Switch Node)
Based on CRM status and form input:
- Routes the workflow to the correct proposal path  
- Ensures proposals are created only at the correct sales stage  

---

#### 4. AI Proposal Content Generation
Using an LLM chain:
- Proposal content is generated or refined  
- Tone and structure are aligned with sales standards  
- Content is customized based on client data and requirements  

This step significantly accelerates proposal writing while maintaining quality.

---

#### 5. Document Preparation
The workflow automates proposal document handling:
- Copies a proposal template file  
- Updates the document with AI-generated content  
- Preserves formatting and structure  
- Downloads the finalized proposal file if needed  

---

#### 6. Draft Email Creation (Human-in-the-Loop)
A proposal email draft is created:
- Proposal document attached  
- Personalized message for the client  
- Saved as a draft (not sent automatically)  

This ensures manual review and approval before sending.

---

#### 7. CRM Update
The CRM record is updated to:
- Mark the proposal as created  
- Store proposal status  
- Track proposal activity for reporting and analytics  

---

#### 8. Sales Notification
A notification is sent to the salesperson:
- Proposal is ready  
- Email draft has been created  
- Awaiting manual review and sending  

Notifications can be delivered via email, chat, or internal messaging tools.

---

### Human-in-the-Loop Design
This workflow intentionally includes manual checkpoints:
- Proposal emails are created as drafts  
- Sales team reviews and approves before sending  
- Ensures quality control and strong client relationships  

---

### Tools & Technologies Used
- n8n (Workflow Automation)  
- CRM Integration  
- LLM / AI Content Generation  
- Google Docs or similar document tools  
- Gmail or Email Draft APIs  
- Notification services  

---

### Use Cases
Ideal for:
- B2B sales teams  
- Agencies sending customized proposals  
- Freelancers and consultants  
- Automated yet controlled sales pipelines  

This workflow is part of a **full Sales Automation System** covering:
lead generation, follow-up, proposal handling, contracts, and onboarding.

