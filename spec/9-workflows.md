# 9 Internal Workflows

In this section, we identify workflows to manifest some of the main services. These may be enhanced or customized as needed for specific implementation needs. The following common preconditions may be needed to be met before utilizing these services:

Entities are registered and active in the  in the system.

Currently acting entities will be logged in the system and has sufficient roles to perform the action.

Initiator building block and the target block must be registered in the system as network participants with status as subscribed and should be active.

This section captures the example workflows that may take place between internal functional blocks to orchestrate key functionalities for a minimum viable product as follows. The exact workflows may be decided depending on implementation time considerations.

* User search for product/service from a provider platform.
* Inventory management
* Viewing an item from the provider catalog.
* Selection of the product.
* Initiation of the purchase request.
* Confirmation of  the order.
* Checking status of the order.
* Cancellation of the order.
* Tracking of an active order.
* Feedback for an order.
* support for an order.
* Catalog management



### 9.1 Searching for Items

The search flow allows consumers to search for available products or services . When a consumer initiates a search request, the catalog providers relevant products or services available respond to the search request by sending back detailed information about their offerings. This includes product details such as descriptions, images, specifications, prices, and any applicable offers or promotions.



```mermaid
sequenceDiagram
    Actor consumer
    participant consumer interface
    box E-Marketplace BB
    participant Catalog Management
    end
    consumer-->>consumer interface: search 
    consumer interface->>Catalog Management:declare search intent
    Catalog Management->>consumer interface:return catalog
    consumer interface-->>consumer:view search results
```



### 9.2 Fetching a quote for selected items

The consumer utilizes the internal workflow within the platform to explore and select from a range of available offers and attributes. These choices have an impact on the pricing, as different combinations can result in varying costs.

Once the consumer has made their selections, the consumer platform sends a request to the provider platform. The purpose of this request is to validate the chosen offers and attributes against the provider's system.

The provider platform conducts the necessary validation checks to ensure the selected offers and attributes are accurate and permissible. If any discrepancies or changes are identified, the provider platform communicates this information back to the consumer.

Upon receiving the feedback from the provider platform, the consumer can review the changes and make any necessary adjustments or confirm the modified selections.

This internal workflow allows the consumer to have control and flexibility in selecting offers and attributes, while also ensuring that the provider's systems validate the choices for accuracy and feasibility.

```mermaid
sequenceDiagram
    Actor consumer
    participant consumer interface
    box E-Marketplace BB
    participant Quotation Management
    participant Inventory Management
    end
    consumer-->>consumer interface: select items <br/> from catalog
    consumer interface->>Quotation Management:request <br/> quote
    Quotation Management->>Inventory Management: check availability
    Inventory Management->>Quotation Management: return availability
    Quotation Management->>consumer interface:return quote <br/> with breakup
    consumer interface-->>consumer: view quote <br/> with breakup
```



### 9.3 Initializing an order by providing billing and fulfillment details

The consumer carefully reviews the contents of their cart, ensuring that everything selected is accurate and satisfactory. Once satisfied, the consumer initiates a checkout call, indicating their intention to proceed with the payment. This action finalizes the cart, preventing any further modifications.

The consumer platform then sends a request to the provider platform to initialize the payment process for the products or services in the cart. In response, the provider platform generates a payment link and presents the consumer with additional terms and conditions related to the payment.

The payment link serves as a gateway for the consumer to complete the transaction securely. It directs them to a designated payment page where they can input their payment information and finalize the purchase.

Alongside the payment link, the provider platform communicates any specific terms and conditions associated with the payment, ensuring that the consumer is aware of any applicable fees, refund policies, or other relevant details.



```mermaid
sequenceDiagram
    Actor consumer
    participant consumer interface
    box E-Marketplace BB
    participant Terms Management
    participant Inventory Management
    participant Quotation Management
    participant Fulfillment Management
    end
    consumer-->>consumer interface: provide billing <br/> and fulfillment details
    consumer interface->>Terms Management: initialize <br/> draft order
    Terms Management->>Inventory Management: check availability
    Inventory Management->>Terms Management: return availability
    Terms Management->>Inventory Management: lock inventory
    Inventory Management->>Terms Management: return inventory <br/> lock status
    Terms Management->>Quotation Management: fetch quote
    Quotation Management->>Terms Management: return quote
    Terms Management->>Fulfillment Management: check serviceability
    Fulfillment Management->>Terms Management: return serviceability <br/> with fulfillment charges
    Terms Management->>Terms Management: Construct draft order <br/> with Payment Terms, <br/> Cancellation Terms, <br/> Fulfillment Terms
    Terms Management->>consumer interface: return draft <br/> order with terms 
    consumer interface-->>consumer:view final order <br/> with checkout link

            

```

### 9.4 Confirming an Order

Once the consumer receives the payment link and reviews the terms and conditions, they proceed to make a payment. Upon a successful transaction, the consumer platform initiates a confirmation call to the provider platform. This call serves as a notification that the payment has been completed and confirms the order placement.

The provider platform acknowledges the confirmation call and responds with a success message. Along with the success message, the provider platform shares the details of the order that has been placed. These order details typically include information such as the order ID, items purchased, quantity, price, and any additional relevant data.

The consumer can then utilize the order details received from the provider platform to further check the status of their order. This information allows the consumer to track the progress of their order, anticipate the delivery, and stay informed about any updates or changes related to the order.



