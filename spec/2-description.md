---
description: This section provides the context of the building block.
---

# 2 Description

{% hint style="success" %}
Set the context of the Building Block for the reader. The description should not assume that the reader has any experience of the GovStack system other than that found on the GovStack website.
{% endhint %}

<mark style="color:blue;">Governments involve, directly or indirectly, in the procurement of various goods and services (e.g.  computers (goods) for its employees, and technical services for various projects to be implemented for the public welfare.</mark> E-marketplaces building block enables trade of products and/or services via electronic media where at least one of the transacting parties taking part in the transaction is the government (either as the procurer or the provider) and the other party(s) can be either providers or consumers of such goods and services (respectively).&#x20;

<mark style="color:blue;">The government eMarketplace facilitates transparency by creating equal opportunities for all the stakeholders (suppliers and consumers); and thus creates efficient market for goods and services. It helps building new relationships thus builds trust. The buyer gains more insights on price information from different suppliers and is empowered to make rational decision making. The sellers can optimize the sales/marketing costs and can also improve their product range/portfolio by observing the demand in their domains thus multiply their market options even in international markets. The digital facility reduces time constraints for both the parties.</mark>

This document allows <mark style="color:blue;">(provides guidance on creating)</mark> an e-marketplace digital public infrastructure to be created by connecting a set of interacting <mark style="color:blue;">(services)</mark> microservices. <mark style="color:blue;">In the context of government, the government can itself act as a supplier (in case of transferring moey to citizens i.e. G2P) and also can demand goods and services from other public entities (departmental transfers i.e. G2G) and private entities (puchasing computers/technical/advisory services i.e. business to government (B2G)).</mark> This infrastructure is fundamentally decentralized or federated, although all the services can exist on a single cloud. This specification does NOT assume any specific implementation architecture or technology. Rather, it defines the actors and the interfaces that need to be implemented by the transacting entities. <mark style="color:blue;">The current document focuses on enabling basic functionalities such as supplier/buyer registration, listing a catalogue of goods and services, initiating a cycle of activities once a user selects a service. The document has not focused on payments/financial transactions between any two entities.</mark>

<mark style="color:blue;">The eMarketplace building block could be useful in variety applications in different sectors for example,</mark>

<mark style="color:blue;">**Government procurement of goods and services (B2G)**</mark>

* <mark style="color:blue;">In Health Sector, procurement of health goods such as pills, injections, syrengies etc.</mark>
* <mark style="color:blue;">In Civil infrastructure sector, procurement of engineering services such as construction of dams, buildings, computers etc.</mark>

<mark style="color:blue;">**Government providing goods and services (G2B)**</mark>



## <mark style="color:blue;">2.1</mark> <mark style="color:blue;"></mark><mark style="color:blue;">**Current scope**</mark>

<mark style="color:blue;">The functional requirements to cover the services required from the eMarketplace Building Block currently have considered specific use cases of</mark>&#x20;

<mark style="color:blue;">**Business to Government (B2G)**</mark>

1. [B2G-Use Case 1: Ministry of Justice - HMPPS Data & Reporting platform](https://app.gitbook.com/o/pxmRWOPoaU8fUAbbcrus/s/PUIGDILlDRSOB6K47k6e/\~/changes/4/b2g-uc1-moj-hpmms-data-and-reporting-platform)
2. [B2G-Use Case 2: Procurement of Sporting Goods by a registered sporting authority](https://app.gitbook.com/o/pxmRWOPoaU8fUAbbcrus/s/PUIGDILlDRSOB6K47k6e/\~/changes/4/mkt-b2g-uc2-sgp-sporting-goods-procurement)

<mark style="color:blue;">**Government to People (G2P)**</mark>

1. G2P-Use Case 1: Application for Pension Services by a citizen from the State Government
2. [G2P-Use Case 2: Online Reservation System (ORS)](https://app.gitbook.com/o/pxmRWOPoaU8fUAbbcrus/s/PUIGDILlDRSOB6K47k6e/\~/changes/4/g2p-uc2-online-reservation-system-ors)
3. [G2P-Use Case 3: Government Auctions Marketplace (GAM)](em-g2p-uc3-government-auctions-marketplace-gam/)

<mark style="color:blue;">These use cases bring forth the need for example implementations of events such as registration of individuals and entities such as users, suppliers and demand seekers, adminstrators, citizens that involves identification and verification ; publishing a catalogue of goods and services; selection of goods and services; scheduling the life cycle events in procurement such as creation of purchase requisition, awarding contract, monitoring the contractors' deliverables, bidding ; outreach communication and messaging notifications about status of procurement/payment. The considerations can be generalized for different types of events involving one or more participants.</mark>&#x20;

<mark style="color:blue;">Currently the following actors have been identified as "users" of the scheduler building block:</mark>

* <mark style="color:blue;">"Supplier Admin" is who manages the building block's implementation settings. A building block admin is also responsible to enrolment of entitles and Organizers of those entities that use the eMarketplace building block. The Admins interacts with the list of goods and services, cycle of procurement activities, communication management.</mark>
* <mark style="color:blue;">"Buyers" are who participate in events to perform various activities. Buyers MUST be registered in the eMarketplace Building Block before they can be enrolled in events. Resources MAY apply/respond to multiple goods and services in a catalogue. Hence a registered buyer SHOULD be able to offer services in parallel, if they are short listed by the Supplier.</mark>
* <mark style="color:blue;">"Subscribers" who participate in events to consume various activities. Subscribers must be registered in the eMarketplace before they can be enrolled in events. Subscribers MAY be enrolled in multiple events and MAY be passive to suppliers requests.</mark>&#x20;

<mark style="color:blue;">The eMarketplace MUST be able to enable enable these actors to perform in their roles associated with one or more events.  More specifically, the eMarketplace should facilitate following activities of the actors:</mark>

<mark style="color:blue;">**2.1.1. The eMarketplace MUST enable Building Block Admins (Supplier and Buyer) to**</mark>

* <mark style="color:blue;">register without duplication an entity, into its Entity List with details (e.g. name, phone, email, website, etc.) The entities host various "events" involving their affiliated resources.</mark>
* <mark style="color:blue;">categorize entities for easy searching and sorting. In current scope, "department",  "ministry" may be example entities.</mark>&#x20;
* <mark style="color:blue;">configure rules for performance, security and communication management between the eMarketplace and other building blocks (Registries, Identity and Verification, Information Mediation), applications (across different departments/ministries) and event participants. The exact parameters may be decided at implementation time</mark>&#x20;
* <mark style="color:blue;">extract log reports from the system as needed for monitoring and administering the building block operations.</mark>
* <mark style="color:blue;">register subscribers (persons/citizens/individuals) without duplication into eMarketplace's Subscriber list with contact details (phone/mail/URL/) as needed for communication, and reuse for enrolment to multiple events.</mark>&#x20;
* <mark style="color:blue;">register procurement life cycle events with a defined starting and ending time and  an optional deadline for participants to log in their attendance in the event, if needed.</mark>
* <mark style="color:blue;">to restricted number of Subscribers to an event, based on the sorting/category filter.</mark>
* <mark style="color:blue;">define and maintain a library of predefined stack of messages/notifications for specific Host entity so that it can be reused in multiple events conducted by the specific host entity.</mark>&#x20;
* <mark style="color:blue;">define alert schedules for sending specific Alert messages associated with specific event at specific date-time to associated subscribers or resources or both.</mark>&#x20;
* <mark style="color:blue;">to extract logs related to events that help in continuous improvement in procurement lifecycle event management</mark>

<mark style="color:blue;">**2.1.2  The eMarketplace MUST enable buyers and subscribers to**</mark>

* <mark style="color:blue;">search and extract their own registration details in the eMarketplace</mark>
* <mark style="color:blue;">search and extract their own affiliation details across associated entities</mark>
* <mark style="color:blue;">search and extract details of  events they are enrolled into</mark>
* <mark style="color:blue;">search and extract details of subscribers of events they are enrolled into</mark>
* <mark style="color:blue;">receive scheduled alert messages from events they are enrolled into</mark>
* <mark style="color:blue;">search and list details of events of chosen category in a specified date-time range</mark>
* <mark style="color:blue;">log status/attendance updates related to events they are enrolled into</mark>

#### <mark style="color:blue;">2.1.3  The eMarketplace MUST adminster a catalogue of goods and services to</mark>

* <mark style="color:blue;">get displayed a list of goods and/or services when an appropriate filter is used (for ex. a ministry, a type of service etc.)</mark>
* <mark style="color:blue;">get displayed a list of active/closed/in progress items of procurement; with its stages for the Supplier</mark>
* <mark style="color:blue;">get displayed the number of days remained for the entire project duration, payment milestones, list of deliverables in accordance with the buyer department/ministry.</mark>

#### <mark style="color:blue;">2.1.4  The eMarketplace MUST e-marketplace system automated internal functionality to</mark>

* <mark style="color:blue;">track all procurement lifecycle stages/events and send corresponding alert messages with unique</mark> <mark style="color:blue;"></mark><mark style="color:blue;">**tokens/ID**</mark> <mark style="color:blue;"></mark><mark style="color:blue;">to relevant participants at appropriate times</mark>
* <mark style="color:blue;">detect communication failure with other building blocks and applications and perform retries according to configured rules before logging a communication failure. Associated implementation specific details that are not specified here.</mark>&#x20;

## <mark style="color:blue;">2.2 Out of Scope</mark>

<mark style="color:blue;">The following aspects are out of scope of the current version of the eMarketplace building block specifications considered in this document:</mark>

* <mark style="color:blue;">Any type of payments between two parties.</mark>
*

#### <mark style="color:red;">TODOs</mark>

<mark style="color:red;">\<Need a little more content></mark>

<mark style="color:red;">\<Introduce the concept of E-Marketplace from the government perspective></mark>

<mark style="color:red;">\<Min requs that need to be addresses></mark>

<mark style="color:red;">\<G2P, P2G etc></mark>

<mark style="color:red;">\<Benefits of such an platform></mark>

<mark style="color:red;">\<Generic enough that></mark>&#x20;

<mark style="color:red;">\<Give some example use cases that has been considered in various sectors></mark>

\
\


