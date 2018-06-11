---
title: Azure accountability readiness checklist for the GDPR
description: Provides a convenient way to access information you may need to support GDPR when using Microsoft Azure.
keywords: ARC Azure, Microsoft 365, Microsoft 365 Education, Microsoft 365 documentation, GDPR
author: BrendaCarter
localization_priority: Priority
audience: microsoft-business
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
manager: laurawi
audience: itpro
ms.collection: GDPR
---

# Azure Accountability Readiness checklist for the GDPR

## 1. Introduction
This accountability readiness checklist provides a convenient way to access information you may need to support GDPR when using Microsoft Azure. The checklist is organized using the titles and reference number (in parenthesis for each checklist topic) of a set of privacy and security controls for personal data processors drawn from ISO/IEC CD 27552 Information technology -- Security techniques -- Enhancement to ISO/IEC 27001 for privacy management – Requirements. 

You can manage the items in this checklist with the Compliance Manager [16] by referencing the Control ID and Control Title under Customer Managed Controls in the GDPR tile. This control structure is also used to organize the presentation of the internal controls that Microsoft Azure implements to support GDPR, which you can download here https://servicetrust.microsoft.com/ViewPage/TrustDocuments.
 
To purchase a copy of the complete draft ISO standard, please visit https://shop.bsigroup.com/ProductDetail?pid=000000000030372571.

### 2. Conditions for collection and processing

#### Identify and document purpose (7.2.1)

##### Customer consideration
The customer should document the purpose for which personal data is processed.

