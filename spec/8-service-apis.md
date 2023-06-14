# 8 Service APIs

This section provides a reference for APIs that should be implemented by this Building Block. The APIs defined here establish a blueprint for how the Building Block will interact with other Building Blocks. Additional APIs may be implemented by the Building Block, but the listed APIs define a minimal set of functionality that should be provided by any implementation of this Building Block.&#x20;

The [GovStack non-functional requirements document](https://govstack.gitbook.io/specification/architecture-and-nonfunctional-requirements/6-onboarding) provides additional information on how 'adaptors' may be used to translate an existing API to the patterns described here.

{% hint style="success" %}
All APIs will be defined using the OpenAPI (Swagger) standard. The API definitions will be hosted outside of this document. This section may provide a brief description of required APIs.

This section will primarily contain links to the GitHub repository for OpenAPI definition (yaml) files as well as to a website hosted by GovStack that provides a live API documentation portal.

OpenAPI links to the GitHub repository can be made in an interactive way using the GitBook OpenAPI widget, linking to the GitHub repo version of the .json file, remembering to link to the “raw” url. An example from the Registries BB is shown below and can be replaced:
{% endhint %}

{% swagger src="https://raw.githubusercontent.com/GovStackWorkingGroup/bb-scheduler/main/api/Govstack_scheduler_BB_APIs.json" path="/event/new" method="post" %}
[https://raw.githubusercontent.com/GovStackWorkingGroup/bb-scheduler/main/api/Govstack_scheduler_BB_APIs.json](https://raw.githubusercontent.com/GovStackWorkingGroup/bb-scheduler/main/api/Govstack_scheduler_BB_APIs.json)
{% endswagger %}

{% swagger src="https://raw.githubusercontent.com/GovStackWorkingGroup/bb-scheduler/main/api/Govstack_scheduler_BB_APIs.json" path="/event/modifications" method="put" %}
[https://raw.githubusercontent.com/GovStackWorkingGroup/bb-scheduler/main/api/Govstack_scheduler_BB_APIs.json](https://raw.githubusercontent.com/GovStackWorkingGroup/bb-scheduler/main/api/Govstack_scheduler_BB_APIs.json)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml" path="/search" method="post" %}
[beckn-e-marketplace-bb-0.1-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml" path="/select" method="post" %}
[beckn-e-marketplace-bb-0.1-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml" path="/init" method="post" %}
[beckn-e-marketplace-bb-0.1-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml" path="/confirm" method="post" %}
[beckn-e-marketplace-bb-0.1-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml" path="/status" method="post" %}
[beckn-e-marketplace-bb-0.1-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml" path="/track" method="post" %}
[beckn-e-marketplace-bb-0.1-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml" path="/cancel" method="post" %}
[beckn-e-marketplace-bb-0.1-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml" path="/update" method="post" %}
[beckn-e-marketplace-bb-0.1-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml" path="/rating" method="post" %}
[beckn-e-marketplace-bb-0.1-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml" path="/support" method="post" %}
[beckn-e-marketplace-bb-0.1-resolved.yaml](.gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml)
{% endswagger %}

{% swagger src=".gitbook/assets/beckn-e-marketplace-bb-0.1-resolved.yaml" path="/on_search" method="post" %}
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
