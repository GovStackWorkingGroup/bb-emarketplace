---
description: >-
  This section will highlight important requirements or describe any additional
  cross-cutting requirements that apply to this Building Block.
---

# 5 Cross-Cutting Requirements

## 5.1 Personal Data Privacy (REQUIRED)

Personal data must be kept private and never shared with any parties, except where specific authorization has been granted. The Consent Building Block shall follow the privacy principles as laid out in the GovStack architecture and security recommendations.

## 5.2 All transactions must be Audit Logged  (RECOMMENDED)

Logs should be kept in a database of all created, updated, or deleted records. Logs must include timestamps and identify the user and affiliation that performed the transaction.

All audit logs shall be integrity-protected against tampering. The Consent Building Block shall follow the data policy and audit logging requirements as required by local policies.

## 5.3 Rollback capability (RECOMMENDED)

The Building Block must perform various activities starting from initiation of purchase request/expression of interest to completion of order with feedback etc. In case of any non-compliance (due to both technical and functional reasons), it should be able to roll back to the initial state to safeguard the integrity of the application.

