# 6 Functional Requirements

{% hint style="success" %}
The functional requirements section lists the technical capabilities that this building block should have. These requirements should be sufficient to deliver all functionality that is listed in the Key Digital Functionalities section.

These functional requirements do not define specific APIs - they provide a list of information about functionality that must be implemented within the building block.

These requirements should be defined by subject-matter experts and don’t have to be highly technical in this section.

If there are multiple functional components of a building block, the functional requirements for each component may have its own section
{% endhint %}

_\<Example Functional Requirements>_

### Internal functional components

The E-Marketplace can be visualized as a black box with all key digital functionalities discussed in section 4. It does not assume any particular standard like REST for all internal resource management. A brief description of the functional requirements required to orchestrate each key digital functionality is given below, <mark style="color:blue;">considering the development of a</mark> minimum viable product ~~perspective~~. Detailed design and more elaborate feature lists of these blocks can be customized by developers to optimally match respective implementation needs. It is also left to the application implementing this building block to receive the responses from the E-marketplace and present it appropriately and provision for associated user interface interactions.



### 6.1 Searching&#x20;

1. The e-marketplace must allow creation of a search request with a context and a message. The context MUST contain the action performed (“search”), the location where the search is limited to (ex: country, city, area code etc), the domain / category of search (ex: healthcare, services, etc), the identity of the platform generating the search (ex: domain name), the callback url of the platform generating the search.
2. The context MUST also contain a unique transaction ID to represent a sequence of interactions. It must also contain a unique message ID to match a request with a callback. The search context must contain a timestamp denoting the time of the search.
3. It should allow addition of an intent to the message. Intent should contain fulfillment details in case the customer wants their order fulfilled in a specific way. If there is a preferred method of payment the intent should contain the payment details. The intent should define the category of the search. If search criteria is specific to an offer, intent must contain the offer detail.
4. It should allow multiple search parameters and  should allow updates of search parameters , the system should provide the flexibility to update the search criteria, ex- search is to be modified for category, payment type etc.
5. Once a call is made and the user wants to make a next search call which can not be fulfilled with the existing data from the previous search call, the system should be able to use the selected fields and the modified search fields for the next search call.
6. It must be able to transmit the search request along with all the search parameters to the provider platform.
7. This building block should allow fetching of catalogs that matches the maximum number of search parameters.

### **6.2 Catalog Management**&#x20;

1. The e-marketplace must allow creation of a catalog request for which context is required and should have a message.
2. The context is used to describe the metadata of the details provided in the message part. The context must contain an action. It also must contain a unique transaction ID received by the search request to represent a sequence of interactions. It must also contain a unique message ID to match a request with a callback. It must contain a timestamp denoting the time of the search requested for the catalog.
3. The  message must contain catalog. Catalog is used to describe the products or services provided by the platform. The catalog should be formed on the basis of the search request made by the user and the data is filtered accordingly and added to the catalog.
4. Catalog should be able to provide description, it will have description of the product or service. it can have short description, long description, describing images.
5. Catalog should provide fulfillment details , it will provide the details about the fulfillment mode, if the e-marketplace takes the responsibility of the fulfillment.
6. Catalog should provide payment detail, it provides details about the payment terms offered by the e-marketplace. The terms can be overridden by the providers section, in case e-marketplace does not take responsibility for the payments.
7. Catalog should provide expiry details, it will provide details about the time (timestamp) after which the catalog will not be valid. Consumer platform must be able to process the expiry and invalidate the catalog.Ex- A limited time offer on a service/product.
8. Catalog should provide details of the time to live, ttl describes the time to live for the catalog after which catalog expires.Consumer platform must be able to process the ttl and invalidate the catalog
9. Seller platform must be able to call the on\_search API provided by the buyer platform to provide the catalog of the products.
10. The buyer platform should provide a mechanism to handle the response(catalog) for a search , it should display the products/services in the catalog properly and should be able to filter the products at the UI layer also.
11. Consumer platform should be able to handle multiple responses against a search tied with a message ID made as the response can be from multiple providers

### 6.3 Inventory Management

