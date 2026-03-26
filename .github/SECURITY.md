# Security Policy

## Security Contact Information

**Primary Security Contact:** security@riverside.fm
**Response Hours:** Sunday–Thursday, 09:00–18:00 UTC  

> For **critical/zero-day vulnerabilities**, email with subject line `[CRITICAL]` for expedited handling.

---

## Vulnerability Disclosure Process

We follow a **coordinated disclosure** model. Please give us a reasonable
opportunity to address the issue before any public disclosure.

### Step 1 — Report the Vulnerability (Private)

**Preferred:** Use GitHub's private vulnerability reporting feature (see below).  
**Alternative:** Email security@yourcompany.com with the following details:

- **Summary** — A brief description of the vulnerability
- **Type** — e.g. SQL injection, XSS, SSRF, broken auth, RCE
- **Affected component** — Repository name, file path(s), version(s)
- **Severity** — Your assessment (Critical / High / Medium / Low)
- **Steps to reproduce** — Clear, step-by-step instructions
- **Proof of concept** — Code, screenshots, or a working exploit (if available)
- **Impact** — What an attacker could achieve by exploiting this
- **Suggested fix** — Optional, but appreciated

### Step 2 — Acknowledgement

| Timeframe       | Action                                                              |
| --------------- | ------------------------------------------------------------------- |
| Within 48 hours | We acknowledge receipt of your report                               |
| Within 5 days   | We confirm whether the issue is valid and its initial severity      |
| Within 14 days  | We share our remediation plan and estimated patch timeline          |

If you do not receive an acknowledgement within 48 hours, follow up at
security@riverside.fm with `[FOLLOW-UP]` in the subject line.

### Step 3 — Remediation

- We develop and internally test a fix
- We may request clarification or additional details from you
- You will be notified before any patch is released
- Critical vulnerabilities target a **7-day patch window**;
  High/Medium target **30 days**; Low target **90 days**

---

## Security Advisory Triage Workflow

When a report is received, our security team follows this internal process:

```
Report Received(email)
      │
      ▼
┌─────────────────────┐
│  Triage (≤48hrs)    │  Assign owner, set initial severity (CVSS score),
│                     │  acknowledge reporter
└────────┬────────────┘
         │
         ▼
┌─────────────────────┐
│  Validation (≤5d)   │  Reproduce the issue, confirm scope and impact,
│                     │  update severity if needed
└────────┬────────────┘
         │
    ┌────┴────┐
    │ Valid?  │
    └────┬────┘
    No ──┴──► Close advisory, notify reporter with explanation
         │
        Yes
         ▼
┌─────────────────────┐
│  Remediation        │  Develop fix in a private fork, internal review,
│                     │  security testing, confirm patch with reporter
└─────────────────────┘
```

### Severity & SLA

| Severity     | CVSS Score | Patch Target | Disclosure Window |
| ------------ | ---------- | ------------ | ----------------- |
| 🔴 Critical  | 9.0–10.0   | 7 days       | 14 days           |
| 🟠 High      | 7.0–8.9    | 30 days      | 45 days           |
| 🟡 Medium    | 4.0–6.9    | 60 days      | 90 days           |
| 🔵 Low       | 0.1–3.9    | 90 days      | 90 days           |

Severity is assessed using the [CVSS v3.1 scoring system](https://www.first.org/cvss/calculator/3.1).

---

## Scope

### In Scope

- All code in this repository
- Authentication and authorization mechanisms
- Data handling and storage
- API endpoints and integrations
- Dependency vulnerabilities with a direct exploit path

### Out of Scope

- Vulnerabilities in third-party services we do not control
- Social engineering of employees or contractors
- Physical access attacks
- Denial of service (DoS/DDoS) attacks
- Vulnerabilities requiring unlikely user interaction (e.g. self-XSS)
- Reports from automated scanners without a working proof of concept
