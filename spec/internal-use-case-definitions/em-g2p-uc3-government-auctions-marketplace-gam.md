# EM-G2P-UC3-Government Auctions Marketplace (GAM)

## eM-G2P-UC3-Government Auctions Marketplace (GAM)

#### MKT-G2P-UC3-GAM-Government Auctions Marketplace

**Product Use Case Summary**

| ID      | MKT                             |
| ------- | ------------------------------- |
| Name    | Government Auctions Marketplace |
| Sector  | Government Marketplace          |
| Version | 1.0                             |
| Status  | Draft                           |

This use case streamlines the process of selling surplus government property, making it easier for both the government agency to dispose of property it no longer needs and generate revenue, and for buyers to find and purchase a property. This use case involves the process of a government agency identifying property it no longer needs and transferring it to a centralized platform for disposal. The property is listed on the platform and promoted to potential buyers. Interested registered buyers bid on the property and the highest bidder is awarded the property. Finally, the buyer then pays for and takes possession of the property. The use case steps are

1. **Identifying property** Government agency identifies the surplus property it no longer needs
2. **Transferring property** Government agency transfers the property to Surplus Property Management Office (SPMO)
3. **Listing property** Surplus Property Management Office lists the property on the Surplus Property Auctions marketplace
4. **Bidding on property** Registered bidders bid on the property
5. **Awarding property** The highest bidder is awarded the property
6. **Transfer of property** The buyer takes possession of the property

#### SDG Targets

**Target 8.2** Achieve higher levels of economic productivity through diversification, technological upgrading, and innovation, including through a focus on high-value-added and labour-intensive sectors.

**Target 12.5** By 2030, substantially reduce waste generation through prevention, reduction, recycling, and reuse.

#### Building Blocks

· Identification and authentication

· Content Management

· Information Mediator

· eMarketplace

· Digital registries

· Messaging

· Payment

**Future Building Blocks**

· Artificial Intelligence

· Mobility management

#### Steps

_**Step 1 - Identifying property**_

This step involves the government agency identifying the property that is no longer needed and can be sold to interested buyers. The Property could be any type of item or asset that the government agency has deemed as surplus and is looking to dispose of.

**Workflows**:

The workflows involved in this step:

* The Government Agency identifies surplus property that it no longer needs.
* The Property Officer conducts a physical inspection of the property and prepares a condition report.
* The Property Officer gets approvals from stakeholders within the government agency.
* The agency adds the property to its inventory of surplus property.

**Building Blocks for Workflows:**

* Identification and authentication
* Digital Registeries
* Content Management

**Example Implementation**

Go to G2P-UC3-GAM-S.1

_**Step 2 -**_**&#x20;Transferring property to Surplus Property Management Office**

The government agency that owns surplus property initiates the transfer of the property to the Surplus Property Management Office for disposal. This involves preparing the necessary documentation for the property and obtaining the required approvals.

**Workflows**:

The workflows involved in this step:

* Government agency makes the transfer by submitting the description of the property, its condition, and any other relevant details.
* The transfer will be reviewed and approved by the relevant stakeholders.
* Surplus Property Management Office takes possession of the property and responsibility for its sale.

**Building Blocks for Workflows:**

* Case Management.
* Content Management.
* Digital registries.
* Identification and authentication.



_**Step 3 -**_**&#x20;Listing property**

This step involves Surplus Property Management Office listing the Property on the Surplus Property Management Auctions marketplace, which is a platform for selling surplus and unneeded Gov. assets to the public. The website allows buyers to search for and bid on a wide range of Gov. assets, including Property, equipment, real estate, and more.

**Workflows**:

The workflows involved in this step:

* Surplus Property Management Office determines the appropriate listing category for the property based on its type, condition, and other relevant factors.
* Surplus Property Management Office sets a starting bid price and bidding period for the property.
* Surplus Property Management Office reviews bids as they come in and updates the listing to reflect the current high bid.

**Building Blocks for Workflows:**

* eMarketplace.
* Digital registries.
* Content Management.

**Example Implementation**

Go to G2P-UC3-GAM-S.3

_**Step 4 -**_**&#x20;Bidding on property**

This step involves the registered bidders submitting their bids on the property listed for sale by the Surplus Property Management Office on Auctions platform.

**Workflows**:

The workflows involved in this step:

* Bidders view the listing of the property on the Surplus Property Auctions marketplace.
* Bidders submit their bid amount and bidder information through the Surplus Property Auctions marketplace.
* Surplus Property Management Office receives and records the bid amounts and bidder information.
* The bidding period ends.
* Surplus Property Management Office reviews the bids and selects the highest bidder.

