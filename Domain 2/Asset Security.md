# 2.1 - Identify and classify information and assets

## Data classification

Assigning a sensitivity level or category to information based on CIA requirements. It is determined by the **data owner** and is mandatory for defining security controls.

Before securing anything, you must know what you have. This involves:

- **Asset Inventory**: Cataloging all physical and digital assets (e.g., servers, databases, documents).
- **Ownership Assignment**:
	- _Data Owner_: Senior-level individual responsible for classification and access decisions.
	- _Data Custodian_: Implements controls and maintains data security.
	- _Data Users_: Follow handling procedures and respect classification
### Classification Levels 

Classification standards vary between organizations, but they typically fall into one of two categories:

|**Commercial/Private Sector**|**Government/Military**|**Description**|
|---|---|---|
|**Confidential/Proprietary**|**Top Secret/Secret**|Highest level of protection. Loss would cause severe damage to the organization (e.g., trade secrets, source code, highly sensitive PII).|
|**Private**|**Confidential**|Used for internal business data and personal information whose disclosure would cause harm or legal liability (e.g., salaries, medical records).|
|**Sensitive**|**Sensitive But Unclassified (SBU)**|Requires protection but is not highly damaging if disclosed (e.g., internal memos, financial reports).|
|**Public**|**Unclassified**|Disclosure has no financial or security impact (e.g., marketing materials, press releases, public phone numbers).|

### Key Classification Criteria

The classification should address the following questions:

- **Legal & Regulatory Requirements:** What laws govern this data (GDPR, HIPAA, etc.)?
- **Monetary Value:** What is the financial cost if this data is lost or leaked?
- **Integrity Need:** How critical is it that this data remain accurate and unmodified?
## Asset Classification

Asset classification is the process of assigning a criticality level or category to the **hardware, software, or physical resource** that stores, processes, or transmits data. An asset is usually classified based on the **highest level of data** it handles.

### Examples of Asset Classification

|**Asset Type**|**Primary Function**|**Classification Derived From**|
|---|---|---|
|**Database Server**|Stores customer $\text{PII}$ (Private Data).|The server is classified as **Private** or **Confidential** because of the data it hosts.|
|**Desktop Workstation**|Used for accessing internal email and public websites.|Classified as **Internal** or **Sensitive**.|
|**External Firewall**|Protects the entire network.|Classified as **Critical** or **High** due to its role in **Availability** and **Integrity**.|
### Security Implications

The classification of both data and the assets that hold it directly determines the required security controls:

- **Access Controls:** Only personnel with the proper **clearance** (based on their job function) can access data of a corresponding **classification** level.
    
- **Media Handling:** How data is stored, retained, and destroyed (e.g., using encryption for Confidential data, or mandatory shredding for paper copies).
    
- **Labeling:** All assets and data must be clearly labeled according to their classification to ensure consistent handling by all personnel.

# 2.2 - Establish information and asset handling requirements

Translating the formal **data and asset classification** (e.g., Confidential, Private) into mandatory, actionable **controls** for employees and systems, ensuring that assets are protected throughout their entire lifecycle.

## Key Handling Requirements

These requirements dictate _how_ information and assets must be managed to preserve their confidentiality, integrity, and availability.

### Storage Requirements

Data **at rest**.

- **Encryption:** Mandates the use of strong encryption for highly classified data stored on hard drives, databases, or cloud services.
- **Physical Security:** Specifies where physical documents or media must be stored (e.g., in a locked safe, a fireproof vault, or a secure server room).
- **Access Control:** Defines strict logical and physical access lists for servers and storage devices based on the data's classification (Need-to-Know).
- **Data Labeling and Marking:** Mandates the use of visible labels (e.g., "CONFIDENTIAL - Internal Use Only," or "TOP SECRET") on physical documents, electronic files, and even removable media. This is essential because the level of control applied should always match the label.

### Usage and Processing Requirements

Data **in use** (being processed or actively viewed).

