# Workflow: Meeting Booked & Sales Notification

## Overview
This workflow automates the moment a lead books a meeting through a calendar link.
Once the meeting is scheduled, the system updates the CRM automatically and notifies the assigned salesperson — ensuring no meeting is missed and the sales team is always prepared.

---

## Business Goal
- Instantly reflect booked meetings inside the CRM
- Eliminate manual CRM updates
- Notify sales in real time
- Keep the sales pipeline accurate and reliable

---

## Workflow Trigger

### Calendar Booking Trigger
The workflow starts when a lead books a meeting using a calendar tool (e.g. Calendly or similar).
The trigger captures:
- Lead name
- Lead email
- Meeting date and time

---

## Workflow Steps

### 1. CRM Lookup (Get Lead)
Using the lead email, the workflow:
- Searches for the lead in the CRM
- Retrieves lead details and assigned salesperson
- Confirms the lead exists before continuing

---

### 2. CRM Status Update
The lead status is updated to reflect the new stage:
- Example: **Meeting Booked**
- Optionally stores meeting date and time in the CRM

This keeps the pipeline fully up to date.

---

### 3. Sales Notification
The workflow sends a real-time notification to the salesperson:
- Lead name
- Meeting date & time
- CRM reference or record link

Notifications can be sent via:
- Email
- Slack
- Telegram
- Internal task system

---

## Key Features
- Real-time calendar-based automation
- CRM-driven pipeline updates
- Instant sales notifications
- Clean handoff between automation and human action

---

## Tools & Concepts Used
- n8n Workflow Automation
- Calendar Integration (Calendly or similar)
- CRM API Integration
- Event-based triggers
- Notification systems

---

## Use Case
Ideal for:
- Sales teams using booking links
- Agencies running discovery calls
- B2B sales pipelines
- Businesses needing fast response after booking

This workflow is part of a **complete Sales Automation System**, connecting lead generation, follow-ups, CRM management, and reporting.
