# Workflow: Automated Follow-Up & Lead Status Management

## Overview
This workflow automates the follow-up process for leads that become inactive during the sales cycle.
Instead of manually checking who needs a follow-up, the system monitors CRM activity and triggers the correct action based on the lead’s current stage and history.

The workflow ensures no lead is forgotten, while preventing over-following or wasted sales effort.

---

## Business Goal
- Prevent leads from being ignored or forgotten
- Automate follow-ups based on real inactivity
- Adapt follow-up actions to each sales stage
- Keep CRM statuses accurate and meaningful
- Protect sales time by dropping unresponsive leads

---

## Workflow Trigger

### CRM-Based Trigger
The workflow is triggered directly from the CRM when:
- A lead status has not changed for a defined period (e.g. 7 days)
- The lead is still active in the sales pipeline

This makes the automation fully data-driven.

---

## Workflow Steps

### 1. Batch Processing (Loop)
The workflow processes multiple leads at once:
- Iterates over all inactive leads
- Ensures scalability for large pipelines

---

### 2. Eligibility Filtering (IF Node)
Filters leads to confirm:
- Lead is not already closed or dropped
- Lead is eligible for follow-up
- Follow-up limit has not been exceeded

Ineligible leads are skipped safely.

---

### 3. Stage-Based Decision Logic (Switch Node)
The workflow determines the correct action based on the lead’s current sales stage.

---

### 4. Follow-Up Paths

#### Path A: No Reply to Initial Email
Actions performed:
- Send a follow-up email
- Update CRM status (e.g. Follow-Up Sent)
- Log follow-up attempt count

---

#### Path B: No Reply to Proposal
Actions performed:
- Re-send proposal or reminder
- Update CRM status (e.g. Proposal Follow-Up)
- Notify sales if needed

---

#### Path C: Multiple Follow-Ups with No Response
Actions performed:
- Mark lead as **Dropped**
- Update CRM with drop reason
- Stop further automation for this lead

This prevents infinite loops and wasted effort.

---

## Key Features
- Time-based CRM triggers
- Intelligent follow-up logic per sales stage
- Automatic follow-up limits
- Clean pipeline management
- Scalable batch processing

---

## Tools & Concepts Used
- n8n Workflow Automation
- CRM Trigger & API
- Loop / Batch Processing
- IF & Switch Logic
- Email Automation
- CRM Status Updates

---

## Use Case
Ideal for:
- Sales teams managing many leads
- Cold and warm outreach campaigns
- Agencies and B2B sales pipelines
- Businesses needing consistent follow-up without micromanagement

This workflow is part of a **full Sales Automation System**, working alongside lead generation, email handling, proposals, and onboarding.
