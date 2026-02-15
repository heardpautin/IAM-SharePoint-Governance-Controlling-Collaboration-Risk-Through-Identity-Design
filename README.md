# SharePoint Governance Case Study: When IAM Design Fails

## Project Purpose

This case study demonstrates how weak Identity & Access Management (IAM) design leads to SharePoint governance breakdown in Microsoft 365 environments.

It analyzes real-world failure patterns and provides structured remediation aligned to Governance, Risk, and Compliance (GRC) best practices.

---

## Executive Summary

SharePoint governance failures are rarely platform issues.  
They are identity architecture issues.

When access is assigned directly to users instead of governed groups, control visibility, audit traceability, and risk accountability degrade.

This case study walks through:

- Failure scenario  
- Risk impact  
- Root cause analysis  
- Governance remediation model  

---

## Scenario: Finance Site Access Sprawl

### Environment
- 300-employee organization  
- Microsoft 365 collaboration environment  
- No formal IAM governance policy  

### Observed Issues
- Direct user permissions granted at folder level  
- Broken permission inheritance across 17 folders  
- No quarterly access review process  
- Orphaned SharePoint site owner  
- External sharing links enabled without review  

---

## Risk Analysis

**Control Domain:** Access Control  
**Framework Mapping:** NIST PR.AC / ISO 27001 A.9  

### Risks Identified

1. Excessive Access Exposure  
2. Lack of Audit Traceability  
3. Inability to Certify Access During Audit  
4. Data Leakage via External Sharing  

### Risk Score Example

- Likelihood: 4  
- Impact: 5  
- Inherent Risk: 20 (High)  

---

## Root Cause

- No enforced group-based RBAC model  
- No restriction on Microsoft 365 Group creation  
- No documented policy prohibiting direct permission assignment  
- No ownership accountability model  

---

## Remediation Strategy

1. **Enforce Group-Based Access**
   - All access via Entra Security Groups  
   - Remove direct user permissions  

2. **Standardize Group Naming**
   - SG-FIN-Read  
   - SG-FIN-Contribute  
   - SG-FIN-Owner  

3. **Implement Quarterly Access Certification**
   - Group membership review  
   - Site owner attestation  

4. **Restrict M365 Group Creation**
   - Limit to authorized request workflow  

5. **Monitor Unique Permission Breaks**
   - Document exceptions  
   - Review quarterly  

---

## Governance Outcome

- Improved least privilege enforcement  
- Audit-ready access traceability  
- Reduced residual risk  
- Executive reporting alignment  

---

## Lesson

SharePoint security maturity directly reflects IAM governance maturity.

Collaboration risk is identity risk.

---

## Architecture Overview (Conceptual Model)

HR System  
↓  
Entra Security Groups  
↓  
Microsoft 365 Groups  
↓  
SharePoint Site Roles  
↓  
Document Libraries  
↓  
Folders / Files  

Quarterly Access Review → Entra Security Groups  
Executive Reporting → Quarterly Access Review  

---

## Sample Risk Register (Embedded View)

| Risk ID | Domain | Description | Likelihood | Impact | Score | Owner | Status |
|----------|---------|------------|------------|--------|-------|--------|--------|
| R-001 | Access Control | Direct user permissions bypass RBAC | 4 | 5 | 20 | IAM Lead | Open |
| R-002 | Vendor Risk | No formal vendor tiering process | 3 | 4 | 12 | Security Lead | In Progress |
| R-003 | Logging | SIEM alerts not formally reviewed | 3 | 5 | 15 | SOC Lead | Open |
| R-004 | Incident Response | No annual tabletop exercise | 2 | 4 | 8 | IT Director | Planned |

Scoring Formula: **Likelihood × Impact**

---

## Executive Dashboard Example (Embedded View)

### Risk Metrics
- Total Open Risks: 18  
- High Risks (Score ≥15): 4  
- Risks Accepted This Quarter: 2  
- Overdue Remediation Items: 3  

### Access Governance
- Quarterly Access Review Completion: 96%  
- Dormant Accounts Disabled: 42  
- Privileged Accounts Reviewed: 100%  
- MFA Coverage: 98%  

### Vendor Risk
- Critical Vendors Identified: 12  
- Vendors with Current SOC 2: 10  
- Vendors Pending Reassessment: 2  

### Incident Management
- Security Incidents This Quarter: 5  
- Mean Time to Contain (MTTC): 3.2 hours  
- Tabletop Exercises Conducted: 1  

### Control Health
- Controls Tested This Quarter: 22  
- Controls Passed: 20  
- Controls Requiring Remediation: 2  

---

## Project Artifacts (Downloadable Files)

- 📊 [Full Risk Register CSV](./risk_register_template.csv)
- 📈 [Executive Dashboard Metrics File](./executive_dashboard_metrics.md)

These artifacts demonstrate structured governance tracking, ownership accountability, and executive-level reporting.

---

## Strategic Positioning

This project demonstrates:

- Identity-driven collaboration governance  
- Practical risk management mechanics  
- Executive reporting alignment  
- Framework-mapped access control design  

Strong SharePoint governance is not a configuration exercise — it is an IAM architecture discipline.
