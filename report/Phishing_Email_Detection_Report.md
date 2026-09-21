# Phishing Email Detection & Awareness System

## Future Interns — Cyber Security Task 2

### 1. Objective

The objective of this project is to analyze phishing email samples, identify
phishing indicators, examine available email-header and URL evidence,
classify the emails by risk, and provide practical phishing-awareness
guidance for employees.

### 2. Investigation Methodology

The investigation followed these steps:

1. Collect publicly documented email samples.
2. Inspect the visible sender, subject, and message content.
3. Examine available raw email headers.
4. Review sender domains and mail-delivery infrastructure.
5. Inspect URLs without opening suspicious destinations.
6. Identify social-engineering and technical indicators.
7. Classify each sample based on the combined evidence.
8. Document limitations where technical evidence was unavailable.
9. Create employee awareness and prevention guidance.

### 3. Sample 01 — Account Verification Phishing

**Source:** Future Interns — Cyber Security Task 2

**Classification:** PHISHING

#### Observed Indicators

- Sender is presented only as "Security Team".
- Generic greeting: "Dear User".
- Message claims suspicious account activity.
- Recipient is asked to verify account details immediately.
- The message creates a 24-hour deadline.
- Permanent account lock is threatened.
- The verification URL uses a suspicious domain:
  `http://secure-account-verify[.]com`
- The request involves a potentially sensitive account action.

#### Link Analysis

The URL uses HTTP and a domain that does not identify the legitimate
organization being claimed in the message.

The URL was documented in defanged form and was not opened.

#### Header Analysis

Raw email headers were not provided with this sample.

Therefore, SPF, DKIM, DMARC, Return-Path, Received headers, and sending
infrastructure cannot be verified.

#### Assessment

The combination of generic addressing, urgency, account-lock threats,
a suspicious verification request, and a suspicious domain supports the
classification of this message as phishing.

---

### 4. Sample 02 — Microsoft Account Security Phishing

**Source:** Publicly documented phishing-analysis sample.

**Raw evidence:** `samples/Sample_02.eml`

**Classification:** PHISHING

#### Sender Information

**From:**

`"Microsoft Account Team" <noreply@microsoftonline-verify.com>`

**Return-Path:**

`noreply@microsoftonline-verify.com`

The sender domain shown in the email is `microsoftonline-verify.com`,
which is different from the official `microsoft.com` domain.

#### Authentication Results

The raw headers contain the following results:

- SPF: FAIL
- DKIM: FAIL
- DMARC: FAIL

These authentication failures provide technical evidence that requires
additional investigation and, together with the other indicators,
support the phishing classification.

#### Sending Infrastructure

The Received header shows:

**Sending host:**

`mail.microsoftonline-verify.com`

**Underlying host shown in the header:**

`vps-291847.contabo.net`

**Sending IP:**

`178.238.225.91`

These values are recorded directly from the raw email header. No claim is
made about ownership of the IP address beyond what is shown in the sample.

#### Message Content

The email presents itself as a Microsoft account security alert and
contains:

- "Unusual sign-in activity" warning.
- Claimed country/region: Russia.
- Claimed sign-in IP: `91.234.99.42`.
- Claimed platform: Windows 10.
- Claimed browser: Chrome 120.0.
- Request to secure the account immediately.
- Microsoft-related branding.
- Mandatory-service language.
- A "Review recent activity" action link.

**Important:** `91.234.99.42` is the IP presented in the email body as
the alleged sign-in IP. It is different from the sending IP
`178.238.225.91` found in the email headers.

#### URL Analysis

Observed URL:

`https://bit.ly/3vF9xKz`

The URL uses the Bitly shortening service. The visible shortened URL
does not reveal the final destination from the link text alone.

The URL was extracted from the raw email source but was **not opened or
visited**. Therefore, the final redirect destination is not claimed.

#### Assessment

The combination of Microsoft impersonation, a non-Microsoft sender
domain, SPF/DKIM/DMARC failures, suspicious sending infrastructure,
urgency, Microsoft branding, and a shortened action URL supports the
classification of this message as phishing.

---

### 5. Comparison of Observed Evidence

| Evidence | Sample 01 | Sample 02 |
|---|---|---|
| Generic greeting | Yes | Not the primary indicator |
| Urgency | Yes | Yes |
| Account-security theme | Yes | Yes |
| Suspicious sender/domain | Yes | Yes |
| Suspicious URL | Yes | Yes |
| Raw headers available | No | Yes |
| SPF result | Not available | FAIL |
| DKIM result | Not available | FAIL |
| DMARC result | Not available | FAIL |
| Sending infrastructure | Not available | Available |
| URL destination visited | No | No |

Sample 01 was primarily assessed using visible email content and URL
indicators.

