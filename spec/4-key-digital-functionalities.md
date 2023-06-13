# 4 Key Digital Functionalities

{% hint style="success" %}
The Key Digital Functionalities describe the core (required) functions that this building block must be able to perform. These functionalities should be described as business processes as opposed to technical specifications or API definitions.

Note, this section may be extended after the key functionalities have been listed to include any assumptions or context that is needed. Additionally, if the Building Block contains multiple components, the functionalities for each may be described.
{% endhint %}

Comments: We had to arrive at the KDFs as a consequence of...

Narrate the KDFs from the actor's pov

Refer to recording of May 24th call



Any e-marketplace consists of five key digital functionalities

* **Discovery**
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

\


\


\
\


\
