# 6 Functional Requirements

{% hint style="success" %}
The functional requirements section lists the technical capabilities that this building block should have. These requirements should be sufficient to deliver all functionality that is listed in the Key Digital Functionalities section.

These functional requirements do not define specific APIs - they provide a list of information about functionality that must be implemented within the building block.

These requirements should be defined by subject-matter experts and don’t have to be highly technical in this section.

If there are multiple functional components of a building block, the functional requirements for each component may have its own section
{% endhint %}

<figure><img src=".gitbook/assets/E-Marketplace BB Architecture V2.png" alt=""><figcaption><p>E Marketplace Building Block Functional Architecture</p></figcaption></figure>

_\<Example Functional Requirements>_

### Internal functional components

The E-Marketplace can be visualized as a black box with all key digital functionalities discussed in section 4. It does not assume any particular standard like REST for all internal resource management. A brief description of the functional requirements required to orchestrate each key digital functionality is given below, <mark style="color:blue;">considering the development of a</mark> minimum viable product ~~perspective~~. Detailed design and more elaborate feature lists of these blocks can be customized by developers to optimally match respective implementation needs. It is also left to the application implementing this building block to receive the responses from the E-marketplace and present it appropriately and provision for associated user interface interactions.

### 6.1 Searching

In order to allow a consumer to search contents in the emarket place this key digital functionality  has to address atleast the following functional requirements:

6.1.1  Must allow create / read / update or delete of a specific search intent (example products/consumers/tenders/agents/etc.). It is preferred to have seperate end points for different search intents since it may be required to implement role based access to information of different intents

6.1.2 Must allow filtering extraction of data from catalogs by a set of criteria related to the search intent (e.g. filter tenders based on specific region, value, <mark style="color:blue;">department, type of service, geography, availability of time slots</mark> etc). The filter criteria must be configurable for each type of intent.

6.1.3 It must allow the addition / removal / update of an item in the search intent

6.1.4 It must allow the addition / removal / update of a category in the search intent

6.1.5 It must allow the addition / removal / update of a fulfillment in the search intent

6.1.6 It must allow the addition / removal / update of a payment in the search intent

6.1.7 It must allow the transmission of the search request to a provider platform

6.1.8 It must allow searching, sorting and filtering of a catalog by applying various filters

### 6.2 Catalog Management

6.2.1 The E-Marketplace must allow create / read / update or delete of a catalog

6.2.2 It must allow create / read / update / delete of Items

6.2.3 It must allow create / read / update / delete of Providers

6.2.4 It must allow create / read / update / delete of Agents

6.2.5 It must allow create / read / update / delete of Categories

6.2.6 It must allow create / read / update / delete of Fulfillments

6.2.7 It must allow create / read / update / delete of Payments

6.2.8 Upon receiving a search request, it must return a linked catalog with matched items, categories, providers, fulfillments, and payments

### 6.3 Inventory Management

6.3.1 The E-Marketplace must allow updating the quantity and location of Items across multiple Providers&#x20;

6.3.2 It must allow checking of availability of an Item in a catalog

### 6.4 Quote Agreement

6.4.1 The E-Marketplace must enable the construction of a cart (or a cart-like experience)  on the consumer platform

6.4.2 It must allow addition / removal / update of multiple items and their respective quantities in the cart

6.4.3 It must allow addition / removal / update of offers in the cart

6.4.4 It must allow addition / removal / update of add-ons in the cart

6.4.5 It must allow transmission of the cart from the consumer platform to the provider platform

6.4.6 Upon receiving the cart from the consumer platform, it must allow the provider platform to check for the availability of items or add-ons in the cart

6.4.7 It should check the validity of offers against the items in the cart

6.4.8 it should dynamically calculate the quote based on the available items, offers, and add-ons

6.4.9 It should allow addition / removal / update of the cart with the quote and its breakup

6.4.10 It should transmit the cart with the updated quote from the provider platform to the consumer platform

### 6.5 Terms Agreement

6.5.1 The E-Marketplace must enable the construction of a draft order (or a pre-checkout like experience) on the consumer platform

6.5.2 It must allow the addition / update / removal of billing details to the order

6.5.3 It must allow the addition / update / deletion of fulfillment details to the order

6.5.4 It must allow the transmission of the draft-order from the consumer platform to the provider platform

