---
description: >-
  This section provides a reference for APIs that should be implemented by this
  Building Block.
---

# 8 Service APIs

This section provides a reference for APIs that should be implemented by this Building Block. The APIs defined here establish a blueprint for how the Building Block will interact with other Building Blocks. Additional APIs may be implemented by the Building Block, but the listed APIs define a minimal set of functionality that should be provided by any implementation of this Building Block.&#x20;

The [GovStack non-functional requirements document](https://govstack.gitbook.io/specification/architecture-and-nonfunctional-requirements/6-onboarding) provides additional information on how 'adaptors' may be used to translate an existing API to the patterns described here.

* The microservice interfaces are defined as per [OPENAPI Ver 3.0 standards](https://swagger.io/specification/).&#x20;
* For implementation of Administration APIs, we have referred to [TMF630 REST API Design Guidelines 4.2.0](https://www.tmforum.org/resources/specification/tmf630-rest-api-design-guidelines-4-2-0/).
* For implementation of Interoperability APIs, we have referred to various open-source communication protocols and data standards like [Schema.org](https://schema.org/docs/schemas.html), [HTTP/2](https://datatracker.ietf.org/doc/html/rfc9113), and [DNS](https://datatracker.ietf.org/doc/html/rfc1035). The objective is to use a generic transaction protocol that is agnostic of domain, region, or use case.  [Beckn Protocol API Specification](https://becknprotocol.io/) uses the design principles of such standards and creates a generic protocol that allows the E-Marketplace BB to be accessed by any consumer platform through a standard set of API endpoints.&#x20;

Each service in the e-Marketplace Building Block consists of two types of APIs namely,

* Order Lifecycle APIs:

Consists of a common set of endpoints that allow for decentralized/federated networks to be created that allow discovery, ordering, fulfillment, and post-fulfillment activities during the lifecycle of an order.&#x20;

* Service Administration APIs:

Consists of all the endpoints that are used to configure and manage the business workflows like catalog management, cart management, checkout, terms management, content management, etc. These follow REST Standards for the creation, read, update, and deletion of objects in the database. Both types of APIs will be defined using the OpenAPI (Swagger) standard. The API definitions will be hosted outside of this document. This section may provide a brief description of required APIs.

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



