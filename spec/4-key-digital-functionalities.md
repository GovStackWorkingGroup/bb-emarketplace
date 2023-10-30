---
description: >-
  Key Digital Functionalities describe the core (required) functions that this
  Building Block must be able to perform.
---

# 4 Key Digital Functionalities

In General, this Building Block shall be accessible on various delivery channels such as Mobile, Kiosk, Web, and applications and should be digitally inclusive for users with different capabilities. The Building Block minor features such as physical delivery of goods and services, client feedback, etc. should be able to work on feature phones (without internet) as well. To facilitate various activities and different actors as described in section 2, the e-Marketplace Building Block must have specific Key Digital Functionalities. e-Marketplace transactions by definition should have:

* Consumer Platforms (i.e. Super-apps, Chat messengers, Storefronts, etc.) to provide a rich, demand-centric experience;
* Provider Platforms (i.e. a Hospital Management System, a Tendering Platform, or a Store Backend) that provide a rich, supply-centric experience;
* Consumers (i.e. patients, citizen applicants, procurement personnel, organizations, etc.);
* Providers (i.e. hospitals, government departments, stores, organizations);
* Agent (i.e. government service personnel, sellers, drivers, doctors, etc.);
* Intent (i.e. a search by product, search by category, search by provider, etc.);
* Catalogs (i.e. products, offers, add-ons, services);
* Payments and Settlements (i.e. Cash on Delivery, Prepayment, T+n settlement, etc.);
* Order management (i.e. procurements, appointments, bids, service requests);
* Fulfillments (i.e. appointments, tender approval, delivery of goods and services);
* Management of procurement lifecycle activities (from tendering to bidding, evaluation ordering, delivery tracking to feedback, etc.).

The e-Marketplace Building Block must utilize the above objects to primarily support various consumer-provider interactions like discovery, ordering, fulfillment, and post-fulfillment. For example, a patient (Consumer) on WhatsApp (Consumer Platform) can search (Discovery) for a doctor (Agent) by his name (Intent). This request can be sent to ORS (Healthcare Provider Platform) that returns a list of Hospitals (Providers), with the various services offered (Catalog). Once identified, the patient (Consumer) can book an appointment (Order) with the Doctor (Agent).

The various actors and their activities described in section 2 must be supported by a set of non-redundant, Key Digital Functionalities listed below:

## 4.1 Catalog Management

This key digital functionality should allow providers to quickly and efficiently return a matching catalog upon receipt of a search intent. This e-Marketplace must also allow authorized administrators of the host entity to create and manage aggregated catalogs of providers, products, and services that can operate across multiple locations and timings. This functionality does not only apply to catalogs of products and services, it can be used to publish any economic resource that has a fulfillment cycle (e.g. it should allow government departments to create and manage catalogs of tenders across multiple departments spread across multiple locations). Admins must be able to create, read, update, or delete catalogs, and any sub-component of this catalog like Items/Categories/Providers/Locations/Agents/Fulfillments/Payments/etc. For tendered procurement, the government can publish tenders along with associated documents (e.g. Request for Proposals) in the tender's catalog. Providers can search the catalog and bid accordingly through quotation management services.

In summary, the Building Block enables the cataloging of various elements such as providers/products/services/consumers/tenders/agents/etc., such that they can be searched, retrieved, and shared in appropriate workflows.&#x20;

## 4.2 Inventory Management

Authorized users of provider platforms should be able to manage the inventory of various resources available in a catalog. Providers should be able to manage the availability of products/agents/vehicles/etc., dynamically/on a real-time basis<mark style="color:blue;">,</mark> in this Building Block.

## 4.3 Quotation Management

This key digital functionality should allow consumers to select items, offers, and add-ons from a catalog and build an order. It should be able to transmit them to the respective provider and request a quote. Using this functionality, consumers should be able to bid for items (one or more) selected from (one or more different sources/vendors) in a catalog. It should also be able to render the quotation agreed between transacting entities. Providers should be able to calculate a quote basis the item/offers/add-ons selected and to add dynamic offers without being specifically requested by the consumer. For example, a consumer should be able to add items from a provider's catalog, add offers, select add-ons into a common cart, and view the total cart value. Similarly, a business should be able to create a bid for a tender and submit it to the provider for evaluation. This functionality should also allow providers to request additional information from the consumer that is required to proceed to the next stage. This functionality should also allow providers to transmit requests to the consumer to allow consented data sharing required to calculate a quote.