- **Least Privilege:** Defines the necessary access controls so that employees can only access the data required for their specific job functions.
- **No Unauthorized Copying:** Prohibits copying highly sensitive data onto unauthorized personal devices (e.g., personal phones or USB drives) or transferring it to non-secured environments.
- **Location:** Restrict access based on location (e.g., office vs. remote).
- **Authentication** Use MFA, strong passwords, and identity verification.
- **Monitoring:** Specifies the logging and monitoring requirements for users accessing and manipulating highly sensitive data.


### Transfer and Transmission Requirements

Data **in transit** (moving across networks).

- **Secure Protocols:** Mandates the use of secure protocols (e.g., $\text{TLS/SSL}$, $\text{IPSec}$ $\text{VPN}$) for transmitting sensitive data across untrusted networks (like the internet).
- **Media Transfer:** Dictates secure methods for physically transferring media (e.g., requiring two-person control for transporting backup tapes).
- **Transborder Data Flow:** Ensures compliance with legal restrictions (like GDPR or PIPL) regarding transferring data outside of the country or region of origin.
- **Data masking/tokenization:** Hide sensitive fields during processing or sharing.

>[!tip]
>Understand the differences and applications of data masking/tokenization

### Retention and Destruction Requirements (The Lifecycle End)

Ensures data is kept only as long as legally or operationally necessary, and then destroyed securely.

- **Retention Schedules:** Defines a timeline for how long different classes of data must be kept to satisfy legal, regulatory, or business needs.
- **Secure Destruction:** Specifies the mandated methods for permanently destroying data based on its classification (e.g., **shredding** for paper, **degaussing** or **physical destruction** for magnetic media, or **secure wiping** for solid-state drives).


# 2.3 - Provision information and assets securely

This involves **allocating, configuring, and protecting assets** from the moment they are introduced into the environment. Key principles include:

- **Security by design**: Embed security controls during planning and provisioning, not after deployment.
- **Least privilege**: Grant only necessary access to users and systems.
- **Secure configuration**: Use hardened baselines, disable unused services, and apply patches.
- **Vendor due diligence**: Assess third-party security practices before procurement.

When deploying a new server for patient records, IT applies encryption, disables unused ports, and restricts admin access via MFA.

## Information and asset ownership

Ownership establishes responsibility and accountability for an asset's protection and usage, which is key to maintaining security controls over time.

- **Data Owner:** The **ultimate responsible party** for classifying the data and defining the security requirements (confidentiality, integrity, availability). This is typically a senior manager or executive who understands the data's business impact and legal obligations (e.g., the Chief Financial Officer for financial data).
- **Data Custodian:** The party responsible for the **physical storage, maintenance, and protection** of the asset on behalf of the owner. This is typically the IT department or security staff who execute the technical controls (e.g., performing backups, managing access controls, applying encryption).
- **Data Processor:** Any entity (often a third-party vendor or cloud provider) that processes data on behalf of the Data Owner or Controller. They are legally obligated to follow the owner's security instructions (GDPR context).
- **Users:** End users who access data to perform their job duties. They are responsible for adhering to all established policies and procedures.
## Asset inventory (e.g., tangible, intangible)

An asset inventory is a comprehensive and essential record of all assets within the organization. It's impossible to secure what you don't know you have.

Provide a complete, up-to-date list of all hardware, software, and data to ensure every item is accounted for and protected according to its classification.

- **Tangible Assets:** Physical items with a measurable value and location. This includes servers, laptops, networking equipment, mobile phones, and physical media (tapes, hard drives).
- **Intangible Assets:** Non-physical assets that possess value and require protection. This includes intellectual property (patents, trademarks, source code), company reputation, and digital identities.
- **Data Inventory:** A sub-set focused specifically on tracking where sensitive data (PII, trade secrets) is created, stored, processed, and transmitted.

## Asset management

Asset management encompasses the full set of processes used to manage and track the assets throughout their entire lifecycle, from acquisition to secure disposal.