Sample 02 provided additional technical evidence through its raw email
headers.

---

### 6. Employee Awareness Guidance

Phishing emails attempt to persuade recipients to click links, disclose
credentials, open unsafe attachments, or perform actions that benefit an
attacker.

#### How Employees Can Identify Suspicious Emails

1. **Check the complete sender address.**  
   Do not rely only on the display name.

2. **Look for urgency and pressure.**  
   Account-lock warnings, deadlines, threats, and unexpected security
   alerts should be verified before action.

3. **Inspect links carefully.**  
   Be cautious with unfamiliar domains, shortened URLs, and links that do
   not clearly correspond to the claimed organization.

4. **Watch for sensitive-information requests.**  
   Be cautious when an unexpected email requests passwords, OTPs,
   authentication codes, payment details, or account information.

5. **Use authentication evidence when available.**  
   SPF, DKIM, and DMARC results can help during technical email analysis.

6. **Verify independently.**  
   Instead of using an unexpected email link, open the organization's
   known official website manually or contact a trusted support channel.

### Employee Do's

- Verify the sender's complete email address.
- Check suspicious links before clicking.
- Treat unexpected urgent requests cautiously.
- Report suspected phishing through the approved process.
- Verify account or payment requests using a trusted channel.
- Contact IT/security when unsure.

### Employee Don'ts

- Do not click suspicious links.
- Do not enter passwords through unexpected email links.
- Do not share OTPs or authentication codes.
- Do not open unexpected attachments.
- Do not rely only on logos or display names.
- Do not allow urgency to replace verification.

### If You Clicked a Suspicious Link

1. Stop entering information.
2. Close the suspicious webpage.
3. Inform the organization's IT/security team.
4. If credentials were entered, follow the organization's password-reset
   and incident-response procedure.
5. Report the original email.

---

### 7. Key Lessons

A phishing email does not need to contain a single obvious indicator.
Multiple small indicators can become significant when considered together.

Important checks include:

- Sender identity
- Sender domain
- Reply-To and Return-Path
- Received headers
- SPF
- DKIM
- DMARC
- URL structure
- Urgency and social engineering
- Requests for sensitive actions
- Branding and impersonation

Technical evidence should be combined with message-content analysis rather
than relying on a single signal.

---

### 8. Safety and Handling

Suspicious URLs were not opened or visited during this investigation.

URLs were documented in defanged form where appropriate to reduce the
risk of accidental interaction.

No credentials or personal information were entered into suspicious
websites.

The original Sample 02 `.eml` file is preserved as evidence in:

`samples/Sample_02.eml`

---

### 9. Limitations

- Sample 01 did not include raw email headers, so its authentication and
  delivery infrastructure could not be verified.
- Sample 02's shortened URL was not opened, so its final destination was
  not verified.
- The technical observations in this report are limited to evidence
  available in the supplied/publicly documented samples.
- No unsupported ownership claim is made about the sending IP address.

---

### 10. Evidence Included in This Repository

#### Sample 01

- `samples/Sample_01.txt`
- `analysis/Sample_01_Analysis.txt`
- `header-analysis/Sample_01_Header_Analysis.txt`
- `link-analysis/Sample_01_Link_Analysis.txt`
- `screenshots/Sample_01/01_email_evidence.png`

#### Sample 02

- `samples/Sample_02.eml`
- `samples/Sample_02.txt`
- `samples/Sample_02_Body_Extract.txt`
- `analysis/Sample_02_Analysis.txt`
- `header-analysis/Sample_02_Header_Analysis.txt`
- `link-analysis/Sample_02_Link_Analysis.txt`
- `screenshots/Sample_02/01_raw_headers.png`
- `screenshots/Sample_02/02_authentication_results.png`
- `screenshots/Sample_02/03_sender_infrastructure.png`
- `screenshots/Sample_02/04_email_body.png`
- `screenshots/Sample_02/05_url_evidence.png`

---

### 11. References

**Future Interns — Cyber Security Task 2**

https://futureinterns.com/cyber-security-task-2-2026/

**Sample 02 public source**

https://github.com/jacobdcook/Phishing-Analysis-Lab

**Raw Sample 02**

https://raw.githubusercontent.com/jacobdcook/Phishing-Analysis-Lab/main/samples/sample2.eml

---

### 12. Conclusion

This project demonstrates a practical phishing-email investigation
workflow using both visible email indicators and available technical
evidence.

Sample 01 demonstrates content-based phishing analysis where raw headers
were unavailable.

Sample 02 demonstrates a deeper investigation using raw headers,
authentication results, sender infrastructure, message content, and URL
analysis.

The investigation emphasizes safe handling of suspicious emails and
independent verification before users take security-sensitive actions.
