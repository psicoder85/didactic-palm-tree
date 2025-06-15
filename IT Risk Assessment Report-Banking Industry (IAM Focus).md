> **Disclaimer:**  
> This IT Risk Assessment Report is an illustrative example prepared strictly for educational, evaluative, and consulting demonstration purposes. It is based on standard risk management frameworks, real-world methodologies, and professional experience with past clients.  
>   
> In strict adherence to the principles of the **CIA triad (Confidentiality, Integrity, and Availability)** and professional codes of conduct, **no proprietary, classified, or client-identifiable information** has been disclosed or included.  
>   
> All data, systems, names, and scenarios have been either generalized or anonymized to preserve confidentiality, respect legal obligations, and comply with applicable corporate data protection policies and regional regulations.

# IT Risk Assessment Report – Banking Industry (IAM Focus)

## 1. Executive Summary

This IT Risk Assessment was conducted for a multinational banking institution with a critical focus on its Identity and Access Management (IAM) infrastructure. Given the organization’s exposure to regulatory oversight and the sensitivity of financial and personal data it handles, the assessment was designed to identify and evaluate risks related to user access lifecycle, privileged access, multi-factor authentication, and federated identity systems across on-premises and cloud environments.

The assessment aligned with internationally recognized frameworks, including ISO/IEC 27001:2022, NIST SP 800-53 Rev. 5, and guidance from FFIEC and Basel II standards. The scope spanned internal employee systems, third-party vendor access, and IAM integrations with customer-facing applications.

The assessment process involved:

 - A review of Joiner-Mover-Leaver (JML) processes.

 - Evaluation of technical controls and monitoring tools.

 - Interviews with cross-functional stakeholders including the IAM team, SOC, IT operations, and compliance staff.

 - Detailed gap analysis comparing existing controls with regulatory and best practice benchmarks.

The top risks identified included orphaned accounts post-termination, excessive administrative privileges, weak onboarding/offboarding automation, insufficient PAM coverage, and lack of real-time analytics on IAM events. Particular attention was paid to IAM integration across legacy systems and new cloud infrastructure where conditional access policies were inconsistently applied.

Each risk was evaluated for likelihood and impact, with prioritization determined using a calibrated risk matrix. Recommendations emphasize automation, centralized control, improved audit logging, and clear accountability for access management decisions.

By addressing the identified risks, the bank will be better positioned to prevent unauthorized access, reduce insider threat exposure, and comply with stringent regulatory mandates.

## 2. Objective

The primary objective of this IT Risk Assessment is to evaluate the effectiveness, consistency, and maturity of the Identity and Access Management (IAM) framework within a multinational banking institution. This includes assessing the risks related to user provisioning, privileged access, identity federation, multi-factor authentication (MFA), and integration with legacy and cloud-based applications.
To identify, evaluate, and prioritize risks related to identity lifecycle management, privileged access, multi-factor authentication (MFA), and directory services integration.

Additionally, the objective is to:
1. **Ensure compliance with regulatory requirements such as**
   - ISO/IEC 27001 & ISO/IEC 27002
   - NIST SP 800-53 Rev. 5
   - FFIEC IT Handbook (IAM section)
   - SOC 2 Trust Services Criteria (Security and Confidentiality)
   - NIS2 Directive (where applicable)

2. **Identify technical and procedural weaknesses that could expose the institution to data breaches, insider threats, or audit nonconformities.**

3. **Provide actionable recommendations to improve access governance and reduce risk exposure.**

## 3. Methodology

The assessment was conducted using a hybrid qualitative and semi-quantitative risk analysis approach, aligned with industry best practices from **ISO/IEC 27005** and the **NIST Risk Management Framework (RMF)**.

#### Approach

- **Frameworks Applied:**  
  - ISO/IEC 27001:2022  
  - NIST Cybersecurity Framework (CSF)  
  - COBIT 2019 for IT Governance and Control  

- **Assessment Tools:**  
  - Structured interviews with key stakeholders  
  - Control mapping against established frameworks  
  - Joiner-Mover-Leaver (JML) process analysis  
  - Directory services audits  
  - Review of authentication and access logs  

- **Risk Rating Matrix:**  
  Risks were evaluated by combining *Likelihood* and *Impact* to determine overall *Risk Level*, categorized as:  
  - Low  
  - Medium  
  - High  
  - Critical  

