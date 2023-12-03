---
description: This section lists the technical capabilities of this Building Block.
---

# 6 Functional Requirements

The e-Marketplace does not assume any particular standard like REST (Representational State Transfer) for all internal resource management. A brief description of the functional requirements necessary to orchestrate each key digital functionality is given below, considering the development of a minimum viable product. Detailed design and more elaborate feature lists of these functionalities can be customized by developers to optimally match respective implementation needs. It is also left to the application implementing this Building Block to receive the responses from the e-Marketplace and present them appropriately and provision for associated user interface interactions.

### **6.1 Catalog Management**&#x20;

* The e-Marketplace must allow the creation of a search request with a context and a message. The context must contain the action performed (“search”), the location where the search is limited to (e.g. country, city, area code, etc.), the domain/category of search (e.g. healthcare, services, etc.), the identity of the platform generating the search (e.g. domain, name), the callback URL of the platform generating the search. (REQUIRED)
* The context must also contain a unique transaction ID to represent a sequence of interactions. It must also contain a unique message ID to match a request with a callback. The search context must contain a timestamp denoting the time of the search. (REQUIRED)
* It should allow the addition of an intent to the message. The intent should contain fulfillment details in case the customer wants their order fulfilled in a specific way. If there is a preferred method of payment the intent should contain the payment details. The intent should define the category of the search. If search criteria is specific to an offer, intent must contain the offer detail. (REQUIRED)
* It should allow multiple search parameters and should allow updates of search parameters, the system should provide the flexibility to update the search criteria, ex-search is to be modified for category, payment type, etc. (REQUIRED)
* Once a call is made and the user wants to make a next search call that can not be fulfilled with the existing data from the previous search call, the system should be able to use the selected fields and the modified search fields for the next search call. (REQUIRED)
* It must be able to transmit the search request along with all the search parameters to the provider platform. (REQUIRED)
* This Building Block should allow fetching of catalogs that match the maximum number of search parameters. (RECOMMENDED)
* The e-Marketplace must allow the creation of a catalog request for which context is required and should have a message. (REQUIRED)
* The context is used to describe the metadata of the details provided in the message part. The context must contain an action. It also must contain a unique transaction ID received by the search request to represent a sequence of interactions. It must also contain a unique message ID to match a request with a callback. It must contain a timestamp denoting the time of the search requested for the catalog. (REQUIRED)
* The message must contain a catalog. The catalog is used to describe the products or services provided by the platform. The catalog should be formed based on the search request made by the user and the data filtered accordingly and added to the catalog. (REQUIRED)
* The catalog should be able to provide a description, it will have a description of the product or service, and it can have short/long descriptions or descriptions for images. (REQUIRED)
* The catalog should provide fulfillment details, it will provide the details about the fulfillment mode if the e-Marketplace takes responsibility for the fulfillment. (RECOMMENDED)
* The catalog should provide payment details about the payment terms offered by the e-Marketplace. The terms can be overridden by the providers' section, in case e-Marketplace does not take responsibility for the payments. (REQUIRED)
* The catalog should provide expiry details about the time (timestamp) after which the catalog will not be valid. The consumer platform must be able to process the expiry and invalidate the catalog. E.g. A limited-time offer on a service/product. (REQUIRED)
* The catalog should provide details of the time to live (TTL), which describes the time to set to exist for the catalog before it is discarded by a router and expires. The consumer platform must be able to process the TTL and invalidate the catalog. (REQUIRED)
* The provider platform must be able to call the on\_search API provided by the Consumer platform to provide the catalog of the products. (REQUIRED)
* The Consumer platform should provide a mechanism to handle the response (catalog) for a search, it should display the products/services in the catalog properly and filter the products at the UI layer. (REQUIRED)
* The consumer platform should be able to handle multiple responses against a search tied with a message ID made, as the response can be from multiple providers. (REQUIRED)

### 6.2 Inventory Management

