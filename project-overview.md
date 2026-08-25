# Production-Style Microsoft Entra Identity Security

## Project Overview

This project implements a production-style Microsoft Entra identity security environment.

The environment is treated as a production identity environment rather than a sandbox. Security controls are designed, tested, validated, and documented before enforcement.

## Project Objectives

- Build Conditional Access policies from scratch
- Configure break-glass exclusions
- Establish an MFA baseline
- Require device compliance
- Block legacy authentication
- Implement risk-based Conditional Access policies
- Validate policies using What-If
- Validate policies using Report-only mode
- Configure Privileged Identity Management for Global Administrator
- Configure PIM for one Azure resource role
- Require approval and justification for privileged activation
- Analyze the behavior of three overlapping Conditional Access policies
- Produce a one-page security rationale for each policy

## Environment

| Component | Configuration |
|---|---|
| Identity platform | Microsoft Entra ID |
| Tenant | Default Directory |
| Primary domain | olorodegoodnews797gmail.onmicrosoft.com |
| Entra license | Microsoft Entra ID P1 |
| Environment model | Production-style |

## Security Approach

Conditional Access policies will be created from scratch and tested before enforcement.

What-If and Report-only mode will be used to validate policy behavior.

Break-glass accounts will be excluded from applicable policies to reduce the risk of administrative lockout.

Privileged administrative access will be controlled using Microsoft Entra Privileged Identity Management where the required licensing is available.

## Success Criteria

The project will be considered successful when the implemented policies can be tested and explained, including a scenario where three Conditional Access policies apply to the same sign-in.

The final test will demonstrate how the applicable policies combine to produce the resulting access decision.