- **Process Flows Reviewed:**  
  - IAM architectural design and implementation  
  - User provisioning and deprovisioning workflows  
  - Policy enforcement mechanisms  
  - Third-party and vendor access controls  

#### Techniques Used

- **Structured Interviews:** Conducted with teams from IAM, Security Operations Center (SOC), Human Resources, Legal, and IT Infrastructure to gather process insights and verify control effectiveness.

- **Document Analysis:** Reviewed IAM policies, periodic access review logs, audit findings, and compliance reports to assess governance and operational adherence.

- **Workflow Reviews:** Examined Joiner-Mover-Leaver (JML) procedures and privileged access management workflows to identify gaps and inefficiencies.

- **Control Mapping and Maturity Scoring:** Mapped existing controls to framework requirements and scored maturity on a 5-point scale (from initial/ad hoc to optimized/automated).

- **Threat Modeling:** Analyzed potential attack vectors and insider threats related to identity management, applying a likelihood-impact risk matrix for prioritization.

#### Tools

- IAM audit checklists for comprehensive coverage  
- Governance, Risk, and Compliance (GRC) platforms to centralize evidence collection and document workflows  
- Identity analytics dashboards for manual review of user activity, access patterns, and anomalies  


## 4. Scope

The assessment encompassed identity and access management processes across the organization, with an emphasis on sensitive and regulated environments. The systems and control areas assessed include:

#### User Identity Lifecycle:

- Provisioning, modification, and deprovisioning processes

- Integration with HRIS and ticketing systems

#### Privileged Access Management (PAM):

- Administrative rights management

- Monitoring and session recording

#### Authentication Mechanisms:

- MFA enforcement

- Conditional access and geofencing

- Federation and SSO for internal and external platforms

#### IAM Logging & Auditing:

- Logging practices for access attempts and changes

- Access review frequency and escalation procedures

#### IAM Governance:

- Ownership and accountability for access control policies

- Role definition, segregation of duties, and recertification

The scope also included cloud IAM integrations (e.g., Azure AD), third-party access controls, and customer-facing portals where IAM plays a critical role in trust and compliance.

## 5. Risk Identification & Evaluation

| Risk ID | Risk Description                                             | Likelihood | Impact | Risk Level  | Existing Controls                        | Risk Owner      |
|---------|--------------------------------------------------------------|------------|--------|-------------|------------------------------------------|------------------|
| R1      | Orphaned accounts after offboarding                          | High       | High   | Critical    | Manual deprovisioning                    | HR & IAM Team    |
| R2      | Privileged accounts without time-bound access                | Medium     | High   | High        | Admin roles not limited in duration      | IAM Admin        |
| R3      | Inconsistent MFA enforcement for high-risk apps              | Medium     | High   | High        | Conditional access only partly applied   | Security Ops     |
| R4      | Poor audit trail for IAM changes                             | Medium     | Medium | Medium      | Event logs not centralized               | Compliance       |
| R5      | Shadow IT and unmanaged third-party identities               | Medium     | High   | High        | Lack of vendor onboarding controls       | Vendor Risk Mgt  |
| R6      | Inactive user accounts with stale permissions                | Medium     | High   | High        | No automated inactivity purge              | IAM Governance      |
| R7      | Use of shared accounts for operations or batch jobs          | High       | Medium | High        | Generic credentials in legacy systems      | Infrastructure Team |
| R8      | Misconfigured SSO integrations (e.g., incomplete SAML setup) | Medium     | High   | High        | Lack of validation/testing process         | Application Owners  |
| R9      | Delayed revocation of access during internal transfers       | Medium     | Medium | Medium      | Manual change requests to IT               | HR Business Partner |
| R10     | No centralized visibility into cross-platform entitlements   | Medium     | High   | High        | IAM dashboards missing multi-system view   | IAM Program Lead    |

## 6. Prioritization & Recommendations

### Priority 1: Orphaned Accounts (R1)

**Findings:**
- Departed employees still have valid credentials in AD, Azure AD, and some SaaS apps even after 2 months. At least 15 days is too much.
- Risk of insider threat and unauthorized access.

**Recommendations:**
- Integrate HRIS with IAM platform (e.g., SailPoint, Saviynt)
- Automate deprovisioning and credential revocation
- Run weekly orphaned account reconciliation

-----

### Priority 2: Privileged Access (R2)

**Findings:**
- Domain admins have persistent privileges
- Lack of PAM segmentation

