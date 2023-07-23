---
description: >-
  Key Digital Functionalities describe the core (required) functions that this
  Building Block must be able to perform.
---

# 4 Key Digital Functionalities

{% hint style="success" %}
The Key Digital Functionalities describe the core (required) functions that this building block must be able to perform. These functionalities should be described as business processes as opposed to technical specifications or API definitions.

Note, this section may be extended after the key functionalities have been listed to include any assumptions or context that is needed. Additionally, if the Building Block contains multiple components, the functionalities for each may be described.
{% endhint %}

To facilitate various activities and different actors as described in section 2, the E-Marketplace building block MUST have specific key digital functionalities. E-marketplace transactions by definition should have:

1. Consumer Platforms (like Super-apps, Chat messengers, Storefronts etc) to provide a rich, demand-centric experience
2. Provider Platforms (like a Hospital Management System, A Tendering Platform, or a Store Backend) that provides a rich, supply-centric experience
3. Consumers (like patients, citizen applicants, procurement personnel, <mark style="color:blue;">organizations</mark> etc);
4. Providers (like hospitals, government departments, stores,<mark style="color:blue;">organizations</mark> );
5. Agent (Like government service personel, sellers, drivers, doctors, etc),
6. Intent (like a search by product, search by category, search by provider, etc),
7. Catalogs (like products, offers, add-ons, <mark style="color:blue;">services</mark>).
8. Payments and Settlements (like Cash on Delivery, Prepayment, T+x settlement, etc)
9. Order <mark style="color:blue;">management</mark> (like a procurements, appointments, bids, service request)
10. Fulfillments (like appointments, tender approval, delivery of goods and services)
11. <mark style="color:blue;">Procurement lifecycle activities (from bid invitation to ordering to feedback, milestone deliverables, monitoring, archiving)</mark>

The E-Marketplace building block must utilize the above objects to primarily support various consumer-provider interactions like discovery, ordering, fulfillment, and post-fulfillment. For example, A patient (Consumer) on WhatsApp (Consumer Platform) can search (Discovery) for a doctor (Agent) by his name (Intent). This request can be sent to ORS (Provider Platform) that returns a list of Hospitals (Providers), with the various services offered (Catalog). Once identified, the patient (Consumer) can book an appointment (Order) with the Doctor(Agent).

The various actors and their activities described in section 2 must be supported by a set of non-redundant, Key Digital Functionalities listed below:

## 4.1 Catalog Management

This key digital functionality should allow providers to quickly and efficiently return a matching catalog upon receipt of a search intent. This e-marketplace must also allow authorized administrators of the host entity to create and manage aggregated catalogs of providers, products and services that can operate across multiple locations and timings. It is to be noted that this functionality does not only apply to catalogs of products and services. It can be used to publish any economic resource that has a fulfillment cycle (for example, it should allow government departments to create and manage catalogs of tenders across multiple departments spread across multiple locations). Admins must be able to create, read, update or delete catalogs, and any sub-component of this catalog like Items, Categories, Providers, Locations, Agents, Fulfillments, Payments and others. In summary, the building block enables cataloging of various elements such as providers, products, services, consumers, tenders, agents, etc., such that they can be searched, retrieved, shared in appropriate workflows.&#x20;

## 4.2 Inventory Management

Authorized users of provider platforms should be able to manage inventory of various resources available in a catalog. Providers should be able to manage the availability of products, agents, vehicles etc, <mark style="color:blue;">dynamically/on real time basis,</mark> in this building block.

## 4.3 Quotation Management

This key digital functionality of the e-marketplace building block should allow consumers to select items, offers, and add-ons from a catalog and build an order. It should be able to transmit them to the respective provider and request a quote. Using this functionality, consumers should be able to bid for items <mark style="color:blue;">(one or more)</mark> selected from <mark style="color:blue;">(one or more different sources/vendors)</mark> a catalog. It should also be able to render the quotation agreed between transacting entities. Providers should be able to calculate a quote basis the items, offers and add-ons selected. Providers should also be able to add dynamic offers without being specifically requested by the consumer. For example, a consumer should be able to add items from a provider's catalog, add offers, select add-ons into a common cart and view the total cart value. Similarly, a business should be able to create a bid for a tender and submit it to the provider for evaluation. This functionality should also allow providers to request additional information from the consumer that is required to proceed to the next stage. This functionality should also allow providers to transmit requests to the consumer to allow consented data sharing required to calculate a quote.

## 4.4 Terms Management

