---
description: >-
  This section provides information on the core data structures/data models that
  are used by this Building Block.
---

# 7 Data Structures

The proposed resource model showing the relationship between data objects that are used by this Building Block is illustrated in the diagram below.

## 7.1 E-Marketplace Building Block Data Model

* **TODO**: Create a Class Diagram based on the JSON

## 7.2 Data Structures

### 7.2.1 Ack

**Description:** Outlines the acknowledgement sent in response to an API call. If the implementation uses HTTP/S, then Ack must be returned in the same session. Every API call to a Provider Platform must be responded to with an Ack whether the Provider Platform intends to respond with a callback or not. This has the property `status` that indicates the state of the Acknowledgement.

**Fields:**

<table><thead><tr><th>Name</th><th>Type</th><th>Description</th><th>Notes</th><th data-hidden>Notes</th></tr></thead><tbody><tr><td>status</td><td>string</td><td>The status of the acknowledgement. If the request passes the validation criteria of the Provider Platform, then this is set to ACK. If a Provider Platform responds with status = <code>ACK</code> to a request, it is required to respond with a callback. If the request fails the validation criteria, then this is set to NACK. Additionally, if a Provider Platform does not intend to respond with a callback even after the request meets the validation criteria, it should set this value to <code>NACK</code>.</td><td>Enum Data Type in C: ACK, NACK</td><td></td></tr><tr><td>tags</td><td><a href="7-data-structures.md#7.2.53-taggroup">TagGroup</a> array</td><td>A grouped list of tags containing any additional information sent along with the Acknowledgement.</td><td></td><td></td></tr></tbody></table>

### 7.2.2 AddOn

**Description:** Shows an additional item offered as a value-addition to a product or service. This does not exist independently in a catalog and is always associated with an item.

**Fields:**

