## 3.1 - Research, implement and manage engineering processes using secure design principles

| **Principle**                     | **Explanation**                                                                                                                                                                                                                                                                           |
| --------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Threat Modeling                   | Structured process for identifying, quantifying, and mitigating security threats relevant to an application or system design **before** it is implemented. It helps prioritize security efforts based on potential impact and likelihood.                                                 |
| Least Privilege                   | Granting users, processes, or applications only the minimum access rights or permissions absolutely necessary to perform their required tasks, and nothing more. This limits the blast radius if an account is compromised.                                                               |
| Defense in Depth                  | Employing multiple, layered security controls (administrative, logical, and physical) to protect critical assets. If one layer fails, others act as a backup to prevent compromise.                                                                                                       |
| Secure Defaults                   | The out-of-the-box configuration for all software and hardware should prioritize security over convenience or ease of use (e.g., strong passwords required, unnecessary services disabled).                                                                                               |
| Fail Securely                     | Designing systems so that if a component fails, it defaults to a secure, restrictive state. For example, a power-loss event should cause a critical electric lock to remain locked, or a software failure should result in access being denied.                                           |
| Keep It Simple and Small (KISS)   | Favoring simple, modular designs and minimizing the overall attack surface. Complexity often introduces hidden vulnerabilities and makes systems harder to secure, audit, and maintain.                                                                                                   |
| Segregation of Duties (SoD)       | Administrative control ensuring that no single individual has control over all critical steps in a high-risk process. This requires collusion to commit fraud (e.g., the person who authorizes payment should not be the same person who performs the bank reconciliation).               |
| Privacy by Design                 | Integrating privacy considerations and protections into the design and architecture of IT systems, products, and services from the initial conception phase (not retrofitting them later), ensuring compliance with regulations like GDPR.                                                |
| Zero Trust or Trust But Verify    | **No user, device, or application is trusted by default**, regardless of whether it is inside or outside the network perimeter. Every access request must be authenticated, authorized, and continuously validated.                                                                       |
| Shared Responsibility             | Primarily for cloud computing that defines which security tasks are the responsibility of the **Cloud Service Provider (CSP)** (e.g., physical security, global network) and which tasks are the responsibility of the **customer** (e.g., data encryption, access control, OS patching). |
| Secure Access Service Edge (SASE) | A modern security and networking architecture that converges wide area networking (WAN) and network security services (like $\text{CASB}$, $\text{DLP}$, and firewalls) into a single, cloud-delivered service model. SASE supports the Zero Trust model for remote and mobile users.     |

## 3.2 - Understand the fundamental concepts of security models (e.g., Biba, Star Model, Bell-LaPadula)

**Security models** serve as the **formal, logical blueprint** that translates abstract security goals (like "confidentiality" or "integrity") into a structured, enforceable **security policy**. They prescribe the specific rules, algorithms, and data structures necessary to build and verify secure hardware and software. Essentially, a security model provides **designers and implementers** with a measurable standard to ensure their final system architecture correctly and consistently upholds the organization's high-level security requirements

### Bell-LaPadula Model (Confidentiality)

Protects confidentiality of information, widely used in military/government systems.
**Core Rules:**
- **Simple Security Property (“No Read Up”):** A subject at a lower clearance cannot read data at a higher classification.
- **Star (*) Property (“No Write Down”):** A subject at a higher clearance cannot write to a lower classification, preventing leaks.
- **Discretionary Security Property:** Uses access matrices for discretionary access control.

#### Star Property (within Bell-LaPadula)

The _Star Property_ (or confinement property) is part of Bell-LaPadula.
**Rule:** Prevents subjects at higher security levels from writing to lower levels (_No Write Down_).
    - **Goal:** Stops classified information from leaking into less secure domains.
    - **Modern Use:** Enforced in systems like SELinux, Windows Mandatory Integrity Control, and cloud policies.

### Biba Model (Integrity)

Ensures _integrity_ of information, the inverse of Bell-LaPadula.
**Core Rules:**
- **Simple Integrity Property (“No Read Down”):** A subject cannot read data from a lower integrity level (to avoid contamination).
- **Star (*) Integrity Property (“No Write Up”):** A subject cannot write to a higher integrity level (to avoid corrupting trusted data).
- **Invocation Property:** A process at a lower level cannot request higher-level access.