This key digital functionality of the e-marketplace building block should allow the consumer to share billing details, fulfillment details, <mark style="color:blue;">legal jurisdiction of dispute and resolution mechanism</mark> and any additional information required for the provider to generate the final contract / order with the terms of fulfillment, payment, cancellation, refund, returns, and replacements. Administrators of the provider platforms should be able to configure various rules for final quote calculation, payment terms, and other terms of service depending upon the information received from the consumer. Providers should be able to evaluate the additional information that was requested when executing the quote agreement function, and re-calculate the quote. For example, a healthcare service might have a standard quote for general citizens, but provide a discounted rate when it discovers from the additional data that the consumer is a senior citizen. It should allow the consumer to view the final payment terms, and all details that will be included in the final contract. This functionality should allow for the final draft order/contract to be exchanged between the consumer and the provider.

## 4.5 Order Management

This key digital functionality of the e-marketplace building block should allow the consumer to confirm an order. Bidders can confirm a bid in an auction <mark style="color:blue;">**(are we anticipating to perform auction too?)**</mark>. It should allow creation and confirmation of an order expressed as a dual-digitally signed contract, with the terms that were agreed upon. In case the terms require payment before the creation of the contract, it should also allow the transmission of the proof payment made from the payer to the payee. It should allow the provider to transmit a contract to the consumer. It should also allow the consumer to request the provider to update various elements of the contract. It should also allow updates to the terms of the contract and inform the consumer of the update. _<mark style="color:red;">It should allow browsing of contracts based on its various attributes.</mark>_

## 4.6 Fulfillment Management

This key digital functionality of the e-marketplace building block should allow the consumer of a service to receive various status updates regarding the fulfillment of a contract. This should also allow providers to send various fulfillment updates to the consumer. It should also allow providers to allocate service agents manually or algorithmically if and when required (for example, ambulance allocation as a response to a nearby emergency). <mark style="color:blue;">The contract fulfilment could be having a long duration of workflow (for ex. 3 years), depending upon the nature of the contract signed. The building block should be able to facilitate all the processes and reflect dynamic status of a signed contract with updates/remarks/comments. For example, the sign-off agreement with feedback, lessons learnt report shall be submitted as and when the project finishes formally.</mark>

## 4.7 Tracking Management

Consumers should be able to track the fulfillment of an order in real-time. Providers should be able to stream real-time data to the consumer related to the fulfillment of an order. This tracking is not necessarily geospatial, but can contain any information that provides the consumer with real-time information like tracking of physical variables like temperature, speed, countdown timers in bidding use cases. This functionality should render the real-time data to the consumer via a tracking page.&#x20;

## 4.8 Cancellation Management

This key digital functionality of the e-marketplace building block should allow the consumer or the provider to cancel a contract. This functionality should allow a consumer to view the terms of cancellation sent by a provider in response to a cancellation request. It should also allow both the parties to see the canceled order. Providers should be able to request a cancellation reason along with additional information related to the reason for the cancellation. Consumers should be able to provide a cancellation reason and additional information related to the cancellation request. <mark style="color:blue;">Once a cancellation is agreed by both the parties, the current and historical data related to this activity/chain of activities shall be rolled back or archived, as per the policy.</mark>

## 4.9 Rating and Feedback Management

Users of this key digital functionality should be able to rate various entities involved in the fulfillment of a contract.  These users can be both consumers and providers. A consumer should be able to rate various aspects of the service like the agent, vehicle, quality of service, customer support etc. A provider’s agent should be able to rate the consumer as well. Upon receipt of a rating, a provider can ask for additional feedback related to the rating. <mark style="color:blue;">This means that the activity can occur throughoout the cycle of various activities, not just at the end of a single process.</mark>

## 4.10 Support Management

Users of this key digital functionality should be able contact the support center to enquire about any issues that they may be facing and create a ticket. Customer support executives should be able to view details of a contract, fetch related information, view open tickets, and resolve them. If needed, customer support executives can fetch the contact details of a provider, or their agents to gain more information related to the fulfillment of an order.&#x20;

## 4.11 Information Mediator Interface

This interface handles protocols to interact with the Information Mediator Building Block in order to securely expose e-marketplace services to other Building Blocks. It also enables the e-marketplace to access services of other Building Blocks and applications through the Information Mediator Building Block

## 4.12 Payment Interface

This interface handles protocols to interact with the Payment Building Block via the Information Mediator Building Block in order to initiate payment transactions as per the terms agreed between the consumer and the provider. Consumers should be able to check-out an order through this interface.&#x20;

## 4.13 E-Signature Interface

