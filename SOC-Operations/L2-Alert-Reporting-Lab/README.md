# 🔵 SOC L1 Lab: Alert Reporting, Escalation, & Communication

**Platform:** TryHackMe | **Path:** SOC Level 1 | **Lab:** SOC L1 Alert Reporting  
**Focus:** Alert Reporting, Alert Escalation, & Alert Communication  
Severity Tiers Used: 🔥 Critical | 🔴 High | 🟡 Medium | 🔵 Low 

**Hyperlink Back to SOC L1 Alert Triaging:** 

---

## 📌 1. Executive Summary & Lab Overview
In this laboratory environment for TryHackMe, the **SOC L1 Alert Reporting** phase emphasizes knowing how to accurately report, escalate, and communicate during an active alert sequence. This document outlines the critical steps required to process alert queues seamlessly—ranging from understanding structural guidelines when documenting comments, to recognizing specific criteria that necessitate an immediate ticket escalation, and ensuring clear communication metrics are maintained across the team. This lab functions as a direct continuation of the previously completed *SOC L1 Alert Triage* module, uniting defensive threat analysis with professional workflow reporting and operational handoffs.

### 🎯 Core Learning Objectives
* **Operational Reporting Value:** Understanding the critical requirement for SOC alert documentation and ther signifance to the alerting process
* **Comment Quality Metrics:** Learning how to write descriptive analyst comments
* **Escalation Protocol Execution:** Exploring defensive escalation methods, alert ownership reassignment, and tier-transfer best practices.
* **Crisis Communication Readiness:** Applying out-of-band communication procedures to resolve simulated threat scenarios and engineering log failures confidently.

---

## 📊 2. SIEM Alert Reporting Importance
Before processing advanced tickets, it is essential to understand why SOC Tier 1 analysts must thoroughly document findings rather than simply marking events with a basic True Positive or False Positive verdict. Comprehensive alert reporting helps tackle three critical issues within modern security operations:

| Alert Report Purpose | Explanation | Operational Significance |
| :--- | :--- | :--- |
| **Provide Context for Escalation** | A well-structured summary saves immense time for Tier 2 analysts. | Allows senior responders to instantly grasp the threat scope without repeating foundational alert analysis from scratch. |
| **Save Findings for the Records** | Raw SIEM indices are typically purged after 3–12 months, but alert logs remain indefinitely. | Preserves all historical security context directly inside the ticket infrastructure for compliance, auditing, and future lookbacks. |
| **Improve Investigation Skills** | Condensing highly complex alerts require clear comprehension. | Serves as an exceptional skill-building exercise to refine an L1 analyst's data interpretation and summary capabilities. |

---

## ⚙️ 3. SOC Alert Reporting & Escalation Framework
To process incoming alerts uniformly without dropping critical indicators, every flag or suspicious action is subjected to a mandatory five-point matrix coupled with strict tier-transfer thresholds.

### 1. The Five Ws Matrix
The on-board SIEM dashboard automatically grades all analyst comments against this five-point matrix, requiring a high-quality summary to meet evaluation metrics:
* **Who:** Identify the exact user accounts, email addresses, or system sessions executing the command lines or initiating the downloads.
* **What:** Record the precise malicious activities, execution paths, or anomalous event sequences observed.
* **When:** Record the exact UTC timestamps specifying when the suspicious activity officially started and concluded.
* **Where:** Log the target endpoints, source hostnames, external domains, or affected network zones involved in the alert.
* **Why:** Detail the absolute structural reasoning, technical indicators, and behavioral analysis that confirms your final verdict.

### 2. Escalation Trigger Thresholds
While standard alerts are closed directly at Tier 1, an SOC L1 analyst must immediately reassign ownership to an on-shift L2 analyst under the following four general scenarios:
1. **Major Cyberattack Indicators:** The alert details systemic malicious actions requiring deep investigation or specialized Digital Forensics and Incident Response (DFIR) procedures.
2. **Active Remediation Requirements:** The threat demands immediate operational intervention, including automated malware eradication, endpoint host isolation, or enterprise credential rotation.
3. **External Communication Dependencies:** The incident scope crosses organizational boundaries, requiring immediate coordination with corporate partners, clients, upper management, or law enforcement agencies.
4. **Alert Ambiguity:** The technical properties of the alert are not clearly understood by the L1 responder, requiring peer-to-peer knowledge sharing or senior oversight.

---

## 🔍 4. Alert Reporting & Escalation Examples

### 🚨 Alert Profile 1
* **Alert Name:** Email Marked as Phishing after Delivery
* **Alert Description:** The email was classified as phishing post-delivery after an automated analysis. If the email is spoofed or contains any suspicious links or files, it must be deeply investigated.
* **Assigned Severity:** Medium 🟡
* **Initial Status:** New &rarr; Shifted to **In Progress** (Self-Assigned)
* **Assigned Analyst:** You (L1)

### 📧 Phishing Alert Analysis 
* **Subject:** Important Update: Microsoft Teams Pricing Increase
* **Body Keywords:** 600% price increase; urgent notice; download the report; read the details;
* **Sender:** Microsoft Support<support@microsoft.com>
* **Recipient:** Eddie Huffman, IT Manager<e.huffman@tryhackme.thm>
* **Security Checks:** SPF/Fail; DKIM/Fail;
* **Attached URLs:** None
* **Attached Files:** REPORT.rar


![Alert 1](<Progress .png>)
*Figure 1: Self-assigning the Medium "Potential Phishing Email Delivery" alert and updating status to In Progress.*


---



### 🎣 SOC Analyst Analysis For Alert Profile 1 



#### 📈 Alert Overview
* **My Analysis:** At 19:25 UTC, a sender from the email listed here: support@microsoft.com, sent an email message to the recipient, e.huffman@tryhackme.thm (Eddie Huffman, IT Manager) that contains a report marked as urgent about the 600% Microsoft Team Pricing increase. More information can be found inside the report once downloaded.

#### 🔏 Security Authentication Audit
* **Critical Protocol Failures:** However, the email did not pass the provided security checks (SPF/Fail; DKIM/Fail), which means the email was not sent from an authorized personnel and the email digital signature is not recognized, indicating the email server cannot prove whether or not the email has been tampered with.

#### ⚡ Root Cause & Escalation Action
* **Final Threat Verdict:** Therefore, the email triggered an alert after it was sent, now being classified as phishing email as the attacker probably spoofed the domain to make it appear like it came from a reliable source like Microsoft. By considering the above details, escalating the issue to the L2(E.Fleming).


![Alert 1](Verdict.png)
*Figure 2: Analysis proven correct to capture the flag.*

---