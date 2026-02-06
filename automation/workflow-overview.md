# Gym Membership Automation – Workflow Overview

This document explains how the n8n automation workflow operates end-to-end.

---

## Workflow Goal

Automatically notify gym members about their subscription status at key milestones:
- 7 days before expiry
- 24 hours before expiry
- After expiry

This eliminates manual follow-ups and prevents missed renewals.

---

## High-Level Flow

1. **Schedule Trigger**
   - Runs once daily at a fixed time (8:00 AM)

2. **Airtable – Search Records**
   - Fetches all member records from the membership table

3. **Function Node – Check Subscription Status**
   - Calculates `days_remaining`
   - Assigns a `notificationType`:
     - `7_days`
     - `1_day`
     - `expired`
     - `ignore`

4. **IF Nodes (Decision Layer)**
   - IF – 7 Days Reminder
   - IF – 24 Hours Reminder
   - IF – Expired Reminder

5. **Email Notification (Gmail)**
   - Sends the appropriate email based on the reminder type

---

## Key Design Decisions

- **Exact-day triggers** prevent duplicate or spammy reminders
- **Single daily run** keeps the workflow predictable
- **Data-driven logic** allows easy scaling or reuse for other businesses

---

## Tools Used

- n8n (workflow automation)
- Airtable (member database)
- Gmail (email delivery)

---

## Outcome

A fully automated, low-maintenance membership reminder system that works without manual intervention.