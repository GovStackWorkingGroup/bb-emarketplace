# 8 Service APIs

This section provides a reference for APIs that should be implemented by this Building Block. The APIs defined here establish a blueprint for how the Building Block will interact with other Building Blocks. Additional APIs may be implemented by the Building Block, but the listed APIs define a minimal set of functionality that should be provided by any implementation of this Building Block.&#x20;

The [GovStack non-functional requirements document](https://govstack.gitbook.io/specification/architecture-and-nonfunctional-requirements/6-onboarding) provides additional information on how 'adaptors' may be used to translate an existing API to the patterns described here.

## 8.1 API Standards

* The microservice interfaces are defined as per [OPENAPI Ver3.0 standards](https://swagger.io/specification/).&#x20;
* For implementation of Administration APIs, it is suggested to refer [TMF630\_REST\_API\_Design\_Guidelines](https://www.tmforum.org/resources/standard/tmf630-rest-api-design-guidelines-4-2-0/).
* For implementation of Interoperability APIs, it is suggested to refer to [Beckn Protocol API Specification](https://github.com/beckn/protocol-specifications)

The e-marketplace consists of two categories of APIs namely

1. Platform Administration APIs
2. Platform Interoperability APIs

**Platform Administration APIs** consists of all the endpoints that are used to provide user experience and manage the business workflows like catalog management, cart management, checkout, terms management, content management etc. These follow REST Standards for the creation, read, update, and deletion of objects in the database.&#x20;

**Platform Interoperability APIs** consist of a common set of endpoints that allow for decentralized / federated networks to be created that allow discovery, ordering, fulfillment, and post-fulfillment activities during the lifecycle of an order. These do NOT follow REST Standards. The interoperability APIs follow a specification known as beckn protocol. Due to its abstracted and generic design, it is rapidly gaining extensive adoption in countries like India, Europe to create open interoperable commerce networks across multiple sectors like mobility, retail, healthcare, logistics, energy, financial services, government services, Industry 4.0 and many more.&#x20;

Both types of APIs will be defined using the OpenAPI (Swagger) standard. The API definitions will be hosted outside of this document. This section may provide a brief description of required APIs.

### 8.1.1 Platform Interoperability APIs : Search

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml" path="/search" method="post" %}
[beckn-e-marketplace-bb-0.1-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml" path="/on_search" method="post" %}
[beckn-e-marketplace-bb-0.1-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml)
{% endswagger %}

### 8.1.2 Platform Interoperability APIs : Quote Agreement

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml" path="/select" method="post" %}
[beckn-e-marketplace-bb-0.1-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml)
{% endswagger %}

### 8.1.3 Platform Interoperability APIs : Terms Agreement

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml" path="/init" method="post" %}
[beckn-e-marketplace-bb-0.1-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml)
{% endswagger %}

### 8.1.4 Platform Interoperability APIs : Contract Creation

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml" path="/cancel" method="post" %}
[beckn-e-marketplace-bb-0.1-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml)
{% endswagger %}

### 8.1.5 Platform Interoperability APIs : Cancellation

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml" path="/confirm" method="post" %}
[beckn-e-marketplace-bb-0.1-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml)
{% endswagger %}

### 8.1.6 Platform Interoperability APIs : Contract Update

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml" path="/update" method="post" %}
[beckn-e-marketplace-bb-0.1-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml)
{% endswagger %}

### 8.1.7 Platform Interoperability APIs : Fulfillment

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml" path="/status" method="post" %}
[beckn-e-marketplace-bb-0.1-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml)
{% endswagger %}

### 8.1.8 Platform Interoperability APIs : Tracking

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml" path="/track" method="post" %}
[beckn-e-marketplace-bb-0.1-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml)
{% endswagger %}

### 8.1.9 Platform Interoperability APIs : Rating

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml" path="/rating" method="post" %}
[beckn-e-marketplace-bb-0.1-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml)
{% endswagger %}

### 8.1.0 Platform Interoperability APIs : Support

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml" path="/support" method="post" %}
[beckn-e-marketplace-bb-0.1-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml" path="/on_select" method="post" %}
[beckn-e-marketplace-bb-0.1-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml" path="/on_init" method="post" %}
[beckn-e-marketplace-bb-0.1-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml" path="/on_confirm" method="post" %}
[beckn-e-marketplace-bb-0.1-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml" path="/on_track" method="post" %}
[beckn-e-marketplace-bb-0.1-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml" path="/on_cancel" method="post" %}
[beckn-e-marketplace-bb-0.1-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml" path="/on_update" method="post" %}
[beckn-e-marketplace-bb-0.1-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml" path="/on_status" method="post" %}
[beckn-e-marketplace-bb-0.1-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml" path="/on_rating" method="post" %}
[beckn-e-marketplace-bb-0.1-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml" path="/on_support" method="post" %}
[beckn-e-marketplace-bb-0.1-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml)
{% endswagger %}
