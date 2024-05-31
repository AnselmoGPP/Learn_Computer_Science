# Cybersecurity

<br>![cybersecurity image](https://raw.githubusercontent.com/AnselmoGPP/Learn_Computer_Science/master/resources/miscellany.jpg)

## Table of Contents
+ [Foundations](#foundations)
+ [Managing security risks](#managing-security-risks)
+ [Network security](#network-security)


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

**Cloud computing**: Practice of using remote servers, applications, and network services that are hosted on the internet instead of on local physical devices.
 
**Cloud service provider (CSP)**: Company offering cloud computing services. It also provides on-demand storage, processing power that their customers only pay as needed, and business and web analytics that organizations can use to monitor their web traffic and sales. Companies can pay for storage and services and consume them through the CSP’s application programming interface (API) or web console. It provides 3 main services:
- **Software as a service (SaaS)**: Software suites operated by the CSP that a company can use remotely without hosting the software. 
- **Infrastructure as a service (IaaS)**: Use of virtual computer components offered by the CSP (virtual containers and storage, computing...). Some applications can take advantage of the availability, performance, and security features that are unique to cloud provider services.
- **Platform as a service (PaaS)**: Tools for designing custom applications that are designed and accessed in the cloud and used for a company’s specific business needs.

**On-premise network**: Network where all the devices used for network operations are kept at a physical location owned by the company.

**Cloud network**: Collection of servers or computers that stores resources and data in a remote data center that can be accessed via the internet. It saves money, simplifies operations, and provides more resources.

**Hybrid cloud environment**: It's when an organization use a CSP’s services in addition to their on-premise computers, networks, and storage.

**Multi-cloud environment**: It's when an organization use more than one CSP.

**Software-defined network (SDN)**: Made up of virtual network devices and services. Just like CSPs provide virtual computers, many SDNs also provide virtual switches, routers, firewalls, and more. Most modern network hardware devices also support network virtualization and software-defined networking. This means that physical switches and routers use software to perform packet routing. In the case of cloud networking, the SDN tools are hosted on servers located at the CSP’s data center.

**Benefits** of cloud computing and SDNs:
- __Reliability__: Resources can be accessed consistently and with minimal interruption. 
- __Decreased cost__: Since CSPs have such large data centers, they can offer virtual devices and services at good price.
- __Scalability__: CSPs let consume services in an elastic utility model as needed, so companies only pay for what they need when they need it.
- __Modifiable__: Changes can be made quickly through the CSPs, APIs, or web console—much. Example: if more protection is required, web application firewalls (WAFs), intrusion detection/protection systems (IDS/IPS), or L3/L4 firewalls can be configured quickly, leading to better network performance and security.

**Data packet**: Basic unit of information that travels from one device to another within a network. The packet's content is divided into:
- **Header**: Contains the IP address (Internet Protocol), MAC address (Media Access Protocol), and Protocol number (port number, which tells what to do with the information).
- **Body**: Message to transmit.
- **Footer**: It signals that the packet is finished.

**Bandwidth**: Amount of data a device receives every second.

**Speed**: Rate at which data packets are received or downloaded.

If bandwidth or speed are irregular, it may indicate an attack.

**Packet sniffing**: Practice of capturing and inspecting data packets across a network.

**Network protocol**: Set of standards used for routing and addressing data packets as they travel between devices on a network.

<br>![models image](https://raw.githubusercontent.com/AnselmoGPP/Learn_Computer_Science/master/resources/network_models.png)

**TCP/IP model** (Transmission Control Protocol / Internet Protocol): It's the standard model for network communication, based on the TCP/IP protocols suite. It's a framework for visualizing how data is organized and transmitted accross the network. It has 4 layers:

- **Network access layer** (or Data link layer): It deals with the creation of data packets and transmission across a network. It corresponds to the physical hardware for network transmission (hubs, modems, cables, wiring...). The Address Resolution Protocol (ARP) is needed for mapping IP addresses to MAC addresses (used to identify hosts on the same physical network) for local network communication.

- **Internet layer** (or Network layer): It's responsible for ensuring delivery to the destination host (potentially residing on a different network). It ensures IP addresses are attached to data packets to indicate the location of the sender and receiver. It also determines which protocol is responsible for delivering the data packets and ensures the delivery to the destination host. Some common protocols are:

  - **Internet Protocol** (IP): Set of standards that allow communication between two networks (then, TCP/UDP delivers the data packets to the corresponding service). The IP address works like an address for each private network.

  - **Internet Control Message Protocol (ICMP)**: It shares error and status information of data packets (dropped/disappeared/redirected packets, connectivity issues,...). Useful for detecting and solving network errors. 

- **Transport layer**: Responsible for delivering data between two systems or networks. It includes protocols to control the flow of traffic across a network (which permit or deny communication with other devices), and information about the connection status. Used for error control (ensure data is flowing smoothly).

  - **TCP** (Transmission Control Protocol): Internet communication protocol that allows two devices to form a connection and stream data. It ensures data is reliably transmitted to the destination service (it retransmits any data that is lost or corrupt). The packet's TCP header includes the destination port number.

  - **UDP** (User Datagram Protocol): Connectionless protocol that does not establish a connection between devices before transmissions. Used by applications that are not concerned with the reliability of the transmission. Data sent over UDP is not tracked as extensively as over TCP. Used mostly for real-time performance sensitive applications like video streaming.

- **Application layer**: Responsible for making network requests or responding to requests. It defines which internet services and applications any user can access. Protocols here determine how data packets will interact with receiving devices. It relies on underlying layers to transfer the data across the network. Operations in this layer include file transfers and email services. Some common protocols: HTTP (Hypertext transfer protocol), SMTP (Simple mail transfer protocol), SSH (Secure shell), FTP (File transfer protocol), DNS (Domain name system).

**Port**: Software-based location in the OS of a network device that organizes the sending and receiving of data between devices on a network. When data packets are sent and received across a network, they are assigned a port. Ports divide network traffic into segments based on the service they will perform between two devices. The computers sending and receiving these data segments know how to prioritize and process these segments based on their port number. Port numbers allow computers to split the network traffic and prioritize the operations they will perform with the data. Some common ports are: 25 (e-mail), 443 (secure internet communications), 20 (large file transfers).





