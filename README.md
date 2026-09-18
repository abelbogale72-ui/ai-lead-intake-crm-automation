# AI Lead Intake & CRM Automation

An end-to-end **n8n automation workflow** for capturing website leads, validating incoming data, using AI to qualify and classify leads, storing them in Airtable, detecting duplicates, and routing high-priority leads through Zapier.

## 🚀 Workflow Overview

```text
Website / Form
      ↓
Inbound Lead Webhook
      ↓
Normalize & Validate Lead
      ↓
Valid Lead?
   ↙        ↘
 No          Yes
 ↓            ↓
400 Error   Groq AI
              ↓
        Parse AI Result
              ↓
       Airtable Duplicate Check
          ↙           ↘
      Existing       New Lead
         ↓              ↓
   Update Airtable   Create Airtable
          ↘           ↙
              ↓
       High Priority?
          ↙        ↘
        Yes         No
         ↓           ↓
      Zapier      Continue
         ↘           ↙
        Success Response