> [!Warning] HotTopic
> You need to know the generalities of these models.
> 
> **Bell-LaPadula:** Think _military secrets_ — confidentiality is king.
> **Biba:** Think _financial records_ — integrity is critical

## 3.3 - Select controls based upon systems security requirements

### The Control Selection Process

The selection of controls is typically governed by a formal process, often following frameworks like **NIST SP 800-53** or **ISO 27001**, and involves three key steps:

- **Determine Security Requirements:** This starts by examining the **data classification** (e.g., Confidential, Public) and the **asset value** (AV) to determine the required Confidentiality, Integrity, and Availability (CIA) levels. Regulatory requirements (HIPAA, GDPR, PCI-DSS) also dictate mandatory controls.
- **Risk Assessment:** Identify potential **threats** and **vulnerabilities** to the system. The likelihood and impact of these risks determine the **level of protection** required (e.g., a system holding Top Secret data requires much stronger controls than one holding public marketing data).
- **Baseline Selection:** Start with a defined **security baseline**—a minimum set of controls applicable to all systems of a certain type or classification. This baseline is then customized (or **tailored**) based on the specific system's architecture and operating environment.

## 3.4 - Understand security capabilities of Information Systems (IS) (e.g., memory protection, Trusted Platform Module (TPM), encryption/decryption)

Focuses on the security features built into modern hardware, operating systems, and processors that are used to enforce security policies and protect data. This involves both software-level mechanisms and specialized hardware components.

|**Category**|**Capability**|**Purpose and Security Benefit**|
|---|---|---|
|**Hardware Root of Trust**|**Trusted Platform Module (TPM)**|A secure cryptoprocessor on the motherboard that stores encryption keys and certificates. Crucial for **Secure Boot** and validating the system's integrity before releasing full disk encryption keys (e.g., BitLocker).|
||**Hardware Security Modules (HSMs)**|Tamper-resistant physical devices used to securely generate, store, and manage high-value cryptographic keys for large-scale operations (like Certificate Authorities).|
|**OS & Memory Protection**|**Memory Protection**|Mechanisms used by the OS (like separation of virtual memory space) to prevent one process from reading or writing into another process's allocated memory space, thus enforcing **Process Isolation**.|
||**Address Space Layout Randomization (ASLR)**|Randomly changes the memory addresses of system files and libraries at boot time. This defeats common **buffer overflow attacks** by making it impossible for attackers to predict the location of target code.|
||**Execute Disable Bit (NX/XD)**|A CPU feature that marks memory regions as containing only data, not executable code. This prevents an attacker from inserting and executing malicious code in data areas (like the stack).|
|**Access & Virtualization**|**System Access Control**|The inherent OS controls that enforce security policies, including **DAC** (Discretionary Access Control) and **Mandatory Access Control (MAC)**, such as Windows Mandatory Integrity Control (MIC).|
||**Virtualization Security**|Controls built into hypervisors (e.g., Hyper-V, VMware) to ensure strong **isolation** between different virtual machines ($\text{VMs}$) and between the $\text{VMs}$ and the host OS, protecting the integrity and confidentiality of the entire virtualized environment.|
|**Data Protection**|**Encryption/Decryption**|The built-in ability of the system to efficiently perform cryptographic operations for data protection, supporting features like **Full Disk Encryption (FDE)** for data at rest and secure protocol use ($\text{TLS}$) for data in transit.|

## 3.5 - Assess and mitigate the vulnerabilities of security architectures, designs, and solution elements

As complexity increases, so does the number of potential vulnerabilities and the breadth of areas that must be protected. Each additional layer of intricacy introduces new opportunities for threats to emerge, ultimately diminishing the reliability and trustworthiness of the system’s security.

