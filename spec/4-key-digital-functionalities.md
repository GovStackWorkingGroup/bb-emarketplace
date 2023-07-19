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

To facilitate various activities and different actors as described in section 2, the E-Marketplace building block MUST have specific key digital functionalities. E-marketplace transactions <mark style="color:blue;">**(activities?**</mark><mark style="color:blue;">)</mark> by definition should have:

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

The key digital functionalities would include at minimum the following:

1.

The E-Marketplace building block must utilize the above objects to primarily support various consumer-provider interactions like discovery, ordering, fulfillment, and post-fulfillment. For example, A patient (Consumer) on WhatsApp (Consumer Platform) can search (Discovery) for a doctor (Agent) by his name (Intent). This request can be sent to ORS (Provider Platform) that returns a list of Hospitals (Providers), with the various services offered (Catalog). Once identified, the patient (Consumer) can book an appointment (Order) with the Doctor(Agent).



The various actors and their activities described in section 2 must be supported by a set of non-redundant, Key Digital Functionalities listed below:

## 4.1 Searching (Search Management)

The e-marketplace must allow a consumer to declare a search intent. It should allow a consumer to search and browse a catalog of items <mark style="color:blue;">(goods and services)</mark>. It is to be noted that this intent does not only apply to searching for products or services. Any consumer who wants to search for an economic resource can use this functionality (for example, a citizen can search for products or services offered by government institutions like hospitals, or public services; or a business can search for tenders floated by a government department). This is done by specifying various attributes like item they are looking for, the category of items they want to search, the location where they want to limit their search to, the location they want their product or service delivered, the time when then want to receive the item, who they want to buy from (for example, It must allow businesses to discover catalogs of tenders that have been floated by a specific government department). This key digital functionality should also allow a consumer to view catalogs returned on a federated network. It should also allow users to browse catalogs across multiple providers, filter search results, browse items under a specific category, and view details of a specific Item. <mark style="color:blue;">The search results shall be fetched in chronological order (latest to old; vice versa; and archived).</mark>

## 4.2 Catalog Management

This key digital functionality should allow providers to quickly and efficiently return a matching catalog upon receipt of a search intent. This e-marketplace must also allow authorized administrators of the host entity to create and manage aggregated catalogs of providers, products and services that can operate across multiple locations and timings. It is to be noted that this functionality does not only apply to catalogs of products and services. It can be used to publish any economic resource that has a fulfillment cycle (for example, it should allow government departments to create and manage catalogs of tenders across multiple departments spread across multiple locations). Admins must be able to create, read, update or delete catalogs, and any sub-component of this catalog like Items, Categories, Providers, Locations, Agents, Fulfillments, Payments and others. In summary, the building block enables cataloging of various elements such as providers, products, services, consumers, tenders, agents, etc., such that they can be searched, retrieved, shared in appropriate workflows.&#x20;

## 4.3 Inventory Management

Authorized users of provider platforms should be able to manage inventory of various resources available in a catalog. Providers should be able to manage the availability of products, agents, vehicles etc, <mark style="color:blue;">dynamically/on real time basis,</mark> in this building block.

## 4.4 Quote Agreement (Quote Management)

This key digital functionality of the e-marketplace building block should allow consumers to select items, offers, and add-ons from a catalog and build an order. It should be able to transmit them to the respective provider and request a quote. Using this functionality, consumers should be able to bid for items <mark style="color:blue;">(one or more)</mark> selected from <mark style="color:blue;">(one or more different sources/vendors)</mark> a catalog. It should also be able to render the quotation agreed between transacting entities. Providers should be able to calculate a quote basis the items, offers and add-ons selected. Providers should also be able to add dynamic offers without being specifically requested by the consumer. For example, a consumer should be able to add items from a provider's catalog, add offers, select add-ons into a common cart and view the total cart value. Similarly, a business should be able to create a bid for a tender and submit it to the provider for evaluation. This functionality should also allow providers to request additional information from the consumer that is required to proceed to the next stage. This functionality should also allow providers to transmit requests to the consumer to allow consented data sharing required to calculate a quote.

## 4.5 Terms <mark style="color:blue;">and</mark> Agreement

