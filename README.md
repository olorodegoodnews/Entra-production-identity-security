# Entra-production-identity-security
Production-style Microsoft Entra identity security project covering Conditional Access, emergency access, PIM, policy testing, and security documentation.


# Production-Style Microsoft Entra Identity Security

## Overview

This project demonstrates the design and implementation of a production-style Microsoft Entra identity security environment.

The project focuses on identity security controls including emergency access, Conditional Access, privileged access management, policy validation, and security documentation.

## Objectives

- Establish emergency access accounts
- Implement an MFA baseline
- Block legacy authentication
- Implement device compliance controls
- Test Conditional Access policies using What If
- Validate policies using Report-only mode
- Implement privileged access controls
- Analyze overlapping Conditional Access policies
- Document the rationale behind each security policy

## Environment

| Component | Configuration |
|---|---|
| Identity Platform | Microsoft Entra ID |
| Tenant | Default Directory |
| Primary Domain | Project tenant `.onmicrosoft.com` domain |
| Entra License | Microsoft Entra ID P1 |
| Security Model | Production-style |

## Project Structure

- `project-overview.md` — project objectives and security approach
- `policies/` — Conditional Access policy documentation
- `pim/` — Privileged Identity Management documentation
- `testing/` — policy testing and validation