| System Type                                | Common Vulnerabilities                                            | Mitigation Strategies                                                            |
| ------------------------------------------ | ----------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| **Client-based systems**                   | Malware infections, weak endpoint security, unpatched software    | Endpoint protection, patch management, least privilege, host-based firewalls     |
| **Server-based systems**                   | Misconfigurations, privilege escalation, DoS attacks              | Hardening, monitoring, redundancy, access control                                |
| **Database systems**                       | SQL injection, unauthorized access, data leakage                  | Input validation, encryption, RBAC, auditing                                     |
| **Cryptographic systems**                  | Weak algorithms, poor key management, side-channel attacks        | Strong algorithms (AES, RSA), secure key storage (HSM/TPM), regular key rotation |
| **Industrial Control Systems (ICS)**       | Legacy protocols, lack of patching, physical sabotage             | Network segmentation, monitoring, physical security, compensating controls       |
| **Cloud-based systems (SaaS, IaaS, PaaS)** | Misconfigured storage, insecure APIs, shared responsibility gaps  | Strong IAM, encryption, monitoring, vendor due diligence                         |
| **Distributed systems**                    | Synchronization issues, insecure communication, replication flaws | Secure protocols, redundancy, monitoring, consensus mechanisms                   |
| **Internet of Things (IoT)**               | Weak authentication, insecure firmware, lack of updates           | Device hardening, patching, network segmentation, secure boot                    |
| **Microservices / APIs**                   | Insecure endpoints, excessive permissions, data exposure          | API gateways, authentication (OAuth), rate limiting, input validation            |
| **Containerization**                       | Breakouts, insecure images, misconfigured orchestration           | Image scanning, least privilege, runtime monitoring, Kubernetes security         |
| **Serverless**                             | Dependency vulnerabilities, insecure triggers, lack of visibility | Secure coding, monitoring, IAM restrictions, dependency scanning                 |
| **Embedded systems**                       | Hardcoded credentials, limited patching, physical tampering       | Secure coding, firmware updates, tamper resistance                               |
| **High-Performance Computing (HPC)**       | Resource exhaustion, insecure parallel workloads                  | Access control, workload isolation, monitoring                                   |
| **Edge computing systems**                 | Data exposure at edge nodes, weak physical security               | Encryption, secure communication, hardened edge devices                          |
| **Virtualized systems**                    | Hypervisor attacks, VM escape, resource contention                | Hypervisor hardening, patching, isolation, monitoring                            |

## 3.6 - Select and determine cryptographic solutions




### Cryptographic Life Cycle

The cryptographic life cycle covers the entire lifespan of the key material, which is the most critical element of any cryptographic system.

- **Key Generation:** Creating high-quality, truly random cryptographic keys. Poor random number generation is a single point of failure for an entire cryptographic system.
- **Key Distribution:** The secure process of sharing the secret key between the sender and receiver. This is the hardest part of symmetric key cryptography.
- **Key Storage:** Securing the key material, typically using **Hardware Security Modules (HSMs)** or Trusted Platform Modules (TPMs) to prevent unauthorized access or extraction.
- **Key Usage:** The controlled use of the key for encryption/decryption, signing/verification, etc., enforcing the principle of least privilege.
- **Key Rotation/Revocation:** Periodically retiring old keys (rotation) to limit the amount of data secured by a single key. **Revocation** occurs immediately when a key is known or suspected to be compromised.
- **Key Destruction:** Securely destroying keys at the end of their life cycle to prevent recovery and misuse (e.g., zeroizing $\text{HSMs}$).
- **Algorithm Selection:** Choosing the appropriate mathematical function (e.g., $\text{AES}$, $\text{RSA}$) based on the security goals (Confidentiality vs. Integrity), key length, and required performance. The algorithm must be **publicly vetted, strong, and currently supported** (not deprecated).

### Cryptographic Methods


- **Symmetric (Secret Key) Cryptography:** Uses a **single, shared key** for both encryption and decryption.
	Extremely **fast** and efficient for large amounts of data.
- **Asymmetric (Public Key) Cryptography:** Uses a **pair of keys**: a public key (shared freely) and a private key (kept secret).
    Solves the key distribution problem and provides **Non-repudiation** (digital signatures).
- **Elliptic Curve Cryptography (ECC):** A type of asymmetric cryptography that relies on the mathematical properties of elliptic curves.
    Provides the **same level of security** as $\text{RSA}$ but with **smaller key sizes**, making it highly efficient for mobile and low-power devices.
- **Quantum Cryptography:** The study of cryptographic systems resistant to attacks by quantum computers.
	**Quantum Key Distribution (QKD):** A physical method that uses quantum mechanics to establish a secure, secret key between two parties, providing a level of security that can detect eavesdropping attempts.
    **Post-Quantum Cryptography:** Developing new mathematical algorithms (not quantum mechanical) that run on current computers but are resistant to attacks from future quantum computers.


### Public Key Infrastructure (PKI)

