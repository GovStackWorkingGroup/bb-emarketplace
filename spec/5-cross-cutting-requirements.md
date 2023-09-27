---
description: >-
  This section will highlight important requirements or describe any additional
  cross-cutting requirements that apply to this Building Block.
---

# 5 Cross-Cutting Requirements

## 5.1 TODO

Personal data MUST be kept private and never shared with any parties, except where specific authorisation has been granted. The Consent BB shall follow the privacy principles as laid out in the Govstack architecture.

## 5.2 TODO (RECOMMENDED)

Logs SHOULD be kept in a database of all created, updated, or deleted records. Logs MUST include timestamps and identify the user and affiliation that performed the transaction.

All audit logs shall be integrity protected against tampering. The Consent BB shall follow the data policy and audit logging requirements as laid out in the Govstack architecture.

### <mark style="color:blue;">5.2 Scaling (OPTIONAL)</mark>

<mark style="color:blue;">The building block's hardware environment should be able to fulfil the future requirements, integration of multiple requests from departments in order to efficiently perform the operations.</mark>

### <mark style="color:blue;">5.3 Lifecycle activities (RECOMMENDED)</mark>

<mark style="color:blue;">The BB must perform various activities starting from initiation of purchase request/expression of interest to completion of order with feedback etc. In case of any non-compliance (due to both technical and functional reasons), it should be able to roll-back to initial state to safe guard the integrity of the application.</mark>

<mark style="color:green;">5.4 Accessibility (Arch 4.5 is not clear about the below aspect)</mark>

<mark style="color:green;">The BB shall be accessible on various delivery channels such as Mobile, Kiosk, Web, Application and should be digitally inclusive for users with different capabilities.</mark>

<mark style="color:green;">5.5 Robust (Arch 4.7)</mark>

<mark style="color:green;">The BB's minor features such as physical delivery of goods and services, client feedback etc. should be able to work on feature phones (without internet) as well.</mark>

<mark style="color:green;">5.6 Restoration is not mentioned even in Security (SEC 4.2.5 : Is RECOVER is equivalent to RESTORE?)</mark>

<mark style="color:green;">5.7 Why is that Adaptors not mentioned in SEC 6 BB Modules? Are Connectors and Adaptors same?</mark>

## 5.X Standards