1. The E-Marketplace must allow the sellers to add new products in their inventory.
2. It should be able to provide the current status of the inventory products , the reporting should provide various filters based on which report can be generated.
3. It should allow updating the quantity and location of Items across multiple Providers and must restrict the access to sellers own inventory.
4. Inventory must get adjusted based on the order placed (confirm/cancel/return)
5. It must allow checking of availability of an Item in a catalog to avoid out-of-stock and over-stocking of the product.
6. It should provide a configurable system for notification which notifies based on the defined criteria. Ex- If product quantity is less than 50 , it must notify the seller with email or SMS.

### 6.4 Quotation Management

1. The E-Marketplace must enable the construction of a cart (or a cart-like experience)  on the consumer platform, it must consist of context and message
2. It must allow addition / removal / update of multiple items and their respective quantities in the cart
3. It must allow the consumer to choose from different offers available, and users should be able to modify or remove the offer before an order is placed.
4. It must allow users to modify the addons in the cart, the cart should not be freeze before an order is placed. The consumer should be able to modify the products i.e. add ,remove products also should be able to modify the quantity of the product.
5. It must allow transmission of the cart from the consumer platform to the provider platform
6. Upon receiving the cart from the consumer platform, it must allow the provider platform to check for the availability of items in the cart
7. It should check the validity of offers against the items in the cart
8. it should dynamically calculate the quote based on the available items, offers, and add-ons
9. It should transmit the cart with the updated quote from the provider platform to the consumer platform
10. Provider platform should response with context and either order or with error
11. Consumer platform must process the quote properly and show the details along with the offers/delivery/payments details and break up of the quote.

### 6.5 Order Terms Management&#x20;

1. The E-Marketplace must enable the construction of a draft order (or a pre-checkout like experience) on the consumer platform, the draft order must contain context and message with order details.
2. Consumer applications  must allow the modification of the billing details of the order before a request is sent to the provider.
3. It must allow the consumers to modify the fulfillment details. Ex- Consumer has multiple addresses stored in the application, he should be able to select the address or add a new address for fulfillment. Consumers should also be able to choose from the available fulfillment options.
4. It must allow the transmission of the draft-order from the consumer platform to the provider platform
5. Consumer app must  recalculate the quote based on the modifications made in the fulfillment details
6. Consumer app must check the serviceability of the order on the basis of agent availability
7. Provider platform must re-check the availability of items, validity of offers and re-calculate the quote based on the selection made by the consumer
8. Provider platform must allow creation and modification of payment terms containing the payment stage, final payable amount, payment endpoint and payment schedule to the draft order
9. Provider app  must allow addition of terms of service, cancellation, returns, replacements and refunds wherever applicable
10. Provider platform must response with context and either order or an error
11. It must allow the transmission of the final draft order containing all the details of the order to the consumer platform
12. Consumer platform must be able to handle the final draft order received from the provider and display the final order draft.



### 6.6 Order Management&#x20;

1. The E-Marketplace must enable creation of a confirmed order with an unique Order ID, the confirm order must contain context and message
2. Before confirming an order to provider platform consumer platform must allow modification of a fulfillment state in the order
3. Consumer platform must allow the transmission of the final draft order to the provider platform
4. Provider platform must again allow re-checking of inventory availability before creating the order
5. It must allow the transmission of the confirmed order from the provider platform to the consumer platform
6. Provider platform response to a confirmed order must contain context and either order or an error
7. Consumer platform must be able to handle the order confirmation received from the provider platform and display the success message to the consumer along with the order id and the product's details in the order.

### 6.7 Order Fulfillment&#x20;

1. The E-Marketplace must enable discovering and allocation of an Agent (if applicable) to the fulfillment of a confirmed order.
2. Consumer application must be able to fetch the status of the order from the provider platform.
3. Provider platform must be able to find out the status of the order and provide the details back to the consumer application.
4. Provider application must allow updates of the status of the order.
5. When a new event occurs on the fulfillment, provider platform must pass on the information to the consumer platform.

### 6.8 Order Tracking&#x20;

1. The E-Marketplace must enable fetching of tracking information related to the order
2. It must allow real-time data to be transmitted from the provider to the consumer
3. It must allow the consumer platform to transmit a webhook endpoint to the provider platform which will handle the real time updates on the tracking
4. It must allow the provider platform to transmit a tracking link to the consumer platform
5. Consumer platform must allow display of the tracking details to the consumer along with the history
6. Consumer applications must be able to segregate the tracking details based on the order ID.