This key digital functionality of the e-marketplace building block should allow the consumer to share billing details, fulfillment details, <mark style="color:blue;">legal jurisdiction of dispute and resolution mechanism</mark> and any additional information required for the provider to generate the final contract / order with the terms of fulfillment, payment, cancellation, refund, returns, and replacements. Administrators of the provider platforms should be able to configure various rules for final quote calculation, payment terms, and other terms of service depending upon the information received from the consumer. Providers should be able to evaluate the additional information that was requested when executing the quote agreement function, and re-calculate the quote. For example, a healthcare service might have a standard quote for general citizens, but provide a discounted rate when it discovers from the additional data that the consumer is a senior citizen. It should allow the consumer to view the final payment terms, and all details that will be included in the final contract. This functionality should allow for the final draft order/contract to be exchanged between the consumer and the provider.

## 4.6 Contract Creation and Management

This key digital functionality of the e-marketplace building block should allow the consumer to confirm an order. Bidders can confirm a bid in an auction <mark style="color:blue;">**(are we anticipating to perform auction too?)**</mark>. It should allow creation and confirmation of an order expressed as a dual-digitally signed contract, with the terms that were agreed upon. In case the terms require payment before the creation of the contract, it should also allow the transmission of the proof payment made from the payer to the payee. It should allow the provider to transmit a contract to the consumer. It should also allow the consumer to request the provider to update various elements of the contract. It should also allow updates to the terms of the contract and inform the consumer of the update. _<mark style="color:red;">It should allow browsing of contracts based on its various attributes.</mark>_

## 4.7 Contract Fulfillment

This key digital functionality of the e-marketplace building block should allow the consumer of a service to receive various status updates regarding the fulfillment of a contract. This should also allow providers to send various fulfillment updates to the consumer. It should also allow providers to allocate service agents manually or algorithmically if and when required (for example, ambulance allocation as a response to a nearby emergency). <mark style="color:blue;">The contract fulfilment could be having a long duration of workflow (for ex. 3 years), depending upon the nature of the contract signed. The building block should be able to facilitate all the processes and reflect dynamic status of a signed contract with updates/remarks/comments. For example, the sign-off agreement with feedback, lessons learnt report shall be submitted as and when the project finishes formally.</mark>

## 4.8 Purchase Order fulfillment Tracking (Purchase Order Management)

Consumers should be able to track the fulfillment of an order in real-time. Providers should be able to stream real-time data to the consumer related to the fulfillment of an order. This tracking is not necessarily geospatial, but can contain any information that provides the consumer with real-time information like tracking of physical variables like temperature, speed, countdown timers in bidding use cases. This functionality should render the real-time data to the consumer via a tracking page.&#x20;

## 4.9 Purchase Order Cancellation

This key digital functionality of the e-marketplace building block should allow the consumer or the provider to cancel a contract. This functionality should allow a consumer to view the terms of cancellation sent by a provider in response to a cancellation request. It should also allow both the parties to see the canceled order. Providers should be able to request a cancellation reason along with additional information related to the reason for the cancellation. Consumers should be able to provide a cancellation reason and additional information related to the cancellation request. <mark style="color:blue;">Once a cancellation is agreed by both the parties, the current and historical data related to this activity/chain of activities shall be rolled back or archived, as per the policy.</mark>

## 4.10 Rating and Feedback (Feedback Management)

Users of this key digital functionality should be able to rate various entities involved in the fulfillment of a contract.  These users can be both consumers and providers. A consumer should be able to rate various aspects of the service like the agent, vehicle, quality of service, customer support etc. A provider’s agent should be able to rate the consumer as well. Upon receipt of a rating, a provider can ask for additional feedback related to the rating. <mark style="color:blue;">This means that the activity can occur throughoout the cycle of various activities, not just at the end of a single process.</mark>

## 4.11 Support (Support Management)

Users of this key digital functionality should be able contact the support center to enquire about any issues that they may be facing and create a ticket. Customer support executives should be able to view details of a contract, fetch related information, view open tickets, and resolve them. If needed, customer support executives can fetch the contact details of a provider, or their agents to gain more information related to the fulfillment of an order.&#x20;

## 4.12 Information Mediator Interface

This interface handles protocols to interact with the Information Mediator Building Block in order to securely expose e-marketplace services to other Building Blocks. It also enables the e-marketplace to access services of other Building Blocks and applications through the Information Mediator Building Block

## 4.13 Payment Interface

This interface handles protocols to interact with the Payment Building Block via the Information Mediator Building Block in order to initiate payment transactions as per the terms agreed between the consumer and the provider. Consumers should be able to check-out an order through this interface.&#x20;

## 4.14 E-Signature Interface

