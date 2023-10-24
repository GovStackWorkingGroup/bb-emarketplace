---
description: This section provides the context of the building block.
---

# 2 Description

Governments are involved, directly or indirectly, in the procurement of various goods and services (e.g. computers (goods) for their employees, and technical services for various projects to be implemented for the public welfare. E-marketplace Building Block enables the trade of products and/or services via electronic media where at least one of the transacting parties taking part in the transaction is the government (either as the procurer or the provider) and the other party(ies) can be either providers or consumers of such goods and services (respectively).&#x20;

The government eMarketplace facilitates transparency by creating equal opportunities for all the stakeholders (suppliers and consumers) and thus creates an efficient market for goods and services. It helps build new relationships and thus builds trust. The buyer gains more insights into price information from different suppliers and is empowered to make rational decision-making. The sellers can optimize the sales/marketing costs and can improve their product range/portfolio by observing the demand in their domains thus multiply their market options even in international markets. The digital facility reduces time constraints for both parties.

This document allows (provides guidance on creating) an e-marketplace digital public infrastructure to be created by connecting a set of interacting (services) microservices. In the context of government, the government can itself act as a supplier (in case of transferring money to citizens i.e. G2P) and also can demand goods and services from other public entities (departmental transfers i.e. G2G) and private entities (purchasing computers/technical/advisory services i.e. business to government (B2G)). This infrastructure is fundamentally decentralized or federated, although all the services can exist on a single cloud. This specification does not assume any specific implementation architecture or technology. Instead, it defines the actors and the interfaces that need to be implemented by the transacting entities. The current document focuses on enabling basic functionalities such as supplier/buyer registration, listing a catalog of goods and services, and initiating a cycle of activities once a user selects a service. The document has not focused on payments/financial transactions between any two entities.

The eMarketplace Building Block could be useful in a variety of applications in different sectors for example,

**Government procurement of goods and services (B2G)**

* In the Health Sector, procurement of supplies to government hospitals&#x20;
* In the Civil infrastructure sector, procurement of engineering services such as the construction of dams, buildings, computers, etc.
* In the transportation sector procurement of vehicles and associated maintenance services

**Government providing goods and services (G2B)**

* In the Social Security sector, cash/subsidy support services of government to eligible citizens
* In the health sector, supply of nutrition and medicine to homes of patients/ pregnant mothers&#x20;
* In the education sector government providing free learning materials to students

## 2.1 **Current scope**

While there may be many such use cases, within the current scope The functional requirements to cover the services required from the eMarketplace Building Block currently have considered specific use cases of&#x20;

**Business to Government (B2G)**

1. [B2G-Use Case 1: Ministry of Justice - HMPPS Data & Reporting platform](https://app.gitbook.com/o/pxmRWOPoaU8fUAbbcrus/s/PUIGDILlDRSOB6K47k6e/\~/changes/4/b2g-uc1-moj-hpmms-data-and-reporting-platform)
2. [B2G-Use Case 2: Procurement of Sporting Goods by a registered sporting authority](https://app.gitbook.com/o/pxmRWOPoaU8fUAbbcrus/s/PUIGDILlDRSOB6K47k6e/\~/changes/4/mkt-b2g-uc2-sgp-sporting-goods-procurement)

**Government to People (G2P)**

1. [G2P-Use Case 2: Online Reservation System (ORS)](https://app.gitbook.com/o/pxmRWOPoaU8fUAbbcrus/s/PUIGDILlDRSOB6K47k6e/\~/changes/4/g2p-uc2-online-reservation-system-ors)
2. [G2P-Use Case 3: Government Auctions Marketplace (GAM)](broken-reference)

These use cases have business processes with several steps, wherein specific steps that involve the e-Marketplace Building Block services were studied as example implementations (such as registration, identification, and verification of individual entities and users in various roles; publishing a catalog of goods and services provided by various entities; selection of goods and services and provider entities; scheduling the life cycle events in procurement such as creation of purchase requisition, bid management, vendor assessment, awarding contract, monitoring contractors' deliverables,  outreach communication and messaging notifications about status of procurement/payment, etc.&#x20;

Currently, the following actors have been identified as "users" of the eMarketplace Building Block:

* "Supplier" is who manages the Building Block's implementation settings. A Building Block admin is also responsible for the enrolment of entitles and Organizers of those entities that use the eMarketplace Building Block. The Admins interact with the list of goods and services, the cycle of procurement activities, and communication management.
* "Buyers" are those who participate in events to perform various activities. Buyers MUST be registered in the eMarketplace Building Block before they can be enrolled in events. Resources MAY apply/respond to multiple goods and services in a catalog. Hence a registered buyer SHOULD be able to offer services in parallel if they are short-listed by the Supplier.
* "Subscribers" who participate in events to consume various activities. Subscribers must be registered in the eMarketplace before they can be enrolled in activities. Subscribers MAY be enrolled in multiple events and MAY be passive to suppliers' requests.
* "Internal team member" who participates in internal activities such as technical and financial evaluation of the bids received on the buyer side; preparation of documents and coordination across business development, technical, and managerial teams on the supplier side. The corresponding "internal team member" communicates with the "supplier" or "buyer", respectively.



\
\