PKI is the framework of policies, procedures, software, hardware, and personnel required to manage digital certificates and public-key encryption.
To **bind an identity** (e.g., a person, server, or application) to a public key and verify the authenticity of keys used for encryption, authentication, and digital signatures.
- **Core Components:**
    - **Certificate Authority (CA):** The trusted entity that issues, revokes, and manages digital certificates.
    - **Digital Certificates:** Electronic documents (following the $\text{X.509}$ standard) that attest to the ownership of a public key.
    - **Registration Authority (RA):** Verifies the identity of the individual or organization requesting a certificate from the $\text{CA}$.
    - **Certificate Revocation List (CRL) / Online Certificate Status Protocol (OCSP):** Mechanisms for checking the status of a certificate to see if it has been revoked before its expiration date.

CA = x.509
## 3.7 - Understand methods of cryptanalytic attacks

- Brute force
- Ciphertext only
- Known plaintext
- Frequency analysis
- Chosen ciphertext
- Implementation attacks
- Side-channel
- Fault injection
- Timing
- Man-in-the-Middle (MITM)
- Pass the hash
- Kerberos exploitation
- Ransomware

asd+as
das3fa6sfd5as

| **Attack Category**                     | **Attack Method**            | **Description and Goal**                                                                                                                                                                                           |
| --------------------------------------- | ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **I. Core Algorithm Attacks**           | **Brute Force**              | Attempting every possible key combination until the correct one is found. Feasibility is entirely dependent on **key length**.                                                                                     |
|                                         | **Ciphertext Only (COA)**    | Attacker only has the **encrypted text (ciphertext)** and attempts to deduce the key or plaintext. The weakest form of attack for the adversary.                                                                   |
|                                         | **Known Plaintext (KPA)**    | Attacker possesses both the **plaintext** and its corresponding **ciphertext** for a block of data, using this pairing to derive the secret key.                                                                   |
|                                         | **Chosen Plaintext (CPA)**   | Attacker can choose specific **plaintext** to be encrypted and obtains the resulting ciphertext, allowing analysis of the key's behavior with targeted input.                                                      |
|                                         | **Chosen Ciphertext (CCA)**  | Attacker can choose specific **ciphertext** to be decrypted and obtains the resulting plaintext, allowing analysis of the decryption process.                                                                      |
|                                         | **Frequency Analysis**       | Statistical method (often against classical ciphers) that exploits the non-uniform distribution of characters in a given language.                                                                                 |
| **II. Implementation/Hardware Attacks** | **Side-Channel**             | Gaining information about the key by monitoring **physical characteristics** of the device (e.g., sound, electromagnetic emissions) during crypto operations.                                                      |
|                                         | **Timing Attack**            | A form of side-channel attack that measures the precise **time** a cryptographic operation takes. Variations in time can leak information about the secret key bits.                                               |
|                                         | **Fault Injection**          | Intentionally introducing a hardware error (e.g., voltage glitch) to cause the cryptographic process to fail predictably, which can reveal the secret key.                                                         |
|                                         | **Implementation Attacks**   | Exploiting flaws in the **software or hardware** used to implement the crypto algorithm (e.g., a buffer overflow vulnerability in a key management function).                                                      |
| **III. Network & Protocol Attacks**     | **Man-in-the-Middle (MITM)** | Attacker secretly intercepts and alters communication between two parties who believe they are communicating directly. Often targets $\mathbf{TLS}$ handshakes.                                                    |
|                                         | **Pass the Hash (PtH)**      | Stealing the **NTLM hash** (encrypted password) from system memory ($\text{LSASS}$) and reusing it to authenticate to other network resources without needing the plaintext password.                              |
|                                         | **Kerberos Exploitation**    | Exploiting vulnerabilities in the Kerberos protocol (e.g., **Kerberoasting** or **Golden Ticket attacks**) to steal service ticket hashes or forge credentials for full domain access.                             |
| **IV. Cryptography as a Weapon**        | **Ransomware**               | A malware attack that uses **strong, modern cryptography** (like AES and RSA) to encrypt a victim's files, making them inaccessible. The attack leverages the _use_ of cryptography, not a break in the algorithm. |

## 3.8 - Apply security principles to site and facility design

Ensuring that **physical environments** (sites, buildings, data centers) are designed with **security in mind**, protecting people, assets, and information systems.

