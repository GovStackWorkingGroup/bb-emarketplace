# eM-G2P-UC3-Government Auctions Marketplace (GAM)

### MKT-G2P-UC3-GAM-Government Auctions Marketplace

#### Product Use Case Summary <a href="#product-use-case-summary" id="product-use-case-summary"></a>

| ID      | MKT                             |
| ------- | ------------------------------- |
| Name    | Government Auctions Marketplace |
| Sector  | Government Marketplace          |
| Version | 1.0                             |
| Status  | Draft                           |

This use case streamlines the process of selling surplus government property, making it easier for both the government agency to dispose of property it no longer needs and generate revenue, and for buyers to find and purchase a property. This use case involves the process of a government agency identifying property it no longer needs and transferring it to a centralized platform for disposal. The property is listed on the platform and promoted to potential buyers. Interested registered buyers bid on the property and the highest bidder is awarded the property. Finally, the buyer then pays for and takes possession of the property. The use case steps are &#x20;

1. **Identifying property** Government agency identifies the surplus property it no longer needs
2. **Transferring property** Government agency transfers the property to Surplus Property Management Office (SPMO)&#x20;
3. **Listing property** Surplus Property Management Office lists the property on the Surplus Property Auctions marketplace&#x20;
4. **Bidding on property** Registered bidders bid on the property
5. **Awarding property** The highest bidder is awarded the property
6. **Transfer of property** The buyer takes possession of the property

### SDG Targets&#x20;

**Target 8.2** Achieve higher levels of economic productivity through diversification, technological upgrading, and innovation, including through a focus on high-value-added and labour-intensive sectors.

**Target 12.5** By 2030, substantially reduce waste generation through prevention, reduction, recycling, and reuse.&#x20;

### Building Blocks&#x20;

·      Identification and authentication

·      Content Management

·      Information Mediator

·      eMarketplace

·      Digital registries

·      Messaging&#x20;

·      Payment

**Future Building Blocks**&#x20;

·      Artificial Intelligence

·      Mobility management

### Steps&#x20;

#### _Step 1 - **Identifying property**_

This step involves the government agency identifying the property that is no longer needed and can be sold to interested buyers. The Property could be any type of item or asset that the government agency has deemed as surplus and is looking to dispose of.

**Workflows**:&#x20;

The workflows involved in this step:

* The Government Agency identifies surplus property that it no longer needs.
* The Property Officer conducts a physical inspection of the property and prepares a condition report.
* The Property Officer gets approvals from stakeholders within the government agency.
* The agency adds the property to its inventory of surplus property.

**Building Blocks for Workflows:**

* Identification and authentication&#x20;
* Digital Registeries&#x20;
* Content Management&#x20;

**Example Implementation**

Go to [G2P-UC3-GAM-S.1](g2p-uc3-gam-s.1.md)



#### _Step 2 -_ Transferring property to Surplus Property Management Office

The government agency that owns surplus property initiates the transfer of the property to the Surplus Property Management Office for disposal. This involves preparing the necessary documentation for the property and obtaining the required approvals.

**Workflows**:&#x20;

The workflows involved in this step:

* Government agency makes the transfer by submitting the description of the property, its condition, and any other relevant details.&#x20;
* The transfer will be reviewed and approved by the relevant stakeholders.&#x20;
* Surplus Property Management Office takes possession of the property and responsibility for its sale.&#x20;

**Building Blocks for Workflows:**

* Case Management.
* Content Management.
* Digital registries.
* Identification and authentication.

**Example Implementation**

Go to [G2P-UC3-GAM-S.2](g2p-uc3-gam-s.2.md)



#### _Step 3 -_ Listing property

This step involves Surplus Property Management Office listing the Property on the Surplus Property Management Auctions marketplace, which is a platform for selling surplus and unneeded Gov. assets to the public. The website allows buyers to search for and bid on a wide range of Gov. assets, including Property, equipment, real estate, and more.

**Workflows**:&#x20;

The workflows involved in this step:

* Surplus Property Management Office determines the appropriate listing category for the property based on its type, condition, and other relevant factors.
* Surplus Property Management Office sets a starting bid price and bidding period for the property.
* Surplus Property Management Office reviews bids as they come in and updates the listing to reflect the current high bid.

**Building Blocks for Workflows:**

* eMarketplace.
* Digital registries.
* Content Management.

**Example Implementation**

Go to [G2P-UC3-GAM-S.3](g2p-uc3-gam-s.3.md)



#### _Step 4 -_ **Bidding on property**

This step involves the registered bidders submitting their bids on the property listed for sale by the Surplus Property Management Office on Auctions platform.

**Workflows**:&#x20;

The workflows involved in this step:

* Bidders view the listing of the property on the Surplus Property Auctions marketplace.
* Bidders submit their bid amount and bidder information through the Surplus Property Auctions marketplace.
* Surplus Property Management Office receives and records the bid amounts and bidder information.
* The bidding period ends.
* Surplus Property Management Office reviews the bids and selects the highest bidder.

**Building Blocks for Workflows:**

* eMarketplace
* Authentication & Authorization&#x20;

**Example Implementation**

Go to [G2P-UC3-GAM-S.4](g2p-uc3-gam-s.4.md)



#### _Step 5 -_ **Awarding property**

The Surplus Property Management Office reviews the highest bid and selects the winning bidder to be awarded the property.

**Workflows**:&#x20;

The workflows involved in this step:

* Surplus Property Management Office updates its inventory to reflect the transfer of the property.
* Surplus Property Management Office verifies the payment and transfer details and authorizes the transfer of the property to the highest bidder.
* The highest bidder confirms acceptance of the bid and provides payment and transfer details to the Surplus Property Management Office.
* Surplus Property Management Office sends a notification to the highest bidder that their bid has been accepted and requests payment and transfer of the property.
* Surplus Property Management Office reviews the bids and selects the highest bidder.

**Building Blocks for Workflows:**

* Notifications
* Payment
* eMarketplace
* Messaging

**Example Implementation**

Go to [G2P-UC3-GAM-S.5](g2p-uc3-gam-s.5.md)



#### _Step 6 -_ **Transfer of property**

This step involves the highest bidder paying for the property they have won in the auction and taking possession of it from the seller, in this case, the Surplus Property Management Office. It includes the payment validation and transfer of ownership to the buyer.

**Workflows**:&#x20;

The workflows involved in this step:

* The Surplus Property Management Office confirms receipt of payment and prepares the necessary transfer of ownership and registration documents
* The buyer and Surplus Property Management Office coordinate the transfer of the property, including pickup or delivery arrangements
* The Surplus Property Management Office transfers ownership and registration documents to the buyer, completing the transaction.

**Building Blocks for Workflows:**

* Payment
* eMarketplace

**Example Implementation**

Go to [G2P-UC3-GAM-S.6](g2p-uc3-gam-s.6.md)
