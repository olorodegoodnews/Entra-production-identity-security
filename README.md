# Microsoft Entra ID Production-Style Identity Security Lab

## Documentation Overview

This project demonstrates the implementation of a production-style Microsoft Entra ID identity and access management environment.

A dedicated Microsoft Entra tenant was configured and treated as a production environment rather than a sandbox. The project focuses on Conditional Access, identity protection, device compliance, privileged access management, and security validation.

The implementation follows a controlled deployment approach by configuring security policies in Report-only mode and validating policy behavior before enforcement.

---

# Documentation Objectives

The project was designed to implement and demonstrate:

- Dedicated Microsoft Entra ID tenant administration
- Emergency break-glass access
- Conditional Access policies built from scratch
- Multifactor authentication baseline
- Device compliance controls
- Legacy authentication blocking
- Sign-in risk protection
- User risk remediation
- Conditional Access What-If testing
- Report-only policy validation
- Conditional Access policy overlap analysis
- Privileged Identity Management for Global Administrator
- Approval and justification for privileged role activation
- GitHub documentation of the implementation

---

# Architecture

```text
                         Microsoft Entra ID
                                │
        ┌───────────────────────┼────────────────────────┐
        │                       │                        │
        ▼                       ▼                        ▼
   Identity Security      Conditional Access       Privileged Access
        │                       │                        │
        │                       │                        │
        ▼                       ▼                        ▼
   Break-Glass Account     CA-01 MFA Baseline      PIM Global Admin
                           CA-02 Device Compliance
                           CA-03 Block Legacy Auth
                           CA-04 Sign-in Risk
                           CA-05 User Risk



Security Design
Break-Glass Account

A dedicated emergency administrative account was created:

BG-Admin-01

The account is excluded from applicable Conditional Access policies to provide emergency administrative access if a policy configuration causes unintended lockout.

The break-glass account is not intended for normal administrative activity.

View Break-Glass Documentation



Conditional Access Policies

Five Conditional Access policies were created using a Report-only deployment approach.

Policy	Purpose	State
CA-01	MFA Baseline	Report-only
CA-02	Device Compliance	Report-only
CA-03	Block Legacy Authentication	Report-only
CA-04	Sign-in Risk Protection	Report-only
CA-05	User Risk Remediation	Report-only
CA-01 — MFA Baseline

The MFA baseline policy requires multifactor authentication for users accessing protected resources.

The break-glass account is excluded to prevent accidental administrative lockout.

View Policy Documentation



CA-02 — Device Compliance

This policy requires devices to be marked as compliant before access is granted.

Microsoft Intune was configured to support device compliance evaluation.

The policy was validated using Conditional Access What-If testing.

View Device Compliance Documentation



CA-03 — Block Legacy Authentication

Legacy authentication clients were targeted using Conditional Access.

The policy blocks:

Exchange ActiveSync clients
Other legacy authentication clients

Modern browser authentication was tested to confirm that it was not unnecessarily targeted.

View Legacy Authentication Documentation



CA-04 — Sign-in Risk Protection

The policy responds to elevated sign-in risk detected by Microsoft Entra Identity Protection.

Configuration:

Medium sign-in risk
High sign-in risk
Require MFA
Report-only deployment

View Sign-in Risk Documentation



CA-05 — User Risk Remediation

This policy responds when a user account reaches a High user risk level.

Configuration:

High user risk
Require risk remediation
Report-only deployment

View User Risk Documentation



Conditional Access Validation

All Conditional Access policies were initially deployed using Report-only mode.

Testing included:

Conditional Access What-If
Targeted user testing
Break-glass exclusion testing
Modern authentication validation
Policy overlap analysis

This approach allowed policy behavior to be evaluated before enforcement.



Policy Overlap Testing

One of the main objectives of this project was understanding how multiple Conditional Access policies interact.

Conditional Access does not use a simple priority system where one policy automatically overrides another.

All applicable policies are evaluated.

Example:

CA-01 applies
     ↓
Require MFA

CA-02 applies
     ↓
Require compliant device

Final Result
     ↓
MFA + Compliant Device

The user must satisfy all applicable grant controls.

If any applicable Conditional Access policy blocks access, the sign-in is blocked.

View Policy Overlap Testing



Microsoft Intune Device Compliance

Microsoft Intune was configured to support device compliance testing.

The implementation included:

Dedicated Intune test group
MDM user scope configuration
Windows compliance policy
Microsoft Entra device join testing

A Windows 11 Pro device was successfully joined to Microsoft Entra ID.

During initial testing:

Microsoft Entra Join: Successful
MDM Enrollment: Not completed
Compliance Status: N/A

This demonstrated an important distinction:

A device can successfully join Microsoft Entra ID without automatically becoming managed by Microsoft Intune.

The limitation was documented rather than hidden.

View Intune Documentation



Privileged Identity Management

Privileged Identity Management was configured for the Global Administrator role.

The implementation demonstrated:

Eligible role assignment
Just-in-time activation
Justification requirement
Approval workflow
Separate approver
Temporary privileged access
Eligible User
     ↓
Requests Global Administrator activation
     ↓
Provides justification
     ↓
Approval required
     ↓
Temporary privileged access granted
     ↓
Role automatically expires

View PIM Documentation

Azure Resource Role PIM Limitation

The original project design included PIM for an Azure resource role.

This portion was not implemented because the dedicated Microsoft Entra lab tenant does not currently have an Azure subscription.

The Microsoft Entra Global Administrator PIM implementation was completed successfully.

Testing Methodology
Test	Purpose
What-If Testing	Validate Conditional Access scope
Report-only Mode	Evaluate policy impact safely
Test User	Confirm targeted policy behavior
Break-Glass Account	Confirm emergency account exclusions
Modern Authentication Test	Confirm legacy policy scope
Policy Overlap Test	Understand combined policy requirements
PIM Activation Test	Validate approval and justification workflow
Conditional Access policy configurations
What-If test results
Report-only policy results
Intune MDM configuration
Microsoft Entra device join
PIM eligible assignment
PIM approval workflow
Temporary Global Administrator activation