**Building Blocks for Workflows:**

* eMarketplace
* Authentication & Authorization

**Example Implementation**

Go to G2P-UC3-GAM-S.4

_**Step 5 -**_**&#x20;Awarding property**

The Surplus Property Management Office reviews the highest bid and selects the winning bidder to be awarded the property.

**Workflows**:

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

Go to G2P-UC3-GAM-S.5

_**Step 6 -**_**&#x20;Transfer of property**

This step involves the highest bidder paying for the property they have won in the auction and taking possession of it from the seller, in this case, the Surplus Property Management Office. It includes the payment validation and transfer of ownership to the buyer.

**Workflows**:

The workflows involved in this step:

* The Surplus Property Management Office confirms receipt of payment and prepares the necessary transfer of ownership and registration documents
* The buyer and Surplus Property Management Office coordinate the transfer of the property, including pickup or delivery arrangements
* The Surplus Property Management Office transfers ownership and registration documents to the buyer, completing the transaction.

**Building Blocks for Workflows:**

* Payment
* eMarketplace

**Example Implementation**

## G2P-UC3-GAM-S.1

| ID                 | G2P-UC3-GAM-S.1                                                                                                                                                                                                                                                                                                                                                                      |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Use Case Step      | Identifying property                                                                                                                                                                                                                                                                                                                                                                 |
| Preconditions      | <ul><li>The Government agency must have surplus property that it no longer needs.</li><li>The government agency has identified surplus property that it no longer needs.</li></ul>                                                                                                                                                                                                   |
| Data Inputs        | <ul><li>Description of the property</li><li>Property condition report</li><li>Supporting documentation, such as registration, title, and other certificates</li><li>Identification of the Government agency that owns the property.</li></ul>                                                                                                                                        |
| Actors             | <ul><li>Government Agency: Initiates the process of identifying surplus property that is no longer needed.</li><li>Property Officer: Conducts a physical inspection of the property and prepares a condition report.</li><li>Surplus Property Auctions marketplace.</li></ul>                                                                                                        |
| Normal Course      | <ol><li>1.The Government Agency identifies surplus property that it no longer needs.</li><li>2.The Property Officer conducts a physical inspection of the property and prepares a condition report.</li><li>3.The Property Officer gets approvals from stakeholders within government agency.</li><li>4.The agency adds the property to its inventory of surplus property.</li></ol> |
| Alternative Course | If the property is not suitable for sale on the Surplus Property Auctions marketplace, it may be disposed of through other means, such as recycling, donation, or destruction.                                                                                                                                                                                                       |
| Data Output        | Information about the identified surplus property is added to the government agency's inventory.                                                                                                                                                                                                                                                                                     |
| Post-Conditions    | The surplus property has been successfully identified, inspected, and ready for transfer to the Surplus Property Management Office for listing on the Surplus Property Auctions marketplace.                                                                                                                                                                                         |
| Exceptions         | NA                                                                                                                                                                                                                                                                                                                                                                                   |
| Related BBs        | <ul><li>Identification and authentication</li><li>Digital registries</li><li>Content Management</li></ul>                                                                                                                                                                                                                                                                            |
| Sequence Diagram   | Surplus Property Identification Process​`Government Agency->Property Officer: Identify surplus property Property Officer->Property Officer: Conduct physical inspection and prepare condition report Property Officer->Government Agency: Get approvals from stakeholders Government Agency->Government Agency: Add property to inventory of surplus property`                       |

![](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FPUIGDILlDRSOB6K47k6e%2Fuploads%2FPs03umrTGr2kKZAChFog%2FScreen%20Shot%202023-03-29%20at%207.24.49%20AM.png?alt=media\&token=63ce324e-fbb9-466e-abc6-cf33ffe6a788)\


## G2P-UC3-GAM-S.2