This interface handles protocols to interact with the E-Signature Building Block via the Information Mediator Building Block in order to digitally sign messages exchanged between the consumer and the provider. Sending platforms should be able to digitally sign requests and Receiving Platforms should be able to digitally verify the signature of the message. The consumer and provider should be able to execute digitally signed micro-contracts on each message exchange using this interface.

## 4.15 Registration Interface

This interface handles protocols to interact with the Registration Building Block via the Information Mediator Building Block for signing up users on their respective platforms. Consumers should be able to sign up to Consumer Platforms through this interface. The building block would enable users to register consumers, providers, products, services, agents, into respective catalogs. A registered element of a catalog may be enabled or disabled from being used in the system.

## <mark style="color:blue;">4.16 Digital Identity and Verification Interface</mark>

<mark style="color:blue;">This interface should be able to identify and verify the individuals (may be through citizen identification or other recognized identity), firms (tax number or licence) w.r.t their national data registries, while their registration. This will facilitate authentication, avoids duplication, monitoring and evaluation, fetch dashboard statistics etc.</mark>

## <mark style="color:blue;">4.17 Promotional Communications</mark>

<mark style="color:blue;">The building block should facilitate various out reach activities through social media, online, offline activities to create awareness and interest amongst the stakeholders about the eMarketplace. For example, a notification may be widespread for a fixed duration of time. Interested stakeholders may subscribe to the eMarketplace application/channel to receive notifications/messages of their interest.</mark>

## <mark style="color:blue;">**4.18 Content Management Interface**</mark>

<mark style="color:blue;">This interface should be able to enable the adminstrators to moderate, curate, access and share the content creation. The interface can create details about eMarketplace, create knowledge banks, best practice repositories. It should also be able to connect the BB with social media, able to publish the digital advertisements.</mark>

The building block must allow sellers to add name, images and description to products and services.&#x20;

## <mark style="color:blue;">**4.19 Workflow Interface**</mark>

<mark style="color:blue;">This interface should be able to automate and orchestrate capabilities for specified business processes within and across Building Blocks. The initiation of a workflow, for example-submission of related documents for procurement/purchase request, shall be automated till the fulfilment of that order/request/cancellation.</mark>&#x20;

The building block must allow administrators to configure various workflows that occur within a business or provider.&#x20;

## <mark style="color:blue;">**4.20 Dashboard & Business Analytics Interface**</mark>

<mark style="color:blue;">This interface should be able to data visualize key statistics such number of procurements/items with different status such as active, fulfilled, cancelled. It should be able to indicate archived/historical data as well. The interface should offer data driven insights (risk analysis, predicitive analytics) on most and least consumed goods and services, volume, financial details on monthly and yearly basis.</mark>

## <mark style="color:blue;">**4.21 GIS BB Interface**</mark>

<mark style="color:blue;">The Geographic Information System (GIS) interface should be able to identify, tag, analyze locations of goods and services, persons, entities, piece of equipment, locations with timestamps. This will enable to track the goods and services when they are under active lifecycle of eMarketplace BB.</mark>

## <mark style="color:blue;">**4.22 Consent Management Interface**</mark>

<mark style="color:blue;">This interface should allow an application or system to acquire and validate consent from an authorized user in order to grant access or permissions for carrying out a task. Biometric identities, digital signatures or simply SMS messages may be used to provide consent.</mark>

## <mark style="color:blue;">**4.23 Messaging Interface**</mark>

<mark style="color:blue;">This interface should act as a secured communication channel between users and service providers. Security features, logging, back-up, encrypted and non encrypted messages (such as notifications, reminders, alerts), chatbot services shall be enabled by this interface.</mark>

## <mark style="color:blue;">**4.24 Scheduling Interface**</mark>

<mark style="color:blue;">This interface shall be able to orchestrate processes automatically. For example, when a bidder submits documents, it shall trigget certain series of steps/processes, send an alert by email and SMS, update the stock of remaining items, number of goods and services in active phase etc. It shall also complete the lifecycleof processes involved in a process. For example, from initiation to closure of a series of activities involved in ordering an item/goods/services.</mark>

## <mark style="color:blue;">4.25 Bid Evaluation</mark>

<mark style="color:blue;">The building block should facilitate bid evaluation process (financial, technical or any other type) with a defined criteria. The evaluation shall be conducted by the buyer, only. At first, the buyer defines an evaluation criteria for a good or service. Then the buyer admin/a group of professionals will receive the documents/details submitted by the seller; and evaluate them based on the pre-defined criteria. In case the buyers/suppliers have any clarifications, the concerned party should be able to seek guidance through writing questions or addendum or corrigendum. Finally, the evaluation should select the best bidder/supplier.</mark>