6.5.5 It must re-calculate the quote based on fulfillment details

6.5.6 It must check the serviceability of the order on the basis of agent availability

6.5.7 It must re-check the availability of items, validity of offers and re-calculate the quote

6.5.8 It must allow creation / addition / update of payment terms containing the payment stage, final payable amount, payment endpoint and payment schedule to the draft order

6.5.9 It must allow addition of terms of service, cancellation, returns, replacements and refunds wherever applicable

6.5.10 It must allow the transmission of the final draft order containing all the details of the order



### 6.6 Contract Creation and Management

6.6.1 The E-Marketplace must enable creation of a confirmed order with an Order ID

6.6.2 It must allow update / deletion of a fulfillment state in the order

6.6.3 It must allow the transmission of the final draft order from the consumer platform to the provider platform

6.6.4 It must allow the transmission of the confirmed order from the provider platform to the consumer platform

6.6.5 It must again allow re-checking of inventory availability before creating the order

### 6.7 Contract Fulfillment

6.7.1 The E-Marketplace must enable discovering and allocation of an Agent (if applicable) to the fulfillment of a confirmed order

6.7.2 It must allow update of the fulfillment state of an order

6.7.3 It must allow transmission of fulfillment status updates from the provider platform and the consumer platform

6.7.4 It must allow fetching the latest copy of the order from a provider

### 6.8 Tracking

6.8.1 The E-Marketplace must enable fetching of tracking information related to the order

6.8.2 It must allow real-time data to be transmitted from the provider to the consumer

6.8.3 It must allow the consumer platform to transmit a webhook endpoint to the provider platform&#x20;

6.8.4 It must allow the provider platform to transmit a tracking link to the consumer platform

### 6.9 Cancellation

6.9.1 It must allow creation of an order cancellation request

6.9.2 It must allow creation of a canceled order

6.9.3 roll back all liabilities that were created based on this order before cancellation

6.9.3 It must allow addition of cancellation reason to the cancellation request

6.9.4 It must allow de-allocation of fulfillment services and the agents associated with the fulfillment of the contract

6.9.5 It must allow calculation of cancellation terms (if applicable) depending on the reason provided and time of the cancellation request

6.9.6 It must be possible to add a link to the cancellation terms (including cancellation fee) document to the order

6.9.7 It must allow transmission of the canceled order between the consumer and the provider

### 6.10 Rating and Feedback

6.10.1 The E-Marketplace must allow ratings for various rateable entities to be captured by people involved in a transaction

6.10.2 It must allow the transmission of ratings from the consumer platform to the provider platform

6.10.3 It must allow creation of a request to collect additional feedback related to a rating

6.10.4 It must allow fetching of various rateable entities related to an order

### 6.11 Support

6.11.1 The E-Marketplace must allow support center information like email, phone number and chat URL in relation to an order to be transmitted between the consumer and the provider platforms&#x20;

6.11.2 It must allow the creation/read/update/deletion of tickets in relation to an issue raised by a consumer, or an agent

### 6.12 Information Mediator Interface

6.12.1 This sub-block runs protocols to communicate with the information mediator Building Block for exposing e-marketplace services to external Building Blocks and applications.

6.12.2 It also provides specific calls to APIs of information mediator Building Block to access services of external applications and Building Blocks.&#x20;

6.12.3 It also handles any errors and failures in data exchange between the e-marketplace and other Building Blocks/Apps (such as backoff and retries, etc.).

6.12.4 It routes error information if any to the logger sub-block.&#x20;

6.12.5 It maintains a list of endpoint addresses of Information Mediator, other Building Blocks, and Applications.

### 6.13 Payment Interface

6.13.1 These are dedicated API interfaces defined in the Payment building block and hence not defined here

6.13.2 The Payment interface SHOULD provide the necessary protocol, data format, and information and interface to interact with the Payment Building Block for sending payment collection or settlement instructions to existing payment infrastructures like Banking Systems, Credit Card Networks, Payment Gateways etc to facilitate payments made during a transaction in the E-Marketplace&#x20;

### 6.14 E-Signature Interface

6.14.1 These are dedicated API interfaces defined in the Signature Building Block and hence not defined here

6.14.2 The E-Signature interface SHOULD provide the necessary protocol, data format, and information and interface to interact with the Signature Building Block for the digital signing and subsequent verification of each message that is transmitted between the consumer platform and the provider platform