##### Supporting Microsoft documentation: 
A description of the processing Microsoft performs for you, and the purposes of that processing, that can be included in your accountability documentation.
•	Microsoft Online Services Terms, Data Protection Terms, see Processing of Personal Data; GDPR [[1](gdpr-arc-Azure.md#1)]

##### Addresses GDPR Article(s)
(5)(1)(b), (32)(4)

### Identify lawful basis (7.2.2)

#### Customer consideration
The customer should understand any requirements related to the lawful basis of processing, such as whether consent must first be given.

##### Supporting Microsoft Documentation:  
Windows Azure does not provide direct support for gaining user consent. A description of processing personal data by Microsoft services for inclusion in your accountability documentation is available here: 
•	Key Information from Azure for Customer Data Protection Impact Assessments [[11](gdpr-arc-Azure.md#11)]

##### Addresses GDPR Article(s)
(5)(1)(a), (6)(1)(a), (6)(1)(b), (6)(1)(c), (6)(1)(d), (6)(1)(e), (6)(1)(f), (6)(3), (6)4)(a), (6)(4)(b), (6)(4)(c), (6)(4)(d),  (6)(4)(e), (8)(3), (9)(1), (9)(2)(b), (9)(2)(c), (9)(2)(d), (9)(2)(e), (9)(2)(f), (9)(2)(g), (9)(2)(h), (9)(2)(i), (9)(2)(j), (9)(3), (9)(4), (10), (17)(3)(a), (17)(3)(b), (17)(3)(c), (17)(3)(d), (17)(3)(e), (18)(2), (22)(2)(a), (22)(2)(b), (22)(2)(c), (22)(4)

#### Determine when consent is to be obtained (7.2.3)

##### Customer consideration
The customer should understand legal or regulatory requirements for obtaining consent from individuals prior to processing personal data (when it is required, if the type of processing is excluded from the requirement, etc.), including how consent is collected.

##### Supporting Microsoft Documentation:  
Windows Azure does not provide direct support for gaining user consent.

##### Addresses GDPR Article(s)
 (8)(1), (8)(2)

#### 	Obtain and record consent (7.2.4)
##### Customer consideration
When it is determined to be required, the customer should appropriately obtain consent. The customer should also be aware of any requirements for how a request for consent is presented and collected.

##### Supporting Microsoft Documentation:  
Windows Azure does not provide direct support for gaining user consent.

##### Addresses GDPR Article(s)
(7)(1), (7)(2), (9)(2)(a)

#### Privacy impact assessment (7.2.5)
##### Customer consideration
The customer should be aware of requirements for completing privacy impact assessments (when they should be performed, categories of data that might necessitate one, timing of completing the assessment).

##### Supporting Microsoft Documentation: 
How Microsoft services determine when to perform a DPIA, and an overview of the DPIA program at Microsoft including the involvement of the DPO, is provided n the Service Trust Portal Data [Protection Impact Assessments (DPIAs) page](https://servicetrust.microsoft.com/ViewPage/GDPRDPIA). For support for your DPIAs see:
- Key Information from Azure for Customer Data Protection Impact Assessments [[11](gdpr-arc-Azure.md#11)]

##### Addresses GDPR Article(s)
Article (35)

#### Contracts with PII Processors (7.2.6)
##### Customer consideration
The customer should ensure that their contracts with processors include requirements for aiding with any relevant legal or regulatory obligations related to processing and protecting personal data.

##### Supporting Microsoft Documentation:  
The Microsoft contracts that require us to aid with your obligations under the GDPR, including support for the data subject's rights. 
•	Microsoft Online Services Terms, Data Protection Terms, see Processing of Personal Data; GDPR [[1](gdpr-arc-Azure.md#1)]

##### Addresses GDPR Article(s)
(5)(2), (28)(3)(e), (28)(9)

#### Records related to processing PII (7.2.7)
##### Customer consideration
The customer should maintain all necessary and required records related to processing personal data (e.g. purpose, security measures, etc.). Where some of these records must be provided by a sub-processor, the customer should ensure that they can obtain such records.

##### Supporting Microsoft Documentation:
The tools provided by Microsoft services to help you maintain the records necessary demonstrate compliance and support for accountability under the GDPR. See the Azure Security Documentation [[2](gdpr-arc-Azure.md#2)] for [activity and diagnostic logging](https://docs.microsoft.com/en-us/azure/security/blueprints/fedramp-iaaswa-overview#logging-and-auditing) and logging of [processing of personal data](https://docs.microsoft.com/en-us/azure/security/protection-personal-data-azure-reporting-tools). 

##### Addresses GDPR Article(s)
(5)(2), (24)(1), (30)(1)(a), (30)(1)(b), (30)(1)(c), (30)(1)(d), (30)(1)(g), (30)(1)(f), (30)(3), (30)(4), (30)(5)

### 3.	Rights of data subjects
#### Determining PII principals’ rights and enabling exercise (7.3.1)

##### Customer consideration
The customer should understand requirements around the rights of individuals related to the processing of their personal data. These rights may include things such as access, correction, and erasure. Where the customer uses a third-party system, they should determine which (if any) parts of the system provide tools related to enabling individuals to exercise their rights (e.g. to access their data). Where the system provides such capabilities, the customer should utilize them as necessary.

##### Supporting Microsoft Documentation:
The capabilities Microsoft provides to help you support data subject rights. 
- Azure Data Subject Requests for the GDPR [[9](gdpr-arc-Azure.md#9)]
- Microsoft Azure (All-Up) ISO/IEC 27001:2013 ISMS Statement of Applicability see ISO/IEC 27018 control A.1.1 

##### Addresses GDPR Article(s)
(12)(2)

#### Determining information for PII principals (data subjects) (7.3.2)

##### Customer consideration

The customer should understand requirements for the types of information about processing of personal data that is to be available to be provided to the individual. This may include things such as: 
- Contact details about the controller or its representative;
- information about the processing (purposes, international transfer and related safeguards, retention period, etc.);
- information on how the principal may access and/or amend their personal data; requesting erasure or restriction of processing; receiving a copy of their personal data, and portability of their personal data
- How and from where the personal data were obtained (if not obtained from the principal directly)
- information about the right to lodge a complaint and to whom;
- information regarding corrections to personal data;
- Notification that the organization is no longer in position to identify the data subject (PII principal), in cases where the processing no longer requires the identification of the data subject; 
- Transfers and/or disclosures of personal data;
- existence of automated decision making based solely on automated processing of personal data;
- information regarding the frequency with which information to the data subject is updated and provided (e.g. “just in time” notification, organization defined frequency, etc.)

Where the customer uses third-party systems or processors, they should determine which (if any) of this information may need to be provided by them and ensure that they can obtain the required information from the third-party.

##### Supporting Microsoft Documentation:
Information about Microsoft services that you can include in the data you provide to data subjects. 
- Azure Data Subject Requests for the GDPR [[9](gdpr-arc-Azure.md#9)]
- Key Information from Azure for Customer Data Protection Impact Assessments [[11](gdpr-arc-Azure.md#11)]
- Who can access your data and on what terms [[7](gdpr-arc-Azure.md#7)]

##### Addresses GDPR Article(s)
(11)(2), (13)(1)(a), (13)(1)(b), (13)(1)(c), (13)(1)(d), (13)(1)(e), (13)(1)(f), (13)(2)(c), (13)(2)(d), (13)(2)(e), (13)(3), (13)(4), (14)(1)(a), (14)(1)(b), (14)(1)(c), (14)(1)(d), (14)(1)(e), (14)(1)(f), (14)(2)(b), (14)(2)(e), (14)(2)(f), (14)(3)(a), (14)(3)(b), (14)(3)(c), (14)(4), (14)(5)(a), (14)(5)(b), (14)(5)(c), (14)(5)(d), (15)(1)(a), (15)(1)(b), (15)(1)(c), (15)(1)(d), (15)(1)(e), (15)(1)(f), (15)(1)(g), (15)(1)(h), (15)(2), (18)(3), (21)(4)

#### Providing information to PII principals (7.3.3)
##### Customer consideration
The customer should comply with any requirements around how/when/in what form the required information is to be given to an individual related to the processing of their personal data. In cases where a third-party may provide required information, the customer should ensure that it is within the parameters required by the GDPR.

##### Supporting Microsoft Documentation:
Templated information about Microsoft services that you can include in the data you provide to data subjects. 
- Azure Data Subject Requests for the GDPR [9]
- Key Information from Azure for Customer Data Protection Impact Assessments [[11](gdpr-arc-Azure.md#11)]

##### Addresses GDPR Article(s)
(11)(2), (12)(1), (12)(7), (13)(3), (21)(4)

#### Provide mechanism to modify or withdraw consent (7.3.4)

##### Customer consideration
The customer should understand requirements for informing users about their right to access, correct, and/or erase their personal data and for providing a mechanism for which them to do so. If a third-party system is used and provides this mechanism as part of its functionality, the customer should utilize that functionality as necessary.

##### Supporting Microsoft Documentation:
Information about capabilities in Microsoft services that you can use when defining the information you provide to data subjects when requesting consent. 
- Azure Data Subject Requests for the GDPR [[9](gdpr-arc-Azure.md#9)]

##### Addresses GDPR Article(s)
(7)(3), (13)(2)(c), (14)(2)(d), (18)(1)(a), (18)(1)(b), (18)(1)(c), (18)(1)(d)

#### Provide mechanism to object to processing (7.3.5)

##### Customer consideration
The customer should understand requirements around rights of data subjects. Where an individual has a right to object to processing, the customer should inform them, and have a way for the individual to register their objection.

##### Supporting Microsoft Documentation:
Information about Microsoft services relating to object to processing that you can include in the data you provide to data subjects. 
- Azure Data Subject Requests for the GDPR [[9](gdpr-arc-Azure.md#9)] see *Step 4: Restrict*

###### Addresses GDPR Article(s)
(13)(2)(b), (14)(2)(c), (21)(1), (21)(2), (21)(3), (21)(5), (21)(6)

#### Sharing the exercising of PII principals' rights (7.3.6)

##### Customer consideration
The customer should understand requirements for notifying third-parties with whom personal data has been shared of instances of data modification based on the exercise of individual rights (e.g. an individual requesting erasure or modification, etc.)

##### Supporting Microsoft Documentation:
Information about capabilities in Microsoft services that allow you to discover personal data that you have shared with third parties. 
- Azure Data Subject Requests for the GDPR [[9](gdpr-arc-Azure.md#9)]

##### Addresses GDPR Article(s)
 (19)

#### Correction or erasure (7.3.7)

##### Customer consideration
The customer should understand requirements for informing users about their right to access, correct, and/or erase their personal data and for providing a mechanism for which them to do so. If a third-party system is used and provides this mechanism as part of its functionality, the customer should utilize that functionality as necessary.
Supporting Microsoft Documentation:
Templated information about Microsoft services relating to their ability to access, correct or erase personal data that you can include in the data you provide to data subjects. 
- Azure Data Subject Requests for the GDPR [9] see Step 5: Delete
- Privacy and personal data in Intune [15] <!-- need link --> see View and correct personal data and Audit, export, or delete personal data in Intune.

##### Addresses GDPR Article(s)
(5)(1)(d), (13)(2)(b), (14)(2)(c), (16), (17)(1)(a), (17)(1)(b), (17)(1)(c), (17)(1)(d), (17)(1)(e), (17)(1)(f), (17)(2)

#### Providing copy of PII processed (7.3.8)

##### Customer consideration
The customer should understand requirements around providing a copy of the personal data being processed to the individual. These may include requirements around the format of the copy (i.e. that it is machine readable), transferring the copy, etc. Where the customer uses a third-party system that provides the functionality to provide copies, they should utilize this functionality as necessary.

##### Supporting Microsoft Documentation:
Information about capabilities in Microsoft services to allow you to obtain a copy of their personal data that you can include in the data you provide to data subjects. 
•	Azure Data Subject Requests for the GDPR [[9](gdpr-arc-Azure.md#9)] see Step 6: Export
•	Privacy and personal data in Intune [[15](gdpr-arc-Azure.md#15)] see Audit, export, or delete personal data in Intune

##### Addresses GDPR Article(s)
(15)(3), (15)(4), (20)(1), (20)(2), (20)(3), (20)(4)

#### Request management (7.3.9)

##### Customer consideration
The customer should understand requirements for accepting and responding to legitimate requests from individuals related to the processing of their personal data. Where the customer uses a third-party system, they should understand whether that system provides the capabilities for such handling of requests. If so, the customer should utilize such mechanisms to handle requests as necessary.

##### Supporting Microsoft Documentation:
Information about capabilities in Microsoft services that you can use when defining the information you provide to data subjects as you manage data subject requests.
- Azure Data Subject Requests for the GDPR [[9](gdpr-arc-Azure.md#9)] 

##### Addresses GDPR Article(s)
(12)(3), (12)(4), (12)(5), (12)(6), (15)(1)(a), (15)(1)(b), (15)(1)(c), (15)(1)(d), (15)(1)(e), (15)(1)(f), (15)(1)(g), (15)(1)(h)

#### Automated decision making (7.3.10)

##### Customer consideration
The customer should understand requirements around automated personal data processing and where decisions are made by such automation. These may include providing information about the processing to an individual, objecting to such processing, or to obtain human intervention. Where such features are provided by a third-party system, the customer should ensure that the third party provides any required information or support.

##### Supporting Microsoft Documentation:
Information about any capabilities in Microsoft services for that might support automated decision making that you can use in your accountability documentation, and templated information for data subjects about those capabilities. 
- Key Information from Azure for Customer Data Protection Impact Assessments [11]

##### Addresses GDPR Article(s)
(13)(2)(f), (14)(2)(g), (22)(1), (22)(3)

### 4. Privacy by design and default

### Limit collection (7.4.1)

##### Customer consideration
The customer should understand requirements around limits on collection of personal data (e.g. that the collection should be limited to what is needed for the specified purpose).

##### Supporting Microsoft Documentation:  
A description of the data collected by Microsoft services. 
- Microsoft Online Services Terms, Data Protection Terms, see Processing of Personal Data; GDPR [[1](gdpr-arc-Azure.md#1)]
- Key Information from Azure for Customer Data Protection Impact Assessments [[11](gdpr-arc-Azure.md#11)]
- Privacy and personal data in Intune [[15](gdpr-arc-Azure.md#15)] *see Data collection in Intune*

##### Addresses GDPR Article(s)
(5)(1)(b), (5)(1)(c)

### Limit processing (7.4.2)

##### Customer consideration
The customer is responsible for limiting the processing of personal data so that it is limited to what is adequate for the identified purpose.

##### Supporting Microsoft Documentation:  
A description of the data collected by Microsoft services. 
- Microsoft Online Services Terms, Data Protection Terms, see Processing of Personal Data; GDPR [[1](gdpr-arc-Azure.md#1)]
- Key Information from Azure for Customer Data Protection Impact Assessments [[11](gdpr-arc-Azure.md#11)]
- Privacy and personal data in Intune [[15](gdpr-arc-Azure.md#15)] *see Data storage and processing in Intune*

##### Addresses GDPR Article(s)
(25)(2)

#### Define and document PII minimization and de-identification objectives (7.4.3)
Customer consideration
The customer should understand requirements around de-identification of personal data which may include, when it should be used, the extent to which it should de-identify, and instances when it cannot be used.

##### Supporting Microsoft Documentation:  
Microsoft applies de-identification and pseudonymization internally, where appropriate, to provide additional privacy safeguards for personal data.

##### Addresses GDPR Article(s)
(5)(1)(c)

### Comply with identification levels (7.4.4)

##### Customer consideration
The customer should use and comply with de-identification objectives and methods set by their organization.

##### Supporting Microsoft Documentation:  
Microsoft applies de-identification and pseudonymization internally, where appropriate, to provide additional privacy safeguards for personal data.

##### Addresses GDPR Article(s)
(5)(1)(c)

### PII de-identification and deletion (7.4.5)

##### Customer consideration
The customer should understand requirements around the retention of personal data past its use for the identified purposes.  Where provided tooling by the system, the customer should utilize those tools to erase or delete as necessary.

##### Supporting Microsoft Documentation:  
Capabilities provided by Microsoft Services to support your data retention policies. 
- Azure Data Subject Requests for the GDPR *see Step 5: Delete*

##### Addresses GDPR Article(s)
(5)(1)(c), (5)(1)(e), (6)(4)(e), (11)(1), (32)(1)(a)

#### Temporary files (7.4.6)

##### Customer consideration
The customer should be aware of temporary files that may be created by the system that could lead to non-compliance with policies around processing of personal data (e.g. personal data might be retained in a temporary file longer than required or allowed). Where the system provides such tools for temporary file deletion or checking, the customer should utilize such tools to comply with requirements.

##### Supporting Microsoft Documentation:  
A description of capabilities provided by the service to identify personal data to support your temporary file policies. 
- Azure Data Subject Requests for the GDPR *see Step 1: Discover*

##### Addresses GDPR Article(s)
(5)(1)(c)

### Retention (7.4.7)

##### Customer consideration
The customer should determine how long personal data should be retained, taking into consideration the identified purposes.

##### Supporting Microsoft Documentation:  
Information about the retention of personal data by Microsoft services that you can include in documentation provided to data subjects. 
- Microsoft Online Services Terms, Data Protection Terms, see Data Security, Retention [[1](gdpr-arc-Azure.md#1)]

##### Addresses GDPR Article(s)
(13)(2)(a), (14)(2)(a)

### Disposal (7.4.8)

##### Customer consideration
The customer should utilize any deletion or disposal mechanisms provided by the system to delete personal data.

##### Supporting Microsoft Documentation:  
Capabilities provided by Microsoft Services to support your data deletion policies. 
- Azure Data Subject Requests for the GDPR [[9](gdpr-arc-Azure.md#9)] *see Step 5: Delete*

##### Addresses GDPR Article(s)
(5)(1)(f)
#### Collection procedures (7.4.9)

##### Customer consideration
The customer should be aware of requirements around the accuracy of personal data (e.g., accuracy upon collection, keeping data up to date, etc.) and utilize any mechanisms provided by the system for such.

##### Supporting Microsoft Documentation:  
How Microsoft services support the accuracy of personal data, and any capabilities they provide to support your data accuracy policy. 
- Azure Data Subject Requests for the GDPR [[9](gdpr-arc-Azure.md#9)] *see Step 3: Rectify*

##### Addresses GDPR Article(s)
(5)(1)(d)

#### Transmission controls (7.4.10)

##### Customer consideration
The customer should understand requirements around safeguarding the transmission of personal data, including who has access to transmission mechanisms, records of transmission, etc.

##### Supporting Microsoft Documentation:  
A description of the types of personal data that are transferred by Microsoft services and the locations they are transferred between, and the legal safeguards for the transfer. 
- Key Information from Azure for Customer Data Protection Impact Assessments [[11](gdpr-arc-Azure.md#11)]

##### Addresses GDPR Article(s)
(5)(1)(f) Personal data sharing, transfer, and disclosure 

#### Identify basis for PII transfer (7.5.1)

##### Customer consideration
The customer should be aware of requirements for transferring personal data (PII) to a different geographic location and document what measures are in place to meet such requirements.

##### Supporting Microsoft Documentation:  
A description of the types of personal data that are transferred by Microsoft services and the locations they are transferred between, and the legal safeguards for the transfer. 
- Key Information from Azure for Customer Data Protection Impact Assessments [[11](gdpr-arc-Azure.md#11)]

##### Addresses GDPR Article(s)
Articles (44), (45), (46), (47), (48), and (49)

#### Countries and organizations to which PII might be transferred (7.5.2)

##### Customer consideration
The customer should understand, and be able to provide to the individual, the countries to which personal data is or may be transferred. Where a third-party/processor may perform this transfer, the customer should obtain this information from the processor.

##### Supporting Microsoft Documentation:  
A description of the types of personal data that are transferred by Microsoft services and the locations they are transferred between, and the legal safeguards for the transfer. 
- Key Information from Azure for Customer Data Protection Impact Assessments [[11](gdpr-arc-Azure.md#11)]
- Who can access your data and on what terms [[7](gdpr-arc-Azure.md#7)]

##### Addresses GDPR Article(s)
(30)(1)(e)

#### Records of transfers of PII (personal data) (7.5.3)

##### Customer consideration
The customer should maintain all necessary and required records related to transfers of personal data. Where a third-party/processor performs the transfer, the customer should ensure that they maintain the appropriate records and obtain them as necessary.
Look here and here for...
A description of the types of personal data that are transferred by Microsoft services and the locations they are transferred between, and the legal safeguards for the transfer. 
- Key Information from Azure for Customer Data Protection Impact Assessments [[11](gdpr-arc-Azure.md#11)]
- Who can access your data and on what terms [[7](gdpr-arc-Azure.md#7)]

##### Addresses GDPR Article(s)
(30)(1)(e)

#### Records of PII disclosure to third parties (7.5.4)

##### Customer consideration
The customer should understand requirements around recording to whom personal data has been disclosed. This may include disclosures to law enforcement, etc. Where a third-party/processor discloses the data, the customer should ensure that they maintain the appropriate records and obtain them as necessary.

##### Supporting Microsoft Documentation:
Documentation provided about the categories of recipients of disclosures of personal data including available records of disclosure. 
- Who can access your data and on what terms [[7](gdpr-arc-Azure.md#7)] 
- Privacy and personal data in Intune [[15](gdpr-arc-Azure.md#15)] *see Data security and sharing in Intune*

##### Addresses GDPR Article(s)
(30)(1)(d)

#### Joint controller (7.5.5)

##### Customer consideration
The customer should determine whether they are a joint controller with any other organization, and appropriately document and allocate responsibilities.

##### Supporting Microsoft Documentation
As specified by the Online Services Terms (OST), Microsoft, as a data processor, processes Customer Data only to provide the requested services to our customer, the data controller. 
- Microsoft Online Services Terms, Data Protection Terms, see Processing of Personal Data; GDPR [[1](gdpr-arc-Azure.md#1)]

##### Addresses GDPR Article(s)
(26)(1), (26)(2), (26)(3)

### 5.	Data Protection & Security

#### Understanding the organization and its context (5.2.1)

##### Customer consideration
Customers should determine their role in processing personal data (e.g. controller, processor, co-controller) to identify the appropriate requirements (regulatory, etc.) for processing personal data.

##### Supporting Microsoft Documentation
How Microsoft considers each service as either a processor or controller when processing personal data.
- Microsoft Online Services Terms, Data Protection Terms, see Processing of Personal Data; GDPR, Processor and Controller Roles and Responsibilities [[1](gdpr-arc-Azure.md#1)]

##### Addresses GDPR Article(s)
(24)(3), (28)(10), (28)(5), (28)(6), (32)(3), (40)(1), (40)(2)(a), (40)(2)(b), (40)(2)(c), (40)(2)(d), (40)(2)(e), (40)(2)(f), (40)(2)(g), (40)(2)(h), (40)(2)(i), (40)(2)(j), (40)(2)(k), (40)(3), (40)(4), (40)(5), (40)(6), (40)(7), (40)(8), (40)(9), (40)(10), (40)(11), (41)(1), (41)(2)(a), (41)(2)(b), (41)(2)(c), (41)(2)(d), (41)(3), (41)(4), (41)(5), (41)(6), (42)(1), (42)(2), (42)(3), (42)(4), (42)(5), (42)(6), (42)(7), (42)(8)

#### Understanding the needs and expectations of interested parties (5.2.2)

##### Customer consideration
Customers should identify parties that may have a role or interest in their processing of personal data (e.g. regulators, auditors, data subjects, contracted personal data processors), and be aware of requirements to engage such parties where required.

##### Supporting Microsoft Documentation:  
How Microsoft incorporates the views of all stakeholders in consideration of the risks involved in the processing of personal data. 
- Key Information from Azure for Customer Data Protection Impact Assessments [[11](gdpr-arc-Azure.md#11)]

##### Addresses GDPR Article(s)
(35)(9), (36)(1), (36)(3)(a), (36)(3)(b), (36)(3)(c), (36)(3)(d), (36)(3)(e), (36)(3)(f), (36)(5)

#### Determining the scope of the information security management system (5.2.3, 5.2.4)

##### Customer consideration
As part of any overall security or privacy program that a customer may have, they should include the processing of personal data and requirements relating to it.

##### Supporting Microsoft Documentation:  
How Microsoft services include the processing of personal data in information security management and privacy programs. 
•	Microsoft Azure (All-Up) ISO/IEC 27001:2013 ISMS Statement of Applicability [[13](gdpr-arc-Azure.md#13)] see A.19-A.29
•	SOC 2 Type 2 Audit Report [[12](gdpr-arc-Azure.md#12)]

##### Addresses GDPR Article(s)
(32)(2)

#### Planning (5.3)

##### Customer consideration
Customers should consider the handling of personal data as part of any risk assessment they complete and apply controls as they deem necessary to mitigate risk related to personal data they control.

##### Supporting Microsoft Documentation:  
How Microsoft services consider the risks specific to the processing of personal data as part of their overall security and privacy program. 
- Microsoft Azure (All-Up) ISO/IEC 27001:2013 ISMS Statement of Applicability [[13](gdpr-arc-Azure.md#13)] see A.19-A.29

##### Addresses GDPR Article(s)
(32)(1)(b), (32)(2)

#### 6.2 Information Security Policies

##### Customer consideration
The customer should augment any existing information security policies to include protection of personal data, including policies necessary for compliance with any applicable legislation.

##### Supporting Microsoft Documentation:  
Microsoft policies for information security and any specific measures for the protection of personal information. 
- Microsoft Azure (All-Up) ISO/IEC 27001:2013 ISMS Statement of Applicability [13] see A.19-A.29
- SOC 2 Type 2 Audit Report [[12](gdpr-arc-Azure.md#12)]
- 
##### Addresses GDPR Article(s)
24(2)

##### 6.3 Organization of Information Security Customer consideration
The customer should, within their organization, define responsibilities for security and protection of personal data. This may include establishing specific roles to oversee privacy related matters, including a DPO.  Appropriate training and management support should be provided to support these roles.

##### Supporting Microsoft Documentation
An overview of the role of Microsoft's Data Protection Officer, the nature of his duties, reporting structure and contact information. 
- Microsoft DPO Information [[17](gdpr-arc-Azure.md#17)]

##### Addresses GDPR Article(s)
(37)(1)(a), (37)(1)(b), (37)(1)(c), (37)(2), (37)(3), (37)(4), (37)(5), (37)(6), (37)(7), (38)(1), (38)(2), (38)(3), (38)(4), (38)(5), (38)(6), (39)(1)(a), (39)(1)(b), (39)(1)(c), (39)(1)(d), (39)(1)(e), (39)(2)

#### 6.4 Human Resource Security

##### Customer consideration
The customer should determine and assign responsibility for providing relevant training related to protecting personal data.

##### Supporting Microsoft Documentation:  
An overview of the role of Microsoft's Data Protection Officer, the nature of his duties, reporting structure and contact information. 
- Microsoft Cloud Security Policy [[4](gdpr-arc-Azure.md#4)] see 03. Human Resources Security
- FedRAMP Moderate FedRAMP System Security Plan [[3](gdpr-arc-Azure.md#3)] see 13.2 Awareness and Training (AT)

##### Addresses GDPR Article(s)
(39)(1)(b)

#### 6.5.1 Classification of Information

##### Customer consideration
The customer should explicitly consider personal data as part of a data classification scheme.

##### Supporting Microsoft Documentation:  
How Microsoft considers personal data in data classification, tagging and tracking information.
- GDPR Considerations for Data Controllers Using Windows [11] see Data tagging and tracking

##### Addresses GDPR Article(s)
(39)(1)(b)

#### Management of removable media (6.5.2)
##### Customer consideration
The customer should determine internal policies for the use of removeable media as it relates to the protection of personal data (e.g., encrypting devices).

##### Supporting Microsoft Documentation:  
How Microsoft services protect the security of personal information on any removeable media. 
- FedRAMP Moderate FedRAMP System Security Plan [[3](gdpr-arc-Azure.md#3)] see 13.10 Media Protection (MP)

##### Addresses GDPR Article(s)
(32)(1)(a), (5)(1)(f)

#### Physical media transfer (6.5.3)

##### Customer consideration
The customer should determine internal policies for protecting personal data when transferring physical media (e.g. encryption).

##### Supporting Microsoft Documentation:  
How Microsoft services protects personal data during any transfer of physical media.
- FedRAMP Moderate FedRAMP System Security Plan [[3](gdpr-arc-Azure.md#3)] see 13.10 Media Protection (MP)

##### Addresses GDPR Article(s)
(32)(1)(a), (5)(1)(f)

#### User access management (6.6.1)

##### Customer consideration
The customer should be aware of which responsibilities they have for access control within the service they are using, and manage those responsibilities appropriately, using the tools available.

##### Supporting Microsoft Documentation:  
The tools provided by Microsoft services to help you enforce access control.
- Azure Security Documentation [2] see [Protect personal data with identity and access controls](https://docs.microsoft.com/en-us/azure/security/protect-personal-data-identity-access-controls)

##### Addresses GDPR Article(s)]
(5)(1)(f)

#### User registration and de-registration (6.6.2)

##### Customer consideration
The customer should manage user registration and de-registration within the service they utilize, using the tools available to them.

##### Supporting Microsoft Documentation:  
The tools provided by Microsoft services to help you enforce access control. 
- Azure Security Documentation [2] see [Protect personal data with identity and access controls](https://docs.microsoft.com/en-us/azure/security/protect-personal-data-identity-access-controls)

##### Addresses GDPR Article(s)
(5)(1)(f)

#### User access provisioning (6.6.3)

##### Customer consideration
The customer should manage user profiles, especially for authorized access to personal data, within the service they utilize, using the tools available to them.

##### Supporting Microsoft Documentation:  
How Microsoft services support formal access control to personal data, including user IDs, roles, and the registration and de-registration of users. 
- Azure Security Documentation [[2](gdpr-arc-Azure.md#2)] see [Protect personal data with identity and access controls](https://docs.microsoft.com/en-us/azure/security/protect-personal-data-identity-access-controls)

##### Addresses GDPR Article(s)
(5)(1)(f)

#### Management of privileged access (6.6.4)

##### Customer consideration
The customer should manage user ID's to facilitate tracking of access (especially to personal data), within the service they utilize, using the tools available to them.

##### Supporting Microsoft Documentation:  
How Microsoft services support formal access control to personal data, including user IDs, roles, and the registration and de-registration of users.
- Azure Security Documentation [[2](gdpr-arc-Azure.md#2)] see [Protect personal data with identity and access controls](https://docs.microsoft.com/en-us/azure/security/protect-personal-data-identity-access-controls)

##### Addresses GDPR Article(s)
(5)(1)(f)

#### Secure log on procedures (6.6.5)

##### Customer consideration
The customer should utilize provided mechanisms in the service to ensure secure log on capabilities for their users where necessary.

##### Supporting Microsoft Documentation:  
How Microsoft services support internal access control policies related to personal data.
- Who can access your data and on what terms [[7](gdpr-arc-Azure.md#7)]

##### Addresses GDPR Article(s)
(5)(1)(f)

#### Cryptography (6.7)

##### Customer consideration
The customer should determine which data may need to be encrypted, and whether the service they are utilizing offers this capability. The customer should utilize encryption as needed, using the tools available to them.

***Look here for...***  
How Microsoft services support encryption and pseudonymization to reduce the risk of processing personal data. 
- Azure Security Documentation [2] see [Protect personal data at rest with encryption](https://docs.microsoft.com/en-us/azure/security/protect-personal-data-at-rest) and [Protect personal data in transit](https://docs.microsoft.com/en-us/azure/security/protect-personal-data-in-transit-encryption) with encryption and https://docs.microsoft.com/en-us/azure/security/security-azure-encryption-overvieww 

##### Addresses GDPR Article(s)
(32)(1)(a)

#### Secure disposal or re-use of equipment (6.8.1)

##### Customer consideration
Where the customer uses cloud computing services (PaaS, SaaS, IaaS) they should understand how the cloud provider ensures that personal data is erased from storage space prior to that space being assigned to another customer.

##### Supporting Microsoft Documentation:  
How Microsoft services ensure that personal data is erased from storage equipment before that equipment is transferred or reused. 
- Microsoft Azure Data Security (Data Cleansing and Leakage) [[5](gdpr-arc-Azure.md#5)]

##### Addresses GDPR Article(s)
(5)(1)(f)

#### Clear desk and clear screen policy (6.8.2)

##### Customer consideration
The customer should consider risks around hardcopy material that displays personal data, and potentially restrict the creation of such material. Where the system in use provides the capability to restrict this (e.g., settings to prevent printing or copying/pasting of sensitive data), the customer should consider the need to utilize those capabilities.

##### Supporting Microsoft Documentation:  
What Microsoft implements to manage hardcopy.
- Microsoft maintains these controls internally, see Microsoft Azure (All-Up) ISO/IEC 27001:2013 ISMS Statement of Applicability [[15](gdpr-arc-Azure.md#13)]  A.11.2.9

##### Addresses GDPR Article(s)
(5)(1)(f)

#### Separation of development, testing and operational environments (6.9.1)

##### Customer consideration
The customer should consider the implications of using personal data in development and testing environments within their organization.

##### Supporting Microsoft Documentation:  
How Microsoft ensures that personal data is protected in development and test environments. 
- Microsoft Azure (All-Up) ISO/IEC 27001:2013 ISMS Statement of Applicability [[13](gdpr-arc-Azure.md#13)] see A.12.1.4 
- Azure Standard Response to RFI on Security, Privacy, and Compliance see DSI-05

##### Addresses GDPR Article(s)
5(1)(f)

#### Information backup (6.9.2)

##### Customer consideration
The customer should ensure that they use system provided capabilities to create redundancies in their data and test as necessary.

##### Supporting Microsoft Documentation:  
How Microsoft ensures the availability of data that may include personal data, how accuracy of restored data is ensured, and the tools and procedures Microsoft services provide to allow you to backup and restore data. 
- FedRAMP Moderate FedRAMP System Security Plan [[3](gdpr-arc-Azure.md#3)] see 10.9 Availability

##### Addresses GDPR Article(s)
(32)(1)(c), (5)(1)(f)

#### Event logging (6.9.3)

##### Customer consideration
The customer should understand the capabilities for logging provided by the system and utilize such capabilities to ensure that they can log actions related to personal data that they deem necessary.

##### Supporting Microsoft Documentation:  
The data Microsoft service records for you, including user activities, exceptions, faults and information security events, and how you can access those logs for use as part of your record keeping. 
- Azure Security Documentation [2] see [Document protection of personal data with Azure reporting tools](https://docs.microsoft.com/en-us/azure/security/protection-personal-data-azure-reporting-tools)

##### Addresses GDPR Article(s)
(5)(1)(f)

#### Protection of log information (6.9.4)

##### Customer consideration
The customer should consider requirements for protecting log information that may contain personal data or that may contain records related to personal data processing. Where the system in use provides capabilities to protect logs, the customer should utilize these capabilities where necessary.

##### Supporting Microsoft Documentation:  
How Microsoft protects logs that may contain personal data.
- Azure Security Documentation [[2](gdpr-arc-Azure.md#2)] see [Document protection of personal data with Azure reporting tools](https://docs.microsoft.com/en-us/azure/security/protection-personal-data-azure-reporting-tools)

##### Addresses GDPR Article(s)
(5)(1)(f)

#### Information transfer policies and procedures (6.10.1)

##### Customer consideration
The customer should have procedures for cases where personal data may be transferred on physical media (such as a hard drive being moved between servers or facilities). These may include logs, authorizations, and tracking. Where a third-party or other processor may be transferring physical media, the customer should ensure that that organization has procedures in place to ensure security of the personal data.

##### Supporting Microsoft Documentation:  
How Microsoft services transfer physical media that may contain personal data, including the circumstances when transfer might occur, and the protective measures taken to protect the data. 
- FedRAMP Moderate FedRAMP System Security Plan [[3](gdpr-arc-Azure.md#3)] see 13.10 Media Protection (MP)

##### Addresses GDPR Article(s)
(5)(1)(f)

#### Confidentiality or non-disclosure agreements (6.10.2)

##### Customer consideration
The customer should determine the need for confidentiality agreements or the equivalent for individuals with access to or responsibilities related to personal data.

##### Supporting Microsoft Documentation:  
How Microsoft services ensure that individuals with authorized access to personal data have committed themselves to confidentiality. 
- SOC 2 Type 2 Audit Report [12] see CC1.4 pp72, SOC2 - 13

##### Addresses GDPR Article(s)
(5)(1)(f), (28)(3)(b), (38)(5)

#### Securing application services on public networks (6.11.1)

##### Customer consideration
The customer should understand requirements for encryption of personal data, especially when sent over public networks. Where the system provides mechanisms to encrypt data, the customer should utilize those mechanisms where necessary.

##### Supporting Microsoft Documentation:  
Description of the measures Microsoft services take to protect data in transit, including encryption of the data, and how Microsoft services protect data that may contain personal data as it passes through public data networks, including any encryption measures. 
- Azure Security Documentation [[2](gdpr-arc-Azure.md#2)] see [Protect personal data in transit with encryption](https://docs.microsoft.com/en-us/azure/security/protect-personal-data-in-transit-encryption)

##### Addresses GDPR Article(s)
(5)(1)(f), (32)(1)(a)

#### Secure system engineering principles (6.11.2)

##### Customer consideration
The customer should understand how systems are designed and engineered to consider protection of personal data. Where a customer uses a system engineered by a third-party, it is their responsibility to ensure that such protections have been considered.

##### Supporting Microsoft Documentation:  
How Microsoft services include personal data protection principles as a mandatory part of our secure design/engineering principles. 
- SOC 2 Type 2 Audit Report [12] see CC7.1 pp90 and [What is the Security Development Lifecycle?](https://www.microsoft.com/en-us/sdl/)

##### Addresses GDPR Article(s)
(25)(1)

#### Supplier Relationships (6.12)

##### Customer consideration
The customer should ensure that any information security and personal data protection requirements and that are the responsibility of a third-party are addressed in contractual information or other agreements.  The agreements should also address the instructions for processing.

***Look here for...***
How Microsoft services address security and data protection in our agreements with our suppliers and how we ensure those agreements are effectively implemented.
- Who can access your data and on what terms [[7](gdpr-arc-Azure.md#7)]

##### Addresses GDPR Article(s)
(5)(1)(f), , (28)(1), (28)(3)(a), (28)(3)(b), (28)(3)(c), (28)(3)(d), (28)(3)(e), (28)(3)(f), (28)(3)(g), (28)(3)(h),(30)(2)(d), (32)(1)(b)

#### Management of information security incidents and improvements (6.13.1)

##### Customer consideration
The customer should have processes for determining when a personal data breach has occurred.

##### Supporting Microsoft Documentation:
How Microsoft services determine if a security incident is a breach of personal data, and how we communicate the breach to you. 
- Azure and Breach Notification Under the GDPR [[10](gdpr-arc-Azure.md#10)]

##### Addresses GDPR Article(s)
(33)(2)

#### Responsibilities and procedures (during information security incidents) (6.13.2)

##### Customer consideration
The customer should understand and document their responsibilities during a data breach or security incident involving personal data. Responsibilities may include notifying required parties, communications with processors or other third-parties, and responsibilities within the customer's organization.

##### Supporting Microsoft Documentation:
How to notify Microsoft services if you detect a security incident or breach of personal data. 
- Azure and Breach Notification Under the GDPR [[10](gdpr-arc-Azure.md#10)]

##### Addresses GDPR Article(s)
(5)(1)(f), (33)(1), (33)(3)(a), (33)(3)(b), (33)(3)(c), (33)(3)(d), (33)(4), (33)(5), (34)(1), (34)(2), (34)(3)(a), (34)(3)(b), (34)(3)(c), (34)(4)

#### Response to information security incidents (6.13.3)

##### Customer consideration
The customer should have processes for determining when a personal data breach has occurred.

##### Supporting Microsoft Documentation:
Description of the information Microsoft services provide to help you decide if a breach of personal data has occurred. 
- Azure and Breach Notification Under the GDPR [[10](gdpr-arc-Azure.md#10)]

##### Addresses GDPR Article(s)
(33)(1), (33)(2), (33)(3)(a), (33)(3)(b), (33)(3)(c), (33)(3)(d), (33)(4), (33)(5), (34)(1), (34)(2)

#### Protection of records (6.15.1)

##### Customer consideration
The customer should understand the requirements for records related to personal data processing that need to be maintained.

##### Supporting Microsoft Documentation:  
How Microsoft services store records relating to the processing of personal data. 
- Azure Security Documentation [2] see [Document protection of personal data with Azure reporting tools](https://docs.microsoft.com/en-us/azure/security/protection-personal-data-azure-reporting-tools)

##### Addresses GDPR Article(s)
(5)(2), (24)(2)

#### Independent review of information security (6.15.2)

<!--start table here - on hold

||||
|:-----|:-----|:-----|
|**Issue** |**Description** |
|Customer consideration|The customer should be aware of requirements for assessments of the security of personal data processing. This may include internal or external audits, or other measures for assessing the security of processing. Where the customer is dependent on another organization of third-party for all or part of the processing, they should collect information about such assessments performed by them.|
|Supporting Microsoft Documentation|How Microsoft services test and assesses the effectiveness of technical and organizational measures to ensure the security of processing, including any audits by third parties.<br/>Microsoft Online Services Terms, Data Protection Terms, see Data Security, Auditing Compliance [[1](gdpr-arc-Azure.md#1)]| 
|Addresses GDPR Article(s)|(32)(1)(d), (32)(2)|
|||||

end of table -->
 
##### Customer consideration
The customer should be aware of requirements for assessments of the security of personal data processing. This may include internal or external audits, or other measures for assessing the security of processing. Where the customer is dependent on another organization of third-party for all or part of the processing, they should collect information about such assessments performed by them.

##### Supporting Microsoft Documentation:  
How Microsoft services test and assesses the effectiveness of technical and organizational measures to ensure the security of processing, including any audits by third parties.
- Microsoft Online Services Terms, Data Protection Terms, see Data Security, Auditing Compliance [[1](gdpr-arc-Azure.md#1)]

##### Addresses GDPR Article(s)
(32)(1)(d), (32)(2)

#### Technical compliance review (6.15.3)

##### Customer consideration
The customer should understand requirements for testing and evaluating the security of processing personal data. This may include technical tests such as penetration testing. Where the customer uses a third-party system or processor, they should understand what responsibilities they have for securing and testing the security (e.g. managing configurations to secure data and then testing those configuration settings). Where the third-party is responsible for all or part of the security of processing, the customer should understand what testing or evaluation the third-party performs to ensure the security of the processing.

##### Supporting Microsoft Documentation:  
How Microsoft services are tested security based on identified risks, including tests by third parties, and the types of technical tests and any available reports from the tests. 
- Microsoft Online Services Terms, Data Protection Terms, see Data Security, Auditing Compliance [[1](gdpr-arc-Azure.md#1)]
- For a listing of external certifications see Microsoft Trust Center Compliance offerings [[14](gdpr-arc-Azure.md#14)]
- For more information about penetration testing your applications see Azure Security Documentation [[2](gdpr-arc-Azure.md#2)] [Pen Testing](https://docs.microsoft.com/en-us/azure/security/azure-security-pen-testing)

##### Addresses GDPR Article(s)
(32)(1)(d), (32)(2)

### 6.	Bibliography of Resources and Links<br/>
1. <a name="1"></a>   Online Services Terms <http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46> <br/>
2.<a name="2"></a> Azure Security Documentation on docs.microsoft.com https://docs.microsoft.com/en-us/azure/security/, see Governance and compliance, GDPR <br/>
3.<a name="3"> </a>	FedRAMP Moderate FedRAMP System Security Plan (SSP) https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=e46a519a-bcf6-4dc2-8f60-6d0e4e00a85e&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_FedRAMP_Reports<br/>
4.<a name="4"> </a>	Microsoft Cloud Security Policy https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5868ecc8-50b7-4f91-b43f-640e2b99e86e&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers<br/>
5.	<a name="5"> </a>Microsoft Azure Data Security (Data Cleansing and Leakage)  https://blogs.msdn.microsoft.com/walterm/2014/09/04/microsoft-azure-data-security-data-cleansing-and-leakage/ <br/>
6.	<a name="6"> </a>Azure Standard Response to RFI on Security, Privacy, and Compliance https://gallery.technet.microsoft.com/Azure-Standard-Response-to-5de19cb6 <br/>
7.	<a name="7"> </a>Who can access your data and on what terms https://www.microsoft.com/en-us/trustcenter/Privacy/Who-can-access-your-data-and-on-what-terms <br/>
8.	<a name="8"> </a>Contracts for sub-processors: Contracting with Microsoft https://www.microsoft.com/en-us/procurement/supplier-contracting.aspx <br/>
9.	<a name="9"> </a>Azure Data Subject Requests for the GDPR https://docs.microsoft.com/en-us/microsoft-365/compliance/gdpr-dsr-azure <br/>
10.	<a name="10"> </a>Azure and Breach Notification Under the GDPR https://docs.microsoft.com/en-us/microsoft-365/compliance/gdpr-breach-azure <br/>
11.	<a name="11"> </a>Key Information from Azure for Customer Data Protection Impact Assessments [https://docs.microsoft.com/en-us/microsoft-365/compliance/gdpr-dpia-azure] <br/>
12.	<a name="12"> </a>SOC 2 Type 2 Audit Report [12] https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=3c7123a5-f507-48b7-8dce-cd948e6150e6&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC_%2F_SSAE_16_Reports<br/>
13.	<a name="13"> </a>Microsoft Azure (All-Up) ISO/IEC 27001:2013 ISMS Statement of Applicability https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=47d89200-b24b-491d-b657-7c523ddfb6f9&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_ISO_Reports <br/>
14.	<a name="14"> </a>Microsoft Trust Center Compliance offerings https://www.microsoft.com/en-us/trustcenter/compliance/complianceofferings <br/>
15.	<a name="15"> </a>Privacy and personal data in Intune https://review.docs.microsoft.com/en-us/intune/privacy-personal-data <br/>
16.	<a name="16"> </a>Compliance Manager https://servicetrust.microsoft.com/ComplianceManager <br/>
17.	<a name="17"> </a>Microsoft DPO Information [https://docs.microsoft.com/en-us/microsoft-365/compliance/gdpr-data-protection-officer]


## Learn more

[Microsoft Trust Center](https://www.microsoft.com/en-us/TrustCenter/Privacy/gdpr/default.aspx)