## Everything below this line is DRAFT (Will be Removed Later)

### _DO NOT DELETE_

* Search
* **Ordering**
  * Quote agreement
  * Terms Agreement
  * Confirmation
* **Fulfillment**
  * Status updates
  * Tracking
  * Cancellations
  * Order terms updates
* **Post-fulfillment**
  * Rating
  * Support
* **Payment**
  * Collection from buyer
  * Settlement to seller

Let us look at each of these in detail

### Discovery

**Overview (TL;DR)**

The discovery phase consists of two interactions.&#x20;

1. Searching for product and/or services; and
2. Publishing catalog of products and services

These two interactions are fundamentally asynchronous. &#x20;

The Discovery phase consists of all the interactions that lead to the discovery of a product or a service. Discovery typically begins from an intent. An Intent could be of two types, namely,

1. An Intent to buy
2. An Intent to sell&#x20;

#### Marketing

Expressing an intent to sell is typically known as Marketing. This is enabled through various paradigms such as Catalogs, Advertisement Campaigns, Promotions, Offers, etc.\


The seller may engage in a variety of activities, including

* Product/Service Listing: The seller lists their products/services online, providing detailed descriptions, images, and specifications to help buyers make informed decisions.
* Marketing and Promotion: The seller may engage in a variety of marketing and promotion activities, such as advertising, discounts, and sales, to attract potential buyers.

#### Searching

Expressing an intent to buy is commonly known as “Searching”. This is enabled by various experiences such as search engines, storefront UIs, Conversational UI etc.&#x20;

The buyer may engage in a variety of activities, including:&#x20;

* Searching for products/services: The buyer may search for products/services online, read product/service reviews, compare features and prices from different sellers and view past orders for benchmarking.&#x20;
* Identifying needs and preferences: The buyer may consider their specific needs and preferences, and use this information to narrow down their options.
* Evaluating options: The buyer may evaluate the different options available, considering factors such as price, quality, and delivery time.
* Making a decision: After considering all the relevant factors, the buyer will make a decision on which product or service to purchase.

**Description**

The discovery phase usually begins with the Marketing activity where the seller publishes their catalog of products and services. Sometimes, the products and services catalog may be tagged to one or more categories and subcategories.Additionally, the catalog may also be published with attributes that limit their availability to certain locations,  timings, and payment modalities. Furthermore, the seller may also publish promotional content regarding specific products and services to nudge the consumer to avail them.&#x20;

The catalog publishing activity is usually followed by a search. In this stage, the buyer searches for products or services. In this stage, the buyer can search for products and services via various ways ranging from simple text-based search, and key based search, to more sophisticated searches involving conversational UI, and natural language processing.&#x20;

### Ordering

**Overview**

In this phase, there are six buyer-seller interactions that typically occur. They are grouped by,

**Quote Agreement**

1. (Buyer) Selecting products/services and seeking product / service information from sellers.&#x20;
2. (Seller) Publishing a quote along with dynamic offers, promotions, and discounts and responding to queries

**Terms Agreement**

3. (Buyer) Providing fulfillment information like billing and shipping/delivery information, agent(s) performing the fulfillment & time & location of fulfillment.
4. (Seller) Publishing final draft order with terms of fulfillment and payment

**Order confirmation**

5. (Buyer) Placing an order
6. (Seller) Creating an order\


**Description**

The Ordering phase in a typical e-commerce interaction begins with the buyer selecting one or more items (products and services) and adding them into a cart. It is important to note that in most e-commerce applications, the cart is expressed as a separate staging area where the total cost of the selected items is visible. It is not always necessary for an explicit “cart” to exist in all applications. It can be assumed more like a virtual entity that represents a buyer’s request for a quote from the seller for a specific set of items.&#x20;

In case of government procurements, additional steps will be involved even before the cart is updated. These include and are not limited to contracts, tenders, purchase orders, advance payments, invoicing.&#x20;

After requesting a quote, we proceed to the second interaction where the seller receives the selected items and proceeds to calculate the total cart value. This is a very important step in the order lifecycle, as this is where a seller can provide dynamic and personalized offerings to the buyer in the form of promotional products, add-ons, discounts and subsidies, government program benefits and citizen entitlements.&#x20;

The next interaction involves the buyer providing order-specific information such as billing and shipping information. Sometimes, in this stage, the buyer may need to provide some information in addition to billing and shipping such as credentials, contact information, documents, etc, to prove their trustworthiness.&#x20;

