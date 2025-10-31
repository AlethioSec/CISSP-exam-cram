# 1.1 Understand, adhere to, and promote professional ethics

This is the basics of ISC2, you can get a free exam questions if you know this easy concepts. [^1]

**Preamble:** Understand that safety of the commonwealth, **duty to principals**, and to the profession are of paramount concern.

**The Four Canons:** Memorize and understand the intent of each.

1. **Protect the Society, the Commonwealth, and the Infrastructure.**
2. **Act honorably, honestly, justly, responsibly, and legally.**
3. **Provide diligent and competent service to principals.**
4. **Advance and protect the profession.**

 **Adherence and Promotion:** Know your obligation to **report any unethical conduct** by another (ISC)$^2$ member to avoid being in violation yourself.


>[!Important] ProTip
>You can get a free question just by knowing the canons

## Ethics Violation

The only complaints to be considered will be the ones that specify the canon of our ISC2 Code of Ethics that has been violated.

**Complaints by Canon Eligibility:**

- **Canons I and II**: Open to complaints from any member of the public.
- **Canon III**: Only principals—such as employers or contractors—are authorized to file complaints.
- **Canon IV**: Complaints may only be submitted by other professionals who are certified or licensed and adhere to a recognized code of ethics

>[!info]
>All complaints must be in writing, two copies must be submitted, one in written form one in PDF. 
# 1.2 Understand and apply security concepts

The 5 pillars of Information Security

- **Confidentiality, Integrity, and Availability (CIA Triad):**     
    - **Confidentiality:** Preventing unauthorized disclosure (e.g., encryption, access control).
    - **Integrity:** Preventing unauthorized modification (e.g., hashing, digital signatures, change control).
    - **Availability:** Ensuring timely and uninterrupted access (e.g., redundancy, fault tolerance, backups, disaster recovery).
- **Authenticity:** refers to the assurance that information, communications, or entities are genuine and originate from a verified source. (Digital Signature, hashing, etc.)
- **Non-Repudiation:** Assurance that a party cannot successfully deny the **authenticity** of their signature on a document or the sending of a message (achieved primarily through **digital signatures**).

# 1.3 Evaluate and apply security governance principles

**How security aligns with and supports business goals.**

**Alignment with Business Goals:** Security must be a **business enabler**, not a roadblock. Security governance ensures resources are allocated to managing risks aligned with business priorities.

**Governance Components:**

Organizational Structure: Security Steering Committees, roles (CISO, Data Owner, Custodian, User).
Roles and Responsibilities: Clearly define who is **Accountable, Responsible, Consulted, and Informed (RACI chart)** for security decisions.

**Security control frameworks.**

| Framework                                                              | Description                                                                                                                                               |
| ---------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ISO/IEC 27001 & 27002 (International Organization for Standardization) | Establishes a global standard for Information Security Management Systems (ISMS).                                                                         |
| NIST (National Institute of Standards and Technology)                  | Federal compliance, critical infrastructure protection, and adaptable security controls. (Compliance is often only required for USA government agencies). |
| COBIT (Control Objectives for Information and Related Technology)      | Governance and management of enterprise IT. Aligns IT goals with business objectives, emphasizing performance, accountability, and control.               |
| SABSA (Sherwood Applied Business Security Architecture)                | Business-driven security architecture. Used for designing security architectures that align with business requirements and risk management.               |
| PCI DSS (Payment Card Industry Data Security Standard)                 | Protect cardholder data and reduce credit card fraud. Required for any organization that stores, processes, or transmits credit card data.                |
| FedRAMP (Federal Risk and Authorization Management Program)            | Standardized approach to security assessment and authorization for cloud services used by U.S. federal agencies.                                          |


>[!Important] ProTip
>Questions should give you enough context to know witch region should you focus on appliable frameworks.


- **Due Diligence**: _Investigate before acting._ It’s the process of identifying risks, gathering intelligence, and making informed decisions.
- **Due Care**: _Act responsibly after deciding._ It’s the implementation of safeguards and controls to prevent harm and ensure compliance.

# 1.4 Understand legal, regulatory, and compliance issues that pertain to information security in a holistic context

Focus on the context and jurisdiction of various laws and regulations.
You need to have an **Holistic understanding** how laws, regulations, and standards interact globally.
## Cybercrimes and Data Breaches

You need to know the types of cybercrime and how they will affect your organization, as well as how to respond to every type of it.

Types of crimes:

- DDoS
- Malware
- Ransomware
- Fraud
- Data violation
- Etc.

Industry and Financial Compliance:

- **PCI DSS:** Applies to any organization that stores, processes, or transmits **Cardholder Data**.
- **SOX (Sarbanes-Oxley Act):** Focus on the financial reporting integrity of public companies, requiring security controls over financial data and access.

 ## Licensing and Intellectual Property (IP)

Licensing Contracts that grant permission to use _software_ or technology under specific conditions. You must ensure **license compliance** to avoid fines or lawsuits (e.g., preventing _software_ piracy or misuse of open-source licenses).

- **Copyright:** Protects the **expression of ideas** (source code, books).
- **Trademark:** Protects **brand identity** (logos, slogans).
- **Patent:** Protects **inventions** (how things work).
- **Trade Secret:** Protects confidential business information (e.g., the formula for Coca-Cola).

>[!Important] ProTip
>You need to know the difference between the IP symbols.
>

| **Symbol**        | **Name**                               | **Legal Meaning**                                                                                                                                     | **What it Protects**                                                                                    |
| ----------------- | -------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| **©**             | **Copyright Symbol**                   | Indicates that a work is protected by copyright law and that only the copyright holder has the right to copy, distribute, or adapt the work.          | **Original works of authorship**, such as books, music, art, film, photographs, and **source code**.    |
| **™**             | **Unregistered Trademark** (Trademark) | Used by a business to claim exclusive rights to a mark, even if registration is pending or has not yet been filed.                                    | **Brands**, names, words, slogans, or logos used to identify a product or service.                      |
| **®**             | **Registered Trademark**               | Indicates that the mark is officially registered with the national trademark office (e.g., USPTO in the U.S.). This grants stronger legal protection. | **Brands**, names, words, slogans, or logos that are **officially registered**.                         |
| **℠**             | **Service Mark**                       | Used to identify and distinguish the source of a service, rather than a product.                                                                      | **Services** offered by a business (e.g., banking, transportation, cleaning).                           |

## Import/Export Controls

These controls regulate the cross-border transfer of certain technologies for reasons of national security or foreign policy.

**Cryptography:** This is the main focus in information security. Many countries (including the U.S. in the past) have classified strong encryption _software_ and _hardware_ as **"munitions" or weapons** and are therefore subject to strict export controls.
A company that develops or uses robust encryption solutions must ensure compliance with the **Wassenaar Arrangement** regulations and U.S. export laws, especially if operating internationally.

## Transborder Data Flow

Rules governing where and how personal data can be transferred outside the country where it was collected.

Countries (especially those in the European Union under GDPR) aim to ensure that the personal data of their citizens maintains an **adequate level of protection** when transferred to other jurisdictions.

**Compliance Mechanisms (GDPR):** For transferring EU data to a third country, mechanisms like the following are required:
	**Standard Contractual Clauses (SCCs):** Standardized model agreements.
	**Binding Corporate Rules (BCRs):** EU-approved internal policies for transfers within a corporate group.
	**Adequacy Decisions:** Determination by the European Commission that a third country offers an "essentially equivalent" level of protection to that of the EU.

China enforces a comprehensive legal framework through several key laws:
- **Cybersecurity Law (CSL)**
- **Data Security Law (DSL)**
- **Personal Information Protection Law (PIPL)**

## Issues Related to Privacy

Vital section focused on the protection of personal data. A CISSP professional must know the key laws that establish the rights of the data subject and the obligations of the controller/processor.

