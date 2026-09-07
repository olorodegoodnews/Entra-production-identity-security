# Privileged Identity Management (PIM) Implementation

## Objective

Implement just-in-time privileged access for Microsoft Entra administrative roles.

The goal is to reduce permanent privileged access by requiring administrators to activate privileged roles only when needed.

---

# PIM Security Model

Traditional privileged access:

```text
Administrator
     ↓
Permanent Global Administrator
     ↓
Continuous privileged access
