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

```text
FUTURE_CS_02/
├── samples/
│   ├── Sample_01.txt
│   ├── Sample_02.eml
│   ├── Sample_02.txt
│   └── Sample_02_Body_Extract.txt
├── analysis/
│   ├── Sample_01_Analysis.txt
│   ├── Sample_02_Analysis.txt
│   └── Phishing_Indicators_Summary.txt
├── header-analysis/
│   ├── Sample_01_Header_Analysis.txt
│   └── Sample_02_Header_Analysis.txt
├── link-analysis/
│   ├── Sample_01_Link_Analysis.txt
│   └── Sample_02_Link_Analysis.txt
├── screenshots/
│   ├── Sample_01/
│   └── Sample_02/
├── awareness/
│   └── Employee_Awareness_Guide.txt
├── report/
│   ├── Phishing_Email_Detection_Report.md
│   └── Phishing_Email_Detection_Report.pdf
├── references/
└── README.md
```
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

### Author

**Jyothi**

B.Tech Computer Science and Engineering — Cybersecurity