### 6.15 Registration Interface

6.15.1 These are dedicated API interfaces defined in the Registration Building Block and hence not defined here

6.15.2 The Registration interface SHOULD provide the necessary protocol, data format, and information and interface to interact with the Registration Building Block to enable users on the Consumer Platform and the Provider Platform to sign up on their respective platforms with the required information necessary to perform transactions on the E-Marketplace

### <mark style="color:red;">6.16  Digital Identity & Verification Interface</mark>



### <mark style="color:red;">6.17 Communication and Outreach</mark>



### ## Everything below this line is Draft. Please Ignore

#### DO NOT DELETE

### 6.1 Discovery

The discovery phase consists of two functional interactions.&#x20;

1. Searching
2. Returning a catalog

#### 6.1.1 Searching&#x20;

Expressing an intent to buy is commonly known as “Searching”. This is enabled by various experiences such as search engines, storefront UIs, Conversational UI etc.&#x20;

The buyer may engage in a variety of activities, including:&#x20;

* Searching for products/services: The buyer may search for products/services online, read product/service reviews, compare features and prices from different sellers and view past orders for benchmarking.&#x20;
* Identifying needs and preferences: The buyer may consider their specific needs and preferences, and use this information to narrow down their options.
* Evaluating options: The buyer may evaluate the different options available, considering factors such as price, quality, and delivery time.
* Making a decision: After considering all the relevant factors, the buyer will make a decision on which product or service to purchase.

**6.1.2 Returning a Catalog**

The catalog publishing activity is usually followed by a search. Here the seller returns their catalog of products and services as a response to a search. Sometimes, the products and services catalog may be tagged to one or more categories and subcategories.Additionally, the catalog may also be returned with attributes that limit their availability to certain locations,  timings, and payment modalities. Furthermore, the seller may also publish promotional content regarding specific products and services to nudge the consumer to avail them.&#x20;

### 6.2 Ordering

In this phase, there are six functional interactions that typically occur. They are grouped by,

1. (Buyer) Selecting products/services and seeking product / service information from sellers.&#x20;
2. (Seller) Returning a quote along with dynamic offers, promotions, and discounts and responding to queries
3. (Buyer) Providing fulfillment information like billing and shipping/delivery information, agent(s) performing the fulfillment & time & location of fulfillment.
4. (Seller) Publishing final draft order with terms of fulfillment and payment
5. (Buyer) Placing an order
6. (Seller) Creating an order

#### 6.2.1 Selecting products/services&#x20;

The Ordering phase in a typical e-commerce interaction begins with the buyer selecting one or more items (products and services) and adding them into a cart. It is important to note that in most e-commerce applications, the cart is expressed as a separate staging area where the total cost of the selected items is visible. It is not always necessary for an explicit “cart” to exist in all applications. It can be assumed more like a virtual entity that represents a buyer’s request for a quote from the seller for a specific set of items.&#x20;

In case of government procurements, additional steps will be involved even before the cart is updated. These include and are not limited to contracts, tenders, purchase orders, advance payments, invoicing.&#x20;

#### 6.2.2 Returning a quote

After requesting a quote, we proceed to the second interaction where the seller receives the selected items and proceeds to calculate the total cart value. This is a very important step in the order lifecycle, as this is where a seller can provide dynamic and personalized offerings to the buyer in the form of promotional products, add-ons, discounts and subsidies, government program benefits and citizen entitlements.&#x20;

#### 6.2.3 Providing fulfillment information

The next interaction involves the buyer providing order-specific information such as billing and shipping information. Sometimes, in this stage, the buyer may need to provide some information in addition to billing and shipping such as credentials, contact information, documents, etc, to prove their trustworthiness.&#x20;

#### 6.2.4 Publishing final draft order

The fourth interaction in the ordering stage involves the seller receiving the additional information and calculating the final quote and payment terms that includes shipping costs and taxes; along with the terms and conditions for cancellations, returns, replacements and refunds. This is essentially the final draft of the order between the buyer and the seller before proceeding to checkout.&#x20;

#### 6.2.5 Buyer confirms the order

The next interaction involves the buyer, agreeing to fulfill the terms and conditions and ultimately placing the order. This is generally when the buyer initiates checkout and confirms the order. Sometimes the terms and conditions of the order require the buyer to make the payment before placing the order. In such cases, the buyer first makes the payment to the seller and sends the payment reference along with the order confirmation request.&#x20;

