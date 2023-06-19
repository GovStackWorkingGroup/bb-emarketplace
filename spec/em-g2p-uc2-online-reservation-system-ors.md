# eM-G2P-UC2-Online Reservation System (ORS)

### MKT-G2P-UC2-ORS-Online Reservation System

#### Product Use Case Summary <a href="#product-use-case-summary" id="product-use-case-summary"></a>

| ID      | MKT                       |
| ------- | ------------------------- |
| Name    | Online Reservation System |
| Sector  | Government Marketplace    |
| Version | 1.0                       |
| Status  | Draft                     |



This use case explain the three broad steps in booking a doctor's appointment by a citizen. The three steps included are (1) Citizen's registration (2) Hospital Staff Registration (3) Booking a doctors appointment by a citizen. The ORS service involves a health application consisting of registered hospitals with various departmental services in it pooled across multiple cities in a state or a country. A citizen can choose to select a service in a particular hospital and book an appointment. Then, the citizen can visit the hospital as per the appointment time and seek medicine receipts/diagnostic services, if any, into his/her registered account. A citizen can avail deemed social benefits as per eligible criterian defined by the government.  For example, a citizen can choose to scroll through nearest town/city, select a general or specialized government hospital (for ex. Cancer hospital) and then select a department (oncology) and see who all doctors/slots are available; and then book an appointment as per their convenience. Once the appointment is booked, the citizen receives confirmation details and visits the hospital to consult the doctor. If the doctor suggests any prescription, the same is uploaded into citizen's account by hospital staff-which can be shown across medical shops to get medicine. Nominal fee payments, receiving of medical aid in terms of cash etc. are not considered in this case study.&#x20;



### **SDG Targets​**

12.7: Promote public procurement practices that are sustainable, in accordance with national policies and priorities

12.7.1: Number of countries implementing Sustainable Public Procurement policies and action plans

**3.7 By 2030, ensure universal access to sexual and reproductive health-care services, including for family planning, information and education, and the integration of reproductive health into national strategies and programmes.**

**3.8 Achieve universal health coverage, including financial risk protection, access to quality essential health-care services and access to safe, effective, quality and affordable essential medicines and vaccines for all.**

### **Building Blocks​**

1. Consent
2. Identification and Verification
3. Messaging
4. Registration
5. Scheduling
6. Information Mediator
7. _<mark style="color:red;">Work flow and Algorithm</mark>_
8. Registries

Future building blocks inclusion

* Payments
* UI/UX
* Analytics and Business Intelligence
* Artificial Intelligence (AI)
* Geographic Information Services (GIS)

​<mark style="color:red;">Steps1 - Outreach Communications</mark>

Staff from the Ministry of Health or another leading agency / organization organizes an information awareness campaign about booking health appointments and its benefits through ORS through various channels of communication via mobile messaging and/or aired on national radio/television, internet, social media. Outreach communication is intensive during the kick-off phase of the new programme, but also requires ongoing touchpoints and additional information sharing, e.g. on grievance redressal, rights and responsibilities, behavioural change communication, etc.

Workflows

* **Client communication** to facilitate the spreading of programme awareness for target audience and encouraging enrolment via mobile,web, kiosk, media channel(s)
* Client education for educating potential target beneficiaries around the approach and objective(s), benefit(s), constraint(s), partner(s), etc. of the programme
* **Content management** for the backend Health department and stakeholder staff to populate relevant educational and promotional content that local officers can use during on-the-ground outreach campaigns
* **Identification and Registration** (with aid of geographic information services tool for potential use) in mapping and locating households and individuals for outreach target

**Example Implementation**

To do

**Building Blocks​**

Messaging

​Scheduling

Information Mediation

**2 - Registration, **<mark style="color:red;">**Identification and Verification**</mark>

Registration is the process of collecting information of stakeholders such as citizens and hospital staff, in this use case. Depending on specific grography context, registration works in very different ways – either through self registration, on-demand at local hospitals (either approach potentially building on interoperability existing data sources) or single admin registration of hospital staff. While the practicalities of data collection differ across the types, with very different implications for data quality, currency and completeness, the underlying digital processes are broadly the same. A self registration involves providing data inputs by the citizen while the on-demand registration will facilitate the same services for the individuals who might not be able to help themselves. Further, an adminstrator of hospital may also choose to enrol/register all the doctors details (for example), on behalf of them.

The data registered can be saved into type of registries (for example, citizens, hospital staff registries, hospitals registry, cities registry, departments registry) and can be accessed to collect, organize, store, process, transform, create, and distribute information necessary to support intake and registration of potential beneficiaries (gateway function).&#x20;

**Workflows**

**Data Collection and Reporting** for capturing interview responses or observations during registration process

**Identification and Registration** for enrolled identified beneficiaries in the system and enabling possible permissions for interaction with the Health Application, and (with aid of geographic information services tool) to potentially locate and track households during the interview process

<mark style="color:red;">**Client Case Management**</mark> for creating beneficiary user records

**Example Implementation**

[Citizen Registration](https://app.gitbook.com/o/pxmRWOPoaU8fUAbbcrus/s/PUIGDILlDRSOB6K47k6e/\~/changes/4/g2p-uc2-ors-s1-citizen-registration)

[Hospital Staff Registration](https://app.gitbook.com/o/pxmRWOPoaU8fUAbbcrus/s/PUIGDILlDRSOB6K47k6e/\~/changes/4/g2p-uc2-ors-s2-hospitalstaff-registration)

**Building Blocks**

​Consent​

Registration​​

Registries

Identity and Verification

Information Mediation

Messaging

<mark style="color:red;">**3 - Booking a doctor's apointment**</mark>

This is a key process of the use case where a citizen access the health application (ORS) and books an appointment. The process involves a citizen visiting a catalogue of cities, government hospitals in each city; and selects a department (for example: neurology) in a selected hospitals and books a doctor's appointment at a scheduled slot. Once the citizen visits the hospital, their appointment is reconfirmed and entitlements, if any, are verified by the hospital staff. The doctor, upon completion of diagnosis, can direct the staff to upload the prescriptions, diagnosis results in the same account of the citizen so that the citizen can show case the same to receive medicine and to store the health hisory.

**Workflows**

**Cross verification** of citizen appointment details when the later visits the hospital

**Catalogue of services** The citizen should be able to select a service under a department of a hospital in a city

**Client Case Management** for determining and assigning benefit packages and benefit levels to specific user groups

**Data Analysis and Business Intelligence** / Decision Support potentially for identifying different benefit levels / types in correlation to target groups’ socioeconomic / demographic information, based on existing eligibility criteria

**Document Management** that uploads/stores the prescriptions, diagnosis results by the hospital staff

**Scheduling** The time slot shall get updated automatically whenever a slot is booked or when the slot is cancelled. It shall also communicate the appointment details to citizen and to the hospital staff.

**Example Implementation**

[Booking an appointment](https://app.gitbook.com/o/pxmRWOPoaU8fUAbbcrus/s/PUIGDILlDRSOB6K47k6e/\~/changes/4/g2p-uc2-ors-s3-bookingdoctorsappointment)

**Building Blocks**

​Identity and Verification

Consent

Information Mediation

Digital Registries

Registration

Scheduling

UI/UX

Messaging

Client Case Management

Analytics and Business Intelligence

#### Outputs <a href="#outputs" id="outputs"></a>

1. The citizen is able to successfully register a doctor's appointment in a government hospital

#### Failure Points <a href="#failure-points" id="failure-points"></a>

1. Internet connectivity
2. Lack of awareness
3. Technical failure of the application