This interface handles protocols to interact with the E-Signature Building Block via the Information Mediator Building Block in order to digitally sign messages exchanged between the consumer and the provider. Sending platforms should be able to digitally sign requests and Receiving Platforms should be able to digitally verify the signature of the message. The consumer and provider should be able to execute digitally signed micro-contracts on each message exchange using this interface.

## 4.14 Registration Interface

This interface handles protocols to interact with the Registration Building Block via the Information Mediator Building Block for signing up users on their respective platforms. Consumers should be able to sign up to Consumer Platforms through this interface. The building block would enable users to register consumers, providers, products, services, agents, into respective catalogs. A registered element of a catalog may be enabled or disabled from being used in the system.

## <mark style="color:blue;">4.15 Digital Identity and Verification Interface</mark>

<mark style="color:blue;">This interface should be able to identify and verify the individuals (may be through citizen identification or other recognized identity), firms (tax number or licence) w.r.t their national data registries, while their registration. This will facilitate authentication, avoids duplication, monitoring and evaluation, fetch dashboard statistics etc.</mark>

## <mark style="color:blue;">4.16 Promotional Communications</mark>

<mark style="color:blue;">The building block should facilitate various out reach activities through social media, online, offline activities to create awareness and interest amongst the stakeholders about the eMarketplace. For example, a notification may be widespread for a fixed duration of time. Interested stakeholders may subscribe to the eMarketplace application/channel to receive notifications/messages of their interest.</mark>

## <mark style="color:blue;">**4.17 Content Management Interface**</mark>

<mark style="color:blue;">This interface should be able to enable the adminstrators to moderate, curate, access and share the content creation. The interface can create details about eMarketplace, create knowledge banks, best practice repositories. It should also be able to connect the BB with social media, able to publish the digital advertisements.</mark>

The building block must allow sellers to add name, images and description to products and services.&#x20;

## <mark style="color:blue;">**4.18 Workflow Interface**</mark>

<mark style="color:blue;">This interface should be able to automate and orchestrate capabilities for specified business processes within and across Building Blocks. The initiation of a workflow, for example-submission of related documents for procurement/purchase request, shall be automated till the fulfilment of that order/request/cancellation.</mark>&#x20;

The building block must allow administrators to configure various workflows that occur within a business or provider.&#x20;

## <mark style="color:blue;">**4.19 Dashboard & Business Analytics Interface**</mark>

<mark style="color:blue;">This interface should be able to data visualize key statistics such number of procurements/items with different status such as active, fulfilled, cancelled. It should be able to indicate archived/historical data as well. The interface should offer data driven insights (risk analysis, predicitive analytics) on most and least consumed goods and services, volume, financial details on monthly and yearly basis.</mark>

## <mark style="color:blue;">**4.20 GIS BB Interface**</mark>

<mark style="color:blue;">The Geographic Information System (GIS) interface should be able to identify, tag, analyze locations of goods and services, persons, entities, piece of equipment, locations with timestamps. This will enable to track the goods and services when they are under active lifecycle of eMarketplace BB.</mark>

## <mark style="color:blue;">**4.21 Consent Management Interface**</mark>

<mark style="color:blue;">This interface should allow an application or system to acquire and validate consent from an authorized user in order to grant access or permissions for carrying out a task. Biometric identities, digital signatures or simply SMS messages may be used to provide consent.</mark>

## <mark style="color:blue;">**4.22 Messaging Interface**</mark>

<mark style="color:blue;">This interface should act as a secured communication channel between users and service providers. Security features, logging, back-up, encrypted and non encrypted messages (such as notifications, reminders, alerts), chatbot services shall be enabled by this interface.</mark>

## <mark style="color:blue;">**4.23 Scheduling Interface**</mark>

<mark style="color:blue;">This interface shall be able to orchestrate processes automatically. For example, when a bidder submits documents, it shall trigget certain series of steps/processes, send an alert by email and SMS, update the stock of remaining items, number of goods and services in active phase etc. It shall also complete the lifecycleof processes involved in a process. For example, from initiation to closure of a series of activities involved in ordering an item/goods/services.</mark>

## <mark style="color:blue;">4.24 Bid Evaluation</mark>

<mark style="color:blue;">The building block should facilitate bid evaluation process (financial, technical or any other type) with a defined criteria. The evaluation shall be conducted by the buyer, only. At first, the buyer defines an evaluation criteria for a good or service. Then the buyer admin/a group of professionals will receive the documents/details submitted by the seller; and evaluate them based on the pre-defined criteria. In case the buyers/suppliers have any clarifications, the concerned party should be able to seek guidance through writing questions or addendum or corrigendum. Finally, the evaluation should select the best bidder/supplier.</mark>

