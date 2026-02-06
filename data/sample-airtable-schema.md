# Airtable Schema – Gym Members Table

This document describes the structure of the Airtable base used in the automation.

---

## Table Name
**Members**

---

## Fields

| Field Name        | Type        | Description |
|------------------|------------|-------------|
| Name             | Single line text | Member full name |
| Email            | Email       | Member email address |
| Expiry Date      | Date        | Subscription expiry date |
| Status           | Single select | Active / Expired |
| days_remaining   | Formula / Number | Calculated days until expiry |
| notificationType | Single line text | Used internally by automation |

---

## Notes

- `days_remaining` is calculated in n8n, not Airtable
- `notificationType` is temporary and used only for routing logic
- Schema is intentionally simple for non-technical business owners

---

## Scalability

This schema can be extended to include:
- Membership plans
- Payment status
- WhatsApp phone numbers
- Branch locations