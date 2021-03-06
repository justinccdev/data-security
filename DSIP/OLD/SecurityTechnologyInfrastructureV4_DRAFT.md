Global Alliance for Genomics and Health Security Technology Infrastructure

## **Global Alliance for Genomics and Health**

# **SECURITY TECHNOLOGY INFRASTRUCTURE**

## Standards and implementation practices for protecting the privacy and security of shared genomic and clinical data

## **VERSION 4.0, June 12, 2019**

## **Outline**

1.0 – [Introduction](#1-introduction)

2.0 – [Security Foundation](#2-security-foundation)  
2.1 – [Risk Assessment](#21-risk-assessment)  
2.2 – [Privacy and Security Policy](#22-privacy-and-security-policy)  
2.3 – [Guiding Principles](#23-guiding-principles)  
2.4 – [Information Security Responsibilities](#24-information-security-responsibilities)

3.0 – [Security Technology Building Blocks](#3-security-technology-building-blocks)  
3.1 – [Identity Management](#31-identity-management)  
3.2 – [Authorization and Access Control](#32-authorization-and-access-control)  
3.3 – [Privacy Protection](#33-privacy-protection)  
3.4 – [Audit Logs](#34-audit-logs)  
3.5 – [Data Integrity](#35-data-integrity)  
3.6 – [Non-repudiation](#36-non-repudiation)  
3.7 – [Cryptographic Controls](#37-cryptographic-controls)  
3.8 – [Communications Security](#38-communications-security)

4.0 – [Operational Assurance](#4-operational-assurance)  
4.1 – [Physical and Environmental Security](#41-physical-and-environmental-security)  
4.2 – [Service Assurances](#42-service-assurances)  
4.3 – [Information Security Oversight and Accountability](#43-information-security-oversight-and-accountability)  
4.4 – [Regulatory and Policy Compliance](#44-regulatory-and-policy-compliance)

5.0 – [References](#5-references)

## **1. Introduction**

This document describes the security technology infrastructure recommended for
stakeholders (see section 2.4 below) in the *Global Alliance for Genomics and
Health* (GA4GH) community. As a living document, the *Security Technology
Infrastructure* will be revised and updated over time, in response to changes in
the [GA4GH Privacy and Security
Policy](https://www.ga4gh.org/wp-content/uploads/Privacy-and-Security-Policy.pdf)
[1], and as technology and biomedical science continue to advance.

The GA4GH is an unincorporated collaboration among entities and individuals
pursuing the common mission of accelerating progress in medicine and human
health by advancing a common infrastructure of harmonized approaches to enable
effective and responsible sharing of clinical and genomic data. Towards that
end, the GA4GH develops standards for enabling federated access to semantically
interoperable genomic data through RESTful application programming interfaces
(APIs), along with standards for defining, sharing, and executing portable
application workflows.

All of these standards depend upon a safe, robust, and trustworthy technology
infrastructure that, along with a set of common values and expectations set
forth in the [Framework for Responsible Sharing of Genomic and Health-Related
Data](https://www.ga4gh.org/ga4ghtoolkit/regulatoryandethics/framework-for-responsible-sharing-genomic-and-health-related-data/)
[2], provide the foundation for the GA4GH ecosystem. The viability and success
of the envisioned GA4GH ecosystem are directly dependent upon *trust* – the
ability of Alliance stakeholders to trust each other, the ability of users to
trust the technology infrastructures within which the GA4GH standards are
implemented, and the ability of individuals who contribute their clinical and
genomic data to trust GA4GH stakeholders to use their data responsibly and
respectfully.

As an interdependent, emergent ecosystem, the GA4GH supports multiple physical
and logical architectures. Therefore, the security technology infrastructure
described herein is not intended to describe a physical or operational
implementation, but rather suggests a set of security and architectural
standards, guidelines, and best practices for implementing and operating a
trustworthy, federated, environment within which data and services are shared.
Given the important role that trust plays in pursuing the mission of the GA4GH,
the security technology infrastructure is not limited to those mechanisms
traditionally considered “security” technologies, such as authentication,
authorization, access control, and audit, but also includes architectural
guidance for building and operating trustworthy systems – that is, systems that
can be relied upon to perform their expected functions and to withstand threats
to data integrity, information confidentiality, and service availability.

The *Framework for Responsible Sharing of Genomic and Health-Related Data*
describes the principles that form the trust foundation for GA4GH. The *GA4GH
Privacy and Security Policy,* which builds upon this *Framework*, articulates
policies for securing the data and services provided under the auspices of the
GA4GH with the privacy of the individuals who enable their genomic and
health-related data to be discovered, accessed, and used. The *Security
Technology Infrastructure* defines guidelines, best practices, and standards for
building and operating a technology infrastructure that adheres to the GA4GH
*Framework* principles and enforces the GA4GH *Privacy and Security Policy*.

The technology infrastructure defined herein seeks to reflect the prevailing
state of practice, while enabling emerging approaches to sharing sensitive
information on a massive scale. It is intended to support a broad range of
existing use cases, while allowing innovation. We realize that as the volume and
value of clinical and genomic data continue to increase exponentially, threat
agents will become ever more determined to find and exploit vulnerabilities in
the technology infrastructures that transmit, store, and process these data.

We strongly encourage organizations to adhere to a recognized security
framework, such as ISO/IEC 27001 [3] or the U.S. National Institute of Standards
and Technology Special Publication 800-53 [4] to accomplish the control and
assurance objectives arising from identified risks to data sensitivity and
integrity, and to the availability of services.

## **2. Security Foundation**

### **2.1 Risk Assessment**

The *GA4GH Security Technology Infrastructure* is based on a balanced approach
to risk management that relies on each individual stakeholder to help protect
the security, integrity, and trustworthiness of the GA4GH ecosystem. Each
stakeholder should assess its individual risk on an on-going basis and ensure
that its own implemented policies, procedures, and technology protections are
appropriate and sufficient for managing the identified risks not only to the
enterprise, but to the GA4GH ecosystem. Each stakeholder should perform a
comprehensive risk assessment at least annually and should assess potential risk
impacts whenever significant changes are made to network and system software or
hardware.

To be successful, the GA4GH ecosystem needs to effectively manage the following
risks. [5]

-   Breach of confidentiality – unauthorized disclosure of information that an
    individual or organization wishes to keep confidential.

-   Breach of individual privacy and autonomy – access to and use of an
    individual’s genomic or health-related data without the appropriate
    knowledge or consent of the individual concerned, or for purposes the
    individual has not authorized.

-   Malicious or accidental corruption or destruction of genomic and
    health-related data.

-   Disruption in the availability of data and services necessary to maintain
    appropriate access to clinical and genomic data.

-   Unethical, illegal, or inappropriate actions that attempt to breach security
    controls, surreptitiously obtain or derive information in an unauthorized
    manner, or otherwise undermine the trust fabric of the GA4GH.

From a software point of view, and if applicable, we also encourage stakeholders
to use the OWASP top 10 risks [6] to track other potential sources of threats.

   ### **2.2 Privacy and Security Policy**

The *Privacy and Security Policy* specifically builds upon the *Framework’s*
Core Element: “Privacy, Data Protection and Confidentiality.” The *Security
Technology Infrastructure* recommends technical safeguards, standards, and
practices to enforce the *Policy* across the technology implementations that
together comprise the GA4GH enterprise.

The *Security Technology Infrastructure* recommends technical safeguards,
standards, guidelines, and best practices for implementing and operating a
technology infrastructure that will enable individual stakeholders to implement
GA4GH standards safely, and to enforce the *Policy* defined for the GA4GH
ecosystem.

Thus, the *Security Technology Infrastructure* is defined to meet the following
five control objectives that respond to the risks identified in the above
sub-section.

-   *Control Objective 1*: Implement technology safeguards to prevent
    unauthorized access, use, or disclosure of confidential and private data.

-   *Control Objective 2*: Implement technology safeguards to prevent the
    discovery, access, and use of individuals’ clinical and genomic data, and
    individual identities, other than as authorized by applicable jurisdictional
    law, institutional policy, and individual consents.

-   *Control Objective 3*: Implement technology safeguards to prevent and detect
    accidental or malicious corruption or destruction of data.

-   *Control Objective 4*: Implement technology safeguards to prevent
    disruption, degradation, and interruption of services enabling access to
    data.

-   *Control Objective 5*: Implement technology safeguards to prevent and detect
    potential security attacks and misuse of authorized accesses and privileges.

   ### **2.3 Guiding Principles**

The *Security Technology Infrastructure* is consistent with the [Framework for
Responsible Sharing of Genomic and Health-Related
Data](https://www.ga4gh.org/ga4ghtoolkit/regulatoryandethics/framework-for-responsible-sharing-genomic-and-health-related-data/),
and seeks to enforce the policy articulated in the [GA4GH Privacy and Security
Policy](https://www.ga4gh.org/docs/ga4ghtoolkit/data-security/Privacy-and-Security-Policy.pdf)*.*

   ### **2.4 Information Security Responsibilities**

As a virtual ecosystem, the GA4GH assigns roles and responsibilities for
information security to stakeholders within this ecosystem. From a security and
privacy perspective, the principal stakeholders are:

1.  *Individuals* – people who enable their genomic and health-related data to
    be used and shared within the GA4GH ecosystem

2.  *Global Alliance* – a collaborative community of individuals and
    organizations that collectively provide foundational policy, technology
    standards, leadership, and sustainment to enable the ethical and productive
    sharing and use of genomic and health-related data.

3.  *Data Controllers* – the entities responsible for assuring the quality and
    integrity of data and management of data made available to the GA4GH
    community, consistent with GA4GH standards, applicable law, institutional
    policy, and individual permissions. These may include but are not limited
    to,

    1.  Data Owner – The legal person, agency, or body that has authority and is
        accountable for their organisation’s data and may delegate
        responsibilities to a Data Steward.

    2.  Data Steward – The authority of the Data Steward is delegated to them by
        the Data Owner. They are accountable for the management of data and are
        therefore responsible for ensuring that all relevant legislative
        requirements have been met before data is made available for use by the
        Global Alliance.

4.  *Data Processors* – entities responsible for preserving the context and
    associated business rules of data on behalf of Data Controllers, including
    privacy and security attributes, consistent with GA4GH standards, applicable
    law, institutional policy, and individual permissions. These may include but
    are not limited to,

    1.  Data Custodian – a person who has technical control over a dataset.

    2.  Data service providers – entities that provide data storage, protection,
        management, access, and transmission services to the GA4GH community,
        and optionally ensure that data transmitted or uploaded to other
        destinations are qualified according to the specifications for both data
        and metadata quality, access constraints, and semantics, as appropriate.

    3.  Application service providers – entities that provide application
        services, such as web-based or mobile clients, for manipulating and
        analyzing data using GA4GH standards.

    4.  Infrastructure service providers – entities that provide technology
        resources and technical support for persisting, protecting, managing,
        accessing, transmitting, and using electronic data; includes both
        enterprise and cloud service providers.

5.  *Data Consumers* – individuals and software clients that use data and
    application services available to the GA4GH community.

![Fig 1](https://github.com/ga4gh/data-security/blob/master/STI%20Fig1.png)

**Figure 1. Data security roles and their relationships.**

Consistent with jurisdictional laws and institutional policy, each stakeholder
should publish the names, contact information, and roles of the individual(s)
who have been delegated responsibility for overseeing conformance with the
*Security Technology Infrastructure* and for reporting breaches that involve
GA4GH standards. More on how such breaches should be reported is explained in
section 4.4.

The GA4GH leadership expects that in many cases, one organization may behave in
more than one stakeholder role. For example, a data steward may also be a data
service provider; an infrastructure service provider might also offer
application and data services hosted on the infrastructure they support. In such
cases, the organization as a whole is responsible for demonstrating control
effectiveness for the applicable controls. The expectation is that stakeholders
should document the roles and responsibilities as appropriate within that
community. Furthermore, such organization should assure that security-critical
functions and responsibilities are delegated among multiple roles and multiple
individuals to help avoid conflicts of interest and prevent inappropriate
activities.

Figure 2 below is a graphical representation of the delegation of
responsibilities for implementing and operating in accordance with the GA4GH
*Security Technology Infrastructure*.

![Fig 2](https://github.com/ga4gh/data-security/blob/master/STI%20Fig2.jpg)

**Figure 2. Allocation of responsibility for security protections.** Those
functions listed in the vertical block are the responsibilities of the GA4GH
community as a whole. Functions listed in other blocks are allocated to data
controllers, data processors, data consumers, and GA4GH.

Infrastructure service providers may provide a wide range of services to data
and application service providers, including computing, storage, network, and
security services. Most commonly, these services will be virtualized across data
centers and geographic locations. The applicability of, and responsibility for
providing, each of the security functions within the “data processors” block
will depend upon the specific services provided, as well as the contractual
agreements established between infrastructure service providers and their
customers.

## **3. Security Technology Building Blocks**

This section provides guidance on implementing security services within a
stakeholder’s organization and across the GA4GH interconnected community.

### **3.1 Identity Management**

The effectiveness of the *Security Technology Infrastructure* ultimately is
dependent upon the degree to which the actors (individuals and software
services) are known and can be trusted to conform to applicable policy.

-   Each API exposed by data and application services within the GA4GH community
    will have the capability to electronically authenticate its fully qualified
    domain name using a server certificate or, within the EU, a qualified
    electronic signature, as defined in Regulation (EU) No 910/2014 of the
    European Parliament and of the Council of 23 July 2014 on electronic
    identification and trust services for electronic transactions in the
    internal market and repealing Directive 1999/93/EC [7].

-   Each service provider will authenticate the identity of individuals and
    software accessing data and services under that provider’s control.

-   Data and application service providers are encouraged to externalize
    authentication and authorization services to trusted identity providers and
    brokers.

-   The level of assurance to which individual identities will be established
    (i.e., identity proofing) and authenticated will be consistent with the
    level of risk associated with the actions to be performed by that
    individual. Each data and application service provider is encouraged to use
    the US National Institute of Standards and Technology (NIST) Special
    Publication 800-63-3 [8] as guidance in determining the appropriate level of
    assurance required for identity proofing, authentication, and federation.

-   Service providers are encouraged to make use of the *GA4GH Authentication
    and Authorization Infrastructure* (AAI) standard [9] to federate identity
    authentication and service authorization. Service providers are also
    encouraged to use GA4GH standards for representing researcher identity
    attributes in OpenID Connect (OIDC) claims [10], and data use ontology (DUO)
    [11] for representing security and privacy attributes of shared data.

### **3.2 Authorization and Access Control**

-   Each service provider and service consumer will implement access control
    policies and mechanisms to ensure that only authorized users (human user or
    software client) may access data and services authorized and provided
    through the GA4GH community, and that each authenticated user is given
    access to all of and only those data and services to which it has been
    authorized.

-   Access authorizations may be based on organization, individual user, role,
    location and context (e.g., purpose, authorization time limits).

-   Each service provider and service consumer is responsible for controlling
    access to genomic and health-related data in accordance with applicable law
    and the personal authorizations associated with the data.

-   Each service provider and service consumer is responsible for assuring that
    any disclosure of identifiable data include the personal authorization rules
    the recipient must enforce with respect to access to, and use of, those
    data.

-   Each service provider and service consumer with whom genomic or
    health-related data are shared will control access to and use of those data
    in accordance with the personal authorization rules (i.e., consents,
    permissions) associated with the data.

-   Each data steward is responsible for developing and implementing policies
    and procedures for determining whether a requesting service consumer (human
    user or software client) is granted access to data sets and applications,
    and for authorizing rights and privileges associated with that access, in
    accordance with relevant jurisdictional laws, GA4GH policies, institutional
    policies, and data steward authorizations.

-   Requests for access to data through an API should be communicated in a JSON
    structure, as specified in the *GA4GH Authentication and Authorization
    Infrastructure* (AAI) standard [9], and should include, at a minimum: (1)
    the authenticated identity and attributes of the requester (packaged in
    OpenID Connect tokens, using GA4GH *Researcher Identity* semantics [12]);
    (2) identification of requested resource; and (3) a description of intended
    use, represented in accordance with *GA4GH Data-Use* semantics [11].

-   As a prerequisite to obtaining data access, each data service consumer
    should have attested that (1) data will be used only by the authorized
    requester; and (2) any data persisted on a user device will be disposed of
    in accordance with the *Privacy and Security Policy*.

-   Each service provider is responsible for assigning to each service consumer
    the minimum access rights and privileges necessary for the requested use,
    consistent with the user’s authenticated identity, attributes, and context.

-   Each service provider is responsible for configuring service APIs and
    service platforms so that they allow access consistent with the *Privacy and
    Security Policy* and the *GA4GH AAI Standard*, while blocking inappropriate
    uses and accesses.

-   OpenID Connect tokens issued by trusted identity providers or brokers may be
    used as a basis for authorizing service consumers access rights and
    privileges. For example, a Research Passport issued through the UK National
    Institute of Health Research (NIHR) Research Passport System [13], might be
    used as the basis for authorizing researchers access rights and privileges
    to passport holders.

-   Each service provider should provide publicly accessible documentation of
    its policies and procedures for adjudicating requests for access to data and
    services.

   ### **3.3 Privacy Protection**

-   Each data steward and service provider should use consent-management, access
    control, usage monitoring, auditing mechanisms, and other privacy-protecting
    mechanisms to help ensure that private and sensitive data are collected,
    used, shared, and reused only in accordance with the permissions granted by
    the individual (or authorized representative) to whom the data pertain, and
    in accordance with applicable law and institutional policies. Private and
    sensitive data include both personal data, such as genomic and
    health-related data, and data considered private and confidential by the
    data holder or jurisdictional law, such as, for example, data governed under
    the European General Data Protection Regulation (GDPR) [14], under the
    Health Insurance Portability and Accountability Act (HIPAA) [15], under
    appendix J of the Security and Privacy Controls for Federal Information
    Systems and Organizations [16], under the Australian Information
    Commissioner Act (AICA) [17], or any other similar law.

-   Each data steward should ensure that any procedures used to eliminate or
    minimize direct and/or indirect identifiers from data (e.g.,
    pseudonymisation, de-identification, anonymisation) are performed at the
    earliest practical point in the workflow to minimize potential exposure of
    individual identity.

-   Each data steward should maintain a data inventory that includes defined
    sensitivity of data, restrictions on storage and data flows, and contracted
    data services responsible for enforcing these restrictions.

-   Each data steward should monitor data usage to detect attempts to access or
    use data other than as authorized, including attempts to analytically derive
    identity.

-   Each data steward and data service provider should implement mechanisms to
    prevent the identity of individuals from being leaked through covert means
    such as metadata, URLs, message headers, and inference attacks.

-   Each data steward and data service provider should implement safeguards to
    reduce the likelihood that de-identified, pseudonymized, or anonymised data
    can be re-identified through the query results or data record linkage (to
    prevent attacks such as Bustamante [18] and Homer [19]). The use of
    privacy-preserving record linkage methods [20] and/or any other methods to
    ensure differential privacy [21] are encouraged.

-   Each data steward is responsible for obtaining the individual authorisations
    (e.g., consents) required by applicable law and institutional policy, and
    for conveying these authorisations, or a link to these authorisations, along
    with the associated data.

-   Each data steward is responsible for updating provenance and confidentiality
    metadata associated with the data under its control, preferably using HL7
    FHIR provenance [22] and confidentiality [23] codes.

### **3.4 Audit Logs**

-   Each service provider is responsible for recording and maintaining a log of
    security- relevant events involving access to or use of application and data
    services under that provider’s control.

-   For each security-relevant event, the service provider should record the
    following data elements: user identity, type of event, date and time,
    success or failure indication, origination of event, name of affected data,
    system component, or resource [24].

-   Each service provider should retain the audit log history for at least one
    year, with a minimum of three months immediately available for analysis (for
    example, online, archived, or restorable from backup). This best practice
    should be interpreted within the constraints of applicable law.

-   Each service provider is responsible for monitoring activity on systems and
    networks under its control to detect potential security breaches and data
    misuse.

-   Each service provider should have a layered approach to instrumentation
    including, but not exclusive to;

    -   Log analysis

    -   Exception handling analysis

    -   Web Application Firewalls/Intrusion Detection Systems

-   Service providers’ audit log records should be integratable with existing
    enterprise security monitoring tools.

-   Data stewards and their service providers are jointly responsible for
    implementing the capability to generate an accounting of accesses to and
    disclosures of data that may be associated with the individual’s identity.

   ### **3.5 Data Integrity**

-   Each service provider is responsible for protecting the integrity of genomic
    and health- related data that it holds, uses, or transmits.

-   Each service provider that transmits or receives transmissions containing
    genomic or health-related data is encouraged to use any collision-resistant
    hash function that complies with the Secure Hash Standard [25] by NIST
    (e.g., IETF SHA-2 [26]) to verify the integrity of the transmission.

-   Each data steward is responsible for ensuring the accuracy and verifiability
    of data and associated metadata.

-   Each data steward is responsible for assuring that data provenance
    information is associated with data made available to service consumers.

-   Each service provider who distributes software will ensure that it is free
    from malicious code prior to making it available for distribution.

   ### **3.6 Non-repudiation**

-   Each service provider will have the capability to digitally sign content
    using a qualified electronic signature, as defined in Regulation (EU)
    No 910/2014 of the European Parliament and of the Council of 23 July 2014 on
    electronic identification and trust services for electronic transactions in
    the internal market and repealing Directive 1999/93/EC [7].

-   GA4GH participants who offer downloadable software will digitally sign the
    downloadable files using a qualified electronic signature, as defined in
    Regulation (EU) No 910/2014 of the European Parliament and of the Council of
    23 July 2014 on electronic identification and trust services for electronic
    transactions in the internal market and repealing Directive 1999/93/EC [7].

### **3.7 Cryptographic Controls**

-   Each stakeholder will ensure that any cryptographic controls used are
    compliant with all applicable standards, agreements, laws, and regulations.

-   Each stakeholder that stores genomic or health-related data will use strong
    encryption (cryptography based on industry-tested and accepted algorithms,
    along with strong key lengths and proper key-management practices) to
    encrypt the data for storage [27].

-   Each stakeholder will ensure that plaintext data encryption keys are stored
    outside the system in which data encrypted with those keys are persisted.
    When a key hierarchy is used, plaintext key encryption keys should be stored
    separately on the system storing data encryption keys.

-   Service providers are encouraged to use privacy-preserving encryption
    methods (e.g., homomorphic encryption [28], secure multi-party computation
    [29]) when applicable and practical.

   ### **3.8 Communications Security**

-   Each service provider will ensure that communication channels are secured
    commensurate with the level of risk associated with the content being
    transmitted.

-   Each service provider that transmits unencrypted genomic or health-related
    data will protect its transmission (e.g., using IPsec [30, 31] or Transport
    Layer Security (TLS) protocol [32]).

-   Any electronic mail containing genomic, health-related, or other sensitive
    data will be secured (e.g., using S/MIME Version 2 [33, 34]).

   ## **4. Operational Assurances**

   ### **4.1 Physical and Environmental Security**

-   Each stakeholder who stores or processes genomic or health-related data is
    responsible for providing physical and environmental safeguards to protect
    those data in accordance with applicable laws and regulations, institutional
    policies, and individual consents.

-   Each stakeholder who uses a third party to store or process genomic or
    health-related data is responsible for assuring that business agreements
    include an obligation to provide physical and environmental data protection.

### **4.3 Service Assurances**

All data, application, and infrastructure service providers to the GA4GH
community are responsible for implementing appropriate defense-in-depth
architectural assurances that will enable them to provide a high level of
service expectations, including:

-   *Availability* – the service should be able to perform its functions over a
    specified period of time, generally expressed as the proportion of time that
    a service is actually available within an agreed-upon time period.
    Availability is ensured through architectural and design features, and
    operational procedures that enhance reliability, maintainability,
    serviceability, resiliency, and security safeguards.

-   *Scalability (or elasticity)* – genomic and health-related data stores
    should be capable of expanding as the volume of data continues to grow,
    while protecting the confidentiality, integrity, and availability of data
    and application services.

-   *Infrastructure security* – security features and processes provided as part
    of the data or application service offering GA4GH service providers and user
    organizations should ensure that their networks, operating systems,
    applications, and database management systems isolate software processes and
    datasets to prevent interference and side-channel attacks. A “least
    privileges” approach should be used to harden execution environments.

-   *Code security* - providers who publish code should make sure that secrets
    are never in the code. Code should be checked for downstream library
    vulnerability (“supply chain attack”). Code should have an approval process
    before promotion (“protected branches”) and should be signed.

-   *Data backup* – all genomic and health-related data, critical data or data
    deemed vulnerable should be copied to a secure accessible secondary location
    and preserved in case original data are corrupted, deleted, lost, or altered
    in any way. Backups are ensured through regular copying of full databases
    and incremental data backup jobs of modified or newly created data.

-   *Disaster recovery* – the ability to restore the availability and
    accessibility of genomic and health-related data or data deemed critical in
    a timely manner should a natural disaster or security breach occur.

-   *Data retention* – the period of time that data should be retained is
    contingent on applicable jurisdictional law and institutional policy.
    Archived data should be retained for no longer than is necessary before
    being deleted to minimize the risk of a breach of data.

-   *Data destruction* – ensure that all information that has reached its
    end-of-life (as applicable under jurisdictional law) is destroyed safely and
    permanently to minimize storage and an organization’s risk to a breach of
    data.

Thus:

-   Data stewards should ensure that their service suppliers offer the levels of
    availability, scalability, and infrastructure security necessary to protect
    the data entrusted to them. Similarly, service consumers should ensure that
    data and application services and platforms, including their own personal
    devices, are trustworthy.

-   Each data service provider is responsible for assuring that data are
    transmitted, persisted, and protected in compliance with all applicable
    legal and ethical requirements.

-   At the request of an individual whose data are being stored and shared
    within the GA4GH community, the responsible data steward should provide the
    individual information about how and by whom their data are being accessed
    and used and for what purposes.

-   Data stewards should provide traceability and proof of conduct for all data
    destroyed, particularly when outsourcing this effort to third parties.

-   Each data steward will document the privacy and security practices and
    procedures it uses to make its data and services available within the GA4GH
    community, consistent with the *GA4GH Privacy and Security Policy*, and will
    ensure that its service providers make this documentation conveniently
    available to service consumers and to individuals who contribute their data.

-   Each data steward will document the behavioral standards associated with the
    use of data and services made available to service consumers, consistent
    with GA4GH *Privacy and Security Policy*, and will require service consumers
    to attest to their understanding of, and commitment to adhere to these
    standards.

-   Each service provider will implement privacy and security technology to
    support adherence to the Fair Information Practices Principles, as
    articulated in Part Two of the Organisation for Economic Co-operation and
    Development (OECD) *Guidelines on the Protection of Privacy and Transborder
    Flows of Personal Data* [35].

-   Each service provider will document and enforce written operational
    procedures for protecting the confidentiality and integrity of data, the
    availability of services, and the privacy of individuals who contribute
    their personal data.

   ### **4.4 Information Security Oversight and Accountability**

-   Each GA4GH team that proposes a standard work product will complete an
    initial security risk-assessment at the start of product development.
    Prerequisite to approval as a GA4GH standard, the product will undergo a
    security evaluation that will include a final security risk assessment
    review and assurance testing, as appropriate.

-   Each stakeholder will have documented procedures for monitoring system
    activities, detecting potential threats and vulnerabilities (vulnerability
    reporting), and responding to potential security incidents (breach
    response).

-   Each service provider is strongly encouraged to engage an independent third
    party to conduct penetration testing of its service infrastructure at least
    annually. Any necessary remediation activities should be conducted as
    quickly as possible, and subjected to both functional and assurance testing.

-   Each stakeholder will investigate and resolve security incidents, breaches,
    and reported threats as quickly as possible so as to minimize potential
    damage to individuals, data loss, disruption of data and application
    services.

-   Each stakeholder will report and respond to its breaches in a way consistent
    with the *GA4GH Breach Response Strategy* [36], in particular:

    -   Each stakeholder will report to applicable regulatory authorities or
        identified responsible actors any breaches resulting in the potential
        disclosure of genomic or health-related data

    -   Each stakeholder will report to GA4GH any breaches associated with the
        use of GA4GH standards and breaches that could damage the reputation and
        trustworthiness of the GA4GH community.

    -   Each service provider who experiences or suspects a data breach
        involving the disclosure of potentially identifiable data is responsible
        for expeditiously reporting the breach to the data steward responsible
        for the breached data.

    -   Each service consumer who experiences or suspects a data breach
        involving the disclosure of potentially identifiable data is responsible
        for expeditiously reporting the breach to the relevant institutional
        supervisory authority and to the data steward.

    -   Each data steward who experiences, suspects, or receives a report of a
        data breach involving the disclosure of potentially identifiable data is
        responsible for expeditiously reporting the breach to the individuals
        whose data were breached.

    -   Each data steward should work with its service providers to assess risks
        associated with the storage, use, and transmission of genomic and
        health-related data, and should contractually require appropriate
        technical mechanisms and procedures for preventing, detecting, and
        recovering from data breaches, consistent with the assessed risks.

### **4.5 Regulatory and Policy Compliance**

-   Each stakeholder is individually responsible for implementing protections
    consistent with this infrastructure, and for assuring that contracts with
    third parties address the business partners’ obligations to implement such
    protections.

-   Each stakeholder will implement appropriate security procedures to ensure
    compliance with applicable legislative, regulatory, and contractual
    requirements relating to the use of genomic or health-related data, and
    personal information.

-   Each stakeholder will implement appropriate security procedures to ensure
    compliance with applicable legislative, regulatory, and contractual
    requirements relating to intellectual property rights.

-   Each stakeholder is responsible for implementing, and attesting to having
    implemented, security and privacy processes, procedures, and technology to
    enforce compliance with relevant legislation, regulations, contractual
    clauses, and the *GA4GH Privacy and Security Policy.*

-   GA4GH stakeholders may individually or collectively engage third parties to
    assess compliance with the GA4GH *Security Technology Infrastructure*, and
    to evaluate the effectiveness of implemented protections.

## **5. References**

[1] Global Alliance for Genomics and Health. *Privacy and Security Policy.* 26
May 2015. Available from
<https://www.ga4gh.org/wp-content/uploads/Privacy-and-Security-Policy.pdf>
(accessed 23 April 2019).

[2] Global Alliance for Genomics and Health. *Framework for Responsible Sharing
of Genomic and Health-Related Data*. 10 September 2014. Available from
<https://www.ga4gh.org/genomic-data-toolkit/regulatory-ethics-toolkit/framework-for-responsible-sharing-of-genomic-and-health-related-data/>
(accessed 23 April 2019).

[3] International Organisation for Standardisation/International
Electrotechnical Commission. ISO/IEC 27001:2013. *Information technology –
Security techniques – Information security management systems – Requirements.*
2013. Available from <https://www.iso.org/standard/54534.html> (accessed 23
April 2019).

[4] U.S. National Institute of Standards and Technology. NIST Special
Publication 800-53 Rev 4. Security and privacy controls for federal information
systems. June 2017. Available from
<https://csrc.nist.gov/publications/detail/sp/800-53/rev-4/final> (accessed 23
April 2019).

[5] From March 2014 meeting of Global Alliance Security Working Group.

[6] OWASP Top 10 - 2017 The Ten Most Critical Web Application Security Risks.
Available from
<https://www.owasp.org/images/7/72/OWASP_Top_10-2017_%28en%29.pdf.pdf> (accessed
23 April 2019).

[7] European Commission. Regulation (EU) No 910/2014 of the European Parliament
and of the Council of 23 July 2014 on electronic identification and trust
services for electronic transactions in the internal market and repealing
Directive 1999/93/EC. Available from
<https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=uriserv%3AOJ.L_.2014.257.01.0073.01.ENG>
(accessed 23 April 2019).

[8] Grassi, P, ME Garcia, and JL Fenton. NIST Special Publication 800-63,
Revision 3: Digital identity guidelines. US National Institute of Science and
Technology. June 2017. DOI: 10.6028/NIST.SP.800-63-3. Available from
<https://pages.nist.gov/800-63-3/sp800-63-3.html> (accessed 23 April 2019).

[9] Authentication and Authorization Infrastructure standard (AAI). Currently
under submission to the GA4GH Product Review Committee.

[10] OpenID Connect. Available from <http://openid.net/connect/> (accessed 26
April 2019).

[11] Data Use Ontology standard (DUO). Developed by the GA4GH Data Use and
Researcher Identities (DURI) Work Stream. Available from
<https://github.com/EBISPOT/DUO> (accessed 13 June 2019)

[12] Researcher Identity Standard (RI). Developed by the GA4GH Data Use and
Researcher Identities (DURI) Work Stream with the collaboration of the Data
Security (DSWS) and Regulatory and Ethics Work Streams (REWS). Available from
<https://ga4gh-duri.github.io/> (accessed 13 June 2019)

[13] UK National Institute of Health Research. The research passport and
streamlined human resources arrangements. Available from
<https://www.nihr.ac.uk/about-us/CCF/policy-and-standards/research-passports.htm>
(accessed 23 April 2019).

[14] European Union. General Data Protection Regulation. Available from
<https://eur-lex.europa.eu/eli/reg/2016/679/oj> (accessed 23 April 2019).

[15] United States of America. Health Insurance Portability and Accountability
Act. <https://www.hhs.gov/hipaa/index.html> (accessed 23 April 2019).

[16] Security and Privacy Controls for Federal Information Systems and
Organizations, appendix J, page 437.
<https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-53r4.pdf>
(accessed 3 June 2019).

[17] Australia. The Australian Information Commissioner Act 2010 (AICA).
Available from <https://www.legislation.gov.au/Series/C2010A00052> (accessed 13
June 2019)

[18] Shringarpure, Suyash S; Bustamante, Carlos D: [Privacy Risks from Genomic
Data-Sharing Beacons.](https://www.ncbi.nlm.nih.gov/pubmed/26522470) The
American Journal of Human Genetics, pp. 1–16, 2015, ISSN: 00029297.

[19] Nils Homer; Szabolcs Szelinger; Margot Redman; David Duggan; Waibhav Tembe;
Jill Muehling; John V. Pearson; Dietrich A. Stephan; Stanley F. Nelson; David W.
Craig: [Resolving Individuals Contributing Trace Amounts of DNA to Highly
Complex Mixtures Using High-Density SNP Genotyping
Microarrays.](https://www.ncbi.nlm.nih.gov/pubmed/18769715) PLoS Genet, 4 (8),
pp. e1000167, 2008.

[20] Vatsalan, D, Christen, P, and Verykios, V S. [A taxonomy of
privacy-preserving record linkage
techniques.](https://doi.org/10.1016/j.is.2012.11.005) Information Systems.
38:6:946-969. Sept 2013

[21] Cynthia Dwork, [Differential
Privacy](https://www.utdallas.edu/~muratk/courses/privacy08f_files/differential-privacy.pdf),
in Automata, Languages and Programming, pp. 1--12, Springer, Berlin, Heidelberg,
2006

[22] Health Level Seven. Resource provenance – Content. Available from
<http://www.hl7.org/implement/standards/fhir/provenance.html> (accessed 23 April
2019).

[23] Health Level Seven. HL7 v3 Code System Confidentiality. Available from
<http://hl7.org/implement/standards/fhir/v3/Confidentiality/> (accessed 23 April
2019).

[24] Payment Card Industry Security Standards Council. Framework for a robust
payment card security process. Available from
<https://www.pcisecuritystandards.org/document_library?category=pcidss&document=pci_dss>
(accessed 23 April 2019).

[25] Secure Hash Standard by NIST. Availabe from
<https://www.nist.gov/publications/secure-hash-standard> (accessed 23 April
2019).

[26] Internet Engineering Task Force. IETF Request for Comment (RFC) 6668. SHA-2
data integrity verification for the secure shell (SSH) transport layer protocol.
Available from <http://tools.ietf.org/html/rfc6668> (accessed 23 April 2019).

[27] Barker Elainer, Roginsky Allen. [Transitioning the Use of Cryptographic
Algorithms and Key
Lengths.](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-131Ar2.pdf)
NIST Special Publication 800-131A Revision 2, March 2019

[28] Martin Albrecht and Melissa Chase and Hao Chen and Jintai Ding and Shafi
Goldwasser and Sergey Gorbunov and Shai Halevi and Jeffrey Hoffstein and Kim
Laine and Kristin Lauter and Satya Lokam and Daniele Micciancio and Dustin Moody
and Travis Morrison and Amit Sahai and Vinod Vaikuntanathan, [Homomorphic
Encryption Security
Standard](http://homomorphicencryption.org/wp-content/uploads/2018/11/HomomorphicEncryptionStandardv1.1.pdf).
From [homomorphicencryption.org](http://homomorphicencryption.org/), Toronto,
Canada, November 2018

[29] Fattaneh Bayatbabolghani, and Marina Blanton, [Secure Multi-Party
Computation](http://delivery.acm.org/10.1145/3270000/3264419/p2157-bayatbabolghani.pdf?ip=128.179.151.184&id=3264419&acc=ACTIVE%20SERVICE&key=FC66C24E42F07228%2E7E17DDD1CCA0F75B%2E4D4702B0C3E38B35%2E4D4702B0C3E38B35&__acm__=1560330720_78f5ea35d83ebbbc882da4646172a7d7),
Proceedings of the 2018 ACM SIGSAC Conference on Computer and Communications
Security (CCS '18), Toronto, Canada, 2018

[30] Internet Engineering Task Force. Security architecture for the internet
protocol. RFC 4301. December 2005. Available from
<http://tools.ietf.org/html/rfc4301> (accessed 23 April 2019).

[31] Internet Engineering Task Force. Using advanced encryption standard (AES)
CCM mode with IPsec encapsulating security payload (ESP). RFC 4309. December
2005. Available from <http://tools.ietf.org/html/rfc4309> (accessed 23 April
2019).

[32] Internet Engineering Task Force. The transport layer security protocol,
Version 1.2. RFC 5246. August 2008. Available from
<http://tools.ietf.org/html/rfc5246> (accessed 23 April 2019).

[33] Internet Engineering Task Force. S/MIME Version 2 message specification.
RFC 2311. March 1998. Available from <http://tools.ietf.org/html/rfc2311>
(accessed 23 April 2019).

[34] Internet Engineering Task Force. S/MIME Version 2 certificate handling. RFC
2312. Available from <http://www.ietf.org/rfc/rfc2312.txt> (accessed 23 April
2019).

[35] Organisation for Economic Development and Cooperation. OECD Guidelines on
the protection of privacy and transborder flows of personal data. 11 July 2013.
pp. 14-15. Available from
[http://www.oecd.org/sti/ieconomy/2013-oecd-privacy-guidelines.pdf](http://www.oecd.org/sti/ieconomy/2013-oecd-privacy-guidelines.pdf%20(06)
(accessed 23 April 2019)

[36] Breach Response Protocol. Currently under submission to the GA4GH Product
Review Committee.