* The e-Marketplace must allow the providers to add new products to their inventory. (REQUIRED)
* It should be able to provide the current status of the inventory products, and the reporting should provide various filters based on which report can be generated. (REQUIRED)
* It should allow updating the quantity and location of Items across multiple Providers and must restrict access to the providers' internal inventory. (REQUIRED)
* Inventory must get adjusted based on the order placed (confirm/cancel/return). (REQUIRED)
* It must allow checking of the availability of an Item in a catalog to avoid out-of-stock and over-stocking of the product. (REQUIRED)
* It should provide a configurable system for notification which notifies based on the defined criteria. E.g. If the product quantity is less than 50, it must notify the provider by email or SMS. (RECOMMENDED)

### 6.3 Quotation Management

* The e-Marketplace must enable the construction of a cart (or a cart-like experience)  on the consumer platform, it must consist of context and message. (REQUIRED)
* It must allow the addition/removal/update of multiple items and their respective quantities in the cart. (REQUIRED)
* It must allow the consumer to choose from different offers available, and users should be able to modify or remove the offer before an order is placed. (REQUIRED)
* It must allow users to modify the addons in the cart, the cart should not be frozen before an order is placed. The consumer should be able to modify the products i.e. add/remove products or modify the quantity of the product. (REQUIRED)
* It must allow the transmission of the cart from the consumer platform to the provider platform. (REQUIRED)
* Upon receiving the cart from the consumer platform, it must allow the provider platform to check for the availability of items in the cart. (REQUIRED)
* It should check the validity of offers against the items in the cart. (REQUIRED)
* it should dynamically calculate the quote based on the available items, offers, and add-ons. (REQUIRED)
* It should transmit the cart with the updated quote from the provider platform to the consumer platform. (REQUIRED)
* Provider platform should respond with context and either order or show error. (REQUIRED)
* The consumer platform must process the quote properly and show the details along with the offers/delivery/payments details and break up of the quote. (REQUIRED)

### 6.4 Terms Management&#x20;

* The e-Marketplace must enable the construction of a draft order (or a pre-checkout-like experience) on the consumer platform, the draft order must contain context and a message with order details. (REQUIRED)
* Consumer applications must allow the modification of the billing details of the order before a request is sent to the provider. (REQUIRED)
* It must allow the consumers to modify the fulfillment details. E.g a consumer that has multiple addresses stored in the application should be able to select the address or add a new address for fulfillment. Consumers should also be able to choose from the available fulfillment options. (REQUIRED)
* It must allow the transmission of the draft order from the consumer platform to the provider platform. (REQUIRED)
* The consumer app must recalculate the quote based on the modifications made in the fulfillment details. (REQUIRED)
* The consumer app must check the serviceability of the order based on agent availability. (REQUIRED)
* Provider platform must re-check the availability of items and validity of offers, and re-calculate the quote based on the selection made by the consumer. (REQUIRED)
* Provider platform must allow creation and modification of payment terms containing the payment stage, final payable amount, payment endpoint, and payment schedule to the draft order. (REQUIRED)
* Provider app must allow the addition of terms of service, cancellation, returns, replacements, and refunds wherever applicable. (REQUIRED)
* Provider platform must respond with context and either order or an error. (REQUIRED)
* It must allow the transmission of the final draft order containing all the details of the order to the consumer platform. (REQUIRED)
* The consumer platform must be able to handle the final draft order received from the provider and display the final order draft. (REQUIRED)

### 6.5 Order Management&#x20;

* The e-Marketplace must enable the creation of a confirmed order with a unique Order ID, the confirmed order must contain context and message. (REQUIRED)
* Before confirming an order to the provider platform consumer platform must allow modification of a fulfillment state in the order. (REQUIRED)
* The consumer platform must allow the transmission of the final draft order to the provider platform. (REQUIRED)
* Provider platform must again allow re-checking of inventory availability before creating the order. (REQUIRED)
* It must allow the transmission of the confirmed order from the provider platform to the consumer platform. (REQUIRED)
* Provider platform response to a confirmed order must contain context and either an order or an error. (REQUIRED)
* The consumer platform must be able to handle the order confirmation received from the provider platform and display the success message to the consumer along with the order ID and the product's details in the order. (REQUIRED)

### 6.6 Order Fulfillment&#x20;