**Recommendations:**
- Implement PAM solution (CyberArk, BeyondTrust, or similar)
- Enforce just-in-time (JIT) elevation with session recording
- Conduct quarterly access reviews and revoke unused roles

-----

### Priority 3: MFA Coverage (R3)

**Findings:**
- MFA not enforced for all admin portals
- Some mobile devices bypass conditional access

**Recommendations:**
- Enforce hardware-backed MFA (FIDO2, smartcards)
- Expand conditional access coverage to all high-risk endpoints
- Review exceptions every 30 days

-----

### Priority 4: IAM Change Audit Trails (R4)

**Findings:**
- IAM logs are distributed across platforms
- No centralized SIEM integration

**Recommendations:**
- Centralize IAM logs in SIEM (e.g., Microsoft Sentinel, Splunk)
- Enable immutable audit logs
- Define alert thresholds for sensitive operations

-----

### Priority 5: Third-Party Identity Governance (R5)

**Findings:**
- Third-party users are created manually with shared credentials
- No onboarding/offboarding workflow

**Recommendations:**
- Implement vendor IAM policies
- Require identity verification and access time-boxing
- Extend JML to third-party systems

-------

### Priority 6: Inactive User Accounts (R6)
- **Risk Summary:** Dormant accounts with retained access increase the risk of credential misuse and lateral movement in the event of compromise.
- **Recommendations:**
  - Implement automated user inactivity tracking and account disabling after a defined period (e.g., 30–60 days).
  - Integrate IAM with HRIS to synchronize employment status and trigger account suspension workflows.
  - Conduct monthly reviews of inactive accounts across all platforms and purge if noncompliant.
 
---------

### Priority 7: Shared Accounts in Legacy Systems (R7)
- **Risk Summary:** Shared credentials prevent individual accountability and are prone to misuse or breach, violating multiple compliance requirements.
- **Recommendations:**
  - Transition from shared credentials to role-based access using unique accounts and session-based service accounts.
  - Enforce logging and monitoring on legacy systems where shared accounts remain temporarily necessary.
  - Include shared account removal in the IAM roadmap and deprecate legacy systems accordingly.

---------

### Priority 8: Misconfigured SSO Integrations (R8)
- **Risk Summary:** Partial or misconfigured SSO implementations (e.g., incorrect SAML attributes or token lifetimes) can lead to unauthorized access or SSO bypass.
- **Recommendations:**
  - Mandate validation and certification procedures before onboarding any app into SSO.
  - Standardize token duration, attribute mapping, and logout redirection protocols across platforms.
  - Include SSO configurations in annual IAM audits.
 
---------

### Priority 9: Delayed Role Revocation During Transfers (R9)
- **Risk Summary:** Employees changing roles often retain previous entitlements, causing privilege accumulation and increasing insider threat risk.
- **Recommendations:**
  - Integrate HR role change workflows with IAM role reassignment.
  - Implement policy that automatically revokes obsolete roles during a job transition.
  - Require managerial approval and periodic certification for access retention post-transfer.
 
----------

### Priority 10: Lack of Centralized Entitlement Visibility (R10)
- **Risk Summary:** Disparate access systems create visibility gaps, hindering enforcement of least privilege and raising audit nonconformities.
- **Recommendations:**
  - Deploy cross-platform IAM dashboards aggregating access data from all critical systems (e.g., AD, Azure, SAP).
  - Use entitlement correlation tools to map and visualize risk exposure.
  - Introduce periodic attestation campaigns targeting high-risk entitlements and accounts.
  

## 7. Compliance Mapping Summary

| Standard / Framework     | Controls Addressed                         |
|--------------------------|--------------------------------------------|
| ISO/IEC 27001 & 27002    | A.9 Access Control, A.12 Operations Security |
| NIST SP 800-53           | AC-1 to AC-6, IA-2, IA-5, AU-2              |
| SOC 2                    | CC6.1 (Access), CC7.1 (Monitoring)         |
| FFIEC                    | Identity & Access Management section       |
| NIS2                     | Access Management, Incident Reporting      |

## 8. Conclusion

The current IAM posture contains critical gaps that may lead to audit findings and compromise the security of banking operations. By remediating these high-priority risks through automated provisioning, modern MFA strategies, and PAM integration, the institution will enhance its access governance and resilience against insider threats and regulatory violations.