### 6.9 Order Cancellation&#x20;

1. Consumer platform must allow creation of an order cancellation request for all the active orders which are yet not fulfilled.
2. Consumer platform must provide order id and allow addition of cancellation reason to the cancellation request
3. Provider platform must handle the cancel order request and respond back to the consumer platform
4. Provider platform must allow modification of the order status and  de-allocation of fulfillment services and the agents associated with the fulfillment of the contract
5. It must allow calculation of cancellation terms (if applicable) depending on the reason provided and time of the cancellation request
6. It must be possible to add a link to the cancellation terms (including cancellation fee) document to the order
7. It must allow transmission of the canceled order between the consumer and the provider
8. On cancellation of an order the provider platform must adjust the inventory of the products canceled
9. Consumer platform must handle the response from the provider platform for a cancellation request and update the order status and display the details of cancellation of order along with the cancellation terms (including cancellation fee).

### 6.10 Rating and Feedback Management&#x20;

1. The E-Marketplace must allow ratings for various rateable entities to be captured by people involved in a transaction
2. It must allow the transmission of ratings from the consumer platform to the provider platform
3. It must allow creation of feedback by provider platform to get detailed additional information on the rating provided
4. It must allow creation of a request to collect additional feedback related to a rating
5. It must allow fetching of various rateable entities related to an order

### 6.11 Support Management&#x20;

1. The E-Marketplace must allow support center information like email, phone number and chat URL in relation to an order to be transmitted between the consumer and the provider platforms&#x20;
2. It must allow the creation/read/update/deletion of tickets in relation to an issue raised by a consumer, or an agent

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

6.14.2 The E-Signature interface SHOULD provide the necessary protocol, data format, and information and interface to interact with the e-Signature Building Block for the digital signing and subsequent verification of each message that is transmitted between the consumer platform and the provider platform

### 6.15 Registration Interface

6.15.1 These are dedicated API interfaces defined in the Registration Building Block and hence not defined here

6.15.2 The Registration interface SHOULD provide the necessary protocol, data format, and information and interface to interact with the Registration Building Block to enable users on the Consumer Platform and the Provider Platform to sign up on their respective platforms with the required information necessary to perform transactions on the E-Marketplace

### 6.16  Digital Identity & Verification Interface

6.16.1 These are dedicated API interfaces defined in the Digital Identity & Verification Building Block and hence not defined here.

6.16.2 The Digital Identity & Verification Building Block  SHOULD provide the necessary protocol, data format, and information and interface to interact with the Digital Identity & Verification Building Block to enable users on the Consumer Platform and the Provider Platform interface to verify the digital identities in the E-Marketplace based on their national data registers.

<mark style="color:blue;">6.16.1 These are dedicated API interfaces defined in the Digital Identity & Verification building block and hence not defined here</mark>

<mark style="color:blue;">6.16.2 The Digital Identity & Verification interface SHOULD provide the necessary protocol, data format, and information and interface to interact with the Digital Identity & Verification Building Block for sending user registration data (name, unique identity number, tax number, phone/mobile, email etc.) and verify the same with relevant registries through OTP, SMS, biometrics, physical appearance, during a transaction in the E-Marketplace. In case of any error/mismatch, it should be able to suggest alternatives.</mark>

### <mark style="color:blue;">6.17 Promotional Communications</mark>

<mark style="color:red;">6.17.1</mark> These are dedicated API interfaces defined in the <mark style="color:red;">Communication and Outreach</mark> Building Block and hence not defined here.

6.17.2 The <mark style="color:red;">Communication and Outreach</mark> Building Block  SHOULD provide the necessary protocol, data format, and information and interface to interact with the <mark style="color:red;">Communication and Outreach</mark> Building Block to enable users on the Consumer Platform and the Provider Platform interface to integrate with social media and messaging platform.

### <mark style="color:red;">6.18</mark> <mark style="color:red;"></mark><mark style="color:red;">**Content Management Interface**</mark>

<mark style="color:red;">6.18.1</mark> These are dedicated API interfaces defined in the content management interface Building Block and hence not defined here.