* The e-Marketplace must enable the discovery and allocation of an Agent (if applicable) to the fulfillment of a confirmed order. (REQUIRED)
* Consumer application must be able to fetch the status of the order from the provider platform. (REQUIRED)
* Provider platform must be able to find out the status of the order and provide the details back to the consumer application. (REQUIRED)
* Provider application must allow updates on the status of the order. (REQUIRED)
* When a new event occurs on the fulfillment, the provider platform must pass on the information to the consumer platform. (REQUIRED)

### 6.7 Order Tracking&#x20;

* The e-Marketplace must enable the fetching of tracking information related to the order. (REQUIRED)
* It must allow real-time data to be transmitted from the provider to the consumer. (REQUIRED)
* It must allow the consumer platform to transmit a webhook endpoint to the provider platform which will handle the real-time updates on the tracking. (REQUIRED)
* It must allow the provider platform to transmit a tracking link to the consumer platform. (REQUIRED)
* The consumer platform must allow the display of the tracking details to the consumer along with the history. (REQUIRED)
* Consumer applications must be able to segregate the tracking details based on the order ID. (REQUIRED)

### 6.8 Order Cancellation&#x20;

* The consumer platform must allow the creation of an order cancellation request for all the active orders that are yet not fulfilled. (REQUIRED)
* The consumer platform must provide the order ID and allow the addition of the cancellation reason to the cancellation request. (REQUIRED)
* Provider platform must handle the cancel order request and respond to the consumer platform. (REQUIRED)
* Provider platform must allow modification of the order status and de-allocation of fulfillment services and the agents associated with the fulfillment of the contract. (REQUIRED)
* It must allow the calculation of cancellation terms (if applicable) depending on the reason provided and the time of the cancellation request. (REQUIRED)
* It must be possible to add a link to the cancellation terms (including cancellation fee) document to the order. (REQUIRED)
* It must allow transmission of the canceled order between the consumer and the provider. (REQUIRED)
* On cancellation of an order the provider platform must adjust the inventory of the products canceled. (REQUIRED)
* The consumer platform must handle the response from the provider platform for a cancellation request, and update the order status, and display the details of the cancellation of the order along with the cancellation terms (including the cancellation fee). (REQUIRED)

### 6.9 Rating and Feedback Management&#x20;

* The e-Marketplace must allow ratings for various rateable entities to be captured by people involved in a transaction. (REQUIRED)
* It must allow the transmission of ratings from the consumer platform to the provider platform. (REQUIRED)
* It must allow the creation of feedback by the provider platform to get detailed additional information on the rating provided. (RECOMMENDED)
* It must allow the creation of a request to collect additional feedback related to a rating. (RECOMMENDED)
* It must allow fetching of various rateable entities related to an order. (RECOMMENDED)

### 6.10 Support Management&#x20;

* The e-Marketplace must allow support center information like email, phone number, and chat URL concerning an order to be transmitted between the consumer and the provider platforms. (REQUIRED)&#x20;
* It must allow the creation/read/update/deletion of tickets concerning an issue raised by a consumer, or an agent. (REQUIRED)

### 6.11 Information Mediator Interface

* This sub-block runs protocols to communicate with the information mediator Building Block for exposing e-marketplace services to external Building Blocks and applications. (REQUIRED)&#x20;
* It also provides specific calls to APIs of information mediator Building Block to access services of external applications and Building Blocks. (REQUIRED)&#x20;
* It also handles any errors and failures in data exchange between the e-Marketplace and other Building Blocks/Apps (such as backoff and retries, etc.). (REQUIRED)&#x20;
* &#x20;It routes error information if any to the logger sub-block. (REQUIRED)&#x20;
* It maintains a list of endpoint addresses of Information Mediator, or other Building Blocks/Applications. (REQUIRED)

### 6.12 Payment Interface

* These are dedicated API interfaces defined in the Payments Building Block and hence not defined here:
  * The Payment interface should provide the necessary protocol, data format, and information and interface to interact with the Payments Building Block for sending payment collection or settlement instructions to existing payment infrastructures like Banking Systems, Credit Card Networks, Payment Gateways, etc. to facilitate payments made during a transaction in the e-Marketplace. (RECOMMENDED)&#x20;