- **Acquisition/Provisioning:** Assets must be logged, hardened (configured securely), and tagged **before** they are deployed into the environment. This ensures they meet security standards (e.g., mandatory disk encryption, updated OS).
- **Tracking and Control:** Requires continuous monitoring and auditing of the assets' location, usage, and configuration. This is vital for maintaining compliance and performing rapid incident response.
- **Maintenance:** Ensures that assets receive regular updates, patches, and upgrades to fix vulnerabilities.
- **Secure Disposal (Decommissioning):** The final step in the lifecycle. This mandates that all sensitive data is securely wiped (sanitized or purged) from the asset using approved methods (e.g., degaussing, physical destruction) before the asset is retired or resold.

Asset management ensures assets are tracked, protected, and retired securely.

- **Lifecycle tracking**: From acquisition to disposal
- **Configuration management**: Maintain secure settings and monitor changes
- **Change control**: Formal process for updates and provisioning
- **Separation of duties**: Avoid conflicts of interest in provisioning and approval
- **Monitoring and auditing**: Detect unauthorized changes or access

# 2.4 - Manage data lifecycle


## Data collection

Establishing security at the point of data creation. This includes defining **acceptable data formats**, ensuring legal and regulatory compliance (e.g., obtaining consent for $\text{PII}$), and implementing **input validation** to maintain data integrity from the start.
## Data location

Establish where data is kept, both logically and physically. Controls must ensure data is protected when **at rest** through:

- **Physical Security:** Securing server rooms and storage media.
- **Encryption:** Using techniques like **Full Disk Encryption (FDE)** or database encryption based on the data's classification level.
- **Jurisdictional Compliance:** Ensuring the data's location complies with transborder data flow regulations (e.g., storing EU data only in the EU).
## Data maintenance

All activities required to keep the data current, accurate, and available. This includes:

- **Access Control:** Reviewing and enforcing **Need-to-Know** and **Least Privilege**.
- **Backups:** Creating, securing, and regularly testing data backups to ensure **Availability**.
- **Auditing/Monitoring:** Logging and reviewing access patterns to detect unauthorized data modifications or breaches (Integrity).
## Data retention

Defines how long data must be kept before it can be destroyed. This is a business decision driven by **legal, regulatory, and operational requirements**. A formal **Retention Policy** must be established, often defining different retention periods for different data types (e.g., financial data retained for 7 years, marketing data for 1 year).
## Data remanence

**Residual magnetic or electrical signature** that remains on storage media even after data has been deleted or overwritten. The existence of data remanence means data can often be recovered by an attacker if media is not properly sanitized.
## Data destruction

Data is permanently and securely removed from the storage media to prevent data remanence exploitation. The method used must align with the data's classification:

- **Clearing:** Overwriting media with unclassified data (e.g., zeros). Suitable for lower-classification data.
- **Purging:** A more thorough method (often involving multiple overwriting passes or degaussing) that makes data recovery extremely difficult without laboratory techniques.
- **Destruction:** The most secure method, involving the **physical destruction** of the media (e.g., shredding, incineration, or pulverizing hard drives). Mandatory for highly sensitive or top-secret data.

# 2.5 - Ensure appropriate asset retention (e.g., End of Life (EOL), End of Support)

## End of Life (EOL)

**End of Life (EOL)** refers to the point when a vendor decides to stop marketing, selling, or distributing a product, hardware, or software version.

Once an asset hits EOL, the vendor stops investing in its future development. While the asset may continue to function, it is now considered obsolete from a business and security perspective.
EOL triggers the formal process for the organization to plan the **replacement or migration** of that asset. This phase involves budget planning and choosing a replacement technology.

##  End of Support (EOS)

**End of Support (EOS)** is the most critical security milestone. It refers to the date after which a vendor **will no longer issue patches, security updates, or technical assistance** for a specific product.