6.18.2 The content management interface Building Block  SHOULD provide the necessary protocol, data format, and information and interface to interact with the content management interface Building Block to enable users on the Consumer Platform and the Provider Platform interface to manage content creation.

### <mark style="color:red;">6.19</mark> <mark style="color:red;"></mark><mark style="color:red;">**Workflow Interface**</mark>

<mark style="color:red;">6.19.1</mark> These are dedicated API interfaces defined in the Workflow interface Building Block and hence not defined here.

6.19.2 The workflow interface Building Block  SHOULD provide the necessary protocol, data format, and information and interface to interact with the workflow interface Building Block to enable users on the Consumer Platform and the Provider Platform interface to define and orchestrate the workflow within the system.

### <mark style="color:red;">6.20</mark> <mark style="color:red;"></mark><mark style="color:red;">**Dashboard & Business Analytics Interface**</mark>

<mark style="color:red;">6.20.1</mark> These are dedicated API interfaces defined in the Dashboard & Business Analytics interface Building Block and hence not defined here.

6.20.2 The dashboard & business analytics interface Building Block SHOULD provide the necessary protocol, data format, and information and interface to interact with the dashboard & business analytics interface Building Block to enable users on the Consumer Platform and the Provider Platform interface to visualize the data in the system.

### <mark style="color:red;">6.21</mark> <mark style="color:red;"></mark><mark style="color:red;">**GIS BB Interface**</mark>

<mark style="color:red;">6.21.1</mark> These are dedicated API interfaces defined in the GIS interface Building Block and hence not defined here.

<mark style="color:red;">6.21.2</mark> The GIS interface Building Block SHOULD provide the necessary protocol, data format, and information and interface to interact with the GIS interface Building Block to enable users on the Consumer Platform and the Provider Platform interface to use GIS based services like GIS tagging, tracking etc.

### <mark style="color:red;">6.22</mark> <mark style="color:blue;">**Consent Management Interface**</mark>

<mark style="color:red;">6.22.1</mark> These are dedicated API interfaces defined in the consent management interface Building Block and hence not defined here.

<mark style="color:red;">6.22.2</mark> The consent management interface Building Block SHOULD provide the necessary protocol, data format, and information and interface to interact with the consent management interface Building Block to enable users on the Consumer Platform and the Provider Platform interface to capture and validate the consent of the users.

### 6.23 Messaging Interface

6.22.1 These are dedicated API interfaces defined in the messaging interface Building Block and hence not defined here.

6.22.2 The messaging interface Building Block SHOULD provide the necessary protocol, data format, and information and interface to interact with the messaging interface Building Block to enable users on the Consumer Platform and the Provider Platform interface to exchange messages over a secured channel and have logging features.

### 6.23 Scheduling Interface

6.22.1 These are dedicated API interfaces defined in the scheduling interface Building Block and hence not defined here.

6.22.2 The scheduling interface Building Block SHOULD provide the necessary protocol, data format, and information and interface to interact with the scheduling interface Building Block to enable users on the Consumer Platform and the Provider Platform interface to automate the process based on the events in the system.

<mark style="color:blue;">6.17.1 The buyer MUST be able to publish advertisements/announcements on their website/mobile app/kiosk application about their requirements, vacancies, expertise, hosting events (physical or online), videos, advertisements, schedule of activities for next 6 months etc.</mark>

<mark style="color:blue;">6.17.2 The platform should be able to connect with social media networks and reach the target audience.</mark>

<mark style="color:blue;">6.17.3 The suppliers, citizens, entities should be able to subscribe to social media channels and to the website so as to receive updates from the buyer.</mark>

<mark style="color:blue;">6.17.4 The buyer should be able to send alerts, messages, emails to subscribers about the new announcements.</mark>

<mark style="color:blue;">6.17.5 The subscriber should be able to cancel their subscriptions as and when desired</mark>.

### <mark style="color:blue;">6.18 Content Management Interface</mark>

<mark style="color:blue;">6.18.1 The interface SHOULD be able to moderate, curate content creation</mark>

<mark style="color:blue;">6.18.2 The interface SHOULD enable the user (citizen/supplier) to submit a document, best practices in a prescribed format</mark>

<mark style="color:blue;">6.18.3 The interface SHOULD be able to store the documents in an organized manner</mark>