| ID                 | G2P-UC3-GAM-S.2                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Use Case Step      | Transferring property                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Preconditions      | <ul><li>The Government Agency has identified surplus property that it wishes to transfer to the Surplus Property Management Office.</li><li>Approval from relevant stakeholders within the Government Agency for the transfer.</li></ul>                                                                                                                                                                                                                                                                                                                                                                                  |
| Data inputs        | <p>Details of the surplus property to be transferred, including</p><ul><li>Description</li><li>Condition report</li><li>Inventory number</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Actors             | <ul><li>Government Agency: Initiates the process of transferring surplus property to the Surplus Property Management Office.</li><li>Surplus Property Management Office: Receives surplus property from the Government Agency.</li></ul>                                                                                                                                                                                                                                                                                                                                                                                  |
| Normal Course      | <ol><li>1.The Government Agency initiates the transfer process and provides details of the surplus property to the Surplus Property Management Office.</li><li>2.The Surplus Property Management Office verifies that it is willing and able to accept the property.</li><li>3.The Government Agency provides approval for the transfer from relevant stakeholders within the organization.</li><li>4.The Surplus Property Management Office takes possession of the property and updates its inventory to reflect the new acquisition.</li></ol>                                                                         |
| Alternative Course | <ul><li>If the Property does not meet the transfer requirements, the Surplus Property Management Office rejects the transfer and sends the Property back to the government agency.</li><li>If the transfer document is incomplete or contains errors, the government agency must correct them and resubmit the transfer document.</li><li>If the Surplus Property Management Office is unable to accept the property, the Government Agency may need to identify an alternative recipient.</li></ul>                                                                                                                      |
| Data output        | <ul><li>Legal ownership of the Property is transferred from the government agency to the Surplus Property Management Office.</li><li>The Surplus Property Management Office updates its inventory to reflect the new acquisition.</li><li>The Property's status is updated in the centralized database.</li></ul>                                                                                                                                                                                                                                                                                                         |
| Post-Conditions    | <ul><li>The government agency has successfully transferred the Property to the Surplus Property Management Office.</li><li>The Surplus Property Management Office assumes responsibility for the Property's sale.</li><li>Legal ownership of the Property is transferred from the government agency to the Surplus Property Management Office.</li></ul>                                                                                                                                                                                                                                                                  |
| Exceptions         | <ul><li>The Surplus Property Management Office is unable to accept the property.</li><li>The property is found to be in unacceptable condition.</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Related BBs        | <ul><li>Identification and authentication.</li><li>Digital registries.</li><li>Content Management.</li><li>Case Management.</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Sequence Diagram   | title Transferring Property​`Government Agency->Surplus Property Management Office: Initiate transfer and provide property details Surplus Property Management Office->Government Agency: Verify willingness and ability to accept property Government Agency->Government Agency: Obtain approval from relevant stakeholders Government Agency->Surplus Property Management Office: Provide approval for transfer Surplus Property Management Office->Government Agency: Take possession of property Surplus Property Management Office->Surplus Property Management Office: Update inventory to reflect new acquisition` |

​![](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FPUIGDILlDRSOB6K47k6e%2Fuploads%2FaIO1C19QbJ0EZamaloft%2FScreen%20Shot%202023-03-29%20at%207.46.17%20AM.png?alt=media\&token=879f3d87-8dfd-4b52-9384-1ba108659eab)\


## G2P-UC3-GAM-S.3

| ID                 | G2P-UC3-GAM-S.3                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Use Case Step      | Listing property                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Preconditions      | <ul><li>The property must have been successfully transferred to the Surplus Property Management Office.</li><li>The property must have been inspected and evaluated for condition by the Property Officer.</li></ul>                                                                                                                                                                                                                                                                                                                            |
| Data inputs        | <ul><li>Property information and details (e.g. description, condition, images).</li><li>Property images or videos for showcasing the property</li><li>Property Officer's Inspection report</li></ul>                                                                                                                                                                                                                                                                                                                                            |
| Actors             | <ul><li>Surplus Property Management Office</li><li>Property Officer</li><li>Surplus Property Auctions marketplace.</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Normal Course      | <ol><li>1.Surplus Property Management Office receives the property from the government agency.</li><li>2.The Surplus Property Management Office adds the property to its inventory of available surplus property.</li><li>3.The Surplus Property Management Office creates a listing of the property on the Surplus Property Auctions marketplace, including the property details and any images or videos provided.</li><li>4.Surplus Property Management Office publishes the listing to the Surplus Property Auctions marketplace.</li></ol> |
| Alternative Course | If the property does not meet the criteria for listing on the Surplus Property Auctions marketplace, the property may be disposed of through other means (e.g. donated, recycled, or scrapped).                                                                                                                                                                                                                                                                                                                                                 |
| Data output        | Property listing on the Surplus Property Auctions marketplace.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Post-Conditions    | Property is listed for auction on the Surplus Property Auctions marketplace.                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Exceptions         | <ul><li>The property does not meet the criteria for listing on the Surplus Property Auctions marketplace.</li><li>Technical errors or system issues prevent the creation of the property listing</li></ul>                                                                                                                                                                                                                                                                                                                                      |
| Related BBs        | <ul><li>eMarketplace.</li><li>Digital registries.</li><li>Content Management.</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Sequence Diagram   | title Surplus Property Listing​`Government Agency->Surplus Property Management Office: Transfer property Surplus Property Management Office->Surplus Property Management Office: Add property to inventory Surplus Property Management Office->Surplus Property Management Office: Create property listing Surplus Property Management Office->Surplus Property Auctions marketplace: Publish listing`                                                                                                                                          |