#### 6.2.6 Seller returns the confirmed order

The final interaction in the Ordering phase is where the seller receives the order confirmation request from the buyer. In this operation, the seller confirms the order and adds it to their order book. If the order requires payment to be made before order placement, the seller verifies the payment against the transaction reference sent by the buyer and then creates the order and informs the buyer regarding the confirmed order.&#x20;

### 6.3 Fulfillment

In this phase, these are buyer-seller interactions that typically occur:

1. (Buyer) Requests for status of the order
2. (Seller) Shares the latest status of the fulfillment of the order
3. (Buyer) Requests for tracking of the physical/virtual delivery of the order
4. (Seller) Shares a live tracking of the agent performing the fulfillment
5. (Buyer) Updates order details (item, quantity, fulfillment details, etc.)
6. (Seller) Provides an updated order
7. (Buyer/Seller) Cancels order&#x20;
8. (Seller/Buyer) confirms order cancellation

#### 6.3.1 Consumer requests for status

Once the order is confirmed, the buyer requests for the status of their order.&#x20;

#### 6.3.2 Provider returns latest fulfillment status

The seller can send the status of the order and the fulfillment of the order. The products or services are fulfilled by the seller based on the terms and conditions of the order and can go through pre-defined states that the seller can constantly update.&#x20;

In government contracts, often before the order is confirmed a communication is sent intimating to the participating sellers as to who won the contract and the rationale behind that. The rationale has to be inline with what was T\&C at the time of initiating the process.&#x20;

#### 6.3.3 Consumer requests tracking info&#x20;

The buyer can track the fulfillment of the products or services.&#x20;

#### 6.3.4 Provider returns tracking info

The seller can share a live tracking system to display the physical or virtual delivery of products and services according to the order.&#x20;

#### 6.3.5 Consumer requests for order update

Order details can be updated by the buyer (provided the terms and conditions of the order agreed during the ordering process allows it). The updates could include adding or modifying products/services, location and time of delivery/fulfillment, customer information, payment information, etc.&#x20;

#### 6.3.6 Provider updates the terms of the order

The seller can accept or reject the updates to the order and if accepted, the seller can update the order details, terms and payment information.&#x20;

#### 6.3.7 Consumer cancels the order

The buyer can also cancel the order (or part of the order) by providing a reason for cancellation.

#### 6.3.8 Provider cancels the order with cancellation terms

If the cancellation is within the cancellation terms defined by the seller, the order is canceled and the cancellation payments & related details are communicated to the buyer.

Similarly, the cancellation flow can also be initiated by the seller and communicated to the buyer.

### Post-fulfillment

In this phase, these are buyer-seller interactions that typically occur:

1. (Buyer) Submits a rating for the products/services consumed
2. (Seller) Requests for additional information feedback based on rating received
3. (Buyer) Requests for customer support information
4. (Seller) Provides all possible customer support channels to assist the Buyer

Once the order fulfillment is complete, the Buyer can submit a rating for the rateable entities of the products/services (such as product rating, seller rating, fulfillment rating, etc.). The seller can request for additional feedback from the buyer based on the ratings received.&#x20;

The Buyer can request for customer support information to resolve any issues encountered during any stage of the discovery, ordering, fulfillment or payment phases. In case of updates or cancellations, the customer support team can also be contacted for returns, replacement and refunds as per the order terms. The seller provides the channels of customer support that they have enabled (such as call center information, chat bots assistants, IVR systems, Emails & text based support channels, etc.)

### Payment

The implementers of the e-marketplace building block specifications are expected to use existing payment infrastructures in their region(s) of operation to collect, process and settle payments. Since payments is a highly regulated industry across the world, different geo-political regions may choose different standards and modalities to enable digital payments. Therefore, it is left to the implementer to templatize such region-specific payment modalities and dynamically enable them on the respective user applications of both the payer and payee, based on their respective geo-political locations.

The building block specifies the format of the payment agreement contract between the Buyer and Seller, and the terms of the payment and settlements are mutually agreed by the parties of the order on the marketplace. The actual payment and settlement (such as card payments, bank transfers, post-order settlements, reconciliation of payment information, voucher redeem etc.) can be performed using the payment infrastructure available in the region/jurisdiction.