|Principle|Example Control|Goal|
|---|---|---|
|Defense in Depth|Fences → locks → biometrics|Layered protection|
|Site Selection|Avoid flood plains, crime hotspots|Reduce environmental risk|
|Perimeter Security|Bollards, lighting, CCTV|Deter/detect intrusions|
|Access Control|Badges, biometrics, mantraps|Prevent unauthorized entry|
|Environmental Controls|HVAC, fire suppression, UPS|Maintain availability|
|Redundancy & Resilience|Backup power, alternate sites|Ensure continuity|
|Monitoring & Detection|Cameras, alarms, logs|Detect/respond to incidents|
|Secure Layout|Server rooms in protected areas|Limit exposure|

tipos de redudance

## 3.9 - Design site and facility security controls


|**Area of Design**|**Primary Assets/Vulnerability**|**Key Design Controls & Measures**|
|---|---|---|
|**I. Critical Interior Spaces**|_Server Rooms/Data Centers_|**Multi-factor access control** (e.g., card + biometric), reinforced walls, and strict **access logging/auditing**.|
||_Wiring Closets/IDFs_|Must be **locked** (audited electronic access preferred), free of flammable storage, and monitored to prevent easy network tampering or wiretapping.|
||_Media & Evidence Storage_|**Fire-rated containers/safes**, strict environmental controls (humidity/temp), and rigorous **Chain of Custody** protocols for evidence integrity.|
|**II. Fire Protection**|_Risk of Data Loss/Destruction_|**Detection:** Early warning systems ($\text{VESDA}$), smoke detectors (ionization/photoelectric). **Suppression:** **Clean agents** ($\text{FM-200}$, Novec 1230) preferred over water in data centers to avoid equipment damage.|
|**III. Power Infrastructure**|_Availability/Reliability_|**Redundancy ($\mathbf{N+1}$ or $\mathbf{2N}$):** Multiple power feeds, redundant $\text{UPS}$ units for short-term battery power. **Generators** for long-term backup and **proper grounding** for electrical noise and safety.|
|**IV. Utilities & Environmental**|_HVAC & Environmental Issues_|Maintain stable temperature and humidity ($\mathbf{40\% \text{ to } 60\%}$) to prevent hardware damage and static electricity. Implement **physical barriers** to protect utilities from man-made or natural threats.|

layout de los server

###  Classes of Fire

|**Class**|**Fuel Source**|**Examples**|
|---|---|---|
|**A**|**Ordinary Combustibles (Solids)**|Wood, paper, cloth, trash, most plastics.|
|**B**|**Flammable Liquids**|Gasoline, oil, paint, petroleum grease, alcohol.|
|**C**|**Energized Electrical Equipment**|Wiring, appliances, motors, power tools (The fire stops being Class C when the power is shut off).|
|**D**|**Combustible Metals**|Magnesium, Titanium, Sodium, Potassium.|
|**K**|**Combustible Cooking Media**|Vegetable oils, animal fats, and greases typically found in commercial kitchens.|
hot topic

## 3.10 - Manage the information system lifecycle


The **Information System Lifecycle** ensures that systems are designed, built, operated, and retired in a secure and controlled manner. Each phase has specific security considerations to protect confidentiality, integrity, and availability (CIA).

### Lifecycle Phases & Security Focus

|Phase|Description|Security Considerations|
|---|---|---|
|**Stakeholders needs & requirements**|Identify business goals, compliance needs, and risk tolerance.|Ensure security requirements are captured early (e.g., regulatory compliance, privacy).|
|**Requirements analysis**|Translate stakeholder needs into technical and security requirements.|Define access control, encryption, logging, resilience requirements.|
|**Architectural design**|Create system architecture (hardware, software, network).|Apply security principles: defense in depth, least privilege, segmentation.|
|**Development / implementation**|Build or configure the system.|Secure coding practices, vulnerability testing, configuration hardening.|
|**Integration**|Combine components into a working system.|Validate secure interfaces, API security, compatibility with existing controls.|
|**Verification & validation**|Test system against requirements.|Security testing: penetration tests, code reviews, compliance audits.|
|**Transition / deployment**|Move system into production.|Secure rollout, patch management, user training, change control.|
|**Operations & maintenance / sustainment**|Day-to-day use and upkeep.|Continuous monitoring, incident response, patching, backups, performance tuning.|
|**Retirement / disposal**|Decommission system securely.|Data sanitization, hardware destruction, revocation of credentials, archival of logs.|
