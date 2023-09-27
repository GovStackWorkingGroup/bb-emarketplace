# 6 Functional Requirements

{% hint style="success" %}
The functional requirements section lists the technical capabilities that this building block should have. These requirements should be sufficient to deliver all functionality that is listed in the Key Digital Functionalities section.

These functional requirements do not define specific APIs - they provide a list of information about functionality that must be implemented within the building block.

These requirements should be defined by subject-matter experts and don’t have to be highly technical in this section.

If there are multiple functional components of a building block, the functional requirements for each component may have its own section
{% endhint %}

### Internal functional components

The E-Marketplace can be visualized as a black box with all key digital functionalities discussed in section 4. It does not assume any particular standard like REST for all internal resource management. A brief description of the functional requirements required to orchestrate each key digital functionality is given below, <mark style="color:blue;">considering the development of a</mark> minimum viable product ~~perspective~~. Detailed design and more elaborate feature lists of these blocks can be customized by developers to optimally match respective implementation needs. It is also left to the application implementing this building block to receive the responses from the E-marketplace and present it appropriately and provision for associated user interface interactions.



### **6.1 Catalog Management**&#x20;

* The e-marketplace must allow creation of a search request with a context and a message. The context MUST contain the action performed (“search”), the location where the search is limited to (ex: country, city, area code etc), the domain / category of search (ex: healthcare, services, etc), the identity of the platform generating the search (ex: domain name), the callback url of the platform generating the search.
* The context MUST also contain a unique transaction ID to represent a sequence of interactions. It must also contain a unique message ID to match a request with a callback. The search context must contain a timestamp denoting the time of the search.
* It should allow addition of an intent to the message. Intent should contain fulfillment details in case the customer wants their order fulfilled in a specific way. If there is a preferred method of payment the intent should contain the payment details. The intent should define the category of the search. If search criteria is specific to an offer, intent must contain the offer detail.
* It should allow multiple search parameters and  should allow updates of search parameters , the system should provide the flexibility to update the search criteria, ex- search is to be modified for category, payment type etc.
* Once a call is made and the user wants to make a next search call which can not be fulfilled with the existing data from the previous search call, the system should be able to use the selected fields and the modified search fields for the next search call.
* It must be able to transmit the search request along with all the search parameters to the provider platform.
* This building block should allow fetching of catalogs that matches the maximum number of search parameters.
* The e-marketplace must allow creation of a catalog request for which context is required and should have a message.
* The context is used to describe the metadata of the details provided in the message part. The context must contain an action. It also must contain a unique transaction ID received by the search request to represent a sequence of interactions. It must also contain a unique message ID to match a request with a callback. It must contain a timestamp denoting the time of the search requested for the catalog.
* The  message must contain catalog. Catalog is used to describe the products or services provided by the platform. The catalog should be formed on the basis of the search request made by the user and the data is filtered accordingly and added to the catalog.
* Catalog should be able to provide description, it will have description of the product or service. it can have short description, long description, describing images.
* Catalog should provide fulfillment details , it will provide the details about the fulfillment mode, if the e-marketplace takes the responsibility of the fulfillment.
* Catalog should provide payment detail, it provides details about the payment terms offered by the e-marketplace. The terms can be overridden by the providers section, in case e-marketplace does not take responsibility for the payments.
* Catalog should provide expiry details, it will provide details about the time (timestamp) after which the catalog will not be valid. Consumer platform must be able to process the expiry and invalidate the catalog.Ex- A limited time offer on a service/product.
* Catalog should provide details of the time to live, ttl describes the time to live for the catalog after which catalog expires.Consumer platform must be able to process the ttl and invalidate the catalog
* Seller platform must be able to call the on\_search API provided by the buyer platform to provide the catalog of the products.
* The buyer platform should provide a mechanism to handle the response(catalog) for a search , it should display the products/services in the catalog properly and should be able to filter the products at the UI layer also.
* Consumer platform should be able to handle multiple responses against a search tied with a message ID made as the response can be from multiple providers

### 6.2 Inventory Management

* The E-Marketplace must allow the sellers to add new products in their inventory.
* It should be able to provide the current status of the inventory products , the reporting should provide various filters based on which report can be generated.
* It should allow updating the quantity and location of Items across multiple Providers and must restrict the access to sellers own inventory.
* Inventory must get adjusted based on the order placed (confirm/cancel/return)
* It must allow checking of availability of an Item in a catalog to avoid out-of-stock and over-stocking of the product.
* It should provide a configurable system for notification which notifies based on the defined criteria. Ex- If product quantity is less than 50 , it must notify the seller with email or SMS.

### 6.3 Quotation Management