- **General Data Protection Regulation (GDPR) (EU):**
    - **Scope:** Global (applies to any entity processing data of EU residents, regardless of the entity's location).
    - **Key Concepts:** Right to be forgotten, _Privacy by Design_, explicit consent, and 72-hour breach notifications.
- **California Consumer Privacy Act (CCPA) (US):**
    - **Key Concept:** Grants consumers the right to know what data is collected about them and the right to opt-out of the sale of their information.
- **Personal Information Protection Law (PIPL) (China):**
    - **Key Concept:** One of the strictest privacy laws, requiring specific and individual consent for data processing and applying strict controls to the transfer of data outside of China.
- **Protection of Personal Information Act (POPIA) (South Africa):**
    - **Key Concept:** Establishes eight minimum conditions for the lawful processing of personal information, including **accountability** and security.


## Contractual, Legal, Industry Standards, and Regulatory Requirements

Compliance extends beyond government laws.

- **Legal Requirements:** Refer to statutes or laws enacted by government bodies (such as GDPR, HIPAA, SOX).
- **Regulatory Requirements:** Rules and guidelines issued by regulatory bodies (such as the Mexican National Banking and Securities Commission or the SEC in the US) to implement laws.
- **Industry Standards:** Rules that are not laws, but their compliance is **mandatory** for operating in certain sectors.
    - **PCI DSS (Payment Card Industry Data Security Standard):** An obligatory security requirement for any entity that stores, processes, or transmits payment card data.
    - **ISO/IEC 27001:** An international standard providing a framework for an Information Security Management System (ISMS).
- **Contractual Requirements:** Security obligations imposed through commercial agreements, especially with **third parties and vendors** (via Service Level Agreements - SLAs or Data Processing Addendums - DPAs). These legally commit the parties to maintaining a certain level of security (e.g., the cloud provider must be ISO 27001 compliant).

# 1.5 Understand requirements for investigation types (i.e., administrative, criminal, civil, regulatory, industry standards)

Know the purpose and required procedures for different legal and internal investigations.

- **Administrative/Internal:** Deals with internal policy violations (e.g., improper use of company email). Lower standard of evidence.
- **Criminal:** Deals with violations of criminal law (e.g., theft, hacking). Highest standard of evidence (**beyond a reasonable doubt**). Requires law enforcement involvement.
- **Civil:** Deals with harm to individuals or organizations (e.g., contract disputes, wrongful termination). Standard of evidence is **preponderance of the evidence**.
- **Regulatory/Compliance:** Deals with violations of laws or industry standards (e.g., HIPAA, GDPR, PCI DSS). Often leads to fines or sanctions.
- **Key Security Role:** The security team's role in any investigation is **Forensic Data Collection**—ensuring the chain of custody is maintained and evidence is non-repudiable.

# 1.6 Develop, document, and implement security policy, standards, procedures, and guidelines

|**Document**|**Description**|**Example**|
|---|---|---|
|**Policy**|**High-level statement** of management's intent and expectations (Mandatory).|"All users must use strong passwords."|
|**Standards**|**Mandatory specific requirements** regarding hardware, software, or configuration.|"All passwords must be 12 characters long and use complexity."|
|**Procedures**|**Detailed, step-by-step instructions** for performing a specific task (Mandatory).|"Step 1: Click Start. Step 2: Click Control Panel..."|
|**Guidelines**|**Recommendations/best practices** that are not mandatory (Optional).|"Consider changing your password every 90 days."|

# 1.7 Identify, analyze, assess, prioritize, and implement Business Continuity (BC) requirements

**Business Continuity Planning (BCP)** is the strategic process of **assessing risks** to critical organizational functions and **developing plans, policies, and procedures** to ensure the **continuous operation** of the business during and after a disruptive event. The primary goal of BCP is to implement effective measures that **minimize the total impact** of a potential incident on the organization.


- **Business Impact Analysis (BIA):** The **first step** in BC/DR planning. Identifies critical functions and the impact of their loss.
- **Key Metrics:**
	- **Maximum Tolerable Downtime (MTD):** The absolute maximum time a business function can be down before the organization suffers unacceptable loss.
	- **Recovery Time Objective (RTO):** The target time for a business process to be restored after a disaster. **(RTO $\le$ MTD)**.
	- **Recovery Point Objective (RPO):** The maximum acceptable data loss measured in time (e.g., 4 hours).
- **Disaster Recovery (DR) Plan:** Focuses on the **IT restoration** to meet the RTO/RPO requirements defined by the BIA.
- **Business Continuity (BC) Plan:** Focuses on **sustaining critical business processes** during and after a disruption (including people, facilities, and IT).

>[!info] BCP team selection
>The team must be conformed by cross functional members of the organization to avoid missing areas.


# 1.8 Contribute to and enforce personnel security policies and procedures

Security practices applied to employees from hire to departure.

## Candidate Screening and Hiring Security Controls

This process involves several layers of due diligence to validate a candidate's background and suitability for the role.

### Security in the Hiring Process

The security team's contribution starts long before the background check and includes:

- Job Description Security: Ensuring the job description clearly states the **security clearance, certification (e.g., CISSP, CISM), and/or technical experience** required. It also sets the stage for defining the **Least Privilege** access the role will require.
- Non-Disclosure Agreements (NDAs): Requiring candidates for sensitive roles to sign an NDA _before_ they are exposed to any proprietary information, even during the interview process.
- Background checks: A thorough background investigation is a mandatory security control used to verify a candidate's suitability and mitigate potential risks.

### Onboarding, transfers, and termination processes

They represent key moments when an employee's access and responsibilities change, and if not managed correctly, they introduce significant **insider threat risks** to the organization.

- **Employment:** **Job Rotation** (cross-training and fraud prevention), **Mandatory Vacation** (to discover fraud), **Least Privilege**, **Acceptable Use Policy (AUP)**.
- **Termination:** **Offboarding process** is critical: exit interview, revocation of access (physical and logical), return of company assets. Must be swift and coordinated.

# 1.9 Understand and apply risk management concepts

This involves the systematic process of identifying, assessing, and treating risk.

- **Risk Terminology:**
    - **Asset:** Something of value being protected.
    - **Threat:** A potential danger that may exploit a vulnerability.
    - **Vulnerability:** A weakness that can be exploited by a threat.
    - **Risk:** The **probability** of a threat successfully exploiting a vulnerability and the **impact** of that event.
- **Risk Analysis Methods:**
    - **Qualitative:** Subjective assessment using terms (High, Medium, Low). Faster and easier.
    - **Quantitative:** Objective assessment using monetary values. Requires complex calculation. **(ALE = SLE x ARO)**.
        - **Single Loss Expectancy (SLE):** Monetary loss from a single event.
        - **Annualized Rate of Occurrence (ARO):** Expected number of times a threat will occur per year.
        - **Annualized Loss Expectancy (ALE):** Expected monetary loss per year.
- **Risk Treatment/Response:**
    - **Mitigate:** Apply controls to reduce risk (most common).
    - **Transfer:** Shift risk to a third party (e.g., insurance, outsourcing).
    - **Avoid:** Cease the activity that creates the risk.
    - **Accept:** Formally acknowledge the risk and monitor it (often for risks below a certain threshold).

# 1.10 Understand and apply threat modeling concepts and methodologies

Threat modeling is a structured process to identify and prioritize potential threats.
**Purpose:** Proactive identification of design and implementation weaknesses in systems or applications.

- **Methodologies:**
    - **STRIDE (Microsoft):** Focuses on security requirements of a system.
        - **S**poofing, **T**ampering, **R**epudiation, **I**nformation disclosure, **D**enial of service, **E**levation of privilege.
    - **DREAD (Deprecated but useful for understanding):** Focuses on quantifying risk.
        - **D**amage potential, **R**eproducibility, **E**xploitability, **A**ffected users, **D**iscoverability.
    - **P.A.S.T.A.:** Risk-centric approach based on business objectives.
    - **Trike:** Risk-based and focuses on acceptable levels of risk.
- **Process:** Identify assets, identify threats, analyze vulnerabilities, prioritize risks, implement countermeasures.

>[!info] How does it work
>For each component, the team asks, **"Can this component be subjected to Spoofing? Can it be Tampered with? Can it be used for Repudiation?"** and so on.
>Once a potential threat is identified, security controls (countermeasures) are assigned to mitigate or eliminate that threat.


# 1.11 Apply supply chain risk management (SCRM) concepts

Managing the risk introduced by **third-party vendors, suppliers, and partners**.

- **Focus Areas:**
    
    - **Due Diligence/Vendor Selection:** Thoroughly vetting a vendor's security posture _before_ signing a contract.
    - **Contractual Requirements:** Enforcing security clauses, audit rights, and liability/indemnification terms in the Service Level Agreement (SLA).
    - **Ongoing Monitoring:** Regularly reviewing vendor security reports (e.g., SOC 2 reports) and conducting audits to ensure compliance.
    - **Exit Strategy:** Planning for the secure termination of the relationship, including data return/destruction and access revocation.

## Risks Associated with Acquisition from Suppliers

A supplier's weak security posture can become your vulnerability. This extends beyond simple system failures to intentional malice against the supply chain itself.

### 1. Product Tampering (During Production or Transit)

This is the deliberate, unauthorized **modification** of a product or component by someone in the supply chain _before_ it reaches the end-user.

Altering the physical or logical characteristics of hardware, firmware, or software.
**Security Risk:** The tampering may be designed to bypass security controls, introduce backdoors, or enable future exploitation.

### 2. Counterfeits

This involves substituting genuine, secured products with unauthorized, typically lower-quality, and potentially compromised copies.

Products that are fraudulent duplicates of authentic, certified items.
**Security Risk:** Counterfeit components often lack the rigorous testing, security hardening, or quality assurance of the original. They may contain **undocumented vulnerabilities** or cheap components that are easily compromised or fail prematurely, violating the **Integrity** and **Availability** of your system.

### 3. Implants (Hardware and Software)

An implant is a piece of code, hardware, or firmware secretly inserted into a product that serves an unintended, often malicious, purpose.

Covertly installing malicious functions into a product during the manufacturing, distribution, or handling phases.
**Security Risk:** Implants can function as **covert channels** for data exfiltration, backdoors for remote access, or hidden kill switches to compromise the **Confidentiality, Integrity, and Availability** of the system.

## Mitigation through SCRM

To counter these risks, SCRM requires organizations to apply **due diligence** throughout the supplier lifecycle:

- **Security Requirements in Contracts:** Mandatory contractual clauses requiring the supplier to adhere to specific security standards (e.g., ISO 27001, continuous auditing).
- **Source Verification:** Tracking the provenance of all components to ensure they come from approved, trusted sources.
- **Vetting and Audits:** Regularly auditing the supplier's security posture, manufacturing processes, and personnel security controls (the **Right-to-Audit** clause).
- **Testing:** Thoroughly inspecting and testing newly acquired hardware and software (e.g., integrity checks, sandboxing, code review) before deploying them into the production environment.


# 1.12 Establish and maintain a security awareness, education, and training program

Know the difference between the three components and their respective target audiences.

|**Component**|**Goal**|**Audience**|**Focus**|
|---|---|---|---|
|**Awareness**|Change behavior; simple concepts.|**All Personnel**|"Don't click on strange links."|
|**Training**|Teach a skill; specific job knowledge.|**Specific Roles** (e.g., system admin, HR)|How to patch a server; how to handle PHI.|
|**Education**|In-depth, long-term knowledge; often leads to a degree/certification.|**Security Professionals**|CISSP, CISM, formal degrees.|



[^1]: [ISC2 Code of Ethics](https://www.isc2.org/ethics)
