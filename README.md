# Phishing Email Detection & Awareness System

## Future Interns — Cyber Security Task 2

### Objective

This project analyzes phishing email samples, identifies phishing
indicators, examines available email-header and URL evidence, classifies
the messages, and provides practical phishing-awareness guidance.

### Investigation Workflow

Email Sample
→ Header Analysis
→ Sender Analysis
→ Link Analysis
→ Phishing Indicators
→ Risk Classification
→ Recommended Action
→ Awareness Guidance

### Samples

#### Sample 01

Source:
Future Interns — Cyber Security Task 2

Analysis:
- Sender and content inspection
- Social-engineering indicator analysis
- Suspicious URL analysis
- Phishing classification

Limitation:
Raw email headers were not provided, so SPF, DKIM, DMARC, Return-Path,
Received headers, and sending infrastructure could not be verified.

#### Sample 02

Source:
Publicly documented phishing-analysis sample.

Raw evidence:
samples/Sample_02.eml

Analysis:
- Raw email-header inspection
- Sender and Return-Path analysis
- Received-header analysis
- SPF/DKIM/DMARC review
- Sending-infrastructure review
- HTML body inspection
- URL extraction
- Phishing-indicator analysis

Observed authentication results:
- SPF: FAIL
- DKIM: FAIL
- DMARC: FAIL

### Tools and Techniques

- macOS Terminal
- curl
- grep
- sed
- awk
- Raw .eml inspection
- Email-header analysis
- URL extraction
- Manual phishing-indicator analysis
- Safe URL handling

### Safety

Suspicious URLs were not opened or visited during the investigation.

URLs are documented in defanged form where appropriate to reduce the
risk of accidental interaction.

No credentials or personal information were entered into suspicious
websites.

### Repository Structure

Task2/
├── samples/
├── analysis/
├── header-analysis/
├── link-analysis/
├── screenshots/
├── awareness/
├── report/
├── references/
└── README.md

### Findings

Both analyzed samples were classified as phishing based on their
observed indicators.

Sample 01 was primarily assessed using visible email content and URL
indicators.

Sample 02 included additional technical evidence from the raw email
headers, including SPF, DKIM, and DMARC failures.

### Limitations

The investigation does not claim information that was not directly
available from the samples.

For Sample 01, raw authentication and delivery headers were unavailable.

For Sample 02, the shortened URL was not opened, so its final redirect
destination was not verified.

### References

Future Interns — Cyber Security Task 2
https://futureinterns.com/cyber-security-task-2-2026/

Sample 02 source
https://github.com/jacobdcook/Phishing-Analysis-Lab

Raw Sample 02
https://raw.githubusercontent.com/jacobdcook/Phishing-Analysis-Lab/main/samples/sample2.eml

### Author

**Jyothi Gedhala**

B.Tech Computer Science and Engineering — Cybersecurity