* The E-Marketplace must enable the construction of a cart (or a cart-like experience)  on the consumer platform, it must consist of context and message
* It must allow addition / removal / update of multiple items and their respective quantities in the cart
* It must allow the consumer to choose from different offers available, and users should be able to modify or remove the offer before an order is placed.
* It must allow users to modify the addons in the cart, the cart should not be freeze before an order is placed. The consumer should be able to modify the products i.e. add ,remove products also should be able to modify the quantity of the product.
* It must allow transmission of the cart from the consumer platform to the provider platform
* Upon receiving the cart from the consumer platform, it must allow the provider platform to check for the availability of items in the cart
* It should check the validity of offers against the items in the cart
* it should dynamically calculate the quote based on the available items, offers, and add-ons
* It should transmit the cart with the updated quote from the provider platform to the consumer platform
* Provider platform should response with context and either order or with error
* Consumer platform must process the quote properly and show the details along with the offers/delivery/payments details and break up of the quote.

### 6.4 Order Terms Management&#x20;

* The E-Marketplace must enable the construction of a draft order (or a pre-checkout like experience) on the consumer platform, the draft order must contain context and message with order details.
* Consumer applications  must allow the modification of the billing details of the order before a request is sent to the provider.
* It must allow the consumers to modify the fulfillment details. Ex- Consumer has multiple addresses stored in the application, he should be able to select the address or add a new address for fulfillment. Consumers should also be able to choose from the available fulfillment options.
* It must allow the transmission of the draft-order from the consumer platform to the provider platform
* Consumer app must  recalculate the quote based on the modifications made in the fulfillment details
* Consumer app must check the serviceability of the order on the basis of agent availability
* Provider platform must re-check the availability of items, validity of offers and re-calculate the quote based on the selection made by the consumer
* Provider platform must allow creation and modification of payment terms containing the payment stage, final payable amount, payment endpoint and payment schedule to the draft order
* Provider app  must allow addition of terms of service, cancellation, returns, replacements and refunds wherever applicable
* Provider platform must response with context and either order or an error
* It must allow the transmission of the final draft order containing all the details of the order to the consumer platform
* Consumer platform must be able to handle the final draft order received from the provider and display the final order draft.

### 6.5 Order Management&#x20;

* The E-Marketplace must enable creation of a confirmed order with an unique Order ID, the confirm order must contain context and message
* Before confirming an order to provider platform consumer platform must allow modification of a fulfillment state in the order
* Consumer platform must allow the transmission of the final draft order to the provider platform
* Provider platform must again allow re-checking of inventory availability before creating the order
* It must allow the transmission of the confirmed order from the provider platform to the consumer platform
* Provider platform response to a confirmed order must contain context and either order or an error
* Consumer platform must be able to handle the order confirmation received from the provider platform and display the success message to the consumer along with the order id and the product's details in the order.

### 6.6 Order Fulfillment&#x20;

* The E-Marketplace must enable discovering and allocation of an Agent (if applicable) to the fulfillment of a confirmed order.
* Consumer application must be able to fetch the status of the order from the provider platform.
* Provider platform must be able to find out the status of the order and provide the details back to the consumer application.
* Provider application must allow updates of the status of the order.
* When a new event occurs on the fulfillment, provider platform must pass on the information to the consumer platform.

### 6.7 Order Tracking&#x20;

* The E-Marketplace must enable fetching of tracking information related to the order
* It must allow real-time data to be transmitted from the provider to the consumer
* It must allow the consumer platform to transmit a webhook endpoint to the provider platform which will handle the real time updates on the tracking
* It must allow the provider platform to transmit a tracking link to the consumer platform
* Consumer platform must allow display of the tracking details to the consumer along with the history
* Consumer applications must be able to segregate the tracking details based on the order ID.

### 6.8 Order Cancellation&#x20;

* Consumer platform must allow creation of an order cancellation request for all the active orders which are yet not fulfilled.
* Consumer platform must provide order id and allow addition of cancellation reason to the cancellation request
* Provider platform must handle the cancel order request and respond back to the consumer platform
* Provider platform must allow modification of the order status and  de-allocation of fulfillment services and the agents associated with the fulfillment of the contract
* It must allow calculation of cancellation terms (if applicable) depending on the reason provided and time of the cancellation request
* It must be possible to add a link to the cancellation terms (including cancellation fee) document to the order
* It must allow transmission of the canceled order between the consumer and the provider
* On cancellation of an order the provider platform must adjust the inventory of the products canceled
* Consumer platform must handle the response from the provider platform for a cancellation request and update the order status and display the details of cancellation of order along with the cancellation terms (including cancellation fee).

### 6.9 Rating and Feedback Management&#x20;

* The E-Marketplace must allow ratings for various rateable entities to be captured by people involved in a transaction
* It must allow the transmission of ratings from the consumer platform to the provider platform
* It must allow creation of feedback by provider platform to get detailed additional information on the rating provided
* It must allow creation of a request to collect additional feedback related to a rating
* It must allow fetching of various rateable entities related to an order

