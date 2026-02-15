REPO TITLE:
SharePoint Governance Case Study: When IAM Design Fails

------------------------------------------------------------
PROJECT PURPOSE
------------------------------------------------------------
This case study demonstrates how weak Identity & Access Management (IAM) design leads to SharePoint governance breakdown in Microsoft 365 environments.

It analyzes real-world failure patterns and provides structured remediation aligned to GRC best practices.

------------------------------------------------------------
EXECUTIVE SUMMARY
------------------------------------------------------------
SharePoint governance failures are rarely platform issues.
They are identity architecture issues.

When access is assigned directly to users instead of governed groups,
control visibility, audit traceability, and risk accountability degrade.

This case study walks through:
- Failure scenario
- Risk impact
- Root cause analysis
- Governance remediation model

------------------------------------------------------------
SCENARIO: FINANCE SITE ACCESS SPRAWL
------------------------------------------------------------

Environment:
- 300-employee organization
- Microsoft 365 collaboration environment
- No formal IAM governance policy

Observed Issues:
- Direct user permissions granted at folder level
- Broken permission inheritance across 17 folders
- No quarterly access review process
- Orphaned SharePoint site owner
- External sharing links enabled without review

------------------------------------------------------------
RISK ANALYSIS
------------------------------------------------------------

Control Domain: Access Control
Framework Mapping: NIST PR.AC / ISO 27001 A.9

Risks Identified:
1) Excessive Access Exposure
2) Lack of Audit Traceability
3) Inability to Certify Access During Audit
4) Data Leakage via External Sharing

Risk Score Example:
Likelihood: 4
Impact: 5
Inherent Risk: 20 (High)

------------------------------------------------------------
ROOT CAUSE
------------------------------------------------------------

- No enforced group-based RBAC model
- No restriction on Microsoft 365 Group creation
- No documented policy prohibiting direct permission assignment
- No ownership accountability model

------------------------------------------------------------
REMEDIATION STRATEGY
------------------------------------------------------------

1) Enforce Group-Based Access
   - All access via Entra Security Groups
   - Remove direct user permissions

2) Standardize Group Naming
   Example:
   SG-FIN-Read
   SG-FIN-Contribute
   SG-FIN-Owner

3) Implement Quarterly Access Certification
   - Group membership review
   - Site owner attestation

4) Restrict M365 Group Creation
   - Limit to authorized request workflow

5) Monitor Unique Permission Breaks
   - Document exceptions
   - Review quarterly

------------------------------------------------------------
GOVERNANCE OUTCOME
------------------------------------------------------------

- Improved least privilege enforcement
- Audit-ready access traceability
- Reduced residual risk
- Executive reporting alignment

------------------------------------------------------------
LESSON
------------------------------------------------------------

SharePoint security maturity directly reflects IAM governance maturity.

Collaboration risk is identity risk.




------------------------------------------------------------
ARCHITECTURE: IAM-DRIVEN SHAREPOINT MODEL
------------------------------------------------------------

```mermaid
flowchart TD
A[HR System] --> B[Entra Security Groups]
B --> C[Microsoft 365 Groups]
C --> D[SharePoint Site Roles]
D --> E[Document Libraries]
E --> F[Folders / Files]

G[Quarterly Access Review] --> B
H[Executive Reporting] --> G


## Project Artifacts

- Risk Register Template → risk_register_template.csv
- Executive Dashboard Example → executive_dashboard_metrics.md
