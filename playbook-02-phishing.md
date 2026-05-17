# Playbook 02 — Phishing Email Response

**Severity:** MEDIUM to HIGH
**Analyst Level:** Tier 1
**Framework:** NIST SP 800-61
**Last Updated:** May 2026

---

## What Is A Phishing Attack

Phishing is when an attacker sends a fraudulent email
designed to trick a user into clicking a malicious
link, opening a dangerous attachment, or entering
their credentials on a fake website.

---

## Trigger

A user reports a suspicious email OR the email
security gateway flags a message containing
malicious links or attachments.

---

## Step 1 — Acknowledge The Report

- Log into the ticketing system
- Create a new incident ticket
- Contact the user who reported it
- Tell them clearly — do not click any links,
  do not open any attachments, do not reply

---

## Step 2 — Gather Email Information

| Information Needed | Where To Find It |
|---|---|
| Sender email address | Email header |
| Reply-to address | Email header |
| Subject line | Email itself |
| Links in the email | Hover over without clicking |
| Attachments | Do not open |
| Time received | Email header |
| Who else received it | Email gateway logs |

---

## Step 3 — Analyse The Email Safely

Never click links directly. Use these safe methods:

| What To Check | Safe Tool |
|---|---|
| Suspicious links | VirusTotal URL scanner |
| Attachments | Any.run sandbox |
| Sender domain | WHOIS lookup |
| Email headers | MxToolbox header analyser |

---

## Step 4 — Is It A True Positive?

Signs the email is genuinely malicious:

- Sender domain does not match the display name
- Link URL does not match the display text
- Attachment is an executable or macro enabled file
- Email creates urgency or fear
- Requesting credentials or payment
- Poor grammar and spelling

If two or more of these are present — treat as true positive.

---

## Step 5 — Containment

| Scenario | Action |
|---|---|
| User did not interact | Delete email, block sender |
| User clicked a link | Isolate device immediately |
| User entered credentials | Reset password immediately |
| User opened attachment | Isolate device, scan for malware |
| Multiple users affected | Check all mailboxes, mass delete |

---

## Step 6 — Block The Threat

- Submit request to block sender domain
- Add malicious URLs to web proxy blocklist
- Document all blocking actions with timestamps

---

## Step 7 — Escalate or Close

**Escalate to Tier 2 if:**
- User clicked a link and entered credentials
- User opened an attachment
- Multiple users interacted with the email
- Ransomware or malware indicators present
- Appears to be a targeted campaign

**Close at Tier 1 if:**
- User reported without interacting
- Email deleted from all mailboxes
- Sender blocked successfully
- No credential compromise detected

---

## Step 8 — Document The Incident
Ticket ID:
Date and Time Reported:
Reported By:
Sender Address:
Subject Line:
Malicious Links:        Yes / No
Malicious Attachments:  Yes / No
User Interacted:        Yes / No
Containment Action:
Users Affected:
Escalated:              Yes / No
Analyst:
Time To Resolve:
---

## Step 9 — Recommendations

1. Conduct phishing awareness training for all staff
2. Enable multi-factor authentication on all accounts
3. Review email security gateway filtering rules
4. Implement DMARC, DKIM and SPF email authentication

---

## MITRE ATT&CK Reference

| Technique | ID |
|---|---|
| Phishing | T1566 |
| Spearphishing Link | T1566.002 |
| Spearphishing Attachment | T1566.001 |
| Valid Accounts | T1078 |
