---
description: >-
  This section provides a reference for APIs that should be implemented by this
  Building Block.
---

# 8 Service APIs

This section provides a reference for APIs that should be implemented by this Building Block. The APIs defined here establish a blueprint for how the Building Block will interact with other Building Blocks. Additional APIs may be implemented by the Building Block, but the listed APIs define a minimal set of functionality that should be provided by any implementation of this Building Block.&#x20;

To develop the E-Marketplace Building Block API, we have referred to various open-source specifications and data standards. The objective is to develop an API specification for this building block that is future-proof to accommodate a broad range of use cases that is agnostic of industry sector, region, and implementation technology.&#x20;

To develop a common data standard, Several sector-specific marketplace specifications were referred to like [NetEx](https://www.transmodel-cen.eu/netex-standard/), [TOMP](https://github.com/TOMP-WG/TOMP-API), (for mobility), [Electronic Data Interchange](https://www.edibasics.com/what-is-edi/) for logistics, [Open Contracting and Data Standards](https://www.open-contracting.org/data-standard/) (OCDS), [Universal Business Language](http://docs.oasis-open.org/ubl/UBL-2.1.html) (UBL) for procurements, [HL7 / FHIR ](https://www.hl7.org/implement/standards/index.cfm?ref=nav)for healthcare. &#x20;

To understand activities involved in administering the e-marketplace, several open-source e-marketplace software APIs like [Magento](https://business.adobe.com/products/magento/magento-commerce.html), [WooCommerce](https://woocommerce.com/), and [OpenCart](https://www.opencart.com/), were also referred.

To facilitate interoperability, we have referred to various open-source communication protocols, API and data standards like, [Schema.org](http://schema.org/) , [HTTP/2](https://datatracker.ietf.org/doc/html/rfc9113), and [DNS](https://datatracker.ietf.org/doc/html/rfc1035) and [Beckn protocol](https://becknprotocol.io/).&#x20;

Privacy and Security is especially important to Government E-marketplaces as they usually contain sensitive information about customers and businesses. In such a scenario, it is not recommended to create a “store-of-value” in between the consumer and the marketplace. Instead a more federated approach is needed that transforms a “Store-of-value” into a “Flow-of-value”. Such an architecture will ensure privacy and security of data, minimize concentration risk, and allow for innovation to happen at the edges rather than at the center.&#x20;

The E-Marketplace building block API specification has been _adapted_ from Beckn protocol APIs and schema. Currently Beckn protocol is the only open-source specification that enables transaction interoperability in e-marketplaces through a peer-to-peer (flow-of-value) protocol. It is an open-source generic transaction protocol that when implemented, allows any application to perform discovery, ordering, fulfillment, and post-fulfillment activities _without_ the need of a central intermediary. It is a widely adopted open-source protocol specification built using design principles and standards from all of the above mentioned technologies and standards. It is agnostic of industry sector, region, or implementation technology. It is highly recommended for any e-marketplace application in GovStack to also implement a Beckn protocol interface to allow any platform inside or outside the GovStack ecosystem to access the e-marketplace without the need of a central platform intermediary. Furthermore, It can be adapted to any existing sector-specific standard like the ones mentioned above. The [GovStack non-functional requirements](https://govstack.gitbook.io/specification/architecture-and-nonfunctional-requirements/6-onboarding) document provides additional information on how 'adaptors' may be used to translate an existing API to the patterns described here.

## 8.1 Catalog Management

Platform Administration APIs consist of all the endpoints that are used to provide user experience and manage the business workflows like catalog management, cart management, checkout, terms management, content management, etc. These follow REST Standards for the creation, read, update, and deletion of objects in the database.&#x20;

### 8.1.1 Order lifecycle APIs

These APIs allow searching and browsing of an existing catalog.



{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/search" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

### 8.1.2 Service Administration APIs

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/catalog/{resource}/{id}" method="get" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/catalog/{resource}/{id}" method="put" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/catalog/{resource}/{id}" method="delete" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/catalog/{resource}" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/catalog/provider/{provider_id}/{resource}/{id}" method="get" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/catalog/provider/{provider_id}/{resource}/{id}" method="put" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/catalog/provider/{provider_id}/{resource}/{id}" method="delete" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/catalog/provider/{provider_id}/{resource}" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/inventory/check_availability/{resource}/{id}" method="get" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

## 8.2 Inventory Management

Since inventory is a provider-centric feature, it does not interface with a customer. However, it is called by other services like quotation management, order management, and fulfillment management services.

### 8.2.1 Service Administration APIs



{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/search" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/inventory/check_availability/{resource}/{id}" method="get" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/inventory/add" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/inventory/remove" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/inventory/block" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/inventory/unblock" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

## 8.3 Quotation Management



{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/quotation" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

## 8.4 Order Terms Management

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/terms/payment" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/terms/fulfillment" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/terms/cancellation" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

## 8.5 Order Management

### 8.5.1 Order Lifecycle APIs

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/select" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/init" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/confirm" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/status" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/track" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/cancel" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/update" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

### 8.5.2 Service Administration APIs

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/orders" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

## 8.6  Order Fulfillment

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/fulfillment" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/fulfillment/{order_id}" method="put" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/fulfillment/{order_id}" method="delete" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/fulfillment/check_serviceability" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/fulfillment/{order_id}/agent/allocate" method="put" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/fulfillment/{order_id}/agent/deallocate" method="delete" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

## 8.7 Order Tracking

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/tracking/start" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/tracking/stop" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/tracking/{order_id}/update_location" method="put" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

## 8.8 Order Cancellation

### 8.8.1 Order Lifecycle APIs

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/get_cancellation_reasons" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

## 8.9 Rating and Feedback Management

### 8.10.1 Order Lifecycle APIs



{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/rating" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/get_rating_categories" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

## 8.11 Feedback Management

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved (2).yaml" path="/feedback_form" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved (2).yaml](<.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved (2).yaml>)
{% endswagger %}

## 8.12 Support Management

### 8.11.1 Order Lifecycle APIs

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/support" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

### 8.11.2 Service Administration APIs



{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/search" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/support/{order_id}" method="get" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/support/{order_id}" method="put" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/support/{order_id}" method="delete" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/support/{order_id}/agent" method="get" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/support/{order_id}/agent" method="put" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/support/{order_id}/agent" method="delete" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

## 8.13 Consumer Interface



{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/on_search" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/on_select" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/on_init" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/on_confirm" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/on_track" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/on_cancel" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/on_update" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/on_status" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/on_rating" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/on_support" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/cancellation_reasons" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/return_reasons" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml" path="/rating_categories" method="post" %}
[beckn-e-marketplace-bb-0.2-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.2-resolved.yaml)
{% endswagger %}