## 4.4 Terms Management

This key digital functionality should allow the consumer to share billing details, fulfillment details, legal jurisdiction of dispute and resolution mechanism, and any additional information required for the provider to generate the final contract/order with the terms of fulfillment, payment, cancellation, refund, returns, and replacements. Administrators of the provider platforms should be able to configure various rules for final quote calculation, payment terms, and other terms of service depending upon the information received from the consumer. Providers should be able to evaluate the additional information that was requested when executing the quote agreement function and re-calculate the quote. For example, a healthcare service might have a standard quote for general citizens, but provide a discounted rate when it discovers from the additional data that the consumer is a senior citizen. It should allow the consumer to view the final payment terms and all details that will be included in the final contract. This functionality should allow for the final draft order/contract to be exchanged between the consumer and the provider.

## 4.5 Order Management

This key digital functionality should allow the consumer to confirm an order. Bidders can confirm a bid in an auction. It should allow the creation and confirmation of an order expressed as a dual-digitally signed contract, with the terms that were agreed upon. In case the terms require payment before the creation of the contract, it should: allow the transmission of the proof of payment made from the payer to the payee, allow the provider to transmit a contract to the consumer, allow the consumer to request the provider to update various elements of the contract, allow updates to the terms of the contract and inform the consumer of the update, and allow browsing of contracts based on its various attributes.

## 4.6 Order Fulfillment&#x20;

This key digital functionality should allow the consumer of a service to receive various status updates regarding the fulfillment of a contract. This should allow providers to send various fulfillment updates to the consumer, and allow providers to allocate service agents manually/algorithmically (e.g. ambulance allocation as a response to a nearby emergency). The contract fulfilment could have a long duration of workflow (i.e. 3 years), depending upon the nature of the contract signed. The Building Block should be able to facilitate all the processes and reflect the dynamic status of a signed contract with updates/remarks/comments. For example, the sign-off agreement with feedback, and lessons learned report shall be submitted as and when the project finishes formally.

## 4.7 Order Tracking&#x20;

Consumers should be able to track the fulfillment of an order in real-time. Providers should be able to stream real-time data to the consumer related to the fulfillment of an order. This tracking is not necessarily geospatial but can contain any information that provides the consumer with real-time information like tracking of physical variables like temperature, speed, and countdown timers in bidding use cases. This functionality should render the real-time data to the consumer via a tracking page.&#x20;

## 4.8 Order Cancellation

This key digital functionality should allow the consumer or the provider to cancel a contract. This functionality should allow a consumer to view the terms of cancellation sent by a provider in response to a cancellation request. It should also allow both parties to see the canceled order. Providers should be able to request a cancellation reason along with additional information related to the reason for the cancellation. Consumers should be able to provide a cancellation reason and additional information related to the cancellation request. Once a cancellation is agreed upon by both parties, the current and historical data related to this activity/chain of activities shall be rolled back or archived, as per the policy.

## 4.9 Rating and Feedback Management

Users of this key digital functionality should be able to rate various entities involved in the fulfillment of a contract.  These users can be both consumers and providers. A consumer should be able to rate various aspects of the service like the agent, vehicle, quality of service, customer support, etc. A provider’s agent should be able to rate the consumer as well. Upon receipt of a rating, a provider can ask for additional feedback related to the rating. This means that the activity can occur throughout the cycle of various activities, not just at the end of a single process.

## 4.10 Support Management

Users of this key digital functionality should be able to contact the support center to enquire about any issues that they may be facing and create a ticket. Customer support executives should be able to view details of a contract, fetch related information, view open tickets, and resolve them. If needed, customer support executives can fetch the contact details of a provider, or their agents to gain more information related to the fulfillment of an order.&#x20;

## 4.11 Bid Evaluation

The Building Block should facilitate the bid evaluation process (financial/technical/etc.) with defined criteria. The evaluation shall be conducted by the buyer, only. At first, the buyer defines an evaluation criteria for a good or service. Then the buyer admin/a group of professionals will receive the documents/details submitted by the seller; and evaluate them based on the pre-defined criteria. In case the buyers/suppliers have any clarifications, the concerned party should be able to seek guidance through writing questions/addendum/corrigendum. Finally, the evaluation should select the best bidder/supplier.

