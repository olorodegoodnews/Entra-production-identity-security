# Microsoft Entra ID Production-Style Identity Security Lab

## Project Overview

This project demonstrates the implementation of a production-style Microsoft Entra ID identity and access management environment.

A dedicated Microsoft Entra tenant was configured and treated as a production environment rather than a sandbox. The project focuses on Conditional Access, identity protection, device compliance, privileged access management, and security validation.

The implementation follows a controlled deployment approach by configuring security policies in Report-only mode and validating policy behavior before enforcement.

---

# Project Objectives

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