​![](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FPUIGDILlDRSOB6K47k6e%2Fuploads%2Fw8pgTUnVmSFWqGnf27jo%2FScreen%20Shot%202023-03-29%20at%207.59.43%20AM.png?alt=media\&token=0f6b51d5-f914-4e90-acd1-82d43bdb7e90)\


## G2P-UC3-GAM-S.4

| ID                 | G2P-UC3-GAM-S.4                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Use Case Step      | Bidding on property                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Preconditions      | <ul><li>The property has been listed on the Surplus Property Auctions marketplace.</li><li>Bidders are registered and authenticated on the Surplus Property Auctions marketplace.</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                               |
| Data inputs        | <ul><li>Bid amount</li><li>Bidder information</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Actors             | <ul><li>Bidders</li><li>Surplus Property Management Office</li><li>Surplus Property Auctions marketplace</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Normal Course      | <ol><li>1.Bidders view the listing of the property on the Surplus Property Auctions marketplace.</li><li>2.Bidders submit their bid amount and bidder information through the Surplus Property Auctions marketplace.</li><li>3.Surplus Property Management Office receives and records the bid amounts and bidder information.</li><li>4.The bidding period ends.</li><li>5.Surplus Property Management Office reviews the bids and selects the highest bidder.</li></ol>                                                                                                                                 |
| Alternative Course | If there are no bids, the Surplus Property Management Office may choose to re-list the property for auction.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Data output        | <ul><li>Winning bid amount</li><li>Bidder information</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Post-Conditions    | The highest bidder is identified and notified of their win.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Exceptions         | <ul><li>Invalid bid amount or information is submitted.</li><li>Technical issues with the Surplus Property Auctions marketplace.</li><li>Other unforeseen issues that prevent the auction from being completed.</li></ul>                                                                                                                                                                                                                                                                                                                                                                                 |
| Related BBs        | <ul><li>Authentication &#x26; Authorization</li><li>eMarketplace</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Sequence Diagram   | title Bidding on Property`Bidders->Surplus Property Auctions: View property listing Surplus Property Auctions->Bidders: Display property listingBidders->Surplus Property Auctions: Submit bid and bidder information Surplus Property Auctions->Surplus Property Management Office: Record bid and bidder information Note right of Surplus Property Management Office: Bidding period ends Surplus Property Management Office->Surplus Property Auctions: Provide bid results Surplus Property Auctions->Bidders: Display bid resultsSurplus Property Management Office->Bid Winner: Notify bid winner` |

![](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FPUIGDILlDRSOB6K47k6e%2Fuploads%2FlDfENk6ycmema5RThGXX%2FScreen%20Shot%202023-03-29%20at%208.13.44%20AM.png?alt=media\&token=ef681c31-6f71-4c93-b928-97325c5b80c2)\


## G2P-UC3-GAM-S.5