### 6.13 E-Signature Interface

* These are dedicated API interfaces defined in the e-Signature Building Block and hence not defined here:
  * The E-Signature interface should provide the necessary protocol, data format, information, and interface to interact with the e-Signature Building Block for the digital signing and subsequent verification of each message that is transmitted between the consumer platform and the provider platform. (RECOMMENDED)

### 6.14 Registration Interface

* These are dedicated API interfaces defined in the Registration Building Block and hence not defined here:
  * The Registration interface should provide the necessary protocol, data format, and information and interface to interact with the Registration Building Block to enable users on the Consumer Platform and the Provider Platform to sign up on their respective platforms with the required information necessary to perform transactions on the e-Marketplace. (RECOMMENDED)

### 6.15  Digital Identity & Verification Interface

* These are dedicated API interfaces defined in the Digital Identity and Verification Building Block and hence not defined here:
  * The Digital Identity and Verification Building Block should provide the necessary protocol, data format, and information and interface to interact with the Digital Identity & Verification Building Block to enable users on the Consumer Platform and the Provider Platform interface to verify the digital identities in the e-Marketplace based on their national data registers. (RECOMMENDED)

### 6.16 Promotional Communications

* These are dedicated API interfaces defined in the  Communication and Outreach Building Block and hence not defined here:
  * The Communication and Outreach Building Block should provide the necessary protocol, data format, and information and interface to interact with the Communication and Outreach Building Block to enable users on the Consumer Platform and the Provider Platform interface to integrate with social media and messaging platforms. (RECOMMENDED)

### 6.17 **Content Management Interface**

* These are dedicated API interfaces defined in the Content Management Interface Building Block and hence not defined here:
  * The Content Management Interface Building Block should provide the necessary protocol, data format, and information and interface to interact with the Content Management Interface Building Block to enable users on the Consumer Platform and the Provider Platform interface to manage content creation. (RECOMMENDED)
  * The interface should be able to moderate, and curate content creation. (RECOMMENDED)
  * The interface should enable the user (consumer/provider) to submit a document, and best practices in a prescribed format. (RECOMMENDED)
  * The interface should be able to store the documents in an organized manner. (RECOMMENDED)
  * It should allow any user to access the organized content. (RECOMMENDED)
  * The interface allows the providers to add text, images, product description details, etc. to a good/service. (RECOMMENDED)

### 6.18 **Workflow Interface**

* These are dedicated API interfaces defined in the Workflow interface Building Block and hence not defined here:
  * The Workflow interface Building Block should provide the necessary protocol, data format, and information and interface to interact with the Workflow interface Building Block to enable users on the Consumer Platform and the Provider Platform interface to define and orchestrate the workflow within the system. (RECOMMENDED)
  * The interface should automate the processes involved in a lifecycle of technical activities, as defined by the administrator. (RECOMMENDED)
  * The status of each process should be 'Live', accompanied by timestamp details. (RECOMMENDED)
  * Upon a status is technically fulfilled (whether completed/achieved, failed, or canceled), the next relevant process should get triggered automatically. (RECOMMENDED)

### 6.19 **Dashboard & Business Analytics Interface**

* These are dedicated API interfaces defined in the Dashboard and Business Analytics interface Building Block and hence not defined here:
  * The dashboard and business analytics interface Building Block should provide the necessary protocol, data format, and information and interface to interact with the dashboard & business analytics interface Building Block to enable users on the Consumer Platform and the Provider Platform interface to visualize the data in the system. (RECOMMENDED)
  * This interface should visualize the 'live' data on the identified set of data fields such as the number of items in stock, canceled items, etc. (RECOMMENDED)
  * This interface should analyze the data using basic mathematical operations (e.g. addition, average, and percentage) and offer insights. (RECOMMENDED)
  * The interface may have advanced mathematical operations such as analyzing historical data, and prediction analyses using linear regression and machine learning algorithms. (OPTIONAL)
  * This interface may be able to perform and fetch advance statistics, upon a request from the administrator, such as annual/half-yearly procurement/sales of goods and services, year-on increments, etc. (OPTIONAL)

