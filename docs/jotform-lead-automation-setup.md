# Jotform Lead + Email Automation Setup

Use the current intake form as the free lead capture form:

https://form.jotform.com/261673578323060

## Goal

Collect leads for free from the website, send the client an automatic confirmation email, notify Culturally Ai, and keep every lead in a Google Sheet.

## Free Workflow

1. Website visitor clicks **Get My Free Fit Check** or **Start Private Resume Intake**.
2. Visitor completes the Jotform intake.
3. Jotform sends the client an automatic confirmation email.
4. Jotform sends Starr an admin notification at `starr@culturallyai.com`.
5. Jotform adds the lead to Google Sheets.
6. Starr reviews fit and sends the correct payment link manually.

## Jotform Settings

### 1. Autoresponder Email To Client

Jotform path:

**Settings > Emails > Add an email > Autoresponder**

Send to:

Client email field from the form.

Subject:

`Your Culturally Ai Resume Fit Check Was Received`

Body:

```text
Hi {client_name},

Thank you for completing the Culturally Ai Career Intelligence Intake.

Your information has been received for a private resume fit review. I will review your experience, career goals, target roles, and service needs.

If Culturally Ai is the right fit, you will receive the recommended package, payment details, and next steps by email.

Payment is not collected inside the intake. Strategy calls and writing begin only after payment is complete.

Best,

Starr
Culturally Ai
starr@culturallyai.com
404-419-7440
```

### 2. Admin Notification To Starr

Jotform path:

**Settings > Emails > Add an email > Notification**

Send to:

`starr@culturallyai.com`

Subject:

`New Culturally Ai Resume Lead: {client_name}`

Body:

```text
New Culturally Ai resume lead received.

Client: {client_name}
Email: {client_email}
Phone: {client_phone}
Package interest: {package_interest}
Target role: {target_role}
Salary range: {salary_range}
Timeline: {timeline}

Review the full intake in Jotform, then send the best-fit payment link and next steps.
```

### 3. Optional Conditional Emails

Use Jotform conditional logic only if the form has a package-interest question.

Condition:

If package interest is **Resume Refresh**, send a reply using the $500 recommendation template.

If package interest is **Executive Resume Build**, send a reply using the $750 recommendation template.

If package interest is **LinkedIn Profile**, send a reply using the $150 recommendation template.

Recommendation: keep payment request emails manual at first so each lead feels reviewed and exclusive.

## Google Sheets Lead Tracker

Jotform path:

**Settings > Integrations > Google Sheets**

Recommended sheet columns:

- Date submitted
- Name
- Email
- Phone
- Package interest
- Current role
- Target role
- Salary range
- Timeline
- Resume uploaded
- LinkedIn URL
- Lead status
- Payment sent
- Payment received
- Strategy call booked
- Draft due date
- Notes

Lead status options:

- New
- Reviewing
- Payment sent
- Paid
- Strategy call booked
- Drafting
- Revision
- Complete
- Not a fit

## Manual Follow-Up Templates

### Best-Fit Recommendation

Subject:

`Your Culturally Ai Resume Recommendation`

```text
Hi {client_name},

I reviewed your intake and recommend:

{package_name} - ${price}

This is the best fit because {short_reason}.

Payment link: {payment_link}

Once payment is complete, I will send the booking link if your package includes a strategy call.

Please note: all sales are final. Resume packages include 3 revision rounds, which are used for edits, refinements, accuracy corrections, formatting updates, and positioning adjustments.

Best,

Starr
```

### Not Ready Yet / Needs More Info

Subject:

`Quick Follow-Up on Your Culturally Ai Intake`

```text
Hi {client_name},

Thank you for completing the intake. Before I recommend a package, I need one more detail:

{question_or_missing_item}

Once I have that, I can confirm the best next step.

Best,

Starr
```

### Not a Fit

Subject:

`Culturally Ai Resume Fit Review`

```text
Hi {client_name},

Thank you for completing the intake.

After reviewing your information, I do not think this service is the best fit for your current needs. I want to be careful not to accept work unless I believe the service path makes sense.

Thank you for considering Culturally Ai.

Best,

Starr
```

## Website CTA Language

Use this language on the website:

`Get My Free Fit Check`

Support copy:

`Submit the private intake first. Culturally Ai reviews your background, target roles, and career goals, then sends the best-fit recommendation and next steps by email.`

## Compliance Notes

- Do not guarantee interviews or job offers.
- Do not say the resume will bypass AI.
- Use: `formatted for ATS systems and automated resume screening tools`.
- Payment request emails should repeat: all sales are final and revisions are included.
