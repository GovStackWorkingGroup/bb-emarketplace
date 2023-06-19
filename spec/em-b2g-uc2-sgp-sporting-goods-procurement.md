# eM-B2G-UC2-SGP-Sporting Goods Procurement

### Product use case summary

| ID       | MKT                         |
| -------- | --------------------------- |
| Name     | Sporting Goods Procurement  |
| Sector   | Government Marketplace      |
| Version  | 1.0                         |
| Status   | Draft                       |

This use case explains the procurement of sporting goods / equipment. The buyer is a registered government sporting authority. The seller is any eligible seller of sporting goods / equipment. Both the buyer and seller are registered as per the rules defined in the eMarketplace. For sake of simplicity, the eMarketplace is this use case is called as Government eMarketplace i.e. GEM. Once a seller is registered in GEM, it should publish its catalogue so that buyers are able to find the items they are searching for. The process of procurement involves 3 steps.&#x20;

1. Create purchase requisition (PReq) - Buyer creates a PReq
2. Apply for purchase requisition (PReq) - Seller applies to participate in the PReq process
3. Award purchase requisition (PReq) - Buyer awards a purchase contract to a Seller

&#x20;The actual delivery of the items is out of scope of this use case.

### SGD targets&#x20;

**Target 8.2** Achieve higher levels of economic productivity through diversification, technological upgrading, and innovation, including through a focus on high-value-added and labour-intensive sectors.

**Target 12.9** Support developing countries to strengthen their scientific and technological capacity to move towards more sustainable patterns of consumption and production.

### Building blocks

* Registration
* Digital registries
* Identification and authentication
* Content Management
* Information Mediator
* eMarketplace
* Messaging&#x20;
* Payment

### Steps&#x20;

\
The preconditions for executing a PReq are as follows&#x20;

### Register a buyer&#x20;

1. Buyer submits registration information in the government portal
2. Buyer is evaluated (online or offline)&#x20;
3. Buyer is approved&#x20;
4. Buyer receives notification for approval&#x20;

### Register a seller&#x20;

1. Seller provides mandatory information on on the government portal
2. Seller is evaluated (online or offline)&#x20;
3. Seller is approved (authorised seller)&#x20;
4. Seller receives notification for approval&#x20;

### Publish catalogue (by seller)&#x20;

1. Seller logs in to the government portal&#x20;
2. Seller uploads catalogue of products and/or services&#x20;
3. Seller’s catalogue is evaluated
4. Seller catalogue is published on the government portal

Once the preconditions are completed, a PReq can be created in the system. Listed below are the steps for creating a PReq leading to awarding of a purchase contract to the seller.

### Step 1 - Create purchase requisition (PReq)

This step involves a formal request (broadcast of intent) by the sporting authority for the procurement of sporting goods. Here the sporting authority is the buyer and Seller is anybody who is registered in the government portal, usually a seller of sports goods.&#x20;

#### Workflows

The workflows involved in this step are&#x20;

1. The sporting authority (Buyer) representative logs in to the government portal.&#x20;
2. Buyer searches for the sports goods (cricket kit)
3. Buyer views catalogue of matching products&#x20;
4. Buyer selects the products that matches the requirements
5. Buyer provides the quantity required&#x20;
6. Buyer provides the shipping / delivery location
7. Buyer provides the preferred vendor or a list of approved vendors
8. Buyer selected the option to create a requisition.
9. Buyer creates PReq and submits it for internal approvals.&#x20;

&#x20;The sporting authority seeks internal approval before the requisition is published for response.

#### Building Blocks for Workflows

* Identity&#x20;
* Search&#x20;

#### Functional Blocks for Workflows&#x20;

* Catalogue&#x20;
* Cart
* Fulfilment
* Quotation&#x20;

Example Implementation

[G2P-UC2-SGP-S1](https://docs.google.com/document/d/1-s7IytSA296wYaKLjuy5YYLujT\_beEujUxjm6zwAALc/edit#heading=h.xj29cp8qv3rv)&#x20;

### Step 2 - Apply for purchase requisition (PReq)

This step involves a Seller responding to the PReq through the government portal. The Seller is expected to respond in line with the terms and conditions of the PReq.&#x20;

#### Workflows

The workflows involved in this step are&#x20;

1. Seller logs in to the government portal.&#x20;
2. Seller views the list of open PReqs&#x20;
3. Seller offers a quote for the PReq
4. Seller is asked to authenticate
5. Seller submits the quote&#x20;

#### Building Blocks for Workflows

* Identity&#x20;
* Search&#x20;

#### Functional Blocks for Workflows&#x20;

* Quotation&#x20;

Example Implementation

[G2P-UC2-SGP-S2](https://docs.google.com/document/d/1-s7IytSA296wYaKLjuy5YYLujT\_beEujUxjm6zwAALc/edit#heading=h.6bqb282jxot1)&#x20;

### Step 3 - Award purchase requisition (PReq)

This step involves the Buyers evaluating all the responses from the interested Sellers and awarding a purchase contract to a selected Seller. The Buyers, in order to optimise the purchase contract, may engage in several iterations of negotiations.&#x20;

#### Workflows

The workflows involved in this step are&#x20;

1. Buyer logs in to the government portal.&#x20;
2. Buyer views the list of quotations from the Sellers
3. Buyer is asked to authenticate before viewing the offer price
4. Buyer reviews the offer quotes and terms & conditions
5. Buyer creates preliminary purchase order for one or more offers&#x20;
6. Buyer provides payment details&#x20;
7. Buyer prints final purchase order (or contract) document &#x20;
8. Buyer is asked to authenticate before the final print&#x20;
9. Buyer confirms the purchase order to Seller&#x20;
10. Seller receives notification

#### Building Blocks for Workflows

* Identity&#x20;
* Payment&#x20;

#### Functional Blocks for Workflows&#x20;

* Quotation
* Order&#x20;

Example Implementation

[G2P-UC2-SGP-S3 ](https://docs.google.com/document/d/1-s7IytSA296wYaKLjuy5YYLujT\_beEujUxjm6zwAALc/edit#heading=h.9e05fii8of6c)

\
\