The fourth interaction in the ordering stage involves the seller receiving the additional information and calculating the final quote and payment terms that includes shipping costs and taxes; along with the terms and conditions for cancellations, returns, replacements and refunds. This is essentially the final draft of the order between the buyer and the seller before proceeding to checkout.&#x20;

The next interaction involves the buyer, agreeing to fulfill the terms and conditions and ultimately placing the order. This is generally when the buyer initiates checkout and confirms the order. Sometimes the terms and conditions of the order require the buyer to make the payment before placing the order. In such cases, the buyer first makes the payment to the seller and sends the payment reference along with the order confirmation request.&#x20;

The final interaction in the Ordering phase is where the seller receives the order confirmation request from the buyer. In this operation, the seller confirms the order and adds it to their order book. If the order requires payment to be made before order placement, the seller verifies the payment against the transaction reference sent by the buyer and then creates the order and informs the buyer regarding the confirmed order.&#x20;

### Fulfillment

#### **Overview**

In this phase, these are buyer-seller interactions that typically occur:

1. (Buyer) Requests for status of the order
2. (Seller) Shares the latest status of the fulfillment of the order
3. (Buyer) Requests for tracking of the physical/virtual delivery of the order
4. (Seller) Shares a live tracking of the agent performing the fulfillment
5. (Buyer) Updates order details (item, quantity, fulfillment details, etc.)
6. (Seller) Provides an updated order
7. (Buyer/Seller) Cancels order&#x20;
8. (Seller/Buyer) confirms order cancellation

**Description**

Once the order is confirmed, the buyer requests for the status of their order. The seller can send the status of the order and the fulfillment of the order. The products or services are fulfilled by the seller based on the terms and conditions of the order and can go through pre-defined states that the seller can constantly update.&#x20;

In government contracts, often before the order is confirmed a communication is sent intimating to the participating sellers as to who won the contract and the rationale behind that. The rationale has to be inline with what was T\&C at the time of initiating the process.&#x20;

The buyer can track the fulfillment of the products or services. The seller can share a live tracking system to display the physical or virtual delivery of products and services according to the order.&#x20;

Order details can be updated by the buyer (provided the terms and conditions of the order agreed during the ordering process allows it). The updates could include adding or modifying products/services, location and time of delivery/fulfillment, customer information, payment information, etc. The seller can accept or reject the updates to the order and if accepted, the seller can update the order details, terms and payment information.&#x20;

The buyer can also cancel the order (or part of the order) by providing a reason for cancellation. If the cancellation is within the cancellation terms defined by the seller, the order is canceled and the cancellation payments & related details are communicated to the buyer.

Similarly, the cancellation flow can also be initiated by the seller and communicated to the buyer.

### Post-fulfillment

**Overview**

In this phase, these are buyer-seller interactions that typically occur:

1. (Buyer) Submits a rating for the products/services consumed
2. (Seller) Requests for additional information feedback based on rating received
3. (Buyer) Requests for customer support information
4. (Seller) Provides all possible customer support channels to assist the Buyer

**Description**

Once the order fulfillment is complete, the Buyer can submit a rating for the rateable entities of the products/services (such as product rating, seller rating, fulfillment rating, etc.). The seller can request for additional feedback from the buyer based on the ratings received.&#x20;

The Buyer can request for customer support information to resolve any issues encountered during any stage of the discovery, ordering, fulfillment or payment phases. In case of updates or cancellations, the customer support team can also be contacted for returns, replacement and refunds as per the order terms. The seller provides the channels of customer support that they have enabled (such as call center information, chat bots assistants, IVR systems, Emails & text based support channels, etc.)

### Payment

The implementers of the e-marketplace building block specifications are expected to use existing payment infrastructures in their region(s) of operation to collect, process and settle payments. Since payments is a highly regulated industry across the world, different geo-political regions may choose different standards and modalities to enable digital payments. Therefore, it is left to the implementer to templatize such region-specific payment modalities and dynamically enable them on the respective user applications of both the payer and payee, based on their respective geo-political locations.

The building block specifies the format of the payment agreement contract between the Buyer and Seller, and the terms of the payment and settlements are mutually agreed by the parties of the order on the marketplace. The actual payment and settlement (such as card payments, bank transfers, post-order settlements, reconciliation of payment information, voucher redeem etc.) can be performed using the payment infrastructure available in the region/jurisdiction.
