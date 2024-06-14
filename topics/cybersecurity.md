# Cybersecurity

<br>![cybersecurity image](https://raw.githubusercontent.com/AnselmoGPP/Learn_Computer_Science/master/resources/miscellany.jpg)

## Table of Contents
+ [Foundations](#foundations)
    + [Terminology](#terminology)
    + [Attacks](#attacks)
    + [Domains](#domains)
    + [Ethics](#ethics)
    + [Tools](#tools)
    + [Portfolio](#portfolio)
+ [Managing security risks](#managing-security-risks)
    + [Introduction](#introduction)
    + [Frameworks and controls](#frameworks-and-controls)
+ [Network security](#network-security)
    + [Network architecture](#network-architecture)
    + [Network operations](#network-operations)
        + [Protocols](#protocols)
        + [Wi-Fi](#wi-fi)
        + [Firewalls](#firewalls)
        + [VPNs](#vpns)
        + [Security zones](#security-zones)
        + [Proxy servers](#proxy-servers)
    + [Network intrusions](#network-intrusions)
        + [Attacks](attacks)
        + [Network protocol analyzer](network-protocol-analyzer)
    + [Security hardening](security-hardening)
        + [Security hardening](security-hardening)
        + [OS hardening](os-hardening)
        + [Network hardening](network-hardening)
        + [Cloud hardening](cloud-hardening)
+ [Linux](linux)
+ [SQL](sql)


## Foundations

### Terminology

Organizations have to protect themselves from attacks in order to minimize risks and potential damage.

**Cybersecurity**: Practice of ensuring confidentiality, integrity, and availability of information by protecting networks, devices, people, and data from unauthorized access or criminal exploitation. 

**Asset**: Item perceived as having value to an organization (office space, computers, customers' PII, intellectual property...). Since it carries risk, it requires some security controls.

**Risk**: Anything that can impact confidentiality, integrity, or availability of an asset. It's the "likelihood of a threat occurring". A vulnerability and a threat must be present for there to be a risk. There different risk levels, depending on possible threats and asset's value.
- **Low-risk asset**: Information that would not harm the organization's reputation or ongoing operations, and would not cause financial damage if compromised.
- **Medium-risk asset**: Information not available to the public that may cause some damage to the organization's finances, reputation, or ongoing operations.
- **High-risk asset**: Information protected by regulations/laws that may have severe negative impact on an organization's finances, ongoing operations, or reputation.

**Threat**: Any circumstance or event that can negatively impact assets.
- **Internal threat**: It can be a current/former employee, an external vendor, or a trusted partner who poses a security risk. Sometimes it's accidental (like an employee who accidentally clicks on a malicious email link). Sometimes, he intentionally engages in risky activities (like unauthorized data access).

**Threat actor** (malicious attacker): Person or group who presents a security risk for computers, applications, networks, or data.

**Vulneravility**: Weakness that can be exploited by a threat.

**Attack vectors**: The pathways attackers use to penetrate security defenses

**Security benefits**:
- It protects from internal and external threads
- It ensures regulatory compliance is meet
- It maintains and improves business productivity
- It reduces expenses
- It maintains brand trusth

**Common job titles**:
- Security analyst or specialist
- Cybersecurity analyst or specialist
- Security operations center (SOC) analyst
- Information security analyst

**Security analyst**: Responsible for monitoring and protecting information and systems by:
- Protecting computer and network systems: Monitor organization's internal network, respond to detected threads, search of weaknesses (penetrating testing, etical hacking...). 
- Installing prevention software
- Conducting periodic security audits

**Compliance**: Process of adhering to internal standards and external regulations that enables organizations to avoid fines and security breaches.

**Network security**: Practice of keeping an organization's network infrastructure secure from unauthorized access (including data, services, systems, and devices stored in an the network).

**Cloud**: Network made up of a collection of servers or computers that store resources and data in remote physical locations (data centers) that can be accessed via the internet.

**Cloud security**: Process of ensuring that assets stored in the cloud are properly configured, or set up correctly, and access to those assets is limited to authorized users. It focuses on protecting data, applications, and infrastructure in the cloud.

**Programming**: Proocess that can be used to create a specific set of instructions for a computer to execute tasks (automation of repetitive tasks, reviewing web traffic, alerting suspicious activity...).

**Order of volatility**: A sequence outlining the order of data that must be preserved from first to last

**Protecting and preserving evidence**: The process of properly working with fragile and volatile digital evidence

More terminology: [**National Institute of Standards and Technology glossary**](https://csrc.nist.gov/glossary).

**Necessary skills**:
- Transferable skills (skills from other areas that can apply to different careers): Communication, collaboration, analysis, problems solving, time management, learning.
- Technical skills (skills that require knowledge of specific tools, procedures, and policies): Programming languages, Security Information and Event Management (SIEM) tools, Intrusion detection systems (IDSs), threat landscape knowledge, incident response.

[CompTIA Security+ exam](https://www.comptia.org/certifications/security): Industry leading certification for cybersecurity roles.

**Personally Identifiable Information (PII)**: Any information used to infer an individual's identity (full name, birth date, address, phone number, email address, IP address...). These are key assets that a threat actor will look for. We should make sure we know how it's handled, where it's stored, and that it complies with regulation/law (which varies between jurisdictions). 
- **Sensitive Personally Identifiable Information (SPII)**: Type of PII that falls under stricter handling guidelines (Social security number, medical info, finantial info, biometric data...).

### Attacks

**Computer virus**: Malicious code written to interfere with computer operations an cause damage to data and software.

**Malware**: Software designed to harm devices or networks. Examples:
- __Brain virus__ (1986): Created to track illegal copies of medical software and prevent pirated licenses. The infected floppy disk infected the computer, and this computer would infect any floppy disk introduced in it. The virus spread globally within a couple of months. It slowed down productivity and impacted business operations.
- __Morris worm__ (1988): Created to assess the size of Internet. It crawled the web and installed itself onto computers. However, it continued to re-install itself in already compromised computers until they ran out of memory and crashed. It infected 6000 computers (10% of Internet). This caused the stablishment of CERTs (Computer Emergency Response Teams).
- __LoveLetter__ (2000): Created to steal internet login credentials. It was an email with an attachment called "Love letter for you" which, once opened, scanned the user's address book and sent itself to each person in the list. It infected 45 million computers (estimating 10 billion dollars in damages). This is the firs example of social engineering.
- __Equifax breach__ (2017): Attackers infiltrated the credit reporting agency Equifax, causing one of the largest known data breaches of sensitive information (143 million customer records stolen, affecting about 40% of all americans). The records included PII information. Equifax had several vulnerabilities that the attackers exploited. Equifax paid over 575 million dollars in complaints and fines.

**Common attacks**:

- **Malware**: Software designed to harm devices or networks. There are many types. Main purpose: obtain money or intelligence advantage. Most common attacks:
  - **Virus**: Malicious code written to interfere with computer operations and cause damage to data and software. It needs to be initiated by a user (threat actor), who transmits the virus via a malicious attachment or file download. When someone opens it, the virus hides itself in other files in the now infected system. When the infected files are opened, it allows the virus to insert its own code to damage/destroy data in the system.
  - **Worms**: Malware that can duplicate and spread itself across systems on its own. In contrast to a virus, a worm doesn't need to be downloaded by a user because it self-replicates and spreads from an already infected computer to other devices on the same network.
  - **Ransomware**: Malicious attack where threat actors encrypt an organization's data and demand payment to restore access. 
  - **Spyware**: Malware that’s used to gather and sell information without consent. It can be used to access devices. It may collect personal data (emails, texts, voice and image recording, locations...).

- **Social Engineering**: Manipulation technique that exploits human error to gain private information, access, or valuables. Human error is usually a result of trusting someone without question. The threat actor creates an environment of false trust and lies to exploit people. Most common attacks:
  - **Social media phishing**: A threat actor collects detailed information about their target from social media sites before initiating an attack.
  - **Watering hole attack**: A threat actor attacks a website frequently visited by a specific group of users.
  - **USB baiting**: A threat actor strategically leaves a malware USB stick for an employee to find and install, to unknowingly infect a network. 
  - **Physical social engineering**: A threat actor impersonates an employee, customer, or vendor to obtain unauthorized access to a physical location.
  - **Phishing**: Use of digital communications to trick people into revealing sensitive data or deploying malicious software. Most common attacks:
    - **Business Email Compromise (BEC)**: Malicious email message that seems to be from a known source to make a seemingly legitimate request for information, in order to obtain a financial advantage.
    - **Spear phishing**: Malicious email attack that targets a specific user or group. The email seems to originate from a trusted source. If it targets company executives to gain access to sensitive data, it's called **whaling**.
    - **Vishing**: Exploitation of electronic voice communication to obtain sensitive information or to impersonate a known source.
    - **Smishing**: Use of text messages to trick users, in order to obtain sensitive information or to impersonate a known source.

- **Password attack**: Attempt to access password-secured devices, systems, networks, or data. Some types are: brute force, rainbow table, etc.

- **Physical attack**: It affects digital and physical environments. Some types are: malicious USB cable, malicious flash drive, card cloning and skimming, etc.

- **Adversarial artificial intelligence (AAI)**: It uses AI and ML to conduct attacks more efficiently. 

- **Supply-chain attack**: It targets systems, applications, hardware, and/or software to locate a vulnerability where malware can be deployed. Because every item sold undergoes a process that involves third parties, this means that the security breach can occur at any point in the supply chain. These attacks are costly because they can affect multiple organizations. 

- **Cryptographic attack**: It affects secure forms of communicaton between a sender and intended recipient. Some types are: birthday, collision, downgrade, etc.

- **Web vulnerability**: Unique flaw in a web application that a threat actor could exploit to allow unauthorized access, data theft, and malware deployment. Stay up-to-date on the most critical risks to web applications with [Open Web Application Security Project (OWASP) Top 10](https://owasp.org/www-project-top-ten/).

- **Penetration testing** (pen testing): Act of participating in a simulated attack that helps identify vulnerabilities in systems, networks, websites, applications, and processes. It's a thorough risk assessment that can evaluate and identify external and internal threats as well as weaknesses.

**Social engineering principles**: Social engineering is incredibly effective because people are generally trusting and conditioned to respect authority. These attacks increase with every new social media application that allows public access to people's data. Although sharing personal data (photos, location...) can be convenient, it’s also a risk. Some reasons why social engineering attacks are effective are:
  - Authority: Threat actors impersonate individuals with power. Most people are conditioned to respect and follow authority figures. 
  - Intimidation: Threat actors use bullying tactics (like persuading and intimidating victims into doing what they’re told). 
  - Consensus/Social proof: Because people sometimes do things that they believe many others are doing, threat actors use others’ trust to pretend they are legitimate. Example: a threat actor might try to gain access to private data by telling an employee that other people at the company have given them access to that data in the past. 
  - Scarcity: A tactic used to imply that goods or services are in limited supply. 
  - Familiarity: Threat actors establish a fake emotional connection with users that can be exploited.  
  - Trust: Threat actors establish an emotional relationship with users that can be exploited over time. They use this relationship to develop trust and gain personal information.
  - Urgency: A threat actor persuades others to respond quickly and without questioning.

**Threat actor types**:
  - **Advanced persistent threats (APTs)**: They have significant expertise accessing an organization's network without authorization. APTs tend to research their targets in advance and can remain undetected for an extended period of time. Their intentions can include damaging critical infrastructure (power grid, natural resources...) and gaining access to intellectual property (trade secrets, patents...).
- **Insider threats**: They abuse their authorized access to obtain data that may harm an organization. Their intentions can include: sabotage, corruption, espionage, unauthorized data access or leaks.
- **Hacktivists**: They're driven by a political agenda. They abuse digital technology to accomplish their goals, which may include: demonstrations, propaganda, social change campaigns, fame.

**Hacker**: Any person who uses computers to gain access to computer systems, networks, or data. Three main categories:
- **Authorized hacker** (ethical hacker): He follows a code of ethics and adhere to the law to conduct organizational risk evaluations in order to safeguard people and organizations from malicious threat actors.
- **Semi-authorized hacker** (researcher): He searches for vulnerabilities but don’t take advantage of the vulnerabilities they find.
- **Unauthorized hackers** (unethical hacker): Malicious threat actor who don't follow or respect the law. Their goal is to collect and sell confidential data for financial gain. 

### Domains

**Certified Information Systems Security Professional (CISSP)**: Globally recognized and highly sought-after information security certification, awarded by the International Information Systems Security Certification Consortium. 

CISSP has established 8 domains for security professionals. All of them are related, and gaps in one of them may have negative consequences in an organization.

- **Security and risk management**: Defines security goals and objectives, risk mitigation, compliance, business continuity, and law (legal regulations).
- **Asset security**: Secures digital and physical assets. It's also related to the storage, maintenance, retention, and destruction of data.
- **Security architecture and engineering**:: Optimizes data security by ensuring effective tools, systems, and processes are in place to protect assets and data.
- **Communication and network security**: Manage and secure physical networks and wireless communications.
- **Identity and access management**: Focused on access and authorization (identification, authentication, authorization, accountability) to keep data secure, by ensuring users follow established policies to control and manage assets (physical and logical).
- **Security assessment and testing**: Conducting security control testing, collecting and analyzing data, and conducting security audits to monitor for risks, threats, and vulnerabilities.
- **Security operations**: Conducting investigations and implementing preventive measures.
- **Software development security**: Uses secure coding practices (recommended guidelines for creating secure applications and services). Each phase of the software development lifecycle must undergo security reviews, so security can be fully integrated into the software.

Social engineering attacks fall under the Security and risk management domain. Physical attacks fall under Asset security. Password attacks fall under Communication and network security. AAI techniques fall under Communication and network security and Identity and access management. Cryptographic attacks fall under Communication and network security. Supply-chain attacks can fall under several domains (Security and risk management, Security architecture and engineering, Security operations domains, etc.).

**Risk mitigation**: Process of having the right procedures and rules in place to quickly reduce the impact of a risk like a breach.
**Business continuity**: Organization's ability to maintain their everyday productivity by establishing risk disaster recovery plans.
**Shared responsability**: All individuals within an organization take an active role in lowering risk and maintaining both physical and virtual security.

### Ethics

**Security ethics**: Guidelines for making appropriate decisions as a security professional. Principles:
- __Confidentiality__: If you have access to proprietary or private information, keep it confidential and safe.
- __Privacy protection__: Safeguard personal information from unauthorized use.
- __Laws__: Rules recognized by a community and enforced by a governing entity.

**Counterattacks**:
- In U.S., deploying a counterattack on a threat actor is illegal. You can only defend. Counterattacks can lead to escalation and even more damage. Only approved employees of the federal government or military personnel are allowed to counterattack.
- The international Court of Justice (ICJ) states that a person/group can counterattack if it only affects the party that attacked first, the counterattack is a communications asking to stop, it doesn't escalate, and its effects can be reversed. Organizations typically don't counterattack because these parameters are difficult to control.

### Tools

**Operating system**: Interface between computer hardware and the user (Linux, Windows, macOS...).

**Database**: Organized collection of information or data. It may contain millions of **data points** (specific piece of information).

**Metrics**: Key technical attributes (response time, availability, failure rate...), which are used to assess the performance of a software application.

**Security Orchestration, Automation, and Response (SOAR)**: Collection of applications, tools, and workflows that use automation to respond to security events. Used for threat monitoring and automate repetitive tasks generated by tools such as a **SIEM** or **MDR** (Managed Detection and Response). Example: if a user attempts to log into their computer too many times with the wrong password, a SOAR would automatically block their account to stop a possible intrusion.

**Log**: Record of events that occur within an organization's system (like employees signing into their computers or accessing web-based services). It helps identify vulnerabilities and potential security breaches. Common log sources: 
- __Firewall logs__: Record of attempted or established connections for incoming traffic from Internet. It includes outbound requests to Internet from within the network.
- __Network logs__: Record of all computers and devices that enter and leave the network, and all connections between devices and services on the network.
- __Server logs__: Record of events (login, password, username requests...) related to services (websites, emails, file shares...).

**Security Information and Event Management (SIEM) tools**: Application that collects and analyzes log data to monitor critical activities in an organization. Organizations must configure and customize it to adapt to their unique needs. As cybersecurity evolves, SIEM tools may become more cloud based (cloud-hosted or cloud-native), may adapt to new theat actor tactics and techniques (IoT interconnecting too many devices, new AI/ML threats...), and may increase automation and perform more actions without human intervention (SOAR).

SIEM tools types:
- __Self-hosted__: Managed by the organization. Ideal for physically controlling confidential data.
- __Cloud-hosted__: Provides availability, flexibility, and scalability.
- __Hybrid__: Leverages benefits of cloud while controlling confidential data.

SIEM tools main features:
- Provides real-time visibility, event monitoring and analysis, and automated alerts.
- Stores all log data in a centralized location. 
- Can create customizable dashboards, which show security information in an easy to understand format (charts, graphs, tables...).
- Provides customizable metrics.

Most common SIEM tools:
- **Splunk Enterprise**: Self-hosted data analysis tool for retaining, analyzing, and searching an organization's log data to provide security information and alerts in real-time..
- **Splunk cloud**: Cloud-hosted tool for collecting, searching, and monitoring log data.
- **Google's Chronicle**: Cloud-native tool that stores security data for search and analysis.

**Playbook**: Manual that provides details about any operational action, including incident response, security or compliance reviews, access management, and many other organizational tasks that require a documented process from beginning to end. It varies between organizations. It guides analysts in how to handle a security incident (open attack, privacy incident, data leak, DDoS, service alert...) before, during, and after it occurred. Sometimes, it may need to be updated. Threat identification and mitigation must be urgent, efficient, and accurate. There're different playbooks (incident response, vulnerability response, security alerts, team-specific, product-specific...).

- **Incident response playbook**: Used to identify an attack, contain the damage, and correct the effects of a security breach. Phases:
  - __Preparation__: Organizations mitigate likelihood, risk, and impact of a security incident by documenting procedures, establishing staffing plans, and educating users.
  - __Detection and analysis of events__: Use appropriate tools and strategies for this.
  - __Containment__: Prevent further damage and reduce the immediate impact of the incident.
  - __Eradication and recovery__: Remove the incident's artifacts so the organization can return to normal operations (IT restoration).
  - __Post incident activity__: Document the incident, inform organizational leadership, apply learned lessons, etc.
  - __Coordination__: Report incidents and share information.

There are different types of Incident response playbooks, depending on the attack (ransomware, malware, DDoS...). Playbooks are generally used alongside SIEM and SOAR tools (unusual user behavior is flagged by a SIEM tool > playbook tells analysts how to address the issue). Example case:
1. A SIEM alert signals a potential malware attack
2. Assess the alert (determine if the alert is valid)
3. Take actions and use tools to contain the malware and reduce damage
4. Eliminate traces of the incident and restore the affected systems
5. Post-incident activities

**Network protocol analyzer** (packet sniffer): Tool that captures and analyzes data traffic within a network. Common ones are: **tcpdump** and **Wireshark**.

**Programming**: Used to create a specific set of instructions for a computer to execute tasks. It allows analysts to complete repetitive tasks/processes with great accuracy and efficiency, to reduce the risk of human error, and can save a lot of time. Two important languages are:
- **SQL (Structured Query Language)**: Used for creating, interacting with, and requesting information from a database.
- **Python**: Used to perform tasks that are repetitive and time-consuming, and that require a high level of detail and accuracy.

**Linux**: Open-source operating system. It's primary user interface is the command line, which allows for text-based commands between the user and the OS.

**Suricata**: Open-source network analysis and threat detection software. It's used to inspect entwrok traffic to identify suspicious behavior and generate network data logs.

**Antivirus software** (anti-malware): Software program used to prevent, detect, and eliminate malware and viruses. Some antivirus can scan the memory of a device to find patterns that indicate the presence of malware. 

**Intrusion detection system (IDS)**: Application that monitors system activity and alerts on possible intrusions, unauthorized access, and theft. The system scans and analyzes network packets (which carry small amounts of data through a network).

Every organization's toolkit may be somewhat different based on their security needs.

### Portfolio

There're different ways of presenting a portfolio:

- **Git repository**: It's a folder within a project. There are different Git repository sites: GitHub, GitLab, Bitbucket, etc. To create an online project portfolio on these repositories you need to use a version of Markdown. Learn about GitHub and Markdown [**here**](https://docs.google.com/document/d/13nqRTU4H14NFytodh_tbafXthjNRD7aWU_4Cjq7pKG8/template/preview#heading=h.m08l38wqbrm0).

- **Google Drive or Dropbox**: Cloud platform for storing your documentation. Both let you share your portfolio with others, and changes that you make to it will be updated automatically for anyone with access to your portfolio.

- **Google Sites**: Website hosting with many features for your webpage.

- **Documents folder**: Saved in your computer's hard drive.


## Managing security risks

### Introduction

Key impacts of threats, risks, and vulnerabilities:
- Financial
- Identity theft
- Reputation

**Security lifecycle**: Constantly evolving set of policies and standards that define how an organization manages risks, follows established guidelines, and meets regulatory compliance, or laws.

**Security architecture**: Type of security design composed of multiple components (such as tools and processes) that are used to protect an organization from risks and external threats.

**Security governance**: Practices that help support, define, and direct security efforts of an organization.

**CIA triad**: Foundational security model that helps inform how organizations consider risk when setting up systems and security policies. Components:
- __Confidentiality__: Only authorized users can access specific assets or data.
- __Availability__: Data is accessible to those who are authorized to access it.
- __Integrity__: Data is correct, authentic, and reliable.

**Security audit**: Review of an organization's controls, policies, and procedures against a set of expectations. Audits can be external or internal. 
- **Internal audit**: Conducted by a security team. It's purpose is to identify organizational risk, assess controls, and correct compliance issues. Steps:
  - Establish the scope (specific criteria of the audit) and goals (outline of security objectives)
  - Conduct risk assessment: What is the audit objective? Which assets are most at risk? Are current controls sufficient to protect them? What controls and regulations need to be implemented?
  - Complete controls assessment: Review assets and evaluate risks to them.
  - Assess compliance: Determine whether or not the organization is adhering to necessary compliance regulations.
  - Communicate results to stakeholders: Summarize scope and goals, list existing risks and how quickly they need to be addressed, identify compliance regulations, and provide recommendations.

Web layers:
- **Surface web**: The layer that most people use. It can be accessed using a web browser.
- **Deep web**: Generally requires authorization.
- **Dark web**: Can only be accessed by special software.

**Open Web Applications Security Project (OWASP)**: Non-profit organization focused on improving software security. Set of principles:
- __Minimize attack surface area__: Reduce all potential vulnerabilities a threat actor could exploit (like phising emails and weak passwords).
- __Principle of least privilege__: Limit access to information and resources to reduce the damage a security breach could cause (example: you may have access to logs but not be able to change permissions).
- __Defense in depth__: Multiple security controls that address risks and threats in different ways (MFA, firewall, intrusion detection system, permissions system...).
- __Separation of duties__: This prevent individuals from carrying fraudulent or illegal activities (he who signs paychecks shouldn't be the one who prepares them).
- __Keep security simple__: Avoid unnecessarily complicated solutions because they can become unmanageable.
- __Fix security issues correctly__: When security incidents occur, identify root cause, contain impact, identify vulnerabilities, and conduct tests to ensure a successful remediation.
- __Establish secure defaults__: The optimal security state of an application is its default state for users. It should take extra work to make the application insecure. 
- __Fail securely__: When a control fails or stops, it should default to the most secure option (example: if a firewall fails, it should close all connections and block new ones, rather than accept everything).
- __Don’t trust services__: When working with third-party partners, our organization shouldn’t explicitly trust that their partners’ systems are secure.
- __Avoid security by obscurity__: The security of key systems should not rely on keeping details hidden (like keeping source code secret), but upon many other factors (good password policies, defense in depth, business transaction limits, solid network architecture, fraud and audit controls...).

### Frameworks and controls

**Security posture**: Organization’s ability to manage its defense of critical assets and data and react to change. A strong security posture leads to lower risk for the organization.

**Security frameworks**: Guidelines used for building plans to address security risks, threats, and vulnerabilities (i.e. to help mitigate risk and threats to data and privacy). They provide a structured approach to implementing a security lifecycle. Organizations use security frameworks as a starting point to create their own security policies and processes. Purpose: protecting PII, securing financial information, identifying security weaknesses, managing organizational risks, and aligning security with business goals. Frameworks allow analysts to work alongside other members of the security team to document, implement, and use the policies and procedures created. Example: the healthcare industry uses frameworks to comply with the United States’ Health Insurance Portability and Accountability Act (HIPAA), which requires that medical professionals keep patient information safe. Core components:
  - Identifying and documenting security goals
  - Setting guidelines to achieve security goals
  - Implementing security processes
  - Monitoring and communicating results

**Security controls**: Safeguards designed to reduce specific security risks (safeguard example: data privacy training program for all employees) (risk examples: trespassing, fake employee accounts, free benefits...). Used alongside frameworks to reduce the possibility and impact of a security threat, risk, or vulnerability (i.e. to establish a strong security posture). Controls can be physical (locks, guards, cameras, access cards...), technical (firewalls, antivirus, MFA....), and administrative (authorization, separation of duties, asset classification...) and are typically used to prevent, detect, or correct security issues. Learn about health-related controls [**here**](https://www.hhs.gov/sites/default/files/physical-access-control.pdf). Example: a control that can be used alongside frameworks to ensure a hospital remains compliant with HIPAA is requiring that patients use multi-factor authentication (MFA) to access their medical records. Some common control types are:
- **Encryption**: Process of converting data from a readable format (plain text) to an encoded format (ciphertext). Unauthorized users cannot decode it, which ensures confidentiality of private data. Note that encoding and encryption serve different purposes (encoding uses a public conversion algorithm to enable systems that use different data representations to share information).
- **Authentication**: Process of verifying who someone or something is (log-in to a website, multi-factor authentication (MFA), etc.).
- **Biometrics**: Unique physical characteristics that can be used to verify a person's identity.
- **Authorization**: Granting access to specific resources within a system. It verifies that a person has permission to access a resource.

**National Institute of Standards and Technology (NIST)**: U.S.-based agency that develops multiple voluntary compliance frameworks that organizations worldwide can use to help manage risk. Examples of frameworks include:

  - [**NIST Cybersecurity Framework (CSF)**](https://www.nist.gov/cyberframework): Voluntary framework that consists of standards, guidelines, and best practices to manage cybersecurity risk. Security teams use it as a baseline to manage short and long-term risk. The special publication SP 800-53 is a unified framework for protecting the security of information systems within the U.S. federal government. CSF is based on 5 steps:
    - **Identify**: Management of cybersecurity risk and its effect on an organization's people and assets.
    - **Protect**: Protection of an organization through the implementation of policies, procedures, training, and tools that help mitigate cybersecurity threats.
    - **Detect**: Identify potential security incidents and improve monitoring capabilities to increase the speed and efficiency of detections.
    - **Respond**: Make sure that the proper procedures are used to contain, neutralize, and analyze security incidents, and implement improvements to the security process.
    - **Recover**: Process of returning affected systems back to normal operation.

  - [**NIST Risk Management Framework (RMF)**](https://csrc.nist.gov/projects/risk-management/about-rmf): Voluntary framework based on 7 steps:
    - **Prepare**: Activities necessary to manage security and privacy risks before a breach occurs.
    - **Categorize**: Used to develop risk management processes and tasks.
    - **Select**: Choose, customize, and capture documentation of the controls that protect an organization.
    - **Implement**: Implement security and privacy plans for an organization.
    - **Assess**: Determine if established controls are implemented correctly.
    - **Authorize**: Being accountable for the security and privacy risks that may exist in an organization.
    - **Monitor**: Be aware of how systems are operating.

Other controls, frameworks, and compliance standards important for security professionals:

- **Cyber Threat Framework (CTF)**: Developed by U.S. government to provide a common language for describing and communicating information about cyber threat activity.

- **International Organization for Standardization/International Electrotechnical Commission (ISO/IEC) 27001**: A popular framework is ISO/IEC 27001. The ISO 27000 family of standards enables organizations of all sectors and sizes to manage the security of assets. It outlines requirements for an information security management system, best practices, and controls that support an organization’s ability to manage risks.

- **The Federal Energy Regulatory Commission - North American Electric Reliability Corporation (FERC-NERC)**: Regulation that applies to organizations that work with electricity or that are involved with the U.S. and North American power grid. These types of organizations have an obligation to prepare for, mitigate, and report any potential security incident that can negatively affect the power grid. They are also legally required to adhere to the Critical Infrastructure Protection (CIP) Reliability Standards defined by the FERC. 

- **The Federal Risk and Authorization Management Program (FedRAMP®)**: U.S. federal government program that standardizes security assessment, authorization, monitoring, and handling of cloud services and product offerings.

- **Center for Internet Security (CIS®)**: Nonprofit. It provides a set of controls that can be used to safeguard systems and networks against attacks, and actionable controls that security professionals may follow if a security incident occurs. 

- **General Data Protection Regulation (GDPR)**: E.U. general data regulation that protects the processing of E.U. residents’ data and their right to privacy in and out of E.U. territory. 

- **Payment Card Industry Data Security Standard (PCI DSS)**: International security standard meant to ensure that organizations storing, accepting, processing, and transmitting credit card information do so in a secure environment.

- **The Health Insurance Portability and Accountability Act (HIPAA)**: U.S. federal law from 1996 for protecting patients' health information. If patients' Protected Health Information (PHI) is exposed, the organization has legal obligation to inform them.

- **International Organization for Standardization (ISO)**: Created to establish international standards related to technology, manufacturing, and management across borders. It helps organizations improve their processes and procedures for staff retention, planning, waste, and services. 

- **System and Organizations Controls (SOC type 1, SOC type 2)**: Standard developed by the AICPA® . SOC1 and SOC2 are a series of reports that focus on an organization's user access policies at different organizational levels (such as associate, supervisor, manager, executive, vendor, others).

- [**U.S. Presidential Executive Order 14028**](https://www.whitehouse.gov/briefing-room/presidential-actions/2021/05/12/executive-order-on-improving-the-nations-cybersecurity/): Joe Biden's executive order (2021) for improving the nation’s cybersecurity. Remediation efforts are directed toward federal agencies and third parties with ties to U.S. [critical infrastructure](https://csrc.nist.gov/glossary/term/critical_infrastructure#:~:text=Definition(s)%3A,any%20combination%20of%20those%20matters.)

- **Regulations**: There are a number of regulations that are frequently revised. Try to keep up-to-date with changes and explore more frameworks, controls, and compliance. Suggestions: **Gramm-Leach-Bliley Act** and **Sarbanes-Oxley Act**.


## Network security

### Network architecture

**Network**: Group of interconnected devices (like workstations, cell phones, printers, or other smart devices). 

The devices connected in a network can communicate to each other, over network cables or wireless connections. They have a **network interface** that sends and receives data packets (which provide information about source and destination). These devices maintain information and services for users of a network. Networks at one location can comunicate with networks in other locations and the devices on them. In order for these devices to be able to find each other, they have unique addresses (identifiers) (IP and MAC addresses) that are used to locate each other. Devices can communicate on two types of networks: 
- **LAN** (Local Area Network): It spans a small area (office building, school, home...). A LAN can connect to the internet.
- **WAN** (Wide Area Network): It spans a large geographical area (city, state, country...). Internet can be considered a big WAM.

**Internet Service Provider (ISP)**: IT provides internet connectivity via telephone lines or coaxial cables.

**Network devices**: Specialized vehicles that manage what is being sent and received over the network. Other devices (computers, phones...) connect to the network via network devices. Hubs and switches both direct traffic on a local network. 

- **Hub**: Network device that broadcasts information to every device on the network (like a radio tower that broadcasts a signal to any radio tuned to the correct frequency). It provides a common point of connection for all devices directly connected to it. It also repeats all information out to all ports. This make hubs vulnerable to eavesdropping, so they are not often used on modern networks (organizations use switches instead), but they are more commonly used for a limited network setup (like a home office).

- **Switch**: It makes connections between specific devices on a network by sending and receiving data between them. They analyze the destination address of each data packet and send it to the intended device. It's an optional device that can be used for connecting some devices to the network by providing additional ports and Ethernet connections. It maintains a MAC address table that matches MAC addresses of devices on the network to port numbers on the switch and forwards incoming data packets according to the destination MAC address. Switches are a part of the data link layer in the TCP/IP model. Switches are more secure than hubs because switches only pass data to the intended destination. They can control traffic flow and improve network performance (example: by having different routers, connecting different devices to each one, and connecting these routers to a switch, we can load balance the network and improve its performance).

- **Router**: Network device that connects multiple networks together and directs traffic to the devices on a network (based on the IP address of the destination network). Routers allow devices on different networks to communicate with each other. In the TCP/IP model, routers are a part of the network layer. The IP address of the destination network is contained in the IP header. The router reads the IP header information and forwards the packet to the next router on the path to the destination. This continues until the packet reaches the destination network. Routers can also include a firewall feature that allows or blocks incoming traffic based on information in the transmission. This stops malicious traffic from entering the private network and damaging the local area network. Example: Information from a cell phone in network A is sent to its router, which reads the destination address and forwards it to the router of network B, which directs that information to a tablet.

- **Modem**: Device that usually connects your router to an ISP, bringing internet access to the LAN. Modems receive transmissions or digital signals from the internet and translate them into analog signals that can travel through the physical connection provided by your ISP. Usually, modems connect to a router that takes the decoded transmissions and sends them on to the local network. Example: Information from device in network A > router A > modem A > internet > modem of network B > router B > destination device. 
  - Enterprise networks used by large organizations to connect their users and devices often use other broadband technologies to handle high-volume traffic, instead of using a modem. 

**Virtualization tools**: Software that performs network operations, offered by Cloud service providers, that are normally completed by a hub, switch, router, or modem, and ,
and they are offered by Cloud service providers.). Despite hubs, switches, routers, and modems being physical devices, many functions performed by them can be completed by virtualization tools, providing cost savings and scalability.

**Firewall**: Network security device that monitors incomming and outgoing traffic on your network. It's the first line of defense. It can restrict specific incoming or outgoing traffic (the organization configures its security rules). It often resides between the internal network (secure) and the network resources outside the organization (untrusted) (like the internet).

**Servers**: They provide information and services for the devices on the network. The devices that connect to a server are called **clients**. In a **client-server model**,  clients send requests to the server for information and services, and the server performs the requests for the clients. Examples: DNS servers (perform domain name lookups for internet sites), file servers (store and retrieve files from a database), and corporate mail servers (organize mail for a company). 

**Wireless access point (WAP)**: It sends and receives digital signals over radio waves creating a wireless network. Devices with wireless adapters connect to the access point using Wi-Fi. 
 The WAP and connected devices use Wi-Fi protocols to send data through radio waves, which are sent to routers and switches and directed to their final destination.
- **Wi-Fi**: Set of standards and protocols used by network devices to communicate wirelessly.

**Network diagrams**: Maps that show the devices on the network and how they connect. They use small representative graphics to portray each network device and dotted lines to show how each device connects to the other. They show the architecture and design of a private network, and let us develop and refine strategies for securing network architectures.

**Cloud computing**: Practice of using remote servers, applications, and network services that are hosted on the internet instead of on local physical devices. This allows convenient and on-demand network access to a shared pool of configurable computing resources, which can be configured and released with minimal management effort or interaction with the service provider. 
 
**Cloud service provider (CSP)**: Company offering cloud computing services. It also provides on-demand storage, processing power that their customers only pay as needed, and business and web analytics that organizations can use to monitor their web traffic and sales. Companies can pay for storage and services and consume them through the CSP’s application programming interface (API) or web console. It provides 3 main services:
- **Software as a service (SaaS)**: Software suites operated by the CSP that a company can use remotely without hosting the software. 
- **Infrastructure as a service (IaaS)**: Use of virtual computer components offered by the CSP (virtual containers and storage, computing...). Some applications can take advantage of the availability, performance, and security features that are unique to cloud provider services.
- **Platform as a service (PaaS)**: Tools for designing custom applications that are designed and accessed in the cloud and used for a company’s specific business needs.

**On-premise network**: Network where all the devices used for network operations are kept at a physical location owned by the company.

**Cloud network**: Collection of servers or computers that stores data and resources in a remote data center that can be accessed via the internet. It saves money, simplifies operations, and provides more resources. It provices on-demand storage, processing power, and data analytics.

**Hybrid cloud environment**: It's when an organization use a CSP’s services in addition to their on-premise computers, networks, and storage.

**Multi-cloud environment**: It's when an organization use more than one CSP.

**Software-defined network (SDN)**: Made up of virtual network devices and services. Just like CSPs provide virtual computers, many SDNs also provide virtual switches, routers, firewalls, and more. Most modern network hardware devices also support network virtualization and software-defined networking. This means that physical switches and routers use software to perform packet routing. In the case of cloud networking, the SDN tools are hosted on servers located at the CSP’s data center.

**Benefits** of cloud computing and SDNs:
- __Reliability__: Resources can be accessed consistently and with minimal interruption. 
- __Decreased cost__: Since CSPs have such large data centers, they can offer virtual devices and services at good price.
- __Scalability__: CSPs let consume services in an elastic utility model as needed, so companies only pay for what they need when they need it.
- __Modifiable__: Changes can be made quickly through the CSPs, APIs, or web console—much. Example: if more protection is required, web application firewalls (WAFs), intrusion detection/protection systems (IDS/IPS), or L3/L4 firewalls can be configured quickly, leading to better network performance and security.

**Data packet**: Basic unit of information that travels from one device to another within a network. The packet's content is divided into:
- **Header**: Contains the IP address (Internet Protocol), MAC address (Media Access Protocol), and Protocol number (protocol to use).
- **Body**: Message to transmit.
- **Footer**: It signals that the packet is finished.

**Bandwidth**: Amount of data a device receives every second.

**Speed**: Rate at which data packets are received or downloaded.

If bandwidth or speed are irregular, it may indicate an attack.

**Packet sniffing**: Practice of capturing and inspecting data packets across a network.

**Network protocol**: Set of standards used for routing and addressing data packets as they travel between devices on a network.

**Port**: Software-based location in the OS of a network device that organizes the sending and receiving of data between devices on a network. When data packets are sent and received across a network, they are assigned a port. Ports divide network traffic into segments based on the service they will perform between two devices. Network devices use port numbers to determine what to do with the packet's data. Computers use them to know how to prioritize and process these segments. Firewalls can filter out unwanted traffic based on port numbers (example: an organization may configure a firewall to only allow access to TCP port 995 (POP3) by IP addresses belonging to the organization). Some common ports are: 25 (e-mail), 443 (secure internet communications), 20 (large file transfers).

<br>![models image](https://raw.githubusercontent.com/AnselmoGPP/Learn_Computer_Science/master/resources/network_models.png)

**TCP/IP model** (Transmission Control Protocol / Internet Protocol): It's the standard model for network communication, based on the TCP/IP protocols suite. It's a framework for visualizing how data is organized and transmitted accross the network. It has 4 layers:

- **Network access layer** (or Data link layer): It deals with the creation of data packets and transmission across a network. It corresponds to the physical hardware for network transmission (hubs, modems, cables, wiring...). The Address Resolution Protocol (ARP) is needed for mapping IP addresses to MAC addresses (used to identify hosts on the same physical network) for local network communication.

- **Internet layer** (or Network layer): It's responsible for ensuring delivery to the destination host (potentially residing on a different network). It ensures IP addresses are attached to data packets to indicate the location of the sender and receiver. It also determines which protocol is responsible for delivering the data packets and ensures the delivery to the destination host. Some common protocols are: IP (Internet Protocol), ICMP (Internet Control Message Protocol)...

- **Transport layer**: Responsible for delivering data between two systems or networks. It includes protocols to control the flow of traffic across a network (which permit or deny communication with other devices), and information about the connection status. Used for error control (ensure data is flowing smoothly). Main communication protocols used: TCP (Transmission Control Protocol) and UDP (User Datagram Protocol).

- **Application layer**: Responsible for making network requests or responding to requests. It defines which internet services and applications any user can access. Protocols here determine how data packets will interact with receiving devices. It relies on underlying layers to transfer the data across the network. Operations in this layer include file transfers and email services. Some common protocols: HTTP (Hypertext transfer protocol), SMTP (Simple mail transfer protocol), SSH (Secure shell), FTP (File transfer protocol), DNS (Domain name system).

**OSI model** (Open Systems Interconnection): 

7. **Application layer**: It includes all of the networking protocols that software applications use to connect a user to the internet. Example: an Internet web browser uses HTTP or HTTPS to send and receive information from a website server. An email application uses SMTP to send and receive information. A web browser uses DNS protocol to translate website domain names into IP addresses. 

6. **Presentation layer**: It involves data translation and encryption for the network. It adds to and replaces data with formats understandable by applications (layer 7) on both sending and receiving systems) using a standardized format. Formats at the user end may be different from those of the receiving system. Some formatting at this layer are: encryption (like SSL, which encrypts data between web servers and browsers as part of websites with HTTPS), compression, confirmation that the character code set can be interpreted on the receiving system, etc.

5. **Session layer**: It describes when a connection is established between two devices. An open session allows devices to communicate with each other. Session layer protocols keep the session open while data is being transferred and terminate it once transmission is complete. It's also responsible for authentication, reconnection, setting checkpoints during a data transfer (useful when an interrupted session resumes connection), etc. Sessions include a request (for service from processes in layer 6) and response (for services to layer 4) between applications.

4. **Transport layer**: Responsible for delivering data between devices. It also handles the speed of data transfer, flow of the transfer, and breaking data down into smaller segments (segmentation) for easier transportation. These segments are reassembled at destination so they can be processed at layer 5. The speed and rate of the transmission has to match the connection speed of the destination system. TCP and UDP are transport layer protocols.

3. **Network layer**: It oversees receiving the frames from layer 2 and delivers them to the intended destination (specified on the address included in the data packets). This includes routing packets from one router to another across the internet (i.e. from sending network to receiving network), till it reaches the IP address of the destination network (contained in the header of each packet). Routers use the IP address to route packets from network to network. This address will be stored for future routing purposes in routing tables along the packet's path to its destination.

2. **Data link layer**: It organizes sending and receiving data packets within a single network. It's home to switches on the local network and network interface cards on local devices. Protocols like NCP (network control protocol), HDLC (high-level data link control), and SDLC (synchronous data link control protocol) are used here.

1. **Physical layer**: It corresponds to the physical hardware involved in network transmission. It includes hubs, modems, and cables and wiring that connect. To travel across an ethernet or coaxial cable, a data packet needs to be translated into a stream of 0s and 1s. Then, when this stream is received, it's passed on to higher levels of the OSI model.

Network layer **addresses**: Each device on a network have 3 addresses that identify it on the network: public IP, private IP, and MAC address.

- **IP address**: Unique string of characters that identifies a location of a device on the internet. Each device has a unique IP address. Two types: IPv4 and IPv6 (bigger size than IPv4). IP addresses can be public or private (each one contained in specific value ranges).

  - **Public**: Assigned by your ISP and IANA. Each device of your LAN have the same one. Unique address in global internet. It costs to lease a public IP address. 

  - **Private**: Assigned by the router. Unique only within the private network. Only seen by other devices on the same LAN, which use it to communicate to each other. No cost associated.

- **MAC address**: Unique alphanumeric identifier assigned to each physical device on a network. It's permanent (unmutable) because it is unique to its network interface card. It's used to communicate with devices within the same network. When a switch receives a data packet, it reads the MAC address of the destination device and maps it to a port. It keeps this information in a MAC address table that the switch uses to direct data packets to the appropriate device.

**IPv4 packet**: It's made of 2 parts:

- **Data**: It can vary greatly in size. The maximum possible packet's size (header + data) is 65,535 bytes. It contains the message being transferred over the internet (website information, email text...). 
- **Header**: Its format is determined by the IPv4 protocol and includes the IP routing information that devices use to direct the packet. Its size ranges from 20 to 60 bytes. The first 20 bytes are a fixed set of information (source and destination IP address, header length, total packet length...). The rest range from 0 to 40 (options field). Fields:
  - __Version (VEC)__ (4b): Protocol the packet is using.
  - __IP header length (HLEN or IHL)__ (4b): Packet's header length.
  - __Type of service__ (ToS) (8b): Routers need this information because they prioritize packets for delivery to maintain quality of service on the network.
  - __Total length__ (16b): Entire IP packet's length (header + data) (IPv4 packet's max. length = 65,535 bytes).
  - __Identification__ (16b): Most networks have smaller limit than the IPv4 packet's max. length, so packets are divided (fragmented) into smaller IP packets. Each resulting fragment have a unique identifier so they can be reassembled once they reach their destination.
  - __Flags__ (3b): It provides the router more information about whether the original packet was fragmented and if there're more fragments in transit.
  - __Fragmentation offset__ (13b): It tells the router where in the original packet the fragment belongs.
  - __Time to live (TTL)__ (8b): Counter set by the source. It's decremented by one as it passes through each router along its path. When TTL reaches zero, the router currently holding the packet discards it and returns an ICMP Time Exceeded error message to the sender. This prevents packets from being forwarded by routers indefinitely.
  - __Protocol__ (8b): It tells the receiving device which protocol will be used for the data portion of the packet.
  - __Header checksum__ (16b): Checksum that can be used to detect corruption of the IP header in transit. Corrupted packets are discarded.
  - __Source IP address__ (32b): Address of sending device. IPv4 addresses are made up of 4 decimal, each one between 0 and 255, separated by periods (example: 24.234.2.17). It spans 4 bytes and allow for up to 4.3 billion possible addresses.
  - __Destination IP address__ (32b): Address of destination device.
  - __Options__ (0-40b): Security options to be applied if the HLEN value is greater than 5. This is communicated to the routing devices.
  
**IPv6 packet**: All possible IPv4 addresses cannot cover all the devices needing an IP address (IPv4 address exhaustion), so IPv6 was created. IPv6 is made of 8 hexadecimal numbers, each number made of 4 hexadecimal digits, separated by colons (example: 2002:0db8:0000:0000:0000:ff21:0023:1234 == 2002:0db8::ff21:0023:1234) (consecutive sets of all zeros are represented with a double colon). It spans 16 bytes and allow for up to 340 undecillion addresses (340 + 36 zeros). IPv6 offers more efficient routing and eliminates private address collisions that can occur on IPv4 when 2 devices in the same network try to use the same address. The IPv6 packet header simpler than IPv4:

- __Version__
- __Traffic class__
- __Flow label__
- __Payload length__
- __Next header__
- __Hop limit__
- __Source address__
- __Destination address_


### Network operations

#### Protocols

**Network protocols**: Set of rules used by two or more devices on a network to describe the order of delivery and the structure of the data. They serve as instructions that come with the information in the data packet that tell the receiving device what to do with the data. They're like a common language that allows devices all across the world to communicate with and understand each other. Some protocols have vulnerabilities that malicious actors exploit (example: somebody may use DNS protocol for diverting traffic from a legitimate website to a malicious one). Protocols from the Application layer (layer 7) are assigned **port numbers** by the IANA (Internet Assigned Numbers Authority). There're 3 types of network protocols: Communication, Management, Security.

OSI model:

7. **Application layer**: HTTP, HTTPS, SMTP, DNS... 
6. **Presentation layer**: -
5. **Session layer**: -
4. **Transport layer**: TCP, UDP...
3. **Network layer**: -
2. **Data link layer**: NCP, HDLC, SDLC, ARP...
1. **Physical layer**: -

TCP/IP model:

- Network access layer: ARP...
- Internet layer: IP, ICMP, NAT...
- Transport layer: TCP, UDP, NAT...
- Application layer: DNS, HTTP, HTTPS, SNMP, SMTP, SFTP, FTP, SSH, DHCP, SSH, Telnet, POP, IMAP... 

Example: To access a webpage we may use these protocols:

- DNS: Used for getting the IP address of the website.
- TCP: Used for performing a handshake between you and server, requesting data, and receiving packets to see the webpage.
- ARP: Used for packets to be able to move between network devices (like routers). 
- HTTPS: Used for having secure communication between you and server.

**Communication protocols**: They govern the exchange of information in network transmission. They dictate how the data is transmitted between devices and the timing of the communication. They include methods to recover data lost in transit. Examples:

- **TCP** (Transmission Control Protocol): Internet communication protocol that allows two devices to form a connection and stream data (note: it's not limited to 2 devices: it connects 2 endpoints, but the underlying network infrastructure can handle routing data packets across multiple devices). It ensures data is reliably transmitted to the destination service (it retransmits any data that is lost or corrupt). The packet's TCP header includes the destination port number. Packets are referred to as IP packets. It uses a 3-way handshake process (for verifying both devices before allowing communication): a device sends a SYN (synchronization) request to server, the server responds with a SYN/ACK packet to acknowledge the request, the device sends an ACK packet, and TCP connection is established.

- **UDP** (User Datagram Protocol): Connectionless protocol that does not establish a connection between devices before transmissions, making it less reliable than TCP (data sent over UDP is not tracked as extensively as over TCP). Used in applications that need transmissions to get quickly to destination, and not concerned with transmission's reliability (such as real-time performance sensitive applications like video streaming or sending DNS requests to local DNS servers). Packets are referred as datagrams.

- **IP** (Internet Protocol): Set of standards that allow communication between two networks (then, TCP/UDP delivers the data packets to the corresponding service). The IP address works like an address for each private network.

- **HTTP** (Hypertext Transfer Protocol): It provides a method of communication between clients (browser) and web servers. It uses port 80. It's considered insecure, so it is being replaced on most websites by HTTPS that uses encryption from SSL/TLS for communication.

- **DNS** (Domain Name System): It translates internet domain names into IP addresses. When a client computer wants to access a website domain using an internet browser, a query is sent to a dedicated DNS server (domain name and web address) that returns the IP address of the website. This IP address is used as destination address of your packets. It usually use port 53, but large replies may switch to using TCP.

- **ARP** (Address Resolution Protocol): Used to determine MAC address of the next router or device on the path. It translates the IP address found in data packets into the MAC address of the hardware device. Each device on the network performs ARP and keeps track of matching IP and MAC addresses in an ARP cache. No port assigned (since it's not an application layer protocol).

- **Telnet** (TCP port 23): Used to connect with a remote system. It sends all information in clear text. It uses command line prompts to control another device similar to SSH, but Telnet is not as secure as SSH. It can be used to connect to local or remote devices. 

- **SSH** (Secure Shell) (TCP port 22): It's used to create a secure connection with a remote system. It provides an alternative for secure authentication and encrypted communication. It replaces less secure protocols (like Telnet).

- **POP** (Post office protocol): Used to manage and retrieve email from a mail server. Many organizations have a dedicated mail server on the network that handles incoming and outgoing mail for users on the network. User devices will send requests to the remote mail server and download email messages locally. When using POP, mail has to finish downloading on a local device before it can be read. After downloading, the mail may or may not be deleted from the mail server, so it does not guarantee that a user can sync the same email across multiple devices.
  
  - **POP3** (unencrypted: TCP/UDP port 110) (encrypted: SSL/TLS over TCP/UDP port 995): Most commonly used version of POP.

- **IMAP** (Internet Message Access Protocol) (unencrypted: TCP port 143) (encrypted: SSL/TLS over TCP port 993): Used for incoming email. It downloads the headers of emails and the message content. The content also remains on the email server, which allows users to access their email from multiple devices. IMAP allows users to partially read email before it is finished downloading. Since the mail is kept on the mail server, it allows a user to sync emails across multiple devices.

- **SMTP** (Simple Mail Transfer Protocol) (unencrypted: TCP/UDP port 25) (encrypted: TCP/UDP port 587 using TLS): Used to transmit and route email from the sender to the recipient’s address. It works with MTA (Message Transfer Agent) software, which searches DNS servers to resolve email addresses to IP addresses, to ensure emails reach their intended destination. The TCP port 25 is often used by high-volume spam. It helps to filter out spam by regulating how many emails a source can send at a time.

**Management Protocols**: Used for monitoring and managing activity on a network. They include protocols for error reporting and optimizing performance on the network. Used to troubleshoot network issues. Examples:

- **SNMP** (Simple Network Management Protocol): Used for monitoring and managing devices on a network. It can reset a password on a network device or change its baseline configuration, and send requests to network devices for a report on how much of the network’s bandwidth is being used up.

- **ICMP** (Internet Control Message Protocol): Used by devices to tell each other about status and data transmission errors across the network (dropped/disappeared/redirected packets, connectivity issues,...). Device A asks device B for a status update, and B sends a report to A about the data transmission. It helps to detect and solve network errors. Usually used as a quick way to troubleshoot network connectivity and latency by issuing the `ping` command on Linux OS.

- **DHCP** (Dynamic Host Configuration Protocol) (server: UDP port 67) (client: UDP port 68): Used on a network to configure devices. It works with the router to assign a unique IP address to each device and provide the addresses of the appropriate DNS server and default gateway for each device.

**Security Protocols**: They ensure that data is sent and received securely across a network by using encryption algorithms to protect data in transit. Examples:

- **HTTPS** (HyperText Transfer Protocol Secure): It provides a secure method of communication between clients and website servers. It applies SSL/TLS (Secure Sockets Layer and Transport Layer Security) encryption to all transmissions, so malicious actors cannot read it. It uses port 443

- **SFTP** (Secure File Transfer Protocol): Used to transfer files from one device to another over a network. It uses SSH (Secure Shell), usually by TCP port 22. SSH uses AES (Advanced Encryption Standard) and other encryption types to ensure that unintended recipients cannot intercept the transmissions. It's often used with cloud storage (every time a user uploads or downloads a file from cloud storage, the file is transferred using the SFTP).

- **SSL/TLS**

- **IPSec**

Note: The encryption protocols mentioned don't conceal the source or destination IP address of network traffic.

**NAT** (Network Address Translation): Each device in your LAN have a private IP address that they use to communicate directly with each other. For communications with the public internet, the router can replace in outgoing messages the private source IP address with its public IP address (representing all devices on the LAN to the public) and perform the reverse operation for responses. This process generally requires a router or firewall to be configured to perform NAT. In the TCP/IP model, NAT process is a part of layer 2 (internet layer) and layer 3 (transport layer).

#### Wi-Fi

Around 2000, technologies were developed to send and receive data over radio. Today, users access wireless internet through computers (laptops, smart phones, tablets, desktops). Smart devices (thermostats, door locks, security cameras...) also use wireless internet to communicate with each other and with services on the internet.

**IEEE** (Institute of Electrical and Electronics Engineers): Organization that maintains Wi-Fi standards.

**IEEE 802.11 (Wi-Fi)**: Set of standards that define communications for wireless LANs. Wi-Fi protocols have improved over the years and now provide the same level of security and reliability as wired connections. Wi-Fi name is a marketing term commissioned by Wi-Fi Alliance (former WECA).

**Wireless security protocols**:

- **WEP** (Wired Equivalent Privacy) (1999): Oldest wireless security protocol. Designed to provide the same privacy level on wireless network connections as wired ones. It's largely out of use today. However, it had some flaws, including how encryption was used (WEP encryption can be potentially broken, so it's considered a high-risk security protocol).

- **WPA** (Wi-Fi Protected Access) (2003): Replacement for WEP that improves it and addresses some security issues it had by using TKIP (Temporal Key Integrity Protocol). WPA encryption algorithm uses larger secret keys than WEPs. WPA includes a message integrity check (including a message authentication tag with each transmission) which prevents a malicious actor from altering the transmission or resending at another time (the attack will be identified and the transmission rejected). It has backwards compatibility with older hardware. However, WPA still has vulnerabilities: A key reinstallation attack (KRACK) can be used to decrypt transmissions. Also, if an attacker inserts himself in the WPA authentication handshake process, he can inserts a new encryption key (instead of the dynamic one assigned by WPA), and by setting the new key to all zeros it's as if the transmission is not encrypted at all.

- **WPA2** (2004): It improves upon WPA by using the AES (Advanced Encryption Standard) and CCMP (Counter Mode Cipher Block Chain Message Authentication Code Protocol), which improves upon TKIP by providing encapsulation and ensuring message authentication and integrity. It's considered the security standard for all Wi-Fi transmissions today. However, it's vulnerable to KRACK attacks. It has 2 modes:

  - **WPA2 Personal mode**: Best for home networks. It's easy to implement, and has a faster setup than the Enteprise mode. The global passphrase needs to be applied to each individual computer and access point in a network (ideal for home networks, but unmanageable for organizations).

  - **WPA2 Enterprise mode**: Best for business applications. It provides the necessary security a business. It has a more complicated setup, but offers centralized and individualized control over the Wi-Fi access to a business network. Network administrators can grant or remove user access to a network at any time. Users never have access to encryption keys (preventing potential attackers from recovering network keys on individual computers).

- **WPA3** (2018): It addresses the authentication handshake vulnerability to KRACK attacks. It also uses SAE (Simultaneous Authentication of Equals), a password-authenticated, cipher-key-sharing agreement (preventing attackers from downloading data from wireless network connections to their systems to attempt to decode it). It also increases encryption to make passwords more secure by using 128-bit encryption (WPA3-Enterprise mode offers optional 192-bit encryption). It has 2 modes: Personal and Enterprise.

#### Firewalls

**Firewall**: Network security device (hardware or NVA) that monitors (inspect and filter) traffic to and from your network. It either allows traffic or it blocks it based on a defined set of security rules. It can use **port filtering** (block or allow certain port numbers to limit unwanted communication). Example: allow communications on port 443 for HTTPS or port 25 for email and block everything else. The firewall settings will be determined by the organization's security policy. Some types of firewalls are:

- **Hardware firewall**: It's the most basic way to defend against threats to a network. It inspects each data packet before it's allowed to enter the network.

- **Software firewall: It performs the same functions as a hardware firewall, but it's not a physical device. It's a software installed on a computer or server. If installed on a computer, it will analyze all the traffic received by that computer. If installed on a server, it will protect all the devices connected to the server. It's typically less expensive than a physical device, and occupies no space, but adds some processing overhead to the individual devices.

- **Cloud-based firewall**: Cloud service providers offer firewalls as a service (FaaS) for organizations. It's a software firewall hosted by a cloud service provider. Organizations can configure its rules on the cloud service provider's interface, and the firewall will perform security operations on all incoming traffic before
it reaches the organization’s onsite network. It also protect any assets or processes that an organization might be using in the cloud.

Depending how firewalls operate, they can be **stateful** or **stateless**:

- **Stateful**: It keeps track of information passing through it and proactively filters out threats. A stateful firewall analyzes network traffic for characteristics and
behavior that appear suspicious and stops them from entering the network. It only requires a rule in one direction because it uses a "state table" to track connections, so it can match return traffic to an existing session 

- **Stateless**: It only operates based on predefined rules and doesn't keep track of information from data packets. These preconfigured rules are set by the firewall administrator, and tell the device what to accept and reject. It doesn't store analyzed information, nor discover suspicious trends like a stateful firewall does. It's considered less secure than stateful firewalls. It requires rules to be configured in two directions.

**NGFW** (Next Generation Firewall): It provides even more security than a stateful firewall. It provides stateful inspection of incoming and outgoing traffic and performs more in-depth security functions (see list below). Some NGFWs connect to cloud-based threat intelligence services so they can quickly update to protect against emerging cyber threats.

- __Deep packet inspection__: Kind of packet sniffing that examines data packets and takes actions if threats exist.
- __Intrusion prevention__: It detects security threats and notify firewall administrators.
- __Application layer inspection__: It can inspect traffic at the application layer (TCP/IP model) and are typically application aware. NGFWs can block or allow traffic based on the application (Unlike traditional firewalls that only block traffic based on IP address and ports).
- Some NGFWs have additional features like: Malware Sandboxing, Network Anti-Virus, and URL and DNS Filtering. 

#### VPNs

When you connect to the internet, your ISP receives your network's requests and forwards it to the correct destination server. But your request includes private information, so if the traffic gets intercepted, someone could potentially connect your internet activity with your physical location and your personal information (including bank accounts and credit card numbers). Moreover, the MAC and IP address of the destination device is contained in the header and footer of a data packet, which shows the IP and virtual location of your private network. You can encrypt a data packet to protect your information, but routers won't be able to read the IP and MAC address to know where to send it. Encapsulation solves this by encrypting your data packet and encapsulating it in another data packet that the router can read.

**Encapsulation**: Protect data by wrapping it in other data packets. 

**VPN**: Network security service that encrypts your data packets and encapsulates them in other data packets. This way, your data is encrypted (unreadable while in transit) and your public IP address is changed (your virtual location is hidden so you can keep your data private when using public networks like the internet). It also uses an encrypted tunnel between your device and the VPN server. 

Note: most websites today use HTTPS (it encrypts data being transferred between your device and the website), which makes it harder to intercept personal information even if internet traffic can be seen. A VPN encrypts all your internet traffic protects your privacy even more.

VPNs allow your data to be sent across a public network while remaining anonymous. Many organizations use VPNs to help protect communications from users’ devices to corporate resources. Individuals use VPNs to increase personal privacy. A reputable VPN also minimizes its own access to user internet activity by using strong encryption and other security measures. Organizations are increasingly using a combination of VPN and SD-WAN capabilities to secure their networks.

**SD-WAN** (Software-Defined Wide Area Network): Virtual WAN service that allows organizations to securely connect users to applications across multiple locations and over large geographical distances.

VPNs provide a server that acts as a gateway between a computer and the internet. It creates a path similar to a virtual tunnel that hides the computer’s IP address and encrypts the data in transit to the internet. The main purpose of a VPN is to create a secure connection between a computer and a network. Additionally, a VPN allows trusted connections to be established on non-trusted networks. VPN protocols determine how the secure network tunnel is formed. Different VPN providers provide different VPN protocols.

Two types of VPNs are:

- **Remote access VPN**: Used by individual users to establish a connection between a personal device and a VPN server (client-server connection). It encrypts data sent or received through a personal device. The connection between the user and the remote access VPN is established through the internet.

- **Site-to-site VPN**: Used by enterprises (particularly, by those with many offices across the globe) to extend their network to other networks and locations. It commonly use the IPSec protocol to create an encrypted tunnel between the primary network and the remote network. Disadvantage: it may be complex to configure and manage.

**Endpoint**: Any device connected to a network (computer, mobile device, server...).

**VPN protocol**: Similar to a network protocol. It’s a set of rules or instructions that will determine how data moves between endpoints. It's used to encrypt traffic over a secure network tunnel. VNP providers offer a variety of options for VPN protocols. Choosing one of them depend on many factors (connection speeds, compatibility with netro). Two of them are:

- **IPSec VPN**: Used by most VPN providers to encrypt and authenticate data packets. Since it's one of the earlier VPN protocols, many operating systems support IPSec from VPN providers. It's older and more complex than WireGuard.

- **WireGuard**: It has high-speed and advanced encryption. Designed to be simple to set up and maintain. Is can be used for both site-to-site connection and client-server connections. Its download speed is enhanced by using fewer lines of code. It's open source, which makes it easier for users to deploy and debug. Useful for processes that require faster download speeds (streaming video, downloading large files...).
IPSec VPN

#### Security zones

**Subnetting**: Subdivision of a network into logical groups called subnets (it's like a network inside a network). It divides up a network address range into smaller subnets within the network. They form based on the IP addresses and network mask of the devices on the network. It creates a network of devices to function as their own network. This makes the network more efficient and can be used to create security zones. If devices on the same subnet communicate with each other, the switch changes the transmissions to stay on the same subnet, improving comunication's speed and efficiency (due to a more efficient use of network bandwidth). Creating subnets doesn't require requesting another network IP address from your ISP. Subnetting is one component of creating isolated subnetworks through physical isolation, routing configuration, and firewalls.

**Security zone**: It's a segment of a network that protects the internal network from the internet. It acts like a barrier to internal networks, maintains privacy within corporate groups, and prevents issues from spreading to the whole network.

**Network segmentation**: Security technique that divides the network into segments, each one with its own access permissions and security rules. Security zones control who can access different segments of a network. Example: in a hotel, an unsecured guest Wi-Fi network is kept separate from another encrypted network used by the staff.

**Subnets** (or subnetworks): An organization's network can be divided into subnetworks to maintain privacy for each department. Example: at university, there may be a faculty subnet and a students subnet. If the student's subnet is contaminated, network administrator can isolate it and keep the rest of the network free from contamination.

An organization's network has 2 types of security zones:

- **Uncontrolled zone**: Network outside of the organization's control (like the internet).

- **Controlled zone**: Subnet that protects the internal network from the uncontrolled zone. This zone has several types of networks in different layers:

  - **DMZ** (Demilitarized zone): Outer layer zone. Public-facing services that can access the internet (web servers, proxy servers that host websites for the public, DNS servers that provide IP addresses for internet users, email and file servers that handle external communications, etc.). It acts as a network perimeter to the internal network. Ideally, it's situated between two firewalls (one filtering traffic outside the DMZ, and one filtering traffic entering the internal network).

  - **Internal network**: Inner layer zone. It contains private servers and data that the organization neess to protect.

    - **Restricted zone**: If it exists, it's contained in the Internal network. It protects highly confidential information that is only accessible to employees with certain privileges. It's protected with a firewall between the internal network and the restricted zone.

This way, attacks penetrating the DMZ cannot spread to the internal network, and attacks penetrating the internal network cannot access the restricted zone. A security team may regulate access control policies on these firewalls, and control traffic reaching the DMZ and internal network by restricting IPs and ports (example: only HTTPS traffic may be allowed to access web servers in the DMZ). 

Method of assigning subnet masks to IP addresses to create a subnet:

**Classfull addressing**: Used in the 1980s as a system of grouping IP addresses into classes (Class A to Class E). Each class included a limited number of IP addresses, which were depleted as the number of devices connecting to the internet outgrew the classful range in the 1990s.

**CIDR** (Classless Inter-Domain Routing): Replacement for classful addressing. Classless addressing expanded the number of available IPv4 addresses. It allows to segment classful networks into smaller chunks. CIDR IP addresses are formatted like IPv4 addresses, but they include a slash (`/`) followed by a number at the end of the address (IP network prefix) (examples: 198.51.100.0 is an IPv4 address. 198.51.100.0/24 is a CIDR IP address). CIDR address encompasses all IP addresses between 198.51.100.0 and 198.51.100.255. The CIDR addressing system reduces the number of entries in routing tables and provides more available IP addresses within networks.

**IPAddressGuide**: Online tool for converting CIDR to IPv4 addresses and vice versa.

#### Proxy servers

**Proxy server**: Used to secure internal networks. It's a dedicated server that fulfills the requests of its clients by forwarding them to other servers. It sits between the internet and the rest of the network (NAT serves as a barrier). It's a public IP address that is different from the rest of the private network, which hides the private network's IP address from malicious actors on the internet and adds a layer of security.

It fulfills the request of a client by forwarding them on to other servers. When a request to connect to the network comes in from the internet, the proxy server will determine if the connection request is safe. It uses temporary memory to store data that's regularly requested by external servers, so it doesn't have to fetch data from the organization's internal servers every time (which enhances security). Example: When a client receives an HTTPS response, they will notice a distorted IP address or no IP address rather than the real IP address of the organization's web server.

Some proxy servers can be configured with rules, like a firewall (example: block user's access to unsafe websites).

Some types of proxy servers supporting network security are:

- **Forward proxy server**: It regulates and restricts internal clients when they access resources external to the network. It hides a user's IP address and approve all outgoing requests. In an organization, a forward proxy server receives outgoing traffic from an employee, approves it, and forwards it on to the destination on the internet.

- **Reverse proxy server**: It regulates and restricts external systems when they access to services on the internal network. It accepts traffic from external parties, approves it, and forwards it to the internal servers. This protects internal web servers containing confidential data from exposing their IP address to external parties. 

- **Email proxy server**: It filters spam email by verifying whether a sender's address was forged. This the risk of phishing attacks that impersonate people known to
the organization.

### Network intrusions

#### Attacks

Network attacks may have great negative consequences in an organization: Financial, Reputation, and Public safety.

Attacks can harm an organization by:

- Leaking valuable or confidential information
- Damaging an organization's reputation
- Impacting customer retention
- Costing money and time

Example: In 2014, some hackers attacked the Amerincan home-improvement chain Home Depot and infected their servers with malware. By the time network adminstrators shut down the attack, they had already debit and credit card information of over 56 million customers.

Common network intrusion attacks:

- __Infiltration__: Malware, Spoofing, Packet sniffing...
- __Operations disruption__: Packet flooding...

**Botnet**: Collection of computers infected by malware that are under the control of a single threat actor (bot-herder). Each computer can be controlled remotely to send a data packet to a target system. They can be used to perform a DDoS attack.

**Network Interface Card** (NIC): Piece of hardware that connects a device to a network. It reads the data transmission and, if it contains the device's MAC addres, it accepts the packet and sends it to the device to process the information based on the protocol. A NIC can be set to promiscuous mode, so it accepts all traffic on the network, including packets not addressed to the NIC's device. 

**Defense-in-depth** principle: There isn't a perfect strategy for stopping each kind of attack. You can layer your defense by using multiple strategies (example: encryption will strangthen security and help against DoS attacks).

**Network interception attacks**: 

- **Packet sniffing**: It intercepts network traffic and steals valuable information or interfers with the transmission in some way (altering the message, inserting malicious code...). This can be done with hardware or software tools. A malicious actor can insert himself between two connected devices and spy on every packet comming across his device. Packet sniffing can be passive (packets read in transit) or active (packets manipulated in transit). To be protected, use VPN (encryption), connect to HTTPS websites (SSL/TLS encryption), and avoid unprotected Wi-Fi (doesn't use encryption).

- **IP spoofing**: It changes the source IP of a data packet (obtained via packet sniffing) to impersonate an authorized system (using IP and MAC addresses of authorized devices) and gain access to a network (by passing firewalls). To be protected, use firewalls (if a received packet's sender IP address is the same as the private network, the firewall will deny transmission with that IP address since all devides with that address should already be on the local network. Configure the firewall by creating a rule to reject all incoming traffic that has the same IP address as the local network). Common types are:

  - **On-path attack** (meddler-in-the-middle attack): An attacker places himself in the middle of an authorized connection and intercepts or alters the data in transit. After learning IP and MAC addresses of the devices, he can pretend to be either of them. Alternatively, if an attacker can intercept a DNS lookup, he can spoof the DNS response from the server and redirect a domain name to a different IP address (protect yourself against this by encrypting data in transit, such as TLS).

  - **Replay attack**: An attacker intercepts a data packet in transit and delays it or repeats it at another time. The attacker may want to cause connection issues between devices, or to impersonate the authorized user by repeating the transmission at a later time.

  - **Smurf attack**: Combination of DDoS attack and IP spoofing attack. An attacker sniffs an authorized user's IP address and floods it with packets (example: ICMP flood). Once the spoofed packet reaches the broadcast address, it's sent to all devices and servers on the network. To get protected, use a firewall to monitor any unusual traffic on the network (most NGFW can detect oversized broadcasts before they can crash the network).

**Backdoor attacks**: It works around the security measures by finding a weakness. It may be left intentionally by programmers or system and network adminstrators in order to help programmers conduct troubleshooting or administrative tasks. But it can also be installed by attackers after compromising an organization to ensure persistent access. Once inside, the hacker can cause extensive damage (install malware, DoS attack, steal information, change security settings...).

**DoS attack** (Denial of Service): It targets a network or server and floods it with network traffic. It sends huge amounts of information in order to overload the organization's network (to crash it or make it unable to repond to legitimate users). A network crash can make them vulnerable to other threats and attacks. The attacker doesn't receive a response from the targeted host (unlike IP spoofing). Everything about the data packet is authorized, including header's IP address (if combined with IP spoofing, they use fake IP address). If multiple devices or servers are used, it's a **DDoS attack** (Distributed Denial of Service). Network level DoS attacks target network bandwidth to slow traffic, and some common types are:

- **SYN flood attack**: It simulates a TCP connection and floods a server with SYN packets.
- **ICMP flood**: It floods a server with ICMP packets.
- **Ping of death**: It pings a system by sending it an oversized ICMP packet bigger than 64KB. It may overload the system and crash it.

#### Network protocol analyzer

**Network protocol analyzer** (packet sniffer, packet analyzer): Tool for capturing and analyzing data traffic within a network. Usually used to monitor networks and identify suspicious activity. However, attackers can use it to gain information about a specific network.

Most common ones are:

- SolarWinds NetFlow Traffic Analyzer
- ManageEngine OpManager
- Azure Network Watcher
- Wireshark
- tcpdump

**tcpdump**: Popular, lightweight command-line tool. It uses the open-source libpcap library. It can be installed in Unix-based OSs (Linux, macOS). It provides a brief packet analysis and presents key information about network traffic and each packet. After executing a command, it outputs the sniffed packets to the command line, and optionally to a log file. The output of a captured packet contains some information: timestamp (hours:minutes:seconds), source IP, source port, destination IP, destination port. It may resolve host addresses to hostnames, and resolve port numbers with commonly associated services that use these ports. Commons uses:

- Capture and view network communications and collect statistics about the network (such as troubleshooting network performance issues).
- Establish baseline for network traffic patterns and network utilization metrics.
- Detect and identify malicious traffic.
- Create customized alerts to send the right notifications when network issues or security threats arise.
- Locate unauthorized instant messaging (IM), traffic, or wireless access points.
- Attackers can use it to gain information about a network (like capture data packets containing sensitive information).

```
21:00:23.483629 IP 198.168.10.1.41 > 198.111.123.1.61012
```

### Security hardening

#### Security hardening

**World-writable file**: A file that can be altered by anyone in the world.

**Attack surface**: All potential vulnerabilities a threat actor could exploit in a system.

**Security hardening**: Process of strengthening a system to reduce its vulnerability and attack surface. It's performed on hardware, operating systems, applications, networks, and databases. This is achieved via:

- __Physical security__: Cameras, guards, etc.
- __Software updates__ (patches)
- __Device application configuration changes__: More frequent passwords update, update encryption standards for databases, disable unused elements (applications, services ports), reduce access permissions, etc. Minimizing the number of applications, devices, ports, and access permissions makes network and device monitoring more efficient and reduces the overall attack surface.
- __ Backups__
- __Penetration testing__ (Pen test): Simulated attack that helps identify vulnerabilities in the systems, networks, websites, applications, and processes.

#### OS hardening

**OS hardening**: Set of procedures that maintains OS security and improves it.

**Operative system** (OS): Interface between computer hardware and the user. It's the first program loaded when a computer turns on. It's an intermediary between software applications and the computer hardware. An insecure OS in one device may lead to the whole network being compromised. Recommended OS hardening practices include tasks performed at regular intervals (patch installation, backups, keeping an up-to-date list of devices and authorized users, etc.) and tasks performed once (preliminary safety measures such as configuring a device setting to fit a secure encryption standard).

- **Patch update** (patch installation): Software (including OS) update that, among other things, addresses security vulnerabilities within a program or product. They upgrade software to its latest version. As soon as a software vendor publishes a patch with a vulnerability fix, malicious actors know where the vulnerability is in out-of-date software. Thus, it's important to run patch updates as soon as they're released.

- **Baseline configuration** (baseline image): Documented set of specifications within a system that is used as a basis for future builds, releases, and updates (example: firewall with a list of allowed and disallowed network ports). The newly updated OS must be added to it. If unusual activity affects the OS, we can compare current configuration to the baseline and check if something changed. 

- **Hardware and software disposal**: remove unnecessary vulnerabilities by ensuring that old hardware is properly wiped and disposed of, and delete unused software applications.

- **Password policy**: Security measure that requires passwords to follow specific rules. Ensure the implementation of a strong password policy.

- **Multi-factor authentication (MFA)**: Security measure that requires users to verify their identity in two or more ways to access a system or network. Categories: something you know (pasword...), something you have (ID card...), something unique about you (fingerprint...).

**Brute force attacks**: It's a trial-and-error process of discovering private information. It can be a tedious and time consuming process, but there're a range of tools used to conduct this attack. There're different types of attacks for guessing passwords

- __Simple brute force attack__: The attacker tries to guess a user's login credentials. He may do this by entering any combination of usernames and passwords he can think of.
- __Dictionary attack__: Similar to simple attack, but using a list of commonly used passwords and stolen credentials from previous breaches. Originally, a list of words from the dictionary was used, until complex password rules became a common security practice. 

**Assesing vulnerabilities**: Before an incident occurs, companies can run some tests on their network or web applications to assess vulnerabilities. Virtual machines and sandboxes can be used to test suspicious files, check for vulnerabilities, or simulate a cybersecurity incident.

- **Virtual machine** (VM): Software version of a physical computer. It provides another security layer because it lets you run code in an isolated environment, preventing malicious code from affecting the rest of the system (or preventing damage if its tools are used improperly). It can be deleted and replaced by a pristine image after testing malware, or reverted to a previous state. It's useful when investigating potentially infected machines or running malware in a constrained environment. However, there’s a small risk that a malicious program can escape virtualization and access the host machine. It can be used to test applications. It helps in streamlining many security tasks. It's easy to switch between different VMs.

- **Sandbox**: Type of testing environment that allows you to execute software or programs separate from your network. It's commonly used for testing patches, identifying and addressing bugs, or detecting cybersecurity vulnerabilities. It can also be used to evaluate suspicious software and files, and simulate attack scenarios. It can be a stand-alone physical computer not connected to a network, or a software or cloud-based virtual machine (more time and cost effective). Note that some malware code can detect if it's executed in a VM or sandbox environment, and behave as harmless software when run inside these environments. 

**Prevention measures** against brute force attacks and similar: 

- **Salting and hashing**: Hashing converts information into a unique value that can then be used to determine its integrity. It is a one-way function (i.e., it's impossible to decrypt and obtain the original text). It adds random characters to hashed passwords, which increases length and complexity of hash values, making them more secure.

- **Multi-factor authentication** (MFA): It requires a user to verify his identity in two or more ways to access a system or network. This verification happens using a combination of authentication factors: username and password, fingerprints, facial recognition, or a **one-time password** (OTP) sent to a phone number or email. The **Two-factor authentication** (2FA) is similar to MFA, except it uses only two forms of verification.

- **CAPTCHA** (Completely Automated Public Turing test to tell Computers and Humans Apart): It asks users to complete a simple test that proves they are human, preventing software from trying to brute force a password. **reCAPTCHA** is a Google free CAPTCHA service for protecting websites from bots and malware.

- **Password policies**: Used to standardize good password practices throughout a business. They can include guidelines on password complexity, updating frequency, reusability, number of login attempts before suspending the account, etc.

#### Network hardening

**Network hardening** focuses on port filtering, network access privilege, and encryption. Two basic types of hardening tasks: 

- **Performed regularly**. Examples:

  - **Network log analysis**: Process of examining network logs to identify events of interest. Security teams perform this by using a __log analyzer tool__ or a __SIEM tool__ (Security Information and Even Management). SIEM tools can gather security data from the network (logs) and present it in a single dashboard, which may show network vulnerabilities and list them in a scale of priority. 
  - **Firewall rules maintenance**
  - **Patch updates**
  - **Server backups

- **Performed once**, and then updated as needed. Examples:

  - **Port filtering**: Firewall function that blocks or allows certain port numbers to limit unwanted communication. Only the needed ports should be allowed, while those not being used should be disallowed.
  - **Up-to-date protocols**: Networks should be set up with the most up-to-date wireless protocols available. Older ones should be disallowed.
  - **Network segmentation**: Create isolated subnets for different departments in the organization. This way, issues in one subnet doesn't spread accros the whole company, and each user only has access to the part of the network required for his role. This can also separate different security zones (network zones containing confidential data should be separate from the resto fo the network.
  - **Firewalls**
  - **Communications encryption**: Use the latest encryption standards (rules or methods used to conceal outgoing data and uncover or decrypt incoming data), specially in restricted zones.

**Network security applications**:

**SOC** (Security Operations Center): Place where security analysts monitor the activity across the network. 

The **defense in depth** approach adds layers of security (devices, tools, strategies) to a network until the network owner is satisfied with the level of security. Some tools available are: Firewall, IDS (Intrusion Detection System), IPS (Intrusion Prevention System), SIEM tools. Each tool is a layer that incrementally hardens the network.

- **Firewall**: It allows or blocks traffic based on a set of rules. The header of incoming packets are inspected and allowed or denied based on its port number. NGFWs also inspect packet payloads. Each system should have its own firewall, regardless of the network firewall.

- **IDS** (Intrusion Detection System): Application that monitors system activity and alerts on possible intrusions, based on the signature of malicious traffic and anomalies. It can be configured to detect known attacks. It often sniff data packets moving across the network and analyze them. It's placed behind the firewall and before entering the LAN (to analyze filtered traffic, which reduces false positives). New and sophisticated attacks might not be caught. It doesn’t stop the incoming traffic if it detects something awry. It’s up to the network administrator to catch the malicious activity before it damages the network. When combined with a firewall, it adds another layer of defense. 

- **IPS** (Intrusion Prevention System): Application that monitors system activity and takes action to stop intrusive activity. More secure than IDS (it doesn't stop detected anomalies). It searches for signatures of known attacks and data anomalies. It reports anomalies and blocks a specific sender or drops suspicious packets. It's placed between a firewall and the internal network. It's inline (if it breaks, the connection between the private network and the internet breaks). False positive can result in legitimate traffic getting dropped.

- **Full packet capture devices**: Used to record and analyze all of the data that is transmitted over your network. They also aid in investigating alerts created by an IDS. 

- **SIEM tools** (Security Information and Event Management system): Applications that collect and analyze log data in real time to monitor critical activities (examples: Google's Chronicle, Splunk, etc.). They report suspicious activity in a central dashboard. They also analyze network log data sourced from firewalls, IDSs, IPSs, VPNs, proxies, and DNS logs. They're a way to aggregate security event data and place it all in one place for security analysts to analyze (single pane of glass). SIEM tools are used in combination with other security methods. Security analysts determine how to respond to the information on the dashboard and decide when the events require to be oversight.

#### Cloud hardening

**Zero-day attack**: Exploit that was previously unknown.

**VM escapes** (Virtual Machine escapes): Exploit where a malicious actor gains access to the primary hypervisor, potentially the host computer and other VMs.

**Encryption**: Process of scrambling information into ciphertext, which is not readable to anyone without the encryption key. Classic encryption encoded information using an algorithm to convert any given character to a new value. Modern encryption relies on the secrecy of a key, rather than the secrecy of an algorithm.

Many organizations use network services in the cloud. The cloud servers provider host these servers but cannot prevent intrusions (internal or external). Using a server **baseline image** for all server instances stored in the cloud allows us to compare data in cloud servers with the baseline image and confirm that no unverified changes have been done. Similar to OS hardening, data and applications are kept **separate** depending on their service category (examples: Older applications separated from newer applications. Software dealing with internal functions separated from front-end applications). Cloud services provide ease of deployment, speed of deployment, cost savings, and scalability, but present some unique security challenges.

**Shared responsibility model**: Cloud security principle stating that the CSP must take responsibility for security involving the cloud infrastructure, including physical data centers, hypervisors, and host operating systems. The company using the cloud service is responsible for the assets and processes that they store or operate in the cloud. This ensures that both agree about where their security responsibility begins and ends. Problem: an organization may assume that the CSP is taking care of security that is actually responsability of the organization (example: CSP takes responsibility for securing the cloud services, but it's the organization’s responsibility to ensure that services are configured properly according to the organization's security requirements). 

**Cloud security hardening**: Various techniques and tools can be used to secure cloud network infrastructure and resources.
 
- **IAM** (Identity access management): Collection of processes and technologies that helps organizations manage digital identities in their environment. It also authorizes how users can use different cloud resources. Improper configuration of cloud user roles increases risk of unauthorized users accessing critical cloud operations.

- **Configuration**: There're many cloud services available, and each one must be carefully configured to meet security and compliance requirements, especially during an initial migration into the cloud (ensure that every process moved into the cloud has been configured correctly). Otherwise, the network could be compromised. Misconfigured cloud services are a common source of cloud security issues.
 
- **Attack surface**: Each service or application on a network provided by a CSP (Cloud Service Provider) carries risks and vulnerabilities, and increases an organization’s overall attack surface (compensate this with increased security measures). Cloud networks using many services introduce lots of entry points into an organization’s network (used to introduce malware or pose security vulnerabilities), unless the network is designed correctly. Often, CSPs use more secure options, and are under more scrutiny than traditional on-premises networks.

- **Zero-day attacks**: CSPs are more likely to know about this attack occurring before a traditional IT organization does. CSPs have ways of patching hypervisors and migrating workloads to other virtual machines, so customers are not impacted by the attack. There are also several tools available for patching at the OS.

- **Visibility and tracking**: Network administrators have access to every data packet (sniff and inspect) crossing the network with both on-premise and cloud networks. This is used for learning about network performance or checking for possible threats and attacks. This is offered in the cloud through flow logs and tools (such as packet mirroring). CSPs take responsibility for security in the cloud (some provide strong security measures to protect their infrastructure), but don't allow their clients (organizations) to monitor traffic on the CSP’s servers. CSPs pay for third-party audits to verify how secure a cloud network is and identify potential vulnerabilities (including on-premise infrastructure vulnerabilities, and compliance lapses from the CSP).

- **Things change fast in the cloud**: CSPs work hard to stay up-to-date with technology advancements. For some organizations this can be a potential challenge to keep up with (it requires them to often update their IT processes and align with changes made by the CSP). Cloud service updates can affect security considerations for the organizations using them (example: connection configurations might need to be changed based on the CSP’s updates). Cloud networking offers various options that might appear attractive, but each service adds complexity to the security profile of the organization, and requires security personnel to monitor all cloud services. 

- **Hypervisors**: It abstracts the host’s hardware from the operating software environment. Vulnerabilities in hypervisors or misconfigurations can lead to virtual machine escapes. As a CSP customer, you will rarely deal with hypervisors directly. Two types:
  - Hypervisors running on the hardware of the host computer (example: VMware®'s ESXi). Commonly used by CSPs (they manage hipervisor and other virtualization components, ensure that cloud resources and cloud environments are available, and provide regular patches and updates).
  - Hypervisors operating on the software of the host computer (example: VirtualBox). 

- **Baselining**: It's a fixed reference point that cover how the cloud environment is configured and set up. This reference point can be used to compare changes made to a cloud environment. Proper configuration and setup can greatly improve the security and performance of a cloud environment. Examples of establishing a baseline in a cloud environment: restricting access to the admin portal of the cloud environment, enabling password management, enabling file encryption, and enabling threat detection services for SQL databases.

- **Cryptography in the cloud**: It can be applied to secure data that is processed and stored in a cloud environment, preventing unauthorized access. It uses encryption and secure key management systems to provide data integrity and confidentiality. 

- **Cryptographic erasure**: Method of erasing the encryption key for the encrypted data. When destroying data in the cloud, traditional data destruction methods are not as effective. **Crypto-shredding** is a newer technique where the cryptographic keys used for decrypting the data are destroyed, making the data undecipherable and preventing anyone from decrypting it. When crypto-shredding, all copies of the key need to be destroyed so no one has any opportunity to access the data in the future.

- **Key Management**: The encryption keys must be secure. Customers typically don't have access to the specific encryption keys used by the CSPs to encrypt their data, but customers can usually provide their own encryption keys. This makes the customer responsible of keeping encryption keys secure and confidential, and limits how the CSP can help if keys are compromised or destroyed. The shared responsibility model makes the customer not entirely responsible for maintenance of the cryptographic infrastructure. Organizations and customers don't have access to the CSP directly, but they can request audits and security reports to the CSP, which let them assess and monitor the risk involved with allowing the CSP to manage the infrastructure. For federal contractors, FEDRAMP provides a list of verified CSPs. Some measures to further protect your data are:

  - **TPM** (Trusted Platform Module): It's a computer chip that can securely store passwords, certificates, and encryption keys.
  - **CloudHSM** (Cloud hardware security module): Computing device that provides secure storage for cryptographic keys and processes cryptographic operations (like encryption and decryption).


## Linux






# SQL

