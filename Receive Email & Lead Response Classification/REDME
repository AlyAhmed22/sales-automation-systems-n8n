# Workflow: Receive & Qualify Incoming Lead Emails

## Overview
This workflow automates the process of handling incoming replies from leads during a sales campaign.
Its main goal is to save sales time by automatically qualifying replies, updating the CRM, and notifying the sales team — while keeping a **human-in-the-loop** for critical actions.

The workflow receives an email, checks if it is related to the campaign, verifies the lead in the CRM, analyzes intent using AI, and then routes the lead to the correct next step.

---

## Business Goal
- Reduce manual email handling
- Automatically detect interested vs non-interested leads
- Keep CRM status always up to date
- Notify sales instantly when action is needed
- Maintain control before sending client-facing emails

---

## Workflow Steps

### 1. Email Trigger
The workflow starts when a new email is received.
This represents a reply from a previously contacted lead.

---

### 2. Email Filtering (IF Node)
Checks whether the incoming email is related to the sales campaign:
- Subject keywords
- Sender email
- Campaign identifiers

Unrelated emails are ignored.

---

### 3. CRM Lookup (Get Lead)
The workflow queries the CRM to:
- Find the lead by email
- Confirm the lead already exists
- Retrieve current lead status and owner

This prevents processing unknown or irrelevant contacts.

---

### 4. AI Intent Classification (LLM Chain)
The email content is sent to an AI model to classify intent:
- Interested
- Not interested / rejection
- Neutral or unclear

The AI only supports decision-making — it does not take final control.

---

### 5. Decision Routing (Switch Node)

#### Path A: Lead is Interested
Actions performed:
- Update CRM lead status to **Interested**
- Prepare a calendar booking email (draft for human approval)
- Send a real-time notification to the assigned salesperson
- Notify sales to review CRM and follow up

Human-in-the-loop:
- Email is reviewed before sending
- Sales confirms next steps

---

#### Path B: Lead is Not Interested
Actions performed:
- Update CRM lead status to **Dropped**
- No client communication is sent
- Workflow ends cleanly

---

## Key Features
- CRM-driven decision making
- AI-assisted lead qualification
- Automatic status transitions
- Sales notifications
- Safe automation with human approval points

---

## Tools & Concepts Used
- n8n Workflow Automation
- Email Trigger
- IF & Switch Logic
- CRM Integration (generic / CRM-agnostic)
- AI / LLM Chain for intent classification
- Human-in-the-loop design

---

## Use Case
Ideal for:
- Cold email campaigns
- Inbound lead replies
- Sales teams handling high email volume
- Businesses needing faster lead response times

This workflow is part of a larger **Sales Automation System** covering the full sales lifecycle.