This risk assessment confirms that the current Identity and Access Management (IAM) program demonstrates foundational controls but lacks full maturity and integration required by today’s complex regulatory and threat landscape. While existing technical teams and policies are well intentioned, gaps in consistency, automation, and documentation create vulnerabilities that could be exploited both internally and externally.

Mitigating these risks through the prioritized recommendations will:

 - Strengthen security posture and align with regulatory frameworks.

 - Enable a smoother audit process for financial and cybersecurity compliance.

 - Reduce operational inefficiencies related to manual access governance.

 - Provide leadership with clear, measurable steps to enhance oversight.

Moving forward, adopting a risk-driven IAM roadmap, backed by executive sponsorship, automation tools (e.g., PAM, IGA platforms), and robust documentation practices will help the bank transition to a proactive, resilient, and audit-ready identity governance program.

## 9. Next Steps

To ensure timely and effective remediation of the risks identified in this report, the following next steps are recommended:

To operationalize this risk assessment and drive continuous improvement in security posture, the following steps are recommended:

1. **Action Plan Development**  
   Assign ownership for each high and critical risk. Develop detailed remediation plans with scope, deadlines, and required resources.

2. **IAM Steering Committee Review**  
   Present key findings, control deficiencies, and proposed actions to the IAM Steering Committee for validation, prioritization, and governance alignment.

3. **Risk Treatment Plan (RTP)**  
   Document treatment strategies (e.g., mitigate, accept, transfer, avoid) in alignment with ISO/IEC 27001 and HIPAA standards. Ensure each control has an assigned risk owner and target deadline.

4. **Roadmap Development**  
   Develop both 6-month and 12-month maturity improvement roadmaps. Align efforts with business strategy, audit cycles, and compliance timelines.

5. **Track Key Performance Indicators (KPIs)**  
   Begin continuous monitoring of measurable metrics including:
   - **Mean Time to Deprovision (MTTD)**
   - **Privilege Elevation Review Frequency**
   - **MFA Coverage Rate**
   - **% of Automated Provisioning**

6. **Control Implementation & Training**  
   Roll out technical, administrative, and procedural controls. Ensure all stakeholders are trained and informed on policy changes and new responsibilities.

7. **Schedule Reassessment**  
   Establish a cadence of **quarterly reassessments** and **biannual control effectiveness reviews**. Integrate findings into the enterprise risk register.

8. **Audit & Certification Preparation**  
   Ensure all remediation steps are auditable. Prepare evidence for internal and external compliance audits (HIPAA, ISO 27001, SOC 2, etc.).

-----

## 9. Appendices

### Appendix A – Risk Matrix Key

| Risk Level | Description                                  |
|------------|----------------------------------------------|
| Low        | Minimal impact or likelihood; monitor only   |
| Medium     | Manageable; requires periodic review         |
| High       | Significant; requires planned mitigation     |
| Critical   | Severe; immediate action required            |

### Appendix B – Acronyms and Definitions

- **IAM** – Identity and Access Management  
- **JML** – Joiner, Mover, Leaver  
- **GRC** – Governance, Risk, and Compliance  
- **RTP** – Risk Treatment Plan  
- **PII** – Personally Identifiable Information  

### Appendix C – References

- ISO/IEC 27001:2022 – Information Security Management  
- NIST SP 800-53 Rev. 5 – Security and Privacy Controls  
- NIST Cybersecurity Framework (CSF)  
- HIPAA Security Rule and Privacy Rule  
- COBIT 2019 – Governance and Management of Enterprise IT
  
---

> **Assessment Statement**  
>  
> This IT Risk Assessment was conducted by **Jair Abrego Cubilla** in collaboration with other certified professionals, using a combination of vendor-agnostic tools, standard methodologies and authorized proprietary tools to ensure neutrality, accuracy, and relevance.  
>  
> The contents of this report are intended solely for informational, educational, and internal planning purposes. While every effort has been made to ensure that the findings, evaluations, and recommendations align with leading frameworks such as ISO/IEC 27001, NIST, HIPAA, SOC 2, and others, this document does **not** constitute a legally binding opinion or professional certification.  
>  
> The report is provided **as-is** and does not imply any warranty or legal responsibility. Any proprietary references or examples are illustrative and anonymized, and no confidential client data has been included or disclosed. All recommendations should be further evaluated and adapted by internal stakeholders and legal counsel before implementation.

