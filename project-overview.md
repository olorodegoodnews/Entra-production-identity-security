# Production-Style Microsoft Entra Identity Security

## Project Overview

This project implements a production-style Microsoft Entra identity security environment.

The project focuses on identity protection, Conditional Access, emergency access, privileged access management, policy testing, and security documentation.

## Objectives

- Establish secure emergency access accounts
- Implement a Microsoft Entra MFA baseline
- Block legacy authentication
- Implement device-based access controls
- Test Conditional Access policies using What If
- Validate policies using Report-only mode
- Implement Privileged Identity Management where licensing permits
- Analyze overlapping Conditional Access policies
- Document the security rationale for each policy

## Environment

- Microsoft Entra ID
- Microsoft Entra ID P1
- Dedicated project tenant
- Production-style identity configuration

## Security Approach

All security controls will be tested before enforcement where possible.

Conditional Access policies will use exclusions for emergency access accounts where appropriate.

Each policy will have documented:

- Purpose
- Security threat
- Scope
- Exclusions
- Access controls
- Testing results
- Expected user experience
- Security rationale
