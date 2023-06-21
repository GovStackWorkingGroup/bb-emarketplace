---
description: This section provides the context of the building block.
---

# 2 Description

{% hint style="success" %}
Set the context of the Building Block for the reader. The description should not assume that the reader has any experience of the GovStack system other than that found on the GovStack website.
{% endhint %}

Governments involve, directly or indirectly, in the procurement of various goods and services (e.g.  computers (goods) for its employees, and technical services for various projects to be implemented for the public welfare. E-marketplaces building block enables trade of products and/or services via electronic media where at least one of the transacting parties taking part in the transaction is the government (either as the procurer or the provider) and the other party(s) can be either providers or consumers of such goods and services (respectively).&#x20;

The government eMarketplace facilitates transparency by creating equal opportunities for all the stakeholders (suppliers and consumers); and thus creates efficient market for goods and services. It helps building new relationships thus builds trust. The buyer gains more insights on price information from different suppliers and is empowered to make rational decision making. The sellers can optimize the sales/marketing costs and can also improve their product range/portfolio by observing the demand in their domains thus multiply their market options even in international markets. The digital facility reduces time constraints for both the parties.

This document allows (provides guidance on creating) an e-marketplace digital public infrastructure to be created by connecting a set of interacting (services) microservices. In the context of government, the government can itself act as a supplier (in case of transferring moey to citizens i.e. G2P) and also can demand goods and services from other public entities (departmental transfers i.e. G2G) and private entities (puchasing computers/technical/advisory services i.e. business to government (B2G)). This infrastructure is fundamentally decentralized or federated, although all the services can exist on a single cloud. This specification does NOT assume any specific implementation architecture or technology. Rather, it defines the actors and the interfaces that need to be implemented by the transacting entities. The current document focuses on enabling basic functionalities such as supplier/buyer registration, listing a catalogue of goods and services, initiating a cycle of activities once a user selects a service. The document has not focused on payments/financial transactions between any two entities.

The eMarketplace building block could be useful in variety applications in different sectors for example,

**Government procurement of goods and services (B2G)**

* In Health Sector, procurement of supplies to government hospitals&#x20;
* In Civil infrastructure sector, procurement of engineering services such as construction of dams, buildings, computers etc.
* In transportation sector procurement of vehicles and associated maintenance services

**Government providing goods and services (G2B)**

* In Social security sector, cash/subsidy support services of government to eligible citizens
* In health sector, supply of nutrition and medicine to homes of patients/ pregnant mothers&#x20;
* In education sector govt providing free learning materials to students

## 2.1 **Current scope**

While there may be many of such use cases, within the current scope The functional requirements to cover the services required from the eMarketplace Building Block currently have considered specific use cases of&#x20;

**Business to Government (B2G)**

1. [B2G-Use Case 1: Ministry of Justice - HMPPS Data & Reporting platform](https://app.gitbook.com/o/pxmRWOPoaU8fUAbbcrus/s/PUIGDILlDRSOB6K47k6e/\~/changes/4/b2g-uc1-moj-hpmms-data-and-reporting-platform)
2. [B2G-Use Case 2: Procurement of Sporting Goods by a registered sporting authority](https://app.gitbook.com/o/pxmRWOPoaU8fUAbbcrus/s/PUIGDILlDRSOB6K47k6e/\~/changes/4/mkt-b2g-uc2-sgp-sporting-goods-procurement)

**Government to People (G2P)**

1. G2P-Use Case 1: Application for Pension Services by a citizen from the State Government
2. [G2P-Use Case 2: Online Reservation System (ORS)](https://app.gitbook.com/o/pxmRWOPoaU8fUAbbcrus/s/PUIGDILlDRSOB6K47k6e/\~/changes/4/g2p-uc2-online-reservation-system-ors)
3. [G2P-Use Case 3: Government Auctions Marketplace (GAM)](broken-reference)

These use cases have business process with several steps, wherein specific steps that involve the e-marketplace building block services were studies as example implementations (such as registration, identification and verification of individual entities and users in various roles; publishing a catalogue of goods and services provided by various entities; selection of goods and services and provider entities; scheduling the life cycle events in procurement such as creation of purchase requisition, bid management, vendor assessment, awarding contract, monitoring contractors' deliverables,  outreach communication and messaging notifications about status of procurement/payment, etc.&#x20;

Currently the following actors have been identified as "users" of the scheduler building block:

* "Supplier" is who manages the building block's implementation settings. A building block admin is also responsible to enrolment of entitles and Organizers of those entities that use the eMarketplace building block. The Admins interacts with the list of goods and services, cycle of procurement activities, communication management.
* "Buyers" are who participate in events to perform various activities. Buyers MUST be registered in the eMarketplace Building Block before they can be enrolled in events. Resources MAY apply/respond to multiple goods and services in a catalogue. Hence a registered buyer SHOULD be able to offer services in parallel, if they are short listed by the Supplier.
* "Subscribers" who participate in events to consume various activities. Subscribers must be registered in the eMarketplace before they can be enrolled in activities. Subscribers MAY be enrolled in multiple events and MAY be passive to suppliers requests.
* Building block admins???
* More actors ??? (property officer and Supply Property Management office in the case of GAM use case; internal teams does the bid evaluation and inform the buyer admin?; What if both the supplier and buyer are same entity as in the case of Sporting Goods Procurement use case?)

The eMarketplace MUST be able to enable enable these actors to perform in their roles associated with one or more events.  More specifically, the eMarketplace should facilitate following activities of the actors:

1. _The eMarketplace BB MUST enable Admins to_&#x20;

* enable the registration process of both supplies and buyers.&#x20;
* enable the verification of Foundational IDs come with no specified purpose or attached entitlement but functionalities simply let an entity prove who it is.
* Captures only limited information about users, such as name, date of birth, address and gender
* For a given set of credentials, fetches a corresponding ID if it exists in the registry
* Uses different biometric methods to identify and authenticate users through means other than user photographs (eg fingerprints, iris scans, facial recognition) to ensure there are no duplicates or fakes, creating a highly trustworthy database
* open bank accounts, buying SIM cards, receive entitlements from the government, sign forms electronically, invest in mutual funds and getting credit
* Incorporate privacy into its design when the purpose of the authentication is not revealed if a service provider sends an authentication request.

**2.1.1. The eMarketplace MUST enable Building Block Admins (Supplier and Buyer) to**

* <mark style="color:green;">seek consent from the entities, peoples while registration</mark>
* <mark style="color:green;">dynamically identify, verify and validate the registration details against that of public registries.</mark>
* register without duplication an entity, into its Entity List with details (e.g. name, phone, email, website, etc.) The entities host various "activities" involving their affiliated resources (client case management).
* categorize entities for easy searching and sorting. In current scope, "department",  "ministry" may be example entities.&#x20;
* configure rules for performance, security and communication management between the eMarketplace and other building blocks (Registries, Identity and Verification, Information Mediation), applications (across different departments/ministries) and event participants. The exact parameters may be decided at implementation time&#x20;
* extract log reports from the system as needed for monitoring and administering the building block operations.
* register subscribers (persons/citizens/individuals) without duplication into eMarketplace's Subscriber list with contact details (phone/mail/URL/) as needed for communication, and reuse for enrolment to multiple activities.&#x20;
* register procurement life cycle events with a defined starting and ending time and  an optional deadline for participants to log in their attendance in the activity, if needed.
* to restricted number of Subscribers to an activity, based on the sorting/category filter.
* define and maintain a library of predefined stack of messages/notifications for specific Host entity so that it can be reused in multiple activities conducted by the specific host entity.&#x20;
* define alert schedules for sending specific Alert messages associated with specific event at specific date-time to associated subscribers or resources or both.&#x20;
* to extract logs related to activities that help in continuous improvement in procurement lifecycle event management
* to generate (for ex. purchase order/request), upload and download the correspondance, circulars, agreements in .doc and .pdf formats (document management).
* (the supplier) to implement large scale outreach communication, awareness campaign activities through electronic means.
* to have grievance readdressal mechanism.
* to facilitate seek/offer/resolve/implement feedback mechanisms once the enrolled activities are completed.
* to delegate the access management so that a particular role can perform only the tasks/activities that they are intended to.
* to facilitate workflow management amongst active suppliers and buyers.
* to handle exceptions when a registration is failed, unable to generate a purchase request etc.
* to facilitate communication between both the parties, such as seeking clarification, responding to questions raised by the bidder on bidding process or any other etc.





**2.1.2  The eMarketplace MUST enable buyers and subscribers to**

* search and extract their own registration details in the eMarketplace
* search and extract their own affiliation details across associated entities
* search and extract details of activities they are enrolled into
* search and extract details of subscribers of activities they are enrolled into
* receive scheduled alert messages from activities they are enrolled into
* search and list details of activities of chosen category in a specified date-time range
* log status/attendance updates related to activities they are enrolled into
* view current status, details, list of activities dynamically

### <mark style="color:red;">What about suppliers and other actors? (See actors list above )</mark>

#### 2.1.3  The eMarketplace MUST enable adminstrator to catalogue of goods and services&#x20;

* get displayed a list of goods and/or services when an appropriate filter is used (for ex. a ministry, a type of service etc.)
* get displayed a list of active/closed/in progress items of procurement; with its stages for the Supplier
* get displayed the number of days remained for the entire project duration, payment milestones, list of deliverables in accordance with the buyer department/ministry.

#### 2.1.4  The eMarketplace MUST have system automated internal functionality to

* track all procurement lifecycle stages/events and send corresponding alert messages with unique **tokens/ID** to relevant participants at appropriate times
* detect communication failure with other building blocks and applications and perform retries according to configured rules before logging a communication failure. Associated implementation specific details that are not specified here.&#x20;

## 2.2 Out of Scope

The following aspects are out of scope of the current version of the eMarketplace building block specifications considered in this document:

* Any type of payments between two parties.
* Internal coordination on  both supplier side (for example: preparation of business case ) and buyer side (technical evaluation of bids) are outside of the current scope.







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


