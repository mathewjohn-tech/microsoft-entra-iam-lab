# microsoft-entra-iam-lab
# Microsoft Entra ID – Identity & Access Management (IAM) Lab

## Project Overview

This project demonstrates the implementation of identity and access management (IAM) controls in a simulated corporate environment using Microsoft Entra ID.

The lab models **SecureTech Solutions**, a fictional organization with Finance and Human Resources departments. The objective was to provision employee identities, organize users into security groups, configure application access, implement SAML 2.0 Single Sign-On (SSO), and validate authentication and authorization controls.

## Technologies Used

- Microsoft Entra ID (Free)
- Microsoft Entra Admin Center
- SAML 2.0
- Microsoft Entra SAML Toolkit
- Enterprise Applications
- Security Groups
- Microsoft Entra Sign-in Logs

## Lab Environment

**Organization:** SecureTech Solutions (Simulated)

| User | Department | Security Group |
|---|---|---|
| Sarah Johnson | Finance | Finance-Employees |
| Emily Davis | Human Resources | HR-Employees |

Two departmental security groups were created to organize employee identities.

Because Microsoft Entra ID Free does not support group-based enterprise application assignment in this environment, application access was configured using direct user assignments.

## Implementation

### 1. User Provisioning

Created fictional employee accounts in Microsoft Entra ID and configured organizational attributes, including department, job title, and company name.

### 2. Security Group Management

Created the `Finance-Employees` and `HR-Employees` security groups and assigned users according to their departments.

### 3. Enterprise Application Access

Created a simulated Finance Portal enterprise application and assigned Sarah Johnson access.

Configured the Microsoft Entra SAML Toolkit enterprise application with **Assignment required** enabled. Sarah was assigned access, while Emily remained unassigned.

### 4. SAML 2.0 Single Sign-On

Integrated Microsoft Entra ID with the Microsoft Entra SAML Toolkit test application.

Configured the SAML Entity ID, Assertion Consumer Service (ACS) URL, Sign-on URL, identity provider endpoints, and token-signing certificate.

### 5. Authentication and Authorization Testing

Tested application access using two employee identities.

| Test Case | Expected Result | Observed Result |
|---|---|---|
| Sarah Johnson – Assigned user | Successful SSO authentication | Passed |
| Emily Davis – Unassigned user | Access denied | Passed |

Sarah's successful authentication was verified using Microsoft Entra sign-in logs.

Emily's access was blocked with **AADSTS50105**, confirming that the enterprise application's user-assignment requirement was enforced.

## Security Concepts Demonstrated

- Identity provisioning and user administration
- Security group management
- SAML 2.0 federation and Single Sign-On
- Authentication versus authorization
- Application access restrictions
- Least-privilege access principles
- Sign-in log analysis and authentication troubleshooting

## Key Takeaways

This lab provided hands-on experience configuring cloud identity services and validating application access restrictions.

It demonstrated how Microsoft Entra ID can serve as an identity provider for SAML-enabled applications and enforce access requirements based on administrator-controlled assignments.

## Future Improvements

- Simulate employee onboarding, transfers, and offboarding
- Conduct manual user access reviews
- Investigate additional authentication events
- Document identity lifecycle management procedures

---

**Disclaimer:** This project was completed in a personal lab using fictional employee identities. It does not represent a production deployment.