| ID                 | G2P-UC3-GAM-S.5                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Use Case Step      | Awarding property                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Preconditions      | <ul><li>The property has been listed on the Surplus Property Auctions marketplace.</li><li>Registered bidders have placed bids on the property.</li><li>There is at least one bidder for the property.</li><li>The bidding period has ended.</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Data inputs        | <ul><li>Bid information for all bidders.</li><li>Property information.</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Actors             | <ul><li>Surplus Property Management Office</li><li>Surplus Property Auctions marketplace</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Normal Course      | <ol><li>1.Surplus Property Management Office reviews the bids and selects the highest bidder.</li><li>2.Surplus Property Management Office sends a notification to the highest bidder that their bid has been accepted and requests payment and transfer of the property.</li><li>3.The highest bidder confirms acceptance of the bid and provides payment and transfer details to the Surplus Property Management Office.</li><li>4.Surplus Property Management Office verifies the payment and transfer details and authorizes the transfer of the property to the highest bidder.</li><li>5.Surplus Property Management Office updates its inventory to reflect the transfer of the property.</li></ol> |
| Alternative Course | If the highest bidder fails to provide payment or transfer details within a specified timeframe, the Surplus Property Management Office may select the next highest bidder.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Data output        | <ul><li>Notification to the highest bidder that their bid has been accepted.</li><li>Authorization for the transfer of the property.</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Post-Conditions    | <ul><li>The property has been transferred to the highest bidder.</li><li>Payment has been received by the Surplus Property Management Office.</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Exceptions         | <ul><li>The highest bidder fails to provide payment or transfer details.</li><li>The highest bidder provides incorrect payment or transfer details.</li><li>The property is damaged or not as described in the listing.</li><li>The Surplus Property Management Office is unable to transfer the property to the highest bidder for legal or other reasons.</li></ul>                                                                                                                                                                                                                                                                                                                                      |
| Related BBs        | <ul><li>Messaging</li><li>eMarketplace</li><li>Payment</li><li>Notifications</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Sequence Diagram   | title Awarding Property​`Surplus Property Management Office -> Surplus Property Management Office: Review Bids\nSelect Highest Bidder Surplus Property Management Office -> Highest Bidder: Send Notification\nRequest Payment & Transfer Details Highest Bidder -> Surplus Property Management Office: Confirm Bid\nProvide Payment & Transfer Details Surplus Property Management Office -> Surplus Property Management Office: Verify Payment & Transfer Details\nAuthorize Transfer of Property Surplus Property Management Office -> Surplus Property Management Office: Update Inventory`                                                                                                            |

![](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FPUIGDILlDRSOB6K47k6e%2Fuploads%2F5M2VW5J5PSBxlkiu4fYp%2FScreen%20Shot%202023-03-29%20at%208.24.47%20AM.png?alt=media\&token=28b07e63-991f-4146-b69a-7d377937cf4f)\


## G2P-UC3-GAM-S.6

| ID                 | G2P-UC3-GAM-S.6                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Use Case Step      | Transfer of property                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Preconditions      | <ul><li>The Surplus Property Management Office has selected the highest bidder and sent a notification to them.</li><li>The highest bidder has confirmed their acceptance of the bid and provided payment and transfer details.</li></ul>                                                                                                                                                                                                                                                                                                                           |
| Data inputs        | <ul><li>Payment details (e.g. payment method, amount, transaction ID)</li><li>Transfer details (e.g. shipping address, tracking information)</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                              |
| Actors             | <ul><li>Surplus Property Management Office</li><li>Highest bidder</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Normal Course      | <ol><li>1.The highest bidder provides payment and transfer details to the Surplus Property Management Office.</li><li>2.The Surplus Property Management Office verifies the payment and transfer details.</li><li>3.The Surplus Property Management Office authorizes the transfer of the property to the highest bidder.</li><li>4.The Surplus Property Management Office updates its inventory to reflect the transfer of the property.</li><li>5.The Surplus Property Management Office confirms the transfer of the property with the highest bidder.</li></ol> |
| Alternative Course | If the payment or transfer details provided by the highest bidder are not valid, the Surplus Property Management Office may request corrected information or cancel the transaction.                                                                                                                                                                                                                                                                                                                                                                                |
| Data output        | <ul><li>Confirmation of payment and transfer details</li><li>Confirmation of the transfer of the property</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Post-Conditions    | <ul><li>The highest bidder has paid for and received the property.</li><li>The Surplus Property Management Office has updated its inventory to reflect the transfer of the property.</li></ul>                                                                                                                                                                                                                                                                                                                                                                      |
| Exceptions         | <ul><li>Invalid payment or transfer details provided by the highest bidder.</li><li>Errors or delays in the payment or transfer process.</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Related BBs        | <ul><li>Payment</li><li>eMarketplace</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Sequence Diagram   | title Transfer of Property​`Highest Bidder->Surplus Property Management Office: Provides payment and transfer details Surplus Property Management Office->Highest Bidder: Verifies payment and transfer details Surplus Property Management Office->Highest Bidder: Authorizes transfer of property Surplus Property Management Office->Surplus Property Management Office: Updates inventory Surplus Property Management Office->Highest Bidder: Confirms transfer of propert`y                                                                                    |

![](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FPUIGDILlDRSOB6K47k6e%2Fuploads%2FdFdMmPK9Kh79f4WmnrTt%2FScreen%20Shot%202023-03-29%20at%208.35.12%20AM.png?alt=media\&token=763b143e-bb1f-4308-9ec2-a16305c83e9e)\