| Name       | Type                                                 | Description                       |
| ---------- | ---------------------------------------------------- | --------------------------------- |
| id         | string                                               | Provider-defined ID of the add-on |
| descriptor | [Descriptor](7-data-structures.md#7.2.19-descriptor) | Description of the add-on         |
| price      | [Price](7-data-structures.md#7.2.40-price)           | Price of the add-on               |

### 7.2.3 Address

**Description:** Outlines a postal address that is stored as a string value.

### 7.2.4 Agent

**Description:** Outlines the direct performer, driver or executor that fulfils an order. It is usually a person. But in some rare cases, it could be a non-living entity like a drone, or a bot. Some examples of agents are a doctor in the healthcare sector, a driver in the mobility sector, or a delivery person in the logistics sector. This object can be set at any stage of the order lifecycle. This can be set at the discovery stage when the Provider Platform wants to provide details on the agent fulfilling the order, like in healthcare, where the doctor's name appears during a search. This object can also be used to search for a particular person that the customer wants to fulfil an order. Sometimes, this object gets instantiated after the order is confirmed, like in the case of on-demand taxis, where the driver is assigned after the user confirms the ride.

**Fields:**

| Name         | Type                                                     | Description                                         |
| ------------ | -------------------------------------------------------- | --------------------------------------------------- |
| person       | [Person](7-data-structures.md#7.2.39-person)             | Personal details of the agent                       |
| contact      | [Contact](7-data-structures.md#7.2.13-contact)           | Contact details of the agent                        |
| organization | [Organization](7-data-structures.md#7.2.37-organization) | The organization details which the agent belongs to |
| rating       | [Rating](7-data-structures.md#7.2.43-rating)             | The average user rating of the agent                |

### 7.2.5 Authorization

**Description:** Outlines an authorization mechanism used to start or end the fulfilment of an order. For example, in the mobility sector, the driver may require a one-time password to initiate the ride. In the healthcare sector, a patient may need to provide a password to open a video conference link during a teleconsultation.

**Fields:**

<table><thead><tr><th>Name</th><th>Type</th><th>Description</th><th>Notes</th><th data-hidden>Enum</th></tr></thead><tbody><tr><td>type</td><td>string</td><td>Type of authorization mechanism used. The allowed values for this field can be published as part of the network policy.</td><td></td><td></td></tr><tr><td>token</td><td>string</td><td>Token used for authorization. This is typically generated at the Provider Platform. The Application Platform can send this value to the user via any channel that it uses to authenticate the user like SMS, Email, Push notification, or in-app rendering.</td><td></td><td></td></tr><tr><td>valid_from</td><td>string</td><td>Timestamp in RFC3339 format from which token is valid.</td><td>Format: date-time</td><td></td></tr><tr><td>valid_to</td><td>string</td><td>Timestamp in RFC3339 format until which token is valid.</td><td>Format: date-time</td><td></td></tr><tr><td>status</td><td>string</td><td>Status of the token.</td><td></td><td></td></tr></tbody></table>

### 7.2.6 Billing

**Description:** Outlines the billing details of an entity. This has properties like name, organization, address, email, phone, time, tax\_number, created\_at,updated\_at.

**Fields:**

<table><thead><tr><th>Name</th><th>Type</th><th>Description</th><th>Notes</th><th data-hidden>Enum</th></tr></thead><tbody><tr><td>name</td><td>string</td><td>Name of the billable entity</td><td></td><td></td></tr><tr><td>organization</td><td><a href="7-data-structures.md#7.2.37-organization">Organization</a></td><td>Details of the organization being billed.</td><td></td><td></td></tr><tr><td>address</td><td><a href="7-data-structures.md#7.2.3-address">Address</a></td><td>The address of the billable entity</td><td></td><td></td></tr><tr><td>state</td><td><a href="7-data-structures.md#7.3.49-state">State</a></td><td>The state where the billable entity resides. This is important for state-level tax calculation</td><td></td><td></td></tr><tr><td>city</td><td><a href="7-data-structures.md#7.2.12-city">City</a></td><td>The city where the billable entity resides.</td><td></td><td></td></tr><tr><td>email</td><td>string</td><td>Email address where the bill is sent to</td><td>Format: email</td><td></td></tr><tr><td>phone</td><td>string</td><td>Phone number of the billable entity</td><td></td><td></td></tr><tr><td>time</td><td><a href="7-data-structures.md#7.2.54-time">Time</a></td><td>Details regarding the billing period.</td><td></td><td></td></tr><tr><td>tax_id</td><td>string</td><td>ID of the billable entity as recognized by the taxation authority</td><td></td><td></td></tr></tbody></table>

### 7.2.7 Cancellation

**Description:** Outlines a cancellation event.

**Fields:**

<table><thead><tr><th>Name</th><th>Type</th><th>Description</th><th>Format</th><th data-hidden>Enum</th></tr></thead><tbody><tr><td>time</td><td>string</td><td>Date-time when the order was cancelled by the buyer</td><td>Format: date-time</td><td></td></tr><tr><td>cancelled_by</td><td>string</td><td></td><td>Enum Data Type in C: CONSUMER, PROVIDER</td><td>CONSUMER, PROVIDER</td></tr><tr><td>reason</td><td><a href="7-data-structures.md#7.2.35-option">Option</a> array</td><td>The reason for cancellation.</td><td></td><td></td></tr><tr><td>additional_description</td><td><a href="7-data-structures.md#7.2.19-descriptor">Descriptor</a></td><td>Any additional information regarding the nature of cancellation.</td><td></td><td></td></tr></tbody></table>

### 7.2.8 CancellationTerm

**Description:** Outlines the cancellation terms of an item or an order. This can be referenced at an item or order level. Item-level cancellation terms can override the terms at the order level.

**Fields:**

| Name               | Type                                                             | Description                                                                                                                        |
| ------------------ | ---------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| fulfillment\_state | [FulfillmentState](7-data-structures.md#7.2.26-fulfillmentstate) | The state of fulfillment during which this term is applicable. ([Fulfillment State](7-data-structures.md#7.3.26-fulfillmentstate)) |
| reason\_required   | boolean                                                          | Indicates whether a reason is required to cancel the order                                                                         |
| cancel\_by         | [Time](7-data-structures.md#7.2.54-time)                         | Information related to the [time](7-data-structures.md#7.3.54-time) of cancellation.                                               |
| cancellation\_fee  | [Fee](7-data-structures.md#7.2.23-fee)                           | The cancellation fees levied on the customer                                                                                       |
| xinput             | [XInput](7-data-structures.md#7.2.57-xinput)                     | Form to capture information related to the cancellation                                                                            |
| external\_ref      | [MediaFile](7-data-structures.md#7.2.33-mediafile)               | Any attachements related to the cancellation                                                                                       |

### 7.2.9 Catalog

**Description:** Outlines the products or services offered by a Provider Platform. This is typically sent as the response to a search intent from an Application Platform. The payment terms, offers and terms of fulfilment supported by the Provider Platform can also be included here. The Provider Platform can show the hierarchical nature of products/services in its catalog using the parent\_category\_id in categories. The Provider Platform can also send a TTL (time to live) in the context which is the duration for which an Application Platform can cache the catalog and use the cached catalog. This has properties for Business to Business Procurement (BBP) like descriptor/categories/fulfillments/payments/offers/providers/exp. This is used in the following situations. This is typically used in the discovery stage when the Provider Platform sends the details of the products and services it offers as a response to a search intent from the Application Platform.&#x20;

**Fields:**

<table><thead><tr><th>Name</th><th>Type</th><th>Description</th><th>Notes</th><th data-hidden>Enum</th></tr></thead><tbody><tr><td>descriptor</td><td><a href="7-data-structures.md#7.2.19-descriptor">Descriptor</a></td><td>Description of the catalog</td><td></td><td></td></tr><tr><td>fulfillments</td><td><a href="7-data-structures.md#7.2.25-fulfillment">Fulfillment</a> array</td><td>Fulfillment modes offered at the Provider Platform level. This is used when a Provider Platform itself offers fulfillments on behalf of the providers it has aggregated.</td><td></td><td></td></tr><tr><td>payments</td><td><a href="7-data-structures.md#7.2.38-payment">Payment</a> array</td><td>Payment terms offered by the Provider Platform for all transactions. This can be overriden at the provider level.</td><td></td><td></td></tr><tr><td>offers</td><td><a href="7-data-structures.md#7.2.34-offer">Offer</a> array</td><td>Offers at the Provider Platform-level. This is usually used when the platform aggregates catalogs of multiple providers</td><td></td><td></td></tr><tr><td>providers</td><td><a href="7-data-structures.md#7.2.41-provider">Provider</a> array</td><td>Provider of service or product. </td><td></td><td></td></tr><tr><td>exp</td><td>string</td><td>Timestamp after which catalog will expire</td><td>Format: date-time</td><td></td></tr><tr><td>ttl</td><td>string</td><td>Duration in seconds after which this catalog will expire</td><td></td><td></td></tr></tbody></table>

### 7.2.10 Category

**Description:** A label under which a collection of items can be grouped.

**Fields:**

| Name                 | Type                                                   | Description                                    |
| -------------------- | ------------------------------------------------------ | ---------------------------------------------- |
| id                   | string                                                 | ID of the category                             |
| parent\_category\_id | [Category](7-data-structures.md#7.2.10-category)       | ID of the parent category                      |
| descriptor           | [Descriptor](7-data-structures.md#7.2.19-descriptor)   | Description of the category                    |
| time                 | [Time](7-data-structures.md#7.2.54-time)               | Time at or during which this category is valid |
| ttl                  | string                                                 | Time to live for an instance of this schema    |
| tags                 | [TagGroup](7-data-structures.md#7.2.53-taggroup) array | Array of grouped key value pairs               |

### 7.2.11 Circle

**Description:** Describes a circular region of a specified radius centered at a specified GPS coordinate.

**Fields:**

| Name   | Type                                         | Description                    |
| ------ | -------------------------------------------- | ------------------------------ |
| gps    | [Gps](7-data-structures.md#7.2.27-gps)       | GPS Co-ordinates of the center |
| radius | [Scalar](7-data-structures.md#7.2.47-scalar) | Radius of the circle           |

### 7.2.12 City

**Description:** Outlines a city

**Fields:**

| Name | Type   | Description      |
| ---- | ------ | ---------------- |
| name | string | Name of the city |
| code | string | City code        |

### 7.2.13 Contact

**Description:** Outlines the contact information of an entity.

**Fields:**

| Name  | Type   | Description                                                      |
| ----- | ------ | ---------------------------------------------------------------- |
| phone | string |                                                                  |
| email | string |                                                                  |
| jcard | object | A Jcard object as per draft-ietf-jcardcal-jcard-03 specification |

### 7.2.14 Context

**Description:**

Every API call in Beckn Protocol has a context. It provides a high-level overview to the receiver about the nature of the intended transaction. Typically, it is the Application Platform that sets the transaction context based on the consumer's location and action on their UI. But sometimes, during unsolicited callbacks, the Provider Platform also sets the transaction context but it is usually the same as the context of a previous full-cycle, request-callback interaction between the Application Platform and the Provider Platform. The context object contains four types of fields. Demographic information about the transaction using fields like `domain`, `country`, and `region`. Addressing details like the sending and receiving platform's ID and API URL. Interoperability information like the protocol version that is implemented by the sender and transaction details like the method being called at the receiver's endpoint, the transaction\_id that represents an end-to-end user session at the Application Platform, a message ID to pair requests with callbacks, a timestamp to capture sending times, a ttl to specify the validity of the request, and a key to encrypt information if necessary. This object must be passed in every interaction between an Application Platform and a Provider Platform. In HTTP/S implementations, it is not necessary to send the context during the synchronous response. However, in asynchronous protocols, the context must be sent during all interactions.

**Fields:**

<table><thead><tr><th>Name</th><th>Type</th><th>Description</th><th>Notes</th><th data-hidden>Enum</th></tr></thead><tbody><tr><td>domain</td><td><a href="7-data-structures.md#7.2.20-domain">Domain</a></td><td>Industry sector code that is relevant to this transaction</td><td></td><td></td></tr><tr><td>location</td><td><a href="7-data-structures.md#7.2.32-location">Location</a></td><td>The location where the request is restricted to</td><td></td><td></td></tr><tr><td>action</td><td>string</td><td>The Beckn protocol method being called by the sender and executed at the receiver.</td><td></td><td></td></tr><tr><td>version</td><td>string</td><td>Version of transaction protocol being used by the sender.</td><td></td><td></td></tr><tr><td>bap_id</td><td>string</td><td>Subscriber ID of the Application Platform</td><td></td><td></td></tr><tr><td>bap_uri</td><td>string</td><td>Subscriber URL of the Application Platform for accepting callbacks from Provider Platforms.</td><td></td><td></td></tr><tr><td>bpp_id</td><td>string</td><td>Subscriber ID of the Provider Platform</td><td></td><td></td></tr><tr><td>bpp_uri</td><td>string</td><td>Subscriber URL of the Provider Platform for accepting calls from Application Platforms.</td><td></td><td></td></tr><tr><td>transaction_id</td><td>string</td><td>This is a unique value which persists across all API calls from <code>search</code> through <code>confirm</code>. This is done to indicate an active user session across multiple requests. The Provider Platforms can use this value to push personalized recommendations, and dynamic offerings related to an ongoing transaction despite being unaware of the user active on the Application Platform.</td><td>Format: uuid</td><td></td></tr><tr><td>message_id</td><td>string</td><td>This is a unique value which persists during a request / callback cycle. Since beckn protocol APIs are asynchronous, Application Platforms need a common value to match an incoming callback from a Provider Platform to an earlier call. This value can also be used to ignore duplicate messages coming from the Provider Platform. It is recommended to generate a fresh message_id for every new interaction. When sending unsolicited callbacks, Provider Platforms must generate a new message_id.</td><td>Format: uuid</td><td></td></tr><tr><td>timestamp</td><td>string</td><td>Time of request generation in RFC3339 format</td><td>Format: date-time</td><td></td></tr><tr><td>key</td><td>string</td><td>The encryption public key of the sender</td><td></td><td></td></tr><tr><td>ttl</td><td>string</td><td>The duration in ISO8601 format after timestamp for which this message holds valid</td><td></td><td></td></tr></tbody></table>

### 7.2.15 Country

**Description:** Outlines a country.

**Fields:**

| Name | Type   | Description                                          |
| ---- | ------ | ---------------------------------------------------- |
| name | string | Name of the country                                  |
| code | string | Country code as per ISO 3166-1 and ISO 3166-2 format |

### 7.2.16 Credential

**Description:** Outlines a credential of an entity (Person or Organization).

**Fields:**

<table><thead><tr><th>Name</th><th>Type</th><th>Description</th><th>Notes</th><th data-hidden>Enum</th></tr></thead><tbody><tr><td>id</td><td>string</td><td></td><td></td><td></td></tr><tr><td>type</td><td>string</td><td>Takes a default value of "VerifiableCredential"</td><td></td><td></td></tr><tr><td>url</td><td>string</td><td>URL of the credential</td><td>Format: uri</td><td></td></tr></tbody></table>

### 7.2.17 Customer

**Description:** Outlines a customer buying/availing a product or a service.

**Fields:**

| Name    | Type                                           | Description                      |
| ------- | ---------------------------------------------- | -------------------------------- |
| person  | [Person](7-data-structures.md#7.2.39-person)   | Personal details of the customer |
| contact | [Contact](7-data-structures.md#7.2.13-contact) | Contact details of the customer  |

### 7.2.18 DecimalValue

**Description:** Outlines a numerical value in decimal form. The string value should match the pattern "\[+-]?(\[0-9]\*\[.])?\[0-9]+".

### 7.2.19 Descriptor

**Description:** Physical description of something.

**Fields:**

| Name             | Type                                                     | Description                                                              |
| ---------------- | -------------------------------------------------------- | ------------------------------------------------------------------------ |
| name             | string                                                   | Name of the entity being described using this object                     |
| code             | string                                                   | Code of the entity being described using this object                     |
| short\_desc      | string                                                   | Short description of the entity being described using this object        |
| long\_desc       | string                                                   | Long description of the entity being described using this object         |
| additional\_desc | object                                                   | Additional descriptions of the entity being described using this object  |
| media            | [MediaFile](7-data-structures.md#7.2.33-mediafile) array | Multimedia files describing the entity being described using this object |
| images           | [Image](7-data-structures.md#7.2.28-image) array         | Image describing the entity being described using this object            |

### 7.2.20 Domain

**Description:** Outlines the industry sector or sub-sector. The network policy should contain codes for all the industry sectors supported by the network. Domains can be created in varying levels of granularity. The granularity of a domain can be decided by the participants of the network. Too broad domains will result in irrelevant search broadcast calls to Provider Platforms that don't have services supporting the domain. Too narrow domains will result in a large number of registry entries for each Provider Platform. It is recommended that network facilitators actively collaborate with various working groups and network participants to carefully choose domain codes keeping in mind relevance, performance, and opportunity cost. It is recommended that networks choose broad domains like mobility, logistics, healthcare etc, and progressively granularize them as and when the number of network participants for each domain grows large.

**Fields:**

| Name             | Type   | Description                                                                                                                                                                                                                 |
| ---------------- | ------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| name             | string | Name of the domain                                                                                                                                                                                                          |
| code             | string | Standard code representing the domain. The standard is usually published as part of the network policy. Furthermore, the network facilitator should also provide a mechanism to provide the supported domains of a network. |
| additional\_info | string | A url that contains addtional information about that domain.                                                                                                                                                                |

### 7.2.21 Duration

**Description:** Outlines duration as per ISO8601 format.

### 7.2.22 Error

**Description:** Outlines an error object that is returned by an Application Platform, Provider Platform or BG as a response or callback to an action by another network participant. This object is sent when any request received by a network participant is unacceptable. This object can be sent either during Ack or with the callback.

**Fields:**

| Name    | Type   | Description                                                                                                                      |
| ------- | ------ | -------------------------------------------------------------------------------------------------------------------------------- |
| code    | string | Standard error code. For full list of error codes, refer to docs/protocol-drafts/BECKN-005-ERROR-CODES-DRAFT-01.md of this repo" |
| paths   | string | Path to json schema generating the error. Used only during json schema validation errors                                         |
| message | string | Human readable message describing the error. Used mainly for logging. Not recommended to be shown to the user.                   |

### 7.2.23 Fee

**Description:** A fee applied to a particular entity.

**Fields:**

| Name       | Type                                                     | Description                             |
| ---------- | -------------------------------------------------------- | --------------------------------------- |
| percentage | [DecimalValue](7-data-structures.md#7.2.18-decimalvalue) | Percentage of order value levied as fee |
| amount     | [Price](7-data-structures.md#7.2.40-price)               | Value of the fee levied                 |

### 7.2.24 Form

**Description:** Outlines a form.

**Fields:**

| Name           | Type   | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                    | Notes        | Enum                       |
| -------------- | ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | -------------------------- |
| url            | string | The URL from where the form can be fetched. The content fetched from the url must be processed as per the mime\_type specified in this object. Once fetched, the rendering platform can choosed to render the form as-is as an embeddable element; or process it further to blend with the theme of the application. In case the interface is non-visual, the the render can process the form data and reproduce it as per the standard specified in the form. | Format: uri  |                            |
| data           | object | The form submission data                                                                                                                                                                                                                                                                                                                                                                                                                                       |              |                            |
| mime\_type     | string | This field indicates the nature and format of the form received by querying the url. MIME types are defined and standardized in IETF's RFC 6838.                                                                                                                                                                                                                                                                                                               |              | text/html, application/xml |
| submission\_id | string |                                                                                                                                                                                                                                                                                                                                                                                                                                                                | Format: uuid |                            |

### 7.2.25 Fulfillment

**Description:** Outlines how an order will be rendered/fulfilled to the end customer.

**Fields:**

| Name     | Type                                                             | Description                                                                                                                                                                                                                                                                                                                                                                                                                |
| -------- | ---------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id       | string                                                           | Unique reference ID to the fulfillment of an order                                                                                                                                                                                                                                                                                                                                                                         |
| type     | string                                                           | A code that describes the mode of fulfillment. This is typically set when there are multiple ways an order can be fulfilled. For example, a retail order can be fulfilled either via store pickup or a home delivery. Similarly, a medical consultation can be provided either in-person or via tele-consultation. The network policy must publish standard fulfillment type codes for the different modes of fulfillment. |
| rateable | boolean                                                          | Whether the fulfillment can be rated or not                                                                                                                                                                                                                                                                                                                                                                                |
| rating   | [Rating](7-data-structures.md#7.2.43-rating)                     | The rating value of the fulfullment service.                                                                                                                                                                                                                                                                                                                                                                               |
| state    | [FulfillmentState](7-data-structures.md#7.2.26-fulfillmentstate) | The current state of fulfillment. The Provider Platform must set this value whenever the state of the order fulfillment changes and fire an unsolicited `on_status` call.                                                                                                                                                                                                                                                  |
| tracking | boolean                                                          | Indicates whether the fulfillment allows tracking. Has a default value of false.                                                                                                                                                                                                                                                                                                                                           |
| customer | [Customer](7-data-structures.md#7.2.17-customer)                 | the intended recipient of a fulfilled order                                                                                                                                                                                                                                                                                                                                                                                |
| agent    | [Agent](7-data-structures.md#7.2.4-agent)                        | The agent that is currently handling the fulfillment of the order                                                                                                                                                                                                                                                                                                                                                          |
| contact  | [Contact](7-data-structures.md#7.2.13-contact)                   | Contact details related to the fulfillment                                                                                                                                                                                                                                                                                                                                                                                 |
| vehicle  | [Vehicle](7-data-structures.md#7.2.56-vehicle)                   | Vehicle used for fulfillment of the order                                                                                                                                                                                                                                                                                                                                                                                  |
| stops    | [Stop](7-data-structures.md#7.2.50-stop) array                   | The list of logical stops encountered during the fulfillment of an order.                                                                                                                                                                                                                                                                                                                                                  |
| path     | string                                                           | The physical path taken by the agent that can be rendered on a map. The allowed format of this property can be set by the network.                                                                                                                                                                                                                                                                                         |
| tags     | [TagGroup](7-data-structures.md#7.2.53-taggroup) array           | List of grouped key-value pairs to transmit extended metadata related to the fulfillment                                                                                                                                                                                                                                                                                                                                   |

### 7.2.26 FulfillmentState

**Description:** Outlines the state of fulfilment.

**Fields:**

<table><thead><tr><th>Name</th><th>Type</th><th>Description</th><th>Notes</th><th data-hidden>Enum</th></tr></thead><tbody><tr><td>descriptor</td><td><a href="7-data-structures.md#7.2.19-descriptor">Descriptor</a></td><td>The description of the current fulfillment state of a confirmed order</td><td></td><td></td></tr><tr><td>updated_at</td><td>string</td><td>Time at which the state of fulfillment was updated</td><td>Format: date-time</td><td></td></tr><tr><td>updated_by</td><td>string</td><td>ID of entity which changed the state</td><td></td><td></td></tr></tbody></table>

### 7.2.27 Gps

**Description:** Outlines a GPS coordinate. The string value should be of the pattern "^\[-+]?(\[1-8]?\d(\\.\d+)?|90(\\.0+)?),\s\*\[-+]?(180(\\.0+)?|((1\[0-7]\d)|(\[1-9]?\d))(\\.\d+)?)$".

### 7.2.28 Image

**Description:** Outlines an image.

**Fields:**

| Name       | Type   | Description                                                                              | Notes       | Enum                       |
| ---------- | ------ | ---------------------------------------------------------------------------------------- | ----------- | -------------------------- |
| url        | string | URL to the image. This can be a data url or an remote url                                | Format: uri |                            |
| size\_type | string | The size of the image. The network policy can define the default dimensions of each type |             | xs, sm, md, lg, xl, custom |
| width      | string | Width of the image in pixels                                                             |             |                            |
| height     | string | Height of the image in pixels                                                            |             |                            |

### 7.2.29 Intent

**Description:** The intent to buy or avail of a product or a service. The Application Platform can declare the intent of the consumer containing what they want (A product, service, offer)/Who they want (A seller, service provider, agent etc)/Where they want it and where they want it from/When they want it (start and end time of fulfilment/How they want to pay for it/This has properties like descriptor, provider, fulfilment, payment, category, offer, item, tags. This is typically used by the Application Platform to send the purpose of the user's search to the Provider Platform. This will be used by the Provider Platform to find products or services it offers that may match the user's intent. For example, in Mobility, the mobility consumer declares a mobility intent. In this case, the mobility consumer declares information that describes various aspects of their journey like, where would they like to begin their journey (intent.fulfillment.start.location)/Where would they like to end their journey (intent.fulfillment.end.location)/When would they like to begin their journey (intent.fulfillment.start.time)/When would they like to end their journey (intent.fulfillment.end.time)/Who is the transport service provider they would like to avail services from (intent.provider)/Who is traveling (This is not recommended in public networks) (intent.fulfillment.customer)/What kind of fare product would they like to purchase (intent.item)/What add-on services would they like to avail/What offers would they like to apply on their booking (intent.offer)/What category of services would they like to avail (intent.category)/What additional luggage are they carrying/How would they like to pay for their journey (intent.payment). For example, in health domain, a consumer declares the intent for a lab booking the describes various aspects of their booking like, where would they like to get their scan/test done (intent.fulfillment.start.location)/When would they like to get their scan/test done (intent.fulfillment.start.time)/When would they like to get the results of their test or scan (intent.fulfillment.end.time)/Who is the service provider they would like to avail services from (intent.provider)/Who is getting the test or scan (intent.fulfillment.customer)/What kind of test or scan would they like to purchase (intent.item)/What category of services would they like to avail (intent.category)/How would they like to pay for their journey (intent.payment).

**Fields:**

| Name        | Type                                                   | Description                                                                                                  |
| ----------- | ------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ |
| descriptor  | [Descriptor](7-data-structures.md#7.2.19-descriptor)   | A raw description of the search intent. Free text search strings, raw audio, etc can be sent in this object. |
| provider    | [Provider](7-data-structures.md#7.2.41-provider)       | The provider from which the customer wants to place to the order from                                        |
| fulfillment | [Fulfillment](7-data-structures.md#7.2.25-fulfillment) | Details on how the customer wants their order fulfilled Fulfillment                                          |
| payment     | [Payment](7-data-structures.md#7.2.38-payment)         | Details on how the customer wants to pay for the order. Payment                                              |
| category    | [Category](7-data-structures.md#7.2.10-category)       | Details on the item category                                                                                 |
| offer       | [Offer](7-data-structures.md#7.2.34-offer)             | details on the offer the customer wants to avail                                                             |
| item        | [Item](7-data-structures.md#7.2.31-item)               | Details of the item that the consumer wants to order                                                         |
| tags        | [TagGroup](7-data-structures.md#7.2.53-taggroup) array | [Tags](7-data-structures.md#7.3.52-tag)                                                                      |

### 7.2.30 ItemQuantity

**Description:** Outlines the count or amount of an item.

**Fields:**

| Name      | Type   | Description                                                                                                          |
| --------- | ------ | -------------------------------------------------------------------------------------------------------------------- |
| allocated | object | This represents the exact quantity allocated for purchase of the item.                                               |
| available | object | This represents the exact quantity available for purchase of the item. The buyer can only purchase multiples of this |
| maximum   | object | This represents the maximum quantity allowed for purchase of the item                                                |
| minimum   | object | This represents the minimum quantity allowed for purchase of the item                                                |
| selected  | object | This represents the quantity selected for purchase of the item                                                       |
| unitized  | object | This represents the quantity available in a single unit of the item                                                  |

### 7.2.31 Item

**Description:** Outlines a product or a service offered to the end consumer by the provider. In the mobility sector, it can represent a fare product like a one-way journey. In the logistics sector, it can represent the delivery service offering. In the retail domain, it can represent a product like a grocery item.

**Fields:**

| Name                   | Type                                                                  | Description                                                                                                                    |
| ---------------------- | --------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| id                     | string                                                                | ID of the item.                                                                                                                |
| parent\_item\_id       | string                                                                | ID of the item, this item is a variant of                                                                                      |
| parent\_item\_quantity | [ItemQuantity](7-data-structures.md#7.2.30-itemquantity)              | The number of units of the parent item this item is a multiple of                                                              |
| descriptor             | [Descriptor](7-data-structures.md#7.2.19-descriptor)                  | Physical description of the item                                                                                               |
| creator                | [Organization](7-data-structures.md#7.2.37-organization)              | The creator of this item                                                                                                       |
| price                  | [Price](7-data-structures.md#7.2.40-price)                            | The price of this item, if it has intrinsic value                                                                              |
| quantity               | [ItemQuantity](7-data-structures.md#7.2.30-itemquantity)              | The quantity of the item                                                                                                       |
| category\_ids          | array                                                                 | Categories this item can be listed under                                                                                       |
| fulfillment\_ids       | array                                                                 | Modes through which this item can be fulfilled                                                                                 |
| location\_ids          | array                                                                 | Provider Locations this item is available in                                                                                   |
| payment\_ids           | array                                                                 | Payment modalities through which this item can be ordered                                                                      |
| add\_ons               | [AddOn](7-data-structures.md#7.2.2-addon) array                       | Add-ons to be included with the item                                                                                           |
| cancellation\_terms    | [CancellationTerm](7-data-structures.md#7.2.8-cancellationterm) array | Cancellation terms of this item                                                                                                |
| refund\_terms          | RefundTerm array                                                      | Refund terms of this item                                                                                                      |
| replacement\_terms     | [ReplacementTerm](7-data-structures.md#7.2.45-replacementterm) array  | Terms that are applicable be met when this item is replaced Replacement Terms                                                  |
| return\_terms          | [ReturnTerm](7-data-structures.md#7.2.46-returnterm) array            | Terms that are applicable when this item is returned Return Terms                                                              |
| xinput                 | [XInput](7-data-structures.md#7.2.57-xinput)                          | Additional input required from the customer to purchase / avail this item XInput                                               |
| time                   | [Time](7-data-structures.md#7.2.54-time)                              | Temporal attributes of this item. This property is used when the item exists on the catalog only for a limited period of time. |
| rateable               | boolean                                                               | Whether this item can be rated                                                                                                 |
| rating                 | [Rating](7-data-structures.md#7.2.43-rating)                          | The rating of the item                                                                                                         |
| matched                | boolean                                                               | Whether this item is an exact match of the request                                                                             |
| related                | boolean                                                               | Whether this item is a related item to the exactly matched item                                                                |
| recommended            | boolean                                                               | Whether this item is a recommended item to a response                                                                          |
| ttl                    | string                                                                | Time to live in seconds for an instance of this schema                                                                         |
| tags                   | [TagGroup](7-data-structures.md#7.2.53-taggroup) array                | Grouped list of extended data regarding the item                                                                               |

### 7.2.32 Location

**Description:** The physical location of something.

**Fields:**

| Name       | Type                                                 | Description                                                                                                               | Notes       | Enum |
| ---------- | ---------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- | ----------- | ---- |
| id         | string                                               |                                                                                                                           |             |      |
| descriptor | [Descriptor](7-data-structures.md#7.2.19-descriptor) | Description of the location                                                                                               |             |      |
| map\_url   | string                                               | The url to the map of the location. This can be a globally recognized map url or the one specified by the network policy. | Format: uri |      |
| gps        | [Gps](7-data-structures.md#7.2.27-gps)               | The GPS co-ordinates of this location.                                                                                    |             |      |
| address    | [Address](7-data-structures.md#7.2.3-address)        | The address of this location.                                                                                             |             |      |
| city       | [City](7-data-structures.md#7.2.12-city)             | The city this location is, or is located within                                                                           |             |      |
| district   | District                                             | The district this location is, or is located within                                                                       |             |      |
| state      | [State](7-data-structures.md#7.3.49-state)           | The state this location is, or is located within                                                                          |             |      |
| country    | [Country](7-data-structures.md#7.2.15-country)       | The country this location is, or is located within                                                                        |             |      |
| area\_code | string                                               | Area code of the location ex : ZIP code, Pincode etc                                                                      |             |      |
| circle     | [Circle](7-data-structures.md#7.2.11-circle)         | Circle that forms the boundary of the location                                                                            |             |      |
| polygon    | string                                               | The boundary polygon of this location                                                                                     |             |      |
| 3dspace    | string                                               | The three dimensional region describing this location                                                                     |             |      |
| rating     | [Rating](7-data-structures.md#7.2.43-rating)         | The rating of this location                                                                                               |             |      |

### 7.2.33 MediaFile

**Description:** This object contains a URL to a media file.

**Fields:**

<table><thead><tr><th>Name</th><th>Type</th><th>Description</th><th>Notes</th><th data-hidden>Enum</th></tr></thead><tbody><tr><td>mimetype</td><td>string</td><td>indicates the nature and format of the document, file, or assortment of bytes. MIME types are defined and standardized in IETF's RFC 6838</td><td></td><td></td></tr><tr><td>url</td><td>string</td><td>The URL of the file</td><td>Format: uri</td><td></td></tr><tr><td>signature</td><td>string</td><td>The digital signature of the file signed by the sender</td><td></td><td></td></tr><tr><td>dsa</td><td>string</td><td>The signing algorithm used by the sender</td><td></td><td></td></tr></tbody></table>

### 7.2.34 Offer

**Description:** An offer associated with a catalog. This is typically used to promote a particular product and enable more purchases.

**Fields:**

| Name          | Type                                                   | Description                                  |
| ------------- | ------------------------------------------------------ | -------------------------------------------- |
| id            | string                                                 |                                              |
| descriptor    | [Descriptor](7-data-structures.md#7.2.19-descriptor)   | Description of the offer                     |
| location\_ids | array                                                  | IDs of the Locations this offer is valid in  |
| category\_ids | array                                                  | IDs of the Categories this offer is valid in |
| item\_ids     | array                                                  | IDs of the items this offer is valid in      |
| time          | [Time](7-data-structures.md#7.2.54-time)               | Time for which this offer is valid           |
| tags          | [TagGroup](7-data-structures.md#7.2.53-taggroup) array | Additional metadata related to this offer    |

### 7.2.35 Option

**Description:** Outlines a selectable option.

**Fields:**

| Name       | Type                                                 | Description               |
| ---------- | ---------------------------------------------------- | ------------------------- |
| id         | string                                               |                           |
| descriptor | [Descriptor](7-data-structures.md#7.2.19-descriptor) | Description of the option |

### 7.2.36 Order

**Description:** Outlines a legal purchase order. It contains the complete details of the legal contract created between the buyer and the seller.

**Fields:**

<table><thead><tr><th>Name</th><th>Type</th><th>Description</th><th>Notes</th><th data-hidden>Enum</th></tr></thead><tbody><tr><td>id</td><td>string</td><td>Human-readable ID of the order. This is generated at the Provider Platform layer. The Provider Platform can either generate order id within its system or forward the order ID created at the provider level.</td><td></td><td></td></tr><tr><td>ref_order_ids</td><td>array</td><td>A list of order IDs to link this order to previous orders.</td><td></td><td></td></tr><tr><td>status</td><td>string</td><td>Status of the order. Allowed values can be defined by the network policy</td><td>Enum Data Type in C: ACTIVE, COMPLETE, CANCELLED</td><td>ACTIVE, COMPLETE, CANCELLED</td></tr><tr><td>type</td><td>string</td><td>This is used to indicate the type of order being created to Provider Platforms. Sometimes orders can be linked to previous orders, like a replacement order in a retail domain. A follow-up consultation in healthcare domain. A single order part of a subscription order. The list of order types can be standardized at the network level. Has a default value of "DEFAULT"</td><td>Enum Data Type in C: DRAFT, DEFAULT</td><td>DRAFT, DEFAULT</td></tr><tr><td>provider</td><td><a href="7-data-structures.md#7.2.41-provider">Provider</a></td><td>Details of the provider whose catalog items have been selected.</td><td></td><td></td></tr><tr><td>items</td><td><a href="7-data-structures.md#7.2.31-item">Items</a> array</td><td>The items purchased / availed in this order</td><td></td><td></td></tr><tr><td>add_ons</td><td><a href="7-data-structures.md#7.2.2-addon">AddOn</a> array</td><td>The add-ons purchased / availed in this order</td><td></td><td></td></tr><tr><td>offers</td><td><a href="7-data-structures.md#7.2.34-offer">Offers</a> array</td><td>The offers applied in this order</td><td></td><td></td></tr><tr><td>billing</td><td><a href="7-data-structures.md#7.2.6-billing">Billing</a> array</td><td>The billing details of this order</td><td></td><td></td></tr><tr><td>fulfillments</td><td><a href="7-data-structures.md#7.2.25-fulfillment">Fulfillment</a> array</td><td>The fulfillments involved in completing this order</td><td></td><td></td></tr><tr><td>cancellation</td><td><a href="7-data-structures.md#7.2.7-cancellation">Cancellation</a></td><td>The cancellation details of this order</td><td></td><td></td></tr><tr><td>cancellation_terms</td><td><a href="7-data-structures.md#7.2.7-cancellation">CancellationTerm</a> array</td><td>Cancellation terms of this item</td><td></td><td></td></tr><tr><td>refund_terms</td><td>RefundTerm array</td><td>Refund terms of this item</td><td></td><td></td></tr><tr><td>replacement_terms</td><td><a href="7-data-structures.md#7.2.45-replacementterm">ReplacementTerm</a> array</td><td>Replacement terms of this item</td><td></td><td></td></tr><tr><td>return_terms</td><td><a href="7-data-structures.md#7.2.46-returnterm">ReturnTerm</a> array</td><td>Return terms of this item</td><td></td><td></td></tr><tr><td>quote</td><td><a href="7-data-structures.md#7.2.42-quotation">Quotation</a></td><td>The mutually agreed upon quotation for this order.</td><td></td><td></td></tr><tr><td>payments</td><td><a href="7-data-structures.md#7.2.38-payment">Payment</a> array</td><td>The terms of settlement for this order </td><td></td><td></td></tr><tr><td>created_at</td><td>string</td><td>The date-time of creation of this order</td><td>Format: date-time</td><td></td></tr><tr><td>updated_at</td><td>string</td><td>The date-time of updated of this order</td><td>Format: date-time</td><td></td></tr><tr><td>xinput</td><td><a href="7-data-structures.md#7.2.57-xinput">XInput</a></td><td>Additional input required from the customer to confirm this order </td><td></td><td></td></tr><tr><td>tags</td><td><a href="7-data-structures.md#7.2.53-taggroup">TagGroup</a> array</td><td>Grouped list of extended metadata related to the Order</td><td></td><td></td></tr></tbody></table>

### 7.2.37 Organization

**Description:** An organization. Usually a recognized business entity.

**Fields:**

| Name       | Type                                                 | Description                                                  |
| ---------- | ---------------------------------------------------- | ------------------------------------------------------------ |
| descriptor | [Descriptor](7-data-structures.md#7.2.19-descriptor) | Description of the organization                              |
| address    | [Address](7-data-structures.md#7.2.3-address)        | The postal address of the organization                       |
| state      | [State](7-data-structures.md#7.3.49-state)           | The state where the the organization's address is registered |
| city       | [City](7-data-structures.md#7.2.12-city)             | The city where the the organization's address is registered  |
| contact    | [Contact](7-data-structures.md#7.2.13-contact)       | Contact details of the organization                          |

### 7.2.38 Payment

**Description:** Outlines the terms of settlement between the Application Platform and the Provider Platform for a single transaction. When instantiated, this object contains the amount that has to be settled/The payment destination details/When the settlement should happen/A transaction reference ID. During a transaction, the Provider Platform reserves the right to decide the terms of payment. However, the Application Platform can send its terms to the Provider Platform first. If the Provider Platform does not agree to those terms, it must overwrite the terms and return them to the Application Platform. If overridden, the Application Platform must either agree to the terms set by the Provider Platform in order to preserve the provider's autonomy or abort the transaction. In case of such disagreements, the Application Platform and the Provider Platform can perform offline negotiations on the payment terms. Once an agreement is reached, the Application Platform and Provider Platform can resume transactions.

**Fields:**

<table><thead><tr><th>Name</th><th>Type</th><th>Enum</th><th>Format</th><th data-hidden>Description</th></tr></thead><tbody><tr><td>id</td><td>string</td><td></td><td></td><td>ID of the payment term that can be referred at an item or an order level in a catalog</td></tr><tr><td>collected_by</td><td></td><td></td><td></td><td>This field indicates who is the collector of payment. The Application Platform can set this value to 'Application Platform' if it wants to collect the payment first and settle it to the Provider Platform. If the Provider Platform agrees to those terms, the Provider Platform should not send the payment url. Alternatively, the Provider Platform can set this field with the value 'Provider Platform' if it wants the payment to be made directly.</td></tr><tr><td>url</td><td>string</td><td>Format: uri</td><td>uri</td><td>A payment url to be called by the Application Platform. If empty, then the payment is to be done offline. The details of payment should be present in the params object. If tl_method = http/get, then the payment details will be sent as url params. Two url param values, <code>$transaction_id</code> and <code>$amount</code> are mandatory.</td></tr><tr><td>params</td><td>object</td><td></td><td></td><td></td></tr><tr><td>type</td><td>string</td><td>PRE-ORDER, PRE-FULFILLMENT, ON-FULFILLMENT, POST-FULFILLMENT</td><td></td><td></td></tr><tr><td>status</td><td>string</td><td>PAID, NOT-PAID</td><td></td><td></td></tr><tr><td>time</td><td><a href="7-data-structures.md#7.2.54-time">Time</a></td><td>Temporal details related to the settlement of the order</td><td></td><td><a href="7-data-structures.md#7.3.54-time">Time</a></td></tr><tr><td>tags</td><td><a href="7-data-structures.md#7.2.53-taggroup">TagGroup</a> array</td><td>Grouped list of metadata related to the settlement of the order</td><td></td><td><a href="7-data-structures.md#7.3.53-taggroup">Tags</a></td></tr></tbody></table>

### 7.2.39 Person

**Description:** Outlines a person as any individual.

**Fields:**

<table><thead><tr><th>Name</th><th>Type</th><th>Description</th><th>Notes</th><th data-hidden>Enum</th></tr></thead><tbody><tr><td>id</td><td>string</td><td>Describes the identity of the person</td><td></td><td></td></tr><tr><td>url</td><td>string</td><td>Profile url of the person</td><td>Format: uri</td><td></td></tr><tr><td>name</td><td>string</td><td>the name of the person</td><td></td><td></td></tr><tr><td>image</td><td><a href="7-data-structures.md#7.2.28-image">Image</a></td><td><a href="7-data-structures.md#7.3.28-image">Image</a></td><td></td><td></td></tr><tr><td>age</td><td><a href="7-data-structures.md#7.2.21-duration">Duration</a></td><td>Age of the person </td><td></td><td></td></tr><tr><td>dob</td><td>string</td><td>Date of birth of the person</td><td>Format: date</td><td></td></tr><tr><td>gender</td><td>string</td><td>Gender of something, typically a Person, but possibly also fictional characters, animals, etc. While Male and Female may be used, text strings are also acceptable for people who do not identify as a binary gender.Allowed values for this field can be published in the network policy</td><td></td><td></td></tr><tr><td>creds</td><td><a href="7-data-structures.md#7.2.16-credential">Credential</a> array</td><td>List of the person's credentials</td><td></td><td></td></tr><tr><td>languages</td><td>array</td><td></td><td></td><td></td></tr><tr><td>skills</td><td>array</td><td></td><td></td><td></td></tr><tr><td>tags</td><td><a href="7-data-structures.md#7.2.53-taggroup">TagGroup</a> array</td><td>Grouped list containing extended metadata about the person</td><td></td><td></td></tr></tbody></table>

### 7.2.40 Price

**Description:** Outlines the price of an Item

**Fields:**

| Name             | Type                                                     | Description                      |
| ---------------- | -------------------------------------------------------- | -------------------------------- |
| currency         | string                                                   |                                  |
| value            | [DecimalValue](7-data-structures.md#7.2.18-decimalvalue) | Default value of the Item price  |
| estimated\_value | [DecimalValue](7-data-structures.md#7.2.18-decimalvalue) | Estimated value of an Item price |
| computed\_value  | [DecimalValue](7-data-structures.md#7.2.18-decimalvalue) | Computed value of an Item price  |
| listed\_value    | [DecimalValue](7-data-structures.md#7.2.18-decimalvalue) | Listed value of an Item price    |
| offered\_value   | [DecimalValue](7-data-structures.md#7.2.18-decimalvalue) | Offered value of an Item price   |
| minimum\_value   | [DecimalValue](7-data-structures.md#7.2.18-decimalvalue) | Minimum value of an Item price   |
| maximum\_value   | [DecimalValue](7-data-structures.md#7.2.18-decimalvalue) | Maximum value of an Item price   |

### 7.2.41 Provider

**Description:** Outlines the catalog of a business.

**Fields:**

<table><thead><tr><th>Name</th><th>Type</th><th>Description</th><th>Notes</th><th data-hidden>Enum</th></tr></thead><tbody><tr><td>id</td><td>string</td><td>Id of the provider</td><td></td><td></td></tr><tr><td>descriptor</td><td><a href="7-data-structures.md#7.2.19-descriptor">Descriptor</a></td><td>Description of the provider</td><td></td><td></td></tr><tr><td>category_id</td><td>string</td><td>Category Id of the provider at the Provider Platform-level catalog</td><td></td><td></td></tr><tr><td>rating</td><td><a href="7-data-structures.md#7.2.43-rating">Rating</a></td><td>Rating of the provider</td><td></td><td></td></tr><tr><td>time</td><td><a href="7-data-structures.md#7.2.54-time">Time</a></td><td>Time during which the catalog is available</td><td></td><td></td></tr><tr><td>categories</td><td><a href="7-data-structures.md#7.2.10-category">Category</a> array</td><td>Categories in the catalog</td><td></td><td></td></tr><tr><td>fulfillments</td><td><a href="7-data-structures.md#7.2.25-fulfillment">Fulfillment</a> array</td><td>List of fulfillment terms of the provider</td><td></td><td></td></tr><tr><td>payments</td><td><a href="7-data-structures.md#7.2.38-payment">Payment</a> array</td><td>List of payment terms of the provider</td><td></td><td></td></tr><tr><td>locations</td><td><a href="7-data-structures.md#7.2.32-location">Location</a> array</td><td>Locations where the provider can be accessed</td><td></td><td></td></tr><tr><td>offers</td><td><a href="7-data-structures.md#7.2.34-offer">Offer</a> array</td><td>Offers listed by the provider</td><td></td><td></td></tr><tr><td>items</td><td><a href="7-data-structures.md#7.2.31-item">Item</a> array</td><td>Items cataloged by the provider</td><td></td><td></td></tr><tr><td>exp</td><td>string</td><td>Time after which catalog has to be refreshed</td><td>Format: date-time</td><td></td></tr><tr><td>rateable</td><td>boolean</td><td>Whether this provider can be rated or not</td><td></td><td></td></tr><tr><td>ttl</td><td>integer</td><td>The time-to-live in seconds, for this object. This can be overriden at deeper levels. A value of -1 indicates that this object is not cacheable.</td><td></td><td></td></tr><tr><td>tags</td><td><a href="7-data-structures.md#7.2.53-taggroup">TagGroup</a> array</td><td>Grouped metadata related to the provider</td><td></td><td></td></tr></tbody></table>

### 7.2.42 Quotation

**Description:** Outlines a quote. It is the estimated price of products or services from the Provider Platform. This has properties like price, breakup, and TTL.

**Fields:**

<table><thead><tr><th>Name</th><th>Type</th><th>Description</th><th>Notes</th><th data-hidden>Enum</th></tr></thead><tbody><tr><td>id</td><td>string</td><td>ID of the quote.</td><td>Format: uuid</td><td></td></tr><tr><td>price</td><td><a href="7-data-structures.md#7.2.40-price">Price</a></td><td>The total quoted <a href="7-data-structures.md#7.3.40-price">price</a></td><td></td><td></td></tr><tr><td>breakup</td><td>array</td><td>the breakup of the total quoted price</td><td></td><td></td></tr><tr><td>ttl</td><td><a href="7-data-structures.md#7.2.21-duration">Duration</a></td><td>Duration for which the quotation is valid</td><td></td><td></td></tr></tbody></table>

### 7.2.43 Rating

**Description:** Outlines the rating of an entity.

**Fields:**

<table><thead><tr><th>Name</th><th>Type</th><th>Description</th><th>Notes</th><th data-hidden>Notes</th></tr></thead><tbody><tr><td>rating_category</td><td>string</td><td>Category of the entity being rated</td><td>Enum Data Type in C: Item, Order, Fulfillment, Provider, Agent, Support</td><td></td></tr><tr><td>id</td><td>string</td><td>Id of the object being rated</td><td></td><td></td></tr><tr><td>value</td><td>string</td><td>Rating value given to the object. This can be a single value or can also contain an inequality operator like gt, gte, lt, lte. This can also contain an inequality expression containing logical operators like &#x26;&#x26; and</td><td>.</td><td></td></tr></tbody></table>

### 7.2.44 Region

**Description:** Outlines an arbitrary region of space. The network policy should contain a published list of supported regions by the network.

**Fields:**

<table><thead><tr><th>Name</th><th>Type</th><th>Description</th><th>Notes</th><th data-hidden>Format</th></tr></thead><tbody><tr><td>dimensions</td><td>string</td><td>The number of dimensions that are used to describe any point inside that region. The most common dimensionality of a region is 2, that represents an area on a map. There are regions on the map that can be approximated to one-dimensional regions like roads, railway lines, or shipping lines. 3 dimensional regions are rarer, but are gaining popularity as flying drones are being adopted for various fulfillment services.</td><td>Enum Data Type in C: 1, 2, 3</td><td></td></tr><tr><td>type</td><td>string</td><td>The type of region. This is used to specify the granularity of the region represented by this object. Various examples of two-dimensional region types are city, country, state, district, and so on. The network policy should contain a list of all possible region types supported by the network.</td><td></td><td></td></tr><tr><td>name</td><td>string</td><td>Name of the region as specified on the map where that region exists.</td><td></td><td></td></tr><tr><td>code</td><td>string</td><td>A standard code representing the region. This should be interpreted in the same way by all network participants.</td><td></td><td></td></tr><tr><td>boundary</td><td>string</td><td>A string representing the boundary of the region. One-dimensional regions are represented by polylines. Two-dimensional regions are represented by polygons, and three-dimensional regions can represented by polyhedra.</td><td></td><td></td></tr><tr><td>map_url</td><td>string</td><td>The url to the map of the region. This can be a globally recognized map or the one specified by the network policy.</td><td></td><td></td></tr></tbody></table>

### 7.2.45 ReplacementTerm

**Description:** The replacement policy for an item or an order.

**Fields:**

| Name               | Type                                                                   | Description                                                                                                                                                             |
| ------------------ | ---------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| fulfillment\_state | [FulfillmentState](7-data-structures.md#7.2.26-fulfillmentstate) array | The state of fulfillment during which this term is applicable.                                                                                                          |
| replace\_within    | [Time](7-data-structures.md#7.2.54-time)                               | Applicable only for buyer managed returns where the buyer has to replace the item before a certain date-time, failing which they will not be eligible for replacement.  |
| external\_ref      | [MediaFile](7-data-structures.md#7.2.33-mediafile)                     | Any file containing info related to the terms                                                                                                                           |

### 7.2.46 ReturnTerm

**Description:** Outlines the return policy of an item or an order.

**Fields:**

<table><thead><tr><th>Name</th><th>Type</th><th>Description</th><th>Notes</th><th data-hidden>xx</th></tr></thead><tbody><tr><td>fulfillment_state</td><td><a href="7-data-structures.md#7.2.26-fulfillmentstate">FulfillmentState</a> array</td><td>The state of fulfillment during which this term IETF''s applicable. </td><td></td><td></td></tr><tr><td>return_eligible</td><td>boolean</td><td>Indicates whether the item is eligible for return</td><td></td><td></td></tr><tr><td>return_time</td><td><a href="7-data-structures.md#7.2.54-time">Time</a></td><td>Applicable only for buyer managed returns where the buyer has to return the item to the origin before a certain date-time, failing which they will not be eligible for refund.</td><td></td><td></td></tr><tr><td>return_location</td><td><a href="7-data-structures.md#7.2.32-location">Location</a></td><td>The location where the item or order must / will be returned to</td><td></td><td></td></tr><tr><td>fulfillment_managed_by</td><td>string</td><td>The entity that will perform the return</td><td>Enum Data Type in C: CONSUMER, PROVIDER</td><td></td></tr></tbody></table>

### 7.2.47 Scalar

**Description:** Outlines a scalar.

**Fields:**

<table><thead><tr><th>Name</th><th>Type</th><th>Description</th><th>Notes</th><th data-hidden>Format</th></tr></thead><tbody><tr><td>type</td><td>string</td><td></td><td>Enum Data Type in C: CONSTANT, VARIABLE</td><td></td></tr><tr><td>value</td><td><a href="7-data-structures.md#7.2.18-decimalvalue">DecimalValue</a></td><td>Default value</td><td></td><td></td></tr><tr><td>estimated_value</td><td><a href="7-data-structures.md#7.2.18-decimalvalue">DecimalValue</a></td><td>Estimated value</td><td></td><td></td></tr><tr><td>computed_value</td><td><a href="7-data-structures.md#7.2.18-decimalvalue">DecimalValue</a></td><td>Computed value</td><td></td><td></td></tr><tr><td>range</td><td><a href="7-data-structures.md#7.2.18-decimalvalue">DecimalValue</a></td><td>Range of values</td><td></td><td></td></tr><tr><td>unit</td><td>string</td><td>unit of value</td><td></td><td></td></tr></tbody></table>

### 7.2.48 Schedule

**Description:** Outlines schedule as a repeating time period used to describe a regularly recurring event. At a minimum, a schedule will specify frequency which describes the interval between occurrences of the event. Additional information can be provided to specify the schedule more precisely. This includes identifying the timestamps(s) of when the event will take place. Schedules may also have holidays to exclude a specific day from the schedule. This has properties like frequency, holidays, and times.

**Fields:**

| Name      | Type                                             | Description             |
| --------- | ------------------------------------------------ | ----------------------- |
| frequency | [Duration](7-data-structures.md#7.2.21-duration) | Frequency of recurrence |
| holidays  | array                                            | Holidays                |
| times     | [Time](7-data-structures.md#7.2.54-time) array   | Time slots              |

### 7.3.49 State

**Description:** A bounded geopolitical region of governance inside a country.

**Fields:**

| Name | Type   | Description                                          |
| ---- | ------ | ---------------------------------------------------- |
| name | string | Name of the state                                    |
| code | string | State code as per country or international standards |

### 7.2.50 Stop

**Description:** A logical point in space and time during the fulfilment of an order.

**Fields:**

| Name             | Type                                                       | Description                                                                             |
| ---------------- | ---------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| id               | string                                                     |                                                                                         |
| parent\_stop\_id | string                                                     |                                                                                         |
| location         | [Location](7-data-structures.md#7.2.32-location)           | [Location](7-data-structures.md#7.3.32-location) of the stop                            |
| type             | string                                                     | The type of stop. Allowed values of this property can be defined by the network policy. |
| time             | [Time](7-data-structures.md#7.2.54-time)                   | Timings applicable at the stop.                                                         |
| instructions     | [Descriptor](7-data-structures.md#7.2.19-descriptor) array | Instructions that need to be followed at the stop                                       |
| contact          | [Contact](7-data-structures.md#7.2.13-contact)             | Contact details of the stop                                                             |
| person           | [Person](7-data-structures.md#7.2.39-person)               | The details of the person present at the stop                                           |
| authorization    | [Authorization](7-data-structures.md#7.2.5-authorization)  | Authorization details required to commence this leg of fulfillment                      |

### 7.2.51 Support

**Description:** Details of customer support.

**Fields:**

<table><thead><tr><th>Name</th><th>Type</th><th>Description</th><th>Notes</th><th data-hidden>Enum</th></tr></thead><tbody><tr><td>ref_id</td><td>string</td><td></td><td></td><td></td></tr><tr><td>callback_phone</td><td>string</td><td></td><td>Format: phone</td><td></td></tr><tr><td>phone</td><td>string</td><td></td><td>Format: phone</td><td></td></tr><tr><td>email</td><td>string</td><td></td><td>Format: email</td><td></td></tr><tr><td>url</td><td>string</td><td></td><td>Format: uri</td><td></td></tr></tbody></table>

### 7.2.52 Tag

**Description:** Outlines a tag. This is used to contain extended metadata. This object can be added as a property to any schema to describe extended attributes. For Application Platforms, tags can be sent during search to optimize and filter search results. Provider Platforms can use tags to index their catalog to allow better search functionality. Tags are sent by the Provider Platform as part of the catalog response in the `on_search` callback. Tags are also meant for display purposes. Upon receiving a tag, Application Platforms are meant to render them as name-value pairs. This is particularly useful when rendering tabular information about a product or service.

**Fields:**

| Name       | Type                                                 | Description                                                                                                                                                                                                                |
| ---------- | ---------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| descriptor | [Descriptor](7-data-structures.md#7.2.19-descriptor) | Description of the Tag, can be used to store detailed information.                                                                                                                                                         |
| value      | string                                               | The value of the tag. This set by the Provider Platform and rendered as-is by the Application Platform.                                                                                                                    |
| display    | boolean                                              | This value indicates if the tag is intended for display purposes. If set to `true`, then this tag must be displayed. If it is set to `false`, it should not be displayed. This value can override the group display value. |

### 7.2.53 TagGroup

**Description:** A collection of tag objects with group-level attributes ([Documentation on Tag Groups schema](https://github.com/beckn/protocol-specifications/discussions/316)).&#x20;

**Fields:**

| Name       | Type                                                 | Description                                                                                                                                                                                                                                                                                                                                                                                                       |
| ---------- | ---------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| display    | boolean                                              | Indicates the display properties of the tag group. If display is set to false, then the group will not be displayed. If it is set to true, it should be displayed. However, group-level display properties can be overriden by individual tag-level display property. As this schema is purely for catalog display purposes, it is not recommended to send this value during search. Has a default value of true. |
| descriptor | [Descriptor](7-data-structures.md#7.2.19-descriptor) | Description of the TagGroup, can be used to store detailed information.                                                                                                                                                                                                                                                                                                                                           |
| list       | array                                                | An array of Tag objects listed under this group. This property can be set by Application Platforms during search to narrow the `search` and achieve more relevant results. When received during `on_search`, Application Platforms must render this list under the heading described by the `name` property of this schema.                                                                                       |

### 7.2.54 Time

**Description:** Outlines time in its various forms. It can be a single point in time/duration or a structured timetable of operations. This has properties like label, timestamp, duration, range, days, and schedule.

**Fields:**

<table><thead><tr><th>Name</th><th>Type</th><th>Description</th><th>Notes</th><th data-hidden>Enum</th></tr></thead><tbody><tr><td>label</td><td>string</td><td></td><td></td><td></td></tr><tr><td>timestamp</td><td>string</td><td></td><td>Format: date-time</td><td></td></tr><tr><td>duration</td><td><a href="7-data-structures.md#7.2.21-duration">Duration</a></td><td>Duration between two instances of time</td><td></td><td></td></tr><tr><td>range</td><td>object</td><td></td><td></td><td></td></tr><tr><td>days</td><td>string</td><td>comma separated values representing days of the week</td><td></td><td></td></tr><tr><td>schedule</td><td><a href="7-data-structures.md#7.2.48-schedule">Schedule</a></td><td>schedule</td><td></td><td></td></tr></tbody></table>

### 7.2.55 Tracking

**Description:** Contains tracking information that can be used by the Application Platform to track the fulfillment of an order in real-time. which is useful for knowing the location of time-sensitive deliveries.

**Fields:**

| Name     | Type                                             | Description                                                                                                                                                                                                                                                                                                                                                                                 | Format | Enum             |
| -------- | ------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------ | ---------------- |
| id       | string                                           | A unique tracking reference number                                                                                                                                                                                                                                                                                                                                                          |        |                  |
| url      | string                                           | A URL to the tracking endpoint. This can be a link to a tracking webpage, a webhook URL created by the Application Platform where Provider Platform can push the tracking data, or a GET url creaed by the Provider Platform which the Application Platform can poll to get the tracking data. It can also be a websocket URL where the Provider Platform can push real-time tracking data. | uri    |                  |
| location | [Location](7-data-structures.md#7.2.32-location) | In case there is no real-time tracking endpoint available, this field will contain the latest location of the entity being tracked. The Provider Platform will update this value everytime the Application Platform calls the track API.                                                                                                                                                    |        |                  |
| status   | string                                           | This value indicates if the tracking is currently active or not. If this value is `active`, then the Application Platform can begin tracking the order. If this value is `inactive`, the tracking URL is considered to be expired and the Application Platform should stop tracking the order.                                                                                              |        | active, inactive |

### 7.2.56 Vehicle

**Description:** Outlines a vehicle is a device that is designed or used to transport people or cargo over land, water, air, or through space. This has properties like category, capacity, make, model, size, variant, colour,energy\_type, and registration.

**Fields:**

| Name               | Type    | Description |
| ------------------ | ------- | ----------- |
| category           | string  |             |
| capacity           | integer |             |
| make               | string  |             |
| model              | string  |             |
| size               | string  |             |
| variant            | string  |             |
| color              | string  |             |
| energy\_type       | string  |             |
| registration       | string  |             |
| wheels\_count      | string  |             |
| cargo\_volumne     | string  |             |
| wheelchair\_access | string  |             |
| code               | string  |             |
| emission\_standard | string  |             |

### 7.2.57 XInput

**Description:** Contains any additional or extended inputs required to confirm an order. This is typically a Form Input. Sometimes, the selection of catalog elements is not enough for the Provider Platform to confirm an order. For example, to confirm a flight ticket, the airline requires details of the passengers along with information on baggage, and identity, in addition to the class of ticket. Similarly, a logistics company may require details on the nature of the shipment in order to confirm the shipping. A recruiting firm may require additional details on the applicant in order to confirm a job application. For all such purposes, they can choose to send this object attached to any object in the catalog that is required to be sent while placing the order. This object can typically be sent at an item level or at the order level. The item level XInput will override the Order level XInput as it indicates a special requirement of information for that particular item. Hence the Application Platform must render a separate form for the Item and another form at the Order level before confirmation.

**Fields:**

| Name     | Type                                     | Description                                                                                            |
| -------- | ---------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| form     | [Form](7-data-structures.md#7.2.24-form) | Form details to capture input                                                                          |
| required | boolean                                  | Indicates whether the form data is mandatorily required by the Provider Platform to confirm the order. |
| head     | object                                   | Form headers                                                                                           |
