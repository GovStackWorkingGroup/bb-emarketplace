---
description: >-
  This section will highlight important requirements or describe any additional
  cross-cutting requirements that apply to this Building Block.
---

# 5 Cross-Cutting Requirements

{% hint style="success" %}
The Cross-cutting requirements described in this section are an extension of the cross-cutting requirements defined in the architecture blueprint and nonfunctional requirements document. This section will describe any additional cross-cutting requirements that apply to this building block, or any requirements that are defined in the non-functional requirements document that are NOT applicable to this Building Block.

Cross-cutting requirements will use the same language (REQUIRED, RECOMMENDED or OPTIONAL) as specified in the architecture document.
{% endhint %}

_\<Example Cross-Cutting Requirements>_

## 5.1 TODO

Personal data MUST be kept private and never shared with any parties, except where specific authorisation has been granted. The Consent BB shall follow the privacy principles as laid out in the Govstack architecture.

## 5.2 TODO (RECOMMENDED)

Logs SHOULD be kept in a database of all created, updated, or deleted records. Logs MUST include timestamps and identify the user and affiliation that performed the transaction.

All audit logs shall be integrity protected against tampering. The Consent BB shall follow the data policy and audit logging requirements as laid out in the Govstack architecture.

### <mark style="color:blue;">5.1 Security and Privacy (RECOMMENDED)</mark>

<mark style="color:blue;">The building block must respect the country/regional level legal mandates, facilitated by the various activities performed by the BB and by multiple interactions with other BBs such as Information Mediator, Payments, Digital Identity and Verification, and others.</mark>

### <mark style="color:blue;">5.2 Scaling (OPTIONAL)</mark>

<mark style="color:blue;">The building block's hardware environment should be able to fulfil the future requirements, integration of multiple requests from departments in order to efficiently perform the operations.</mark>

### <mark style="color:blue;">5.3 Lifecycle activities (RECOMMENDED)</mark>

<mark style="color:blue;">The BB must perform various activities starting from initiation of purchase request/expression of interest to completion of order with feedback etc. In case of any non-compliance (due to both technical and functional reasons), it should be able to roll-back to initial state to safe guard the integrity of the application.</mark>