Any vulnerability discovered after the EOS date will remain unpatched, creating a permanent, known attack vector. Continuing to use EOS assets exposes the organization to severe risks of compromise, non-compliance, and audit failure.

- **Secure Isolation:** Assets that cannot be immediately replaced (e.g., legacy industrial control systems) must be **isolated** from the main network (e.g., placed on a separate, non-routable network segment) to minimize the risk of exploitation.
- **Mandatory Decommissioning:** For all other assets, EOS mandates **decommissioning** and **secure destruction** (or sanitization) to remove the liability from the network.



# 2.6 - Determine data security controls and compliance requirements

Determining data security controls and compliance requirements involves a systematic process of assessing data's condition, defining the scope, selecting appropriate standards, and deploying specific technological defenses to meet legal and security obligations.

## Data states (e.g., in use, in transit, at rest)

- **At Rest (Storage):** Data residing on non-volatile storage media (hard drives, tapes, cloud storage).
    - **Control Focus:** **Confidentiality** and **Integrity**.
    - **Primary Control:** **Encryption** (Full Disk Encryption, transparent database encryption).
- **In Transit (Transmission):** Data moving across a network (internal LAN, internet, wireless).
    - **Control Focus:** **Confidentiality** and **Integrity**.
    - **Primary Control:** **Secure Protocols** ($\text{TLS/SSL}$, $\text{IPSec}$ $\text{VPN}$) to create a protected tunnel.
- **In Use (Processing):** Data currently loaded into memory ($\text{RAM}$) or being actively processed by a $\text{CPU}$ or application.
    - **Control Focus:** **Confidentiality** and **Integrity**.
    - **Primary Control:** **Access Control** (Least Privilege), **Authorization**, and potentially advanced memory encryption techniques.

## Scoping and tailoring

Before implementing controls, an organization must define its security baseline:

- **Scoping:** The process of **identifying which parts** of a standard or regulatory mandate are applicable to the organization's environment. For example, if a standard has a requirement for physical server rooms, but the organization uses serverless cloud computing, that requirement is "scoped out."
- **Tailoring:** The process of **customizing** the identified controls to fit the specific needs, circumstances, and security posture of the organization. This ensures the controls are effective and cost-efficient.
- **Standards Selection:** Identifying and adopting the necessary compliance frameworks, such as **ISO 27001**, **NIST SP 800-53**, or **COBIT**, to provide a recognized structure for establishing and managing security controls

## Standards selection

Choosing the right frameworks and standards helps align with best practices and regulatory mandates:

**Common Standards**:
- **ISO/IEC 27001**: Information security management systems
- **NIST SP 800-53 / 800-171**: U.S. federal security controls
- **COBIT**: Governance and management of enterprise IT
- **PCI DSS**: Payment card industry data security
- **HIPAA**: Healthcare data protection

Selection depends on industry, geography, data types, and regulatory obligations.

## Data protection methods (e.g., Digital Rights Management (DRM), Data Loss Prevention (DLP), Cloud Access Security Broker (CASB))


| **Method**                              | **Purpose**                                                               | **Example Use Case**                                                |
| --------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| **Digital Rights Management (DRM)**     | Controls access and usage of digital content                              | Prevents unauthorized sharing of licensed media or documents        |
| **Data Loss Prevention (DLP)**          | Detects and blocks unauthorized transmission of sensitive data            | Stops employees from emailing customer PII or copying it to USB     |
| **Cloud Access Security Broker (CASB)** | Enforces security policies across cloud services                          | Prevents uploads of sensitive files to unsanctioned cloud apps      |
| **Encryption**                          | Protects data confidentiality in all states (at rest, in transit, in use) | Encrypts databases, emails, or VPN traffic                          |
| **Tokenization**                        | Replaces sensitive data with non-sensitive tokens                         | Used in payment systems to protect credit card numbers              |
| **Data Masking**                        | Obscures sensitive data for testing or analytics                          | Displays masked SSNs in dev environments to protect real identities |