### 6.20 **GIS Building Block Interface**

* These are dedicated API interfaces defined in the GIS interface Building Block and hence not defined here:
  * The GIS interface Building Block should provide the necessary protocol, data format, and information and interface to interact with the GIS interface Building Block to enable users on the Consumer Platform and the Provider Platform interface to use GIS-based services like GIS tagging, tracking, etc. (RECOMMENDED)
  * This interface should track the goods/services, with timestamps. (RECOMMENDED)
  * The interface should tag the coordinates of entities, of persons as defined by the administrator. (RECOMMENDED)
  * The interface should be live. (RECOMMENDED)

### 6.21 Consent Management Interface

* These are dedicated API interfaces defined in the Consent Management Interface Building Block and hence not defined here:
  * The Consent Management Interface Building Block should provide the necessary protocol, data format, and information and interface to interact with the consent management interface Building Block to enable users on the Consumer Platform and the Provider Platform interface to capture and validate the consent of the users. (RECOMMENDED)
  * This interface should accept data of different types and forms (biometrics, electronic messages, physical inputs). (RECOMMENDED)
  * The interface should let the user decide to accept/reject to share their consent to the applications. (RECOMMENDED)
  * The interface must respect the Consent protocols/related policies as defined by the administrator. (REQUIRED)
  * The interface must validate the consent of the user, as required. (REQUIRED)

### 6.22 Messaging Interface

* These are dedicated API interfaces defined in the Messaging interface Building Block and hence not defined here:
  * The Messaging interface Building Block should provide the necessary protocol, data format, and information and interface to interact with the messaging interface Building Block to enable users on the Consumer Platform and the Provider Platform interface to exchange messages over a secured channel and have logging features. (RECOMMENDED)
  * This interface must act as a secured channel between sending and receiving users. (REQUIRED)
  * This interface should facilitate messages both encrypted and non-encrypted. (RECOMMENDED)
  * Logging, backup, retrieval of lost messages, and storage features shall be enabled by this interface. (RECOMMENDED)

### 6.23 Scheduling Interface

