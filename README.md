# 🎥 Project Demo Video

**YouTube Demo:** https://youtu.be/b6UU-0SX_9k

[▶ Watch Recruitment Pipeline Automation Demo](https://youtu.be/b6UU-0SX_9k)

---

# Task: Build and Correct an n8n Recruitment Pipeline Automation Workflow

I want you to create a complete, professional, and fully functional **Recruitment Pipeline Automation** workflow in n8n.

The workflow should automate the job application process, manage candidate information, track recruitment stages, and send automatic email notifications to candidates whenever their application status changes.

## 1. Job Application Form

Create an n8n Form Trigger node with the following details:

- Form Title: Job Application Form
- Form Description: Apply for a job by submitting your details.

Required form fields:

- Full Name
- Email Address (email field)
- Phone Number
- Job Position
- Resume Link

All fields should be properly configured, with required validation where appropriate.

## 2. Airtable Integration

Connect the form submission to Airtable.

Create a new candidate record containing:

- Full Name
- Email Address
- Phone Number
- Job Position
- Resume Link
- Application Stage

Set the initial Application Stage to **Applied**.

Use the following Airtable configuration as placeholders in the public version:

- Airtable Credential: YOUR_AIRTABLE_CREDENTIAL
- Airtable Base ID: YOUR_AIRTABLE_BASE_ID
- Airtable Table ID: YOUR_AIRTABLE_TABLE_ID

## 3. Scheduled Candidate Processing

Create a Schedule Trigger node that periodically checks Airtable for candidates whose application status requires an email notification.

Use an appropriate execution interval and ensure that the workflow does not repeatedly send the same notification to a candidate.

## 4. Candidate Search and Filtering

Create an Airtable Search node that retrieves candidate records.

The filtering logic should prevent:

- Candidates with the initial Applied stage from receiving premature notifications.
- Candidates whose current stage has already been processed from receiving duplicate emails.
- Records with missing email addresses from being processed.

Use valid Airtable filter formulas and correct n8n expressions.

## 5. Candidate Eligibility Conditions

Add an IF node to determine whether a candidate is eligible for notification.

Only candidates with a valid email address and an eligible recruitment stage should continue through the workflow.

## 6. Recruitment Stage Routing

Use a Switch node to create four separate recruitment branches:

1. Shortlisted
2. Interview
3. Selected
4. Rejected

Each branch should identify the candidate's current application stage and route the candidate to the corresponding email notification node.

## 7. Gmail Email Notifications

Connect Gmail to send professional and personalized emails to candidates.

Create four separate email notification nodes.

**Shortlisted Email:**

Inform the candidate that their application has been shortlisted and explain that they will receive further communication about the next recruitment steps.

**Interview Email:**

Inform the candidate that they have been selected for an interview and provide appropriate interview scheduling information.

**Selected Email:**

Congratulate the candidate on being selected for the position and explain the next steps.

**Rejected Email:**

Politely inform the candidate that their application has not been selected and thank them for their interest.

All emails should include the candidate's name and relevant job position wherever appropriate.

Use the candidate's actual email address dynamically from Airtable.

Use this placeholder for Gmail credentials:

- Gmail Credential: YOUR_GMAIL_CREDENTIAL

## 8. Airtable Status Updates

After each email notification is successfully sent, update the corresponding Airtable candidate record.

Create four separate Airtable Update nodes:

- Mark Shortlisted Email Sent
- Mark Interview Email Sent
- Mark Selection Email Sent
- Mark Rejection Email Sent

Each node should update the appropriate email-processing status field while preserving the candidate's actual recruitment stage.

Use the correct candidate record ID and valid n8n expressions.

Ensure that the email-processing logic prevents duplicate notifications.

## 9. Workflow Structure and Connections

Maintain a clear and organized workflow structure.

Use meaningful node names and connect all nodes correctly.

Ensure that:

- Form submissions create candidate records in Airtable.
- Scheduled processing retrieves eligible candidates.
- Candidate stages are evaluated correctly.
- The Switch node routes candidates to the correct branches.
- Gmail sends the corresponding notification.
- Airtable updates the relevant processing status after successful email delivery.

Avoid unnecessary nodes and preserve the original workflow's intended functionality.

## 10. Public GitHub Version and Privacy

Prepare a separate sanitized version suitable for public GitHub upload.

Replace all private and instance-specific details, including:

- Credential IDs
- Credential names
- Airtable Base ID
- Airtable Table ID
- Webhook IDs and private webhook paths
- n8n instance URLs
- Other personal or environment-specific configuration details

Use clear placeholders such as YOUR_AIRTABLE_BASE_ID and YOUR_GMAIL_CREDENTIAL.

Never expose API keys, access tokens, passwords, or other confidential information.

Keep the original private workflow backup unchanged and separate.

## 11. Final Deliverable

Provide the complete, corrected, and public-safe n8n workflow as a downloadable `.json` file.

The JSON must be valid and directly importable into n8n.

Preserve the complete workflow functionality, node connections, expressions, routing logic, and email notification structure.

Do not omit any essential nodes or replace the actual workflow with pseudocode or a written explanation.

Also provide an updated README.md containing the project overview, key features, technologies used, screenshots, installation instructions, and YouTube demo video link.