```mermaid
sequenceDiagram
user->>consumer interface: payment request
consumer interface-->>payment interface: payment
consumer interface-->>E-sign:request signed
consumer interface-->>Contract Creation and Management:create contract
Contract Creation and Management-->>E-sign:verify request
Contract Creation and Management-->>inventory:check inventory
Contract Creation and Management-->>fulfillment:check fulfillment
Contract Creation and Management-->>consumer interface:response with Order ID
consumer interface-->>E-sign:verify request
consumer interface->>user:response with Order ID
 

```

### 9.5 Checking the status of an order&#x20;

Once an order is confirmed, the user receives the details of the confirmed order, and they have the option to check the status of their order. The order status typically includes stages such as "placed," "packed," "dispatched," and so on. The "placed" status indicates that the order has been successfully received and recorded. The "packed" status signifies that the items in the order have been gathered and prepared for shipment. The "dispatched" status indicates that the package has been handed over to the delivery service for transportation.

#### 9.5.1 User explicitly requests for the fulfillment status of the order

```mermaid
sequenceDiagram
consumer->>consumer interface: order status
    consumer interface->>Contract Fulfillment:fetch order status
    Contract Fulfillment->>consumer interface: return current status of order
consumer interface->>consumer: return current status of order
```

#### 9.5.2 Provider updates the fulfillment status of an order

####

```mermaid
sequenceDiagram
    
Admin->>provider interface: requets update fulfillment status
provider interface->>Contract Fulfillment:Update fulfillment status
Contract Fulfillment->>provider interface:Update fulfillment status response
provider interface->>Admin:Fulfillment details updated
```

### 9.6 Tracking the fulfillment of an order

When a consumer places an order and it is confirmed, they are provided with the option to track the status of their order. This tracking feature allows the consumer to stay informed about the progress of their purchase. The order status typically encompasses various updates related to the delivery process, giving the consumer insights into the whereabouts and estimated arrival time of their package.

One of the primary aspects of the order status is the delivery status, which indicates whether the package has been dispatched from the seller's location or the warehouse. It confirms that the order is on its way to the consumer. This status assures the consumer that their purchase is in the process of being delivered.

#### 9.6.1 Tracking request

User can make a request to get the tracking status of an order.

```mermaid
sequenceDiagram
consumer->>consumer interface: request order tracking
    consumer interface->>Tracking:fetch order tracking status
Tracking->>consumer interface: return current tracking status of order
    consumer interface->>consumer: return current tracking status of order
    
```

#### 9.6.2 Update order track status

User can update the tracking  status of an order.



```mermaid
sequenceDiagram
    
Admin->>provider interface: request order tracking status
provider interface->>Tracking: Update tracking status
provider interface->>Admin:Tracking details updated
```

### 9.7 Cancelling an Order

When a consumer places an order and it is confirmed, they are provided with the option to cancel their order. This will allow user to cancel the order before receiving an order.



```mermaid
sequenceDiagram
consumer->>consumer interface: request order cancellation
    consumer interface->>order cancellation:order cancellation
    order cancellation-->>Order Tracking:update order status
    order cancellation-->>Order Fulfillment:update fulfillment status
    order cancellation-->>consumer interface: cancellation response
    consumer interface->>consumer:order cancellation response
```



### 9.8 Rating and Feedback Management

This allows user to rate any rate able entity in the system, it can be product, service, agent etc. User can also provide the detailed feedback of the entities.

#### 9.8.1 Rating and feedback by user

```mermaid
sequenceDiagram
consumer->>consumer interface: rating and feedback
    consumer interface->>Rating and Feedback Management:rating
Rating and Feedback Management->>consumer interface:rating response
     consumer interface->>consumer: rating acceptance message
```



#### 9.8.2 Rating and feedback by admin

###

```mermaid
sequenceDiagram
Admin->>provider interface: rating and feedback
    provider interface->>Rating and Feedback Management:rating
Rating and Feedback Management->>provider interface:rating response
     provider interface->>Admin: rating acceptance message
```

### 9.9 Support Management

User can make a request for the support, this can happen anytime during the lifecycle of an order.&#x20;



```mermaid
sequenceDiagram
consumer->>consumer interface: support request
    consumer interface->>Support Management:Support request
Support Management->>consumer interface:Support response
consumer interface->>consumer:Support response
    
```



### 9.10 Inventory Management

This enables user to manage inventory of the products also he can add or remove products from the inventory.



```mermaid
sequenceDiagram
    
UI->>provider interface: inventory
provider interface->>Inventory: inventory
Inventory->>provider interface: on_inventory
provider interface->>UI:inventory list
UI->>provider interface: select specific product
provider interface-->>Inventory: inventory_detail
Inventory-->>provider interface: on_inventory_detail
provider interface->>UI:Product detailed information

UI->>provider interface: product inventory modification request
provider interface-->>Inventory: request product inventory modification
Inventory-->>provider interface: response product inventory modification
provider interface->>UI:Product inventory update message
```

### 9.11 Catalog Management

This allow creation of a catalog for a product or a service based on the request made by the user. This allows user to update the catalogs of a product or service. New attributes can be added or removed from a catalog.

#### 9.11.1 User request for catalog

User while searching for products can request for the catalog of the product or the services, the platform will fetch and serve back user with the required catalog.



```mermaid
sequenceDiagram
UI->>consumer platform interface: catalog
    consumer platform interface->>provider platform interface: catalog
    provider platform interface->>Catalog:catalog
    provider platform interface->>consumer platform interface: on_catalog
    consumer platform interface->>UI: catalog Response
```

#### 9.11.2 User modifies catalog

User can modify the catalog of a product or service.



```mermaid
sequenceDiagram
    
UI->>provider interface: catalog
provider interface->>Catalog: catalog
Catalog->>provider interface: on_catalog


```