* These are dedicated API interfaces defined in the Scheduling interface Building Block and hence not defined here:
  * The Scheduling interface Building Block should provide the necessary protocol, data format, and information and interface to interact with the Scheduling interface Building Block to enable users on the Consumer Platform and the Provider Platform interface to automate the process based on the events in the system. (RECOMMENDED)
  * The consumer must be able to publish advertisements/announcements on their website/mobile app/kiosk application about their requirements, vacancies, expertise, hosting events (physical or online), videos, advertisements, schedule of activities for the next 6 months, etc. (REQUIRED)
  * The platform should be able to connect with social media networks and reach the target audience. (RECOMMENDED)
  * The providers, consumers, and entities should be able to subscribe to social media channels and to the website to receive updates from the consumer. (RECOMMENDED)
  * The consumer should be able to send alerts, messages, and emails to subscribers about the new announcements. (RECOMMENDED)
  * The subscriber should be able to cancel their subscriptions as and when desired.  (RECOMMENDED
  * This interface should orchestrate processes with time stamps when triggered.  (RECOMMENDED)
  * &#x20;It should update the processes and current list of stock items.  (RECOMMENDED)
  * It should perform communication-related activities such as sending alerts, reminders, and automated messages, upon achieving a stage/state.  (RECOMMENDED)

### 6.24 Bid Evaluation

* The e-Marketplace must allow the consumer to perform an evaluation (financial, technical, any other). (REQUIRED)
* The e-Marketplace must allow the consumer to pre-define an evaluation criteria for a good or service. (REQUIRED)
* It shall facilitate the consumer and provider to seek clarification on any of the questions, they might have. (REQUIRED)
* It must allow the individual members to read the documents, and other details and share their scores, remarks, and ranking based on the pre-defined criteria. (REQUIRED)
* The evaluation report/remarks shall be fed to the administrator and the final acceptance (not the details) may be communicated to the providers. (REQUIRED)

## **The eMarketplace Building Block must enable Admins to**

* enable the registration process of both prividers and consumers.&#x20;
* enable the verification of Foundational IDs come with no specified purpose or attached entitlement but functionalities simply let an entity prove who it is.
* Captures only limited information about users, such as name, date of birth, address, and gender.
* For a given set of credentials, fetches a corresponding ID if it exists in the registry.
* Uses different biometric methods to identify and authenticate users through means other than user photographs (e.g. fingerprints, iris scans, facial recognition) to ensure there are no duplicates or fakes, creating a highly trustworthy database.
* open bank accounts, buy SIM cards, receive entitlements from the government, sign forms electronically, invest in mutual funds, and get credit.
* Incorporate privacy into its design when the purpose of the authentication is not revealed if a service provider sends an authentication request.

**The e-Marketplace must enable Building Block Admins (Provider and Consumers) to**

* seek consent from the entities, and people while registration.
* dynamically identify, verify, and validate the registration details against those of public registries.
* register without duplication an entity, into its Entity List with details (e.g. name, phone, email, website, etc.). The entities host various "activities" involving their affiliated resources (client case management).
* categorize entities for easy searching and sorting, e.g. "department" or "ministry" .
* configure rules for performance, security, and communication management between the eMarketplace and other Building Blocks (e.g. Registries, Identity and Verification, Information Mediation), applications (across different departments/ministries), and event participants. The exact parameters may be decided at implementation time.
* extract log reports from the system as needed for monitoring and administering the Building Block operations.
* register subscribers (persons/citizens/individuals) without duplication into eMarketplace's Subscriber list with contact details (phone/mail/URL/) as needed for communication, and reuse for enrolment to multiple activities.
* register order life cycle events with a defined starting and ending time and an optional deadline for participants to log in their attendance in the activity if needed.
* access a restricted number of subscribers to an activity, based on the sorting/category filter.
* define and maintain a library of a predefined stack of messages/notifications for a specific host entity so that it can be reused in multiple activities conducted by the specific host entity.
* define alert schedules for sending specific alert messages associated with a certain event at a determined date-time to associated subscribers or resources or both.
* to extract logs related to activities that help in continuous improvement in order lifecycle event management.
* to generate (i.e. purchase order/request), upload, and download the correspondence, circulars, and agreements in ".doc" and ".pdf" formats (document management).
* (the provider) to implement large-scale outreach communication, and awareness campaign activities through electronic means.
* to have a grievance readdress mechanism.
* to facilitate seek/offer/resolve/implement feedback mechanisms once the enrolled activities are completed.
* to delegate access management so that a particular role can perform only the tasks/activities that they are intended to.
* to facilitate workflow management amongst active providers and consumers.
* to handle exceptions when registration fails is unable to generate a purchase request, etc.
* to facilitate communication between both parties, such as seeking clarification, responding to questions raised by the bidder on the bidding process or any other, etc.

**The e-Marketplace must enable consumers and subscribers to**

* search and extract their registration details in the eMarketplace.
* search and extract their affiliation details across associated entities.
* search and extract details of activities they are enrolled into.
* search and extract details of subscribers of activities they are enrolled into.
* receive scheduled alert messages from activities they are enrolled in.
* search and list details of activities of a chosen category in a specified date-time range.
* log status/attendance updates related to activities they are enrolled in.
* view current status, details, and list of activities dynamically.

#### The e-Marketplace must enable the administrator to catalog goods and services&#x20;

* get displayed a list of goods and/or services when an appropriate filter is used (e.g. a ministry or a type of service).
* get displayed a list of active/closed/in progress items of ordering; with its stages for the Provider.
* get displayed the number of days remaining of the entire project duration, payment milestones, and list of deliverables under the consumer department/ministry.

#### The e-Marketplace must have system-automated internal functionality to

* track all order lifecycle stages/events and send corresponding alert messages with unique tokens/IDs to relevant participants at appropriate times.
* detect communication failure with other Building Blocks and applications and perform retries according to configured rules before logging a communication failure. Associated implementation-specific details that are not specified here.&#x20;