<mark style="color:blue;">6.18.4 It should allow any user to access the organized content.</mark>

<mark style="color:blue;">6.18.5 The interface allows the suppliers or users to add text, images, product description details etc. to a good/service</mark>

### <mark style="color:blue;">6.19 Workflow Interface</mark>

<mark style="color:blue;">6.19.1 The interface SHOULD automate the processes involved in a lifecycle of technical activities, as defined by the administrator.</mark>

<mark style="color:blue;">6.19.2 The status of each process should be 'Live', accompanied with time stamp details.</mark>

<mark style="color:blue;">6.19.3 Upon a status is technically fulfilled (whether completed/achieved, failed, cancelled), the next relevant process should get triggered automatically.</mark>

### <mark style="color:blue;">6.20 Dashboard and Business Analytics Interface</mark>

<mark style="color:blue;">6.20.1 This interface SHOULD visualize the 'LIVE' data on identified set of data fields such as number of items in stock, cancelled items etc.</mark>

<mark style="color:blue;">6.20.2 This interface should analyze the data using basic mathematical operations (such as addition, average, percentage) and offer insights.</mark>

<mark style="color:blue;">6.20.3 The interface MAY have advance mathematical operations such as analyzing historical data, prediction analyses using linear regression, machine learning algorithms.</mark>

<mark style="color:blue;">6.20.4 This interface MAY be able to perform and fetch advance statistics, upon a request from the administrator, such as annual/half-yearly procurement/sales of goods and services, year on increments etc.</mark>

### <mark style="color:blue;">6.21 GIS Interface</mark>

<mark style="color:blue;">6.21.1 This interface SHOULD track the goods/services, with timestamps</mark>

<mark style="color:blue;">6.21.2 The interface SHOULD tag the coordinates of entities, of persons as defined by the administrator</mark>

<mark style="color:blue;">6.21.3 The interface SHOULD be live.</mark>

### <mark style="color:blue;">6.22 Consent Management Interface</mark>

<mark style="color:blue;">6.22.1 This interface SHOULD accept the data of different types and forms (biometrics, electronic messages, physical inputs)</mark>

<mark style="color:blue;">6.22.2 The interface SHOULD let the user decide to accept/reject to share their consent to the applications</mark>

<mark style="color:blue;">6.22.3 The interface MUST respect the Consent protocols/related policies as defined by the administrator.</mark>

<mark style="color:blue;">6.22.4 The interface MUST validate the consent of the user, as required.</mark>

### <mark style="color:blue;">6.23 Messaging Interface</mark>

<mark style="color:blue;">6.23.1 This interface MUST act as a secured channel between sending and receiving users</mark>

<mark style="color:blue;">6.23.2 This interface SHOULD facilitate to message both encrypted and non-encryoted</mark>

<mark style="color:blue;">6.23.3 Logging, back-up, retrival of lost messages, storage features shall be enabled by this interface.</mark>

### <mark style="color:blue;">6.24 Scheduling Interface</mark>

<mark style="color:blue;">6.24.1 This interface SHOULD orchestrate processes with time stamps and when triggered</mark>

<mark style="color:blue;">6.24.2 It SHOULD update the processes, current list of stock items</mark>

<mark style="color:blue;">6.24.3 It SHOULD perform communication related activities such as sending alerts, reminders, automated messages, upon achieving a stage/state</mark>

### <mark style="color:blue;">6.25 Bid Evaluation</mark>

<mark style="color:blue;">6.25.1 The eMarketplace MUST allow the buyer to perform an evaluation (financial, technical, any other)</mark>

<mark style="color:blue;">6.25.2 The E-Marketplace must allow the buyer to pre-define an evaluation criteria for a good or service.</mark>

<mark style="color:blue;">6.25.3 It shall facilitate the buyer and supplier to seek clarification on any of the questions, they might have.</mark>&#x20;

<mark style="color:blue;">6.25.4  It must allow the individual members to read the documents, other details and share their scores, remarks, ranking based on the pre-defined criteria</mark>

<mark style="color:blue;">6.25.5 The evaluation report/remarks shall be fed to the administrator and the final acceptance (not the details) may be communicated to the suppliers.</mark>

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