### 6.10 Support Management&#x20;

* The E-Marketplace must allow support center information like email, phone number and chat URL in relation to an order to be transmitted between the consumer and the provider platforms&#x20;
* It must allow the creation/read/update/deletion of tickets in relation to an issue raised by a consumer, or an agent

### 6.11 Information Mediator Interface

* This sub-block runs protocols to communicate with the information mediator Building Block for exposing e-marketplace services to external Building Blocks and applications.
* It also provides specific calls to APIs of information mediator Building Block to access services of external applications and Building Blocks.&#x20;
* It also handles any errors and failures in data exchange between the e-marketplace and other Building Blocks/Apps (such as backoff and retries, etc.).
* It routes error information if any to the logger sub-block.&#x20;
* It maintains a list of endpoint addresses of Information Mediator, other Building Blocks, and Applications.

### 6.12 Payment Interface

* &#x20;These are dedicated API interfaces defined in the Payment building block and hence not defined here.
* The Payment interface SHOULD provide the necessary protocol, data format, and information and interface to interact with the Payment Building Block for sending payment collection or settlement instructions to existing payment infrastructures like Banking Systems, Credit Card Networks, Payment Gateways etc to facilitate payments made during a transaction in the E-Marketplace&#x20;

### 6.13 E-Signature Interface

* These are dedicated API interfaces defined in the Signature Building Block and hence not defined here
* The E-Signature interface SHOULD provide the necessary protocol, data format, and information and interface to interact with the e-Signature Building Block for the digital signing and subsequent verification of each message that is transmitted between the consumer platform and the provider platform

### 6.14 Registration Interface

* These are dedicated API interfaces defined in the Registration Building Block and hence not defined here.
* The Registration interface SHOULD provide the necessary protocol, data format, and information and interface to interact with the Registration Building Block to enable users on the Consumer Platform and the Provider Platform to sign up on their respective platforms with the required information necessary to perform transactions on the E-Marketplace

### 6.15  Digital Identity & Verification Interface

* These are dedicated API interfaces defined in the Digital Identity & Verification Building Block and hence not defined here.
* The Digital Identity & Verification Building Block  SHOULD provide the necessary protocol, data format, and information and interface to interact with the Digital Identity & Verification Building Block to enable users on the Consumer Platform and the Provider Platform interface to verify the digital identities in the E-Marketplace based on their national data registers.
* These are dedicated API interfaces defined in the Digital Identity & Verification building block and hence not defined here
* The Digital Identity & Verification interface SHOULD provide the necessary protocol, data format, and information and interface to interact with the Digital Identity & Verification Building Block for sending user registration data (name, unique identity number, tax number, phone/mobile, email etc.) and verify the same with relevant registries through OTP, SMS, biometrics, physical appearance, during a transaction in the E-Marketplace. In case of any error/mismatch, it should be able to suggest alternatives.

### 6.16 Promotional Communications

* These are dedicated API interfaces defined in the  Communication and Outreach Building Block and hence not defined here.
* The Communication and Outreach Building Block  SHOULD provide the necessary protocol, data format, and information and interface to interact with the Communication and Outreach Building Block to enable users on the Consumer Platform and the Provider Platform interface to integrate with social media and messaging platform.

### 6.17 **Content Management Interface**

* These are dedicated API interfaces defined in the content management interface Building Block and hence not defined here.
* The content management interface Building Block  SHOULD provide the necessary protocol, data format, and information and interface to interact with the content management interface Building Block to enable users on the Consumer Platform and the Provider Platform interface to manage content creation.

### 6.18 **Workflow Interface**

* These are dedicated API interfaces defined in the Workflow interface Building Block and hence not defined here.
* The workflow interface Building Block  SHOULD provide the necessary protocol, data format, and information and interface to interact with the workflow interface Building Block to enable users on the Consumer Platform and the Provider Platform interface to define and orchestrate the workflow within the system.

### 6.19 **Dashboard & Business Analytics Interface**

* These are dedicated API interfaces defined in the Dashboard & Business Analytics interface Building Block and hence not defined here.
* The dashboard & business analytics interface Building Block SHOULD provide the necessary protocol, data format, and information and interface to interact with the dashboard & business analytics interface Building Block to enable users on the Consumer Platform and the Provider Platform interface to visualize the data in the system.

### 6.20 **GIS BB Interface**

* These are dedicated API interfaces defined in the GIS interface Building Block and hence not defined here.
* The GIS interface Building Block SHOULD provide the necessary protocol, data format, and information and interface to interact with the GIS interface Building Block to enable users on the Consumer Platform and the Provider Platform interface to use GIS based services like GIS tagging, tracking etc.

### 6.21 Consent Management Interface

