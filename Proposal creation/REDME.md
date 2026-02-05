Workflow: Proposal Creation & Sending Automation
Overview
This workflow automates the creation, preparation, and delivery of sales proposals after a lead reaches the proposal stage. It combines CRM data, AI-generated content, document templates, and human-in-the-loop approval to ensure high-quality proposals with minimal manual effort.

Business Goal
Save time in proposal creation
Maintain proposal consistency and quality
Reduce manual document handling
Keep CRM always up to date
Ensure sales team control before sending proposals
Workflow Trigger
Form Submission Trigger
The workflow starts when a proposal request form is submitted. This form typically includes:

Lead identifier
Project requirements
Proposal context or notes
Workflow Steps
1. CRM Lookup (Get Lead Data)
The workflow retrieves the lead record from the CRM:

Confirms the lead exists
Fetches client name, email, and deal details
Ensures proposal is linked to the correct CRM record
2. Validation (IF Node)
A validation check is performed to confirm:

Required data is present
The lead is eligible for proposal creation
If validation fails:

The workflow stops
A notification is sent to the sales team for manual review
3. Stage Routing (Switch)
Based on the CRM status and form input:

Routes the workflow to the correct proposal path
Ensures proposals are created only at the correct sales stage
4. AI Proposal Content Generation
Using an LLM Chain:

Proposal content is generated or refined
Tone and structure are aligned with sales standards
Customization is based on client data and requirements
This step accelerates proposal writing while maintaining quality.

5. Document Preparation
The workflow handles proposal documents automatically:

Copies a proposal template file
Updates the document with generated content
Preserves formatting and structure
Downloads the finalized proposal file if needed
6. Draft Email Creation
A proposal email draft is created:

Attached proposal document
Personalized message for the client
Saved as a draft (not sent automatically)
This ensures human-in-the-loop approval before sending.

7. CRM Update
The CRM record is updated to:

Mark proposal as created
Store proposal status
Track proposal activity for reporting
8. Sales Notification
A notification is sent to the salesperson:

Proposal is ready
Email draft created
Awaiting manual review and sending
Notifications can be sent via email, chat, or internal messaging tools.

Human-in-the-Loop Design
This workflow intentionally includes manual checkpoints:

Proposal email is created as a draft
Sales team reviews and approves before sending
Ensures quality control and relationship management
Tools & Technologies Used
n8n Workflow Automation
CRM Integration
LLM / AI Content Generation
Google Docs or similar document tools
Gmail or Email Draft API
Notification services
Use Case
Ideal for:

B2B sales teams
Agencies sending custom proposals
Freelancers and consultants
Automated yet controlled sales pipelines
This workflow is part of a full Sales Automation System covering lead generation, follow-up, proposal handling, contracts, and onboarding.
