# Conditional Access Test Identity

## Purpose

A dedicated test identity is used to validate Conditional Access policies without using the primary administrative account.

## Test Account

- Display name: CA-Test-User
- User principal name: ca-test-user@olorodegoodnews797gmail.onmicrosoft.com
- Administrative role: None

## Usage

The account will be used to test:

- MFA requirements
- Device compliance requirements
- Legacy authentication blocking
- Risk-based Conditional Access
- What-If results
- Report-only results
- Overlapping Conditional Access policies

## Security Consideration

The test identity does not receive privileged administrative roles. This limits the impact of testing while allowing realistic Conditional Access evaluation.