* These are dedicated API interfaces defined in the consent management interface Building Block and hence not defined here.
* The consent management interface Building Block SHOULD provide the necessary protocol, data format, and information and interface to interact with the consent management interface Building Block to enable users on the Consumer Platform and the Provider Platform interface to capture and validate the consent of the users.

### 6.22 Messaging Interface

* These are dedicated API interfaces defined in the messaging interface Building Block and hence not defined here.
* The messaging interface Building Block SHOULD provide the necessary protocol, data format, and information and interface to interact with the messaging interface Building Block to enable users on the Consumer Platform and the Provider Platform interface to exchange messages over a secured channel and have logging features.

### 6.23 Scheduling Interface

* These are dedicated API interfaces defined in the scheduling interface Building Block and hence not defined here.
* The scheduling interface Building Block SHOULD provide the necessary protocol, data format, and information and interface to interact with the scheduling interface Building Block to enable users on the Consumer Platform and the Provider Platform interface to automate the process based on the events in the system.
* The buyer MUST be able to publish advertisements/announcements on their website/mobile app/kiosk application about their requirements, vacancies, expertise, hosting events (physical or online), videos, advertisements, schedule of activities for next 6 months etc.
* The platform should be able to connect with social media networks and reach the target audience.
* The suppliers, citizens, entities should be able to subscribe to social media channels and to the website so as to receive updates from the buyer.
* The buyer should be able to send alerts, messages, emails to subscribers about the new announcements.
* The subscriber should be able to cancel their subscriptions as and when desired.

### 6.24 Content Management Interface

* The interface SHOULD be able to moderate, curate content creation
* The interface SHOULD enable the user (citizen/supplier) to submit a document, best practices in a prescribed format
* The interface SHOULD be able to store the documents in an organized manner
* It should allow any user to access the organized content.
* The interface allows the suppliers or users to add text, images, product description details etc. to a good/service

### 6.25 Workflow Interface

* The interface SHOULD automate the processes involved in a lifecycle of technical activities, as defined by the administrator.
* The status of each process should be 'Live', accompanied with time stamp details.
* Upon a status is technically fulfilled (whether completed/achieved, failed, cancelled), the next relevant process should get triggered automatically.

### 6.26 Dashboard and Business Analytics Interface

* This interface SHOULD visualize the 'LIVE' data on identified set of data fields such as number of items in stock, cancelled items etc.
* This interface should analyze the data using basic mathematical operations (such as addition, average, percentage) and offer insights.
* The interface MAY have advance mathematical operations such as analyzing historical data, prediction analyses using linear regression, machine learning algorithms.
* This interface MAY be able to perform and fetch advance statistics, upon a request from the administrator, such as annual/half-yearly procurement/sales of goods and services, year on increments etc.

### 6.27 GIS Interface

* This interface SHOULD track the goods/services, with timestamps
* The interface SHOULD tag the coordinates of entities, of persons as defined by the administrator
* The interface SHOULD be live.

### 6.28 Consent Management Interface

* This interface SHOULD accept the data of different types and forms (biometrics, electronic messages, physical inputs)
* The interface SHOULD let the user decide to accept/reject to share their consent to the applications
* The interface MUST respect the Consent protocols/related policies as defined by the administrator.
* The interface MUST validate the consent of the user, as required.

### 6.29 Messaging Interface

* This interface MUST act as a secured channel between sending and receiving users
* This interface SHOULD facilitate to message both encrypted and non-encrypted
* Logging, back-up, retrival of lost messages, storage features shall be enabled by this interface.

### 6.30 Scheduling Interface

* This interface SHOULD orchestrate processes with time stamps and when triggered.
* It SHOULD update the processes, current list of stock items.
* &#x20;It SHOULD perform communication related activities such as sending alerts, reminders, automated messages, upon achieving a stage/state.

### 6.31 Bid Evaluation

* &#x20;The eMarketplace MUST allow the buyer to perform an evaluation (financial, technical, any other)
* The E-Marketplace must allow the buyer to pre-define an evaluation criteria for a good or service.
* It shall facilitate the buyer and supplier to seek clarification on any of the questions, they might have.&#x20;
* It must allow the individual members to read the documents, other details and share their scores, remarks, ranking based on the pre-defined criteria.
* The evaluation report/remarks shall be fed to the administrator and the final acceptance (not the details) may be communicated to the suppliers.

6.16.1 These are dedicated API interfaces defined in the Digital Identity & Verification building block and hence not defined here

6.16.2 The Digital Identity & Verification interface SHOULD provide the necessary protocol, data format, and information and interface to interact with the Digital Identity & Verification Building Block for sending user registration data (name, unique identity number, tax number, phone/mobile, email etc.) and verify the same with relevant registries through OTP, SMS, biometrics, physical appearance, during a transaction in the E-Marketplace. In case of any error/mismatch, it should be able to suggest alternatives.
