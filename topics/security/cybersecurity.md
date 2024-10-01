# Cybersecurity

<br>![miscellaneous image](https://raw.githubusercontent.com/AnselmoGPP/Learn_Computer_Science/master/resources/miscellany.jpg)

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
        + [Attacks](#attacks)
        + [Network protocol analyzer](#network-protocol-analyzer)
    + [Security hardening](#security-hardening)
        + [Security hardening](#security-hardening)
        + [OS hardening](#os-hardening)
        + [Network hardening](#network-hardening)
        + [Cloud hardening](#cloud-hardening)
+ [Operative system](#operative-system)
    + [Operative systems](#operative-systems)
    + [Linux](#linux)
        + [Architecture](#architecture)
        + [Distributions](#distributions)
        + [Shells](#shells)
        + [Filesystem](#filesystem)
        + [Manage file content](#manage-file-content)
        + [Authenticate and authorize](#authenticate-and-authorize)
        + [Get help](#get-help)
+ [SQL](#sql)
+ [Assets, threats, and vulnerabilities](#assets-threats-and-vulnerabilities)
    + [Asset security](#asset-security)
    + [Assets protection](#assets-protection)
    + [Vulnerabilities in systems](#vulnerabilities-in-systems)
    + [Threats to asset security](#threats-to-asset-security)
+ [Detection and response](#detection-and-response)
+ [Python automation](#python-automation)
+ [Cybersecurity job](#cybersecurity-job)


## Foundations

### Terminology

Organizations have to protect themselves from attacks in order to minimize risks and potential damage.

**Cybersecurity**: Practice of ensuring confidentiality, integrity, and availability of information by protecting networks, devices, people, and data from unauthorized access or criminal exploitation. 

**Asset**: Item perceived as having value to an organization (office space, computers, customers' PII, intellectual property...). Since it carries risk, it requires some security controls.

**Risk**: Anything that can impact confidentiality, integrity, or availability of an asset. It's the "likelihood of a threat occurring". A vulnerability and a threat must be present for there to be a risk. There're different risk levels, depending on possible threats and asset's value.
- **Low-risk asset**: Information that would not harm the organization's reputation or ongoing operations, and would not cause financial damage if compromised.
- **Medium-risk asset**: Information not available to the public that may cause some damage to the organization's finances, reputation, or ongoing operations.
- **High-risk asset**: Information protected by regulations/laws that may have severe negative impact on an organization's finances, ongoing operations, or reputation (PII, SPII, intellectual property...).

**Threat**: Any circumstance or event that can negatively impact assets.
- **Internal threat**: It can be a current/former employee, an external vendor, or a trusted partner who poses a security risk. Sometimes it's accidental (like an employee who accidentally clicks on a malicious email link). Sometimes, he intentionally engages in risky activities (like unauthorized data access).

**Threat actor** (malicious attacker): Person or group who presents a security risk for computers, applications, networks, or data.

**Vulneravility**: Weakness that can be exploited by a threat.

**Attack vectors**: Pathways attackers use to penetrate security defenses

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

- **Penetration testing** (pen testing): Simulated attack that helps identify vulnerabilities in systems, networks, websites, applications, and processes. It's a thorough risk assessment that can evaluate and identify external and internal threats as well as weaknesses.

**Digital forensics**: Process of collecting and analyzing data to determine what has happened after an attack. Example: to take an investigative look at data related to network activity.

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
- **Security assessment and testing**: Conducting security control testing, collecting and analysing data, and conducting security audits to monitor for risks, threats, and vulnerabilities.
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

Depending how firewalls operate, they can be:

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

<br>![defense in depth](https://raw.githubusercontent.com/AnselmoGPP/Learn_Computer_Science/master/resources/defense_in_depth.png)

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


## Operative system

### Operating systems

**Hardware**: All physical components of a computer.

**Application**: Program that performs a specific task.

**RAM** (Random Access Memory): Hardware component used for short-term memory.

**OS** (Operating System): Interface between computer hardware and the user. It make connections between applications and hardware to allow users to perform tasks. It also manages the resources of the computer. It's responsible for making the device run as efficiently as possible while making it easy to use. It can run multiple applications at once (unlike in 1950s) and access external devices (keyboard, mouse, printer...). Computers communicate in binary language, but the OS makes it easier for us to communicate with them. Many devices (laptops, smartphones, tablets...) have OSs (Linux, Windows, MacOS, iOS, Android...). 

**OS security** is critical for the security of the computer (it involves securing files, data access, user authentication... to protect against threats such as viruses, worms, and malware). A security analyst may be responsible for configuring and maintaining the system security by managing access, or configuring and managing firewalls, setting security policies, enabling virus protection, and performing auditing, accounting, and logging to detect unusual behavior.

The OS **handles resources and memory management** to ensure the limited capacity of the computer system is used where it's needed most. Different programs, tasks, and processes are constantly competing for the resources of the CPU (memory, storage, input/output bandwidth), and all of them have their own reasons. The OS ensures that each program is allocating and de-allocating resources. All this occurs occurs at the same time so that your system functions efficiently. Much of this is hidden from you as a user, but your task manager will list all tasks being processed and their memory and CPU usage. Understanding usage of resources can help you respond to an incident and troubleshoot applications in the system (example: if a computer runs slowly, it may be allocating resources to a malware).

Common operating systems are:

- **Windows** (1985): Used in personal and enterprise computers. It's a closed-source OS (i.e., the source code is not shared freely with the public).
- **macOS* (1984): Used in personal and enterprise computers. It has some open-source components (such as macOS’s kernel) and some closed-source components.
- **Linux** (1991): It's completely open-source (i.e., anyone can access Linux and its source code), which allows developers in the Linux community to collaborate. Linux is particularly important to the security industry. Some distributions are specifically designed for security.
- **ChromeOS** (2011): It's partially open source and is derived from **Chromium OS** (completely open source). It's frequently used in the education field.
- **Android** (2008): It's an open source mobile OS typically used in mobile devices (phones, tablets, watches...).
- **iOS** (2007): It's a partially open source mobile OS typically used in mobile devices (phones, tablets, watches...).

**Security issues** are inevitable with all OSs, so it's important to have the system and its components up to date.

- **Legacy operating systems**: OS that is outdated but still being used. Some organizations use it because the software they rely on is not compatible with newer OSs. This can be more common in industries that use a lot of equipment that requires embedded software (i.e., software placed inside components of the equipment). These OSs can be vulnerable to security issues and threats because they’re no longer supported or updated. Keeping OSs up to date makes them more secure.

- **Other vulnerabilities**: Even when OSs are kept up to date, they can still become vulnerable to attack.

  - [Microsoft Security Response Center (MSRC)](https://msrc.microsoft.com/update-guide/vulnerability): List of known vulnerabilities affecting Microsoft products and services.
  - [Apple Security Updates](https://support.apple.com/en-us/HT201222): List of security updates and information for Apple® OSs (macOS, iOS...) and other products.
  - [Common Vulnerabilities and Exposures (CVE) Report for Ubuntu](https://ubuntu.com/security/cves): List of known vulnerabilities affecting Ubuntu (Linux distribution).
  - [Google Cloud Security Bulletin](https://cloud.google.com/support/bulletins): List of known vulnerabilities affecting Google Cloud products and services.

**Turn on the computer**: The user starts interacting with the hardware by pressing the *turn on* button. This boots the computer, which means that a special microchip (called BIOS or UEFI) is activated. This microchip contains booting instructions responsible for loading the **bootloader** program, which is responsible for starting the OS. Vulnerabilities can occur in a booting process. BIOS is not scanned by antivirus software, so it's vulnerable to malware infection.

**Booting microchip**: Microchip containing loading instructions for the computer. It contains many loading instructions for the computer to follow (such as verify the health of the hardware). The last instruction activates the **bootloader** (program that boots the operating system). Two main types:

- **BIOS** (Basic Input/Output System): Prevalent in older systems (until ~2007).
- **UEFI** (Unified Extensible Firmware Interface): It replaces BIOS in modern systems (after ~2007). It provides enhanced security features.

**Communication process** (once OS is active): User > Application > OS > Hardware. The user wants to accomplish something, so he use an application to complete the task. The application sends a request to the OS. The OS interprets the application's request and directs it to the appropriate hardware component. This component sends information (output) back to the OS, which sends it to the application, which displays it to the user. 

Example: The CPU is used for a computations. The hard drive is used for saving a file.

Example (downloading file from an internet browser): The user decides to download an online file, so he clicks on a download button in the internet browser application. It communicates this action to the OS, which sends the request to download the file to the appropriate hardware for processing. The hardware begins downloading the file, and the OS sends this information to the internet browser application. The internet browser then informs the user when the file has been downloaded.

The computer performs important work that we don't experience directly (it's abstracted), including OS work. Some analogies:

- You make a car (computer) move by pressing a pedal, but you don't see the processes happening inside the car.
- In a restaurant (computer) you place an order (application request). You don't see what happens in the kitchen (OS), but it interprets your request and sends what you requested (output).

**Virtualization**: Process of using software to create virtual representations of various physical machines.

**Virtual machine** (VM): Virtual version of a physical computer (one type of virtualization). The software simulates physical hardware. Virtual systems don’t use dedicated physical hardware, but software-defined versions of the physical hardware (a single VM has a virtual CPU, virtual storage, and other virtual hardware). Virtual systems are just code. OSs can run on VMs. A single computer (**host**) can run multiple VMs (**guests**) by dividing his resources to be shared across all physical and virtual components (example: a computer with 16GB RAM can host 3 VMs with 4GB RAM). 

**Benefits of VMs**: 

- **Security**: They provide an isolated environment (sandbox) on the physical host machine. It is isolated from the host machine and other guest VMs, providing a security layer separated from the other systems (example: VMs infected with malware are isolated from other machines. Also, VMs are a secure environment for placing and examining malware). However, sometimes a malicious program can escape virtualization and access the host, so never completely trust virtualized systems.

- **Efficiency**: VMs can be an efficient and convenient way to perform security tasks. There's no need to have separated physical machines for certain tasks. You can open multiple VMs at once and switch easily between them. This allows you to streamline security tasks (such as testing and exploring various applicationS).

- **Management**: VMs can be managed with a software called a **hypervisor**. It helps users manage multiple VMs, connect the virtual and physical hardware, and allocate the host's shared resources to one or more VMs.

  - **KVM** (Kernel-based VM): Open-source hypervisor that is supported by most major Linux distributions. It's built into the Linux kernel, so it can be used to create VMs on any Linux OS without the need for additional software.

There are **other forms of virtualization**. Some of them don't use OSs. Example: Multiple virtual servers can be created from a single physical server. Also, virtual networks can also be created to more efficiently use the hardware of a physical network. 

**UI** (User Interface): Program that allows the user to control the functions of the OS. Two types of UI are:

- **GUI** (Graphical User Interface): UI that uses icons on the screen to manage different tasks on the computer. Most OSs can be used with a GUI. Its basic components are: start menu, task bar, desktop with icons and shortcuts. It allows only one request (task) at a time (example: moving all jpg files in A to B must be done one by one).
- **CLI** (Command Line Interface): Text-based UI that uses commands to interact with the computer. It's more flexible and powerful than a GUI. It allows for customization, which lets you make multiple requests (tasks) simultaneously (example: all jpg files in A can be moved B simultaneously), so it's more efficient. Commonly used by security analysts.

**History file**: The Linux CLI records a history file of all commands and actions performed in the CLI. Among other things, it lets you ensure all your commands were used correctly, or trace the actions of an attacker.

### Linux

#### Architecture

In the early 1990's, Linus Torvalds and Richard Stallman separately started working on an open source OS based on the UNIX OS. Torvalds introduced the Linux kernel and Stallman worked on the GNU OS. After a few years of work, the missing element for GNU was a kernel. Both, Torvalds' and Stallman’s innovations made what is commonly referred to as Linux.

**GNU Public Licence**: The software under this licence can be used, shared, and modified freely.

**Directory** (folder): It's a file that organizes where other files are stored. It can contain files or other directories.

**Linux** is an open-source OS. It's the most-used OS in security today. Linux and many programs it includes are licensed under the GNU Public License. It's widely used today in many organizations. There're different distributions (varieties), that have been developed (over 600), thanks to the large community contribution. Distributions try to fit the needs of their users. Security analysts usually use Linux (for examining logs, to verify access and authorization, ...), specially distributions designed for their tasks (distributions containing a digital forensic tool, distributions for pen testing, ...).

**Linux architecture** is composed of different components:

- **User**: Person interacting with a computer. They initiate and manage computer tasks. Linux is a multi-user system (multiple users can use the same resources at the same time).

- **Application** (program): Program that performs a specific task. Some applications typically come pre-installed (calculators, calendars...) while others might have to be installed (some web browsers, some email clients...). In Linux, a package manager is often used to install applications. 

- **Shell**: It's the command-line interpreter (CLI). Every input is text based. It allows users to give commands to the kernel and receive responses from it. It translates the commands you enter so that the computer can perform the tasks you want.

- **FHS** (Filesystem Hierarchy Standard): It's a component that organizes data. It specifies the location where data is stored in the OS. It defines how directories, directory contents, and other storage is organized so the OS knows where to find specific data.

- **Kernel**: It's a component that manages processes and memory. It communicates with the applications to route commands to the hardware. It controls all major functions of the hardware, and helps allocate resources efficiently, making the system work faster.

- **Hardware**: It's the collection of physical components of a computer (hard drive, CPU...). It can be internal or peripheral.

  - **Peripheral devices**: Hardware components attached and controlled by the computer system (monitor, printer, keyboard, mouse...). They can be can be added or removed freely. They are not core components needed to run the computer system.

  - **Internal hardware**: Hardware components required to run the computer. It includes the following: 

    - **Main circuit board** (motherboard): It has attached different internal hardware components.

    - **CPU** (Central Processing Unit): Main processor. Used to perform general computing tasks. It executes the instructions provided by programs, which enables these programs to run. 

    - **RAM** (Random Access Memory): Used for short-term memory. Data is stored temporarily here as you perform tasks on your computer. Information in RAM cannot be accessed once the computer has been turned off. The CPU takes the data from RAM to run programs. 

    - **Hard drive**: Used for long-term memory. Programs and files store data here so it can be accessed later (even after the computer has been turned off and on again). A computer can have multiple hard drives.

#### Distributions

**Linux distributions** (distros, flavors): Linux is very customizable and there are different versions available. Since the kernel is open source, anyone can take it and modify it to build a new distribution. Each one contains its own components (tools and apps) and serves its own purpose. Distros include the kernel, utilities, a package management system, and an installer. All distros are derived from another distro, but a few of them are considered parent distros (Red Hat®, parent of CentOS) (Slackware®, parent of SUSE®) (Debian, parent of Ubuntu and KALI LINUX™). Some distributions used in security are:

- **KALI LINUX™**: Debian derived, open-source distro. Trademark of Offensive Security. It's pre-installed with many useful tools for pen testing and digital forensics. It should be used on a virtual machine to prevent damage in case its tools are used improperly, and to be able to revert to a previous state. Some pre-installed tools are: 

  - For pen testing:
    - **Metasploit**: Used to look for and exploit vulnerabilities.
    - **Burp Suite**: It helps to test for weaknesses in web applications.
    - **John the Ripper**: Used to guess passwords. 

  - For digital forensics:
    - **tcpdump**: Command-line packet analyzer. Used to capture network traffic.
    - ** Wireshark**: GUI used to analyze live and captured network traffic.
    - **Autopsy**: Used to analyze hard drives and smartphones.

- **Parrot**: Debian derived, open-source distro. It's user-friendly and has both CLI and GUI. It comes with pre-installed tools related to pen testing and digital forensics.

 - **Ubuntu**: Debian derived, open-source distro. It's popular and user-friendly, and has both CLI and GUI. It includes common applications by default, and many more can be downloaded from a package manager. Also used in cloud computing.

- **Red Hat® Enterprise Linux®**: Subscription-based distro for enterprise use. Not free. It offers a dedicated support team for customers to call about issues.

- **CentOS**: Red Hat® derived, open-source distro. It provides a similar plaform than Red Hat.

**Package**: Piece of software that can be combined with other packages to form an application. Some packages may form an application on their own. It contains the files necessary for an application to be installed. These files include **dependencies** (supplemental files used to run an application).

**Package manager**: Tool that helps users install, manage, and remove packages or applications. It can help resolve issues with dependencies and perform other managemnt tasks. Linux uses multiples package managers. The most recent version should be used because it has the most up-to-date bug fixes and security patches, which helps keep the system more secure. Certain package managers work with certain distributions and use different file extensions. Examples:

- DPKG: For Debian derived distros. It uses `.deb` file extension.
- RPM (Red Hat Package Manager): For Red Hat derived distros. It uses `.rpm` file extension.

**Package management tools**: Tools that allow to easily work with packages through the shell. They're sometimes used instead of package managers because they perform basic tasks more easily (like installing a new package). Most important ones are:

- **APT** (Advanced Package Tool): Used in Debian-derived distros. It's run from the CLI to manage, search, and install packages.
- **YUM** (Yellowdog Updater Modified): Used in Red Hat-derived distros. It's run from the CLI to manage, search, and install packages. It works with `.rpm` files.

How to install applications with APT:

```
apt                           # check if apt is installed
sudo apt install suricata     # install suricata app
sudo apt remove suricata      # uninstall suricata app
apt list --installed          # list installed apps
```

#### Shells

**Command**: Instruction telling the computer to do something (perform math, run tests, execute application, find file, output text, ...). A command may need to include an **argument** (specific information needed by a command). All commands and arguments are case sensitive.

**Shell**: Command-line interpreter. It provides a CLI for you to interact with the OS by entering commands. It also allows to combine commands and connect applications to perform complex and automated tasks. The shell communicates with the kernel to execute these commands. There're different types of shells, all of them using common Linux commands but differing in other features (example: bash and ksh use `$` to indicate user location, while zsh use `%`). Some shell are:

- **bash** (Bourne-Again Shell): Default shell in most Linux distributions. User-friendly. Most popular shell in cybersecurity. The `$` symbol the prompt to enter a new command.
- **csh** (C Shell)
- **ksh** (Korn Shell)
- **tcsh** (Enhanced C shell)
- **zsh** (Z Shell)

The commands in the shell can take input, give output, or give error messages.

- **Standard input**: Information the OS receives from the command line.
- **Standard output**: Information the OS returns through the shell.
- **Standard error**: Error messages the OS returns through the shell.

**String data**: Data consisting of an ordered sequence of characters.

**Navigation tips and keyboard shortcuts**:

- `CTRL + C`: Terminate currently running command
- `CTRL + V`: Paste text
- `clear` (`CTRL + L`): Clear terminal screen
- `CTRL + A`: Set cursor at the beginning of a command
- `CTRL + E`: Set cursor at the end of a command
- `Left/Right arrow key`: Move left/right within a command
- `Up/Down arrow key`: Get last/next command in the command history
- `Tab key`: Get available suggestions for completing your text 
- `echo`: Output a specified string of text (`echo "hello world"`)
- `expr`: Perfom basic calculations (`echo 24 * 3`)

#### Filesystem

**Executable**: File containing a series of commands a computer needs to follow to run programs and perform other functions.

Everything we do in Linux is considered a file somewhere in the system directory. The **FHS** is a hierarchical system where everything grows and branches out from the **root directory** (`/`), the highest-level directory in Linux. Subdirectories branch out further and further away from the root directory. A **file path** describes a file's location (`/home/username/logs`). Some standard FHS directories are:

- `/home`: Contains all the home directories, one per user in the system.
- `/bin`: Contains binary files and other executables.
- `/etc`: Stores system's configuration files.
- `/tmp`: Stores temporary files. It's commonly used by attackers because anyone in the system can modify data in these files.
- `/mnt`: Stores media (USB drives, hard drives, ...).

**Path types**:

- __Absolute path__: Full file path (`/home/username/logs`).
- __Relative_path__: Abbreviated file path. It one of these:
  - `~`: User's home directory (`/home/username/logs` == `~/logs`). Only applicable to directories below user's home.
  - `.`: Current directory
  - `..`: Parent of current directory

**Basic commands**:

- `man hier`: Learn more about FHS and its standard directories.
- `whoami`: Get username of the current user.

- Some navigation commands:

  - `pwd`: Print working directory
  - `cd`: Navigate between directories
  - `ls`: Display files and directories in the current working directory
    - `ls -l`: Display their permissions too
    - `ls -a`: Display hidden files too (they begin with a period `.`)
    - `ls -la`: Display permissions and hidden files too

- Some reading commands:

  - `cat`: Display file content
  - `head`: Display the beginning of a file (default: 10 lines). Show a different number of lines with `-n` (`head -n 5 file.txt`).
  - `tail`: Display the end of a file (default: 10 lines). Useful for reading the most recent information in a log file.
  - `less`: Display file content one page at a time. Additional commands: 
    - `space`: Move forward
    - `b`: Move back
    - `down arrow`: Move forward one line
    - `Up arrow`: Move back one line
    - `q`: Quit and return to terminal

#### Manage file content

**Options**: They modify the behavior of a command. They commonly begin with a hyphen (`-`) and can be a single letter or full word. 

**Asterisk** (`*`): Wildcard to represent zero or more unknown characters.

**Filter content**: Select data matching a certain condition.

- `grep`: Search a specified file and return all lines in the file containing a specified string (`grep abc file.txt`).
- `find`: Search for directories and files that meet specified criteria (contains a given string, has certain file size, were modified in a given time frame...).
  - `find <directory> <options>`: Start searching from directory `<directory>` following the criteria `<options>`.
  - `find ~/logs -name "*abc*"`: Find all files containing word `abc`, surrounded by 0 or more characters, in the file name (`-name` is case-sensitive, `-iname` is not).
  - `find ~/logs -mtime -3`: Find all files modified within the past 3 days (`-mtime +1` = more than 1 day ago) (`-mtime -1` = less than 1 day ago) (`-mtime` for days, `-mmin` for minutes).

**Pipe** (`|`, `>`, `>>`): Send the standard output of one command as standard input to another command for further processing. 
  - `ls /home/analyst/reports | grep users`: Look for string "users" in the file names of all files in directory `/home/analyst/reports`.
  - When used with `echo`, output can be sent to a file rather than the screen with `>` (overwrite file) or `>>` (append) (`echo "hello" >> file.txt`).

**Files operations** (directories are also files):

- `mkdir`: Create new directory.
- `rmdir`: Delete empty directory.
- `touch`: Create new file (`touch data.txt`).
- `rm`: Delete file.
- `mv`: Move file to a new location (`mv filename /desti/nation`) (rename: `mv filename newFilename`).
- `cp`: Copy file into a new location (`cp filename /desti/nation`)

**Command-line editors**: `Vim`, `nano`, `Emacs`, etc.
  - `nano`: Open file: `nano file.txt`. Save changes: `Ctrl + O`. Exit: `Ctrl + X`.

#### Authenticate and authorize

**Authentication**: Proces of verifying who someone is. Process of a user proving that he is who he says he is in a system.

**Authorization**: Concept of granting somebody access to specific resources in a system. 

**Permission**: Type of access granted for a file or directory. 

**Principle of least privilege**: It grants only the minimal access and authorization required to complete a task or function. Users should not have privileges that are beyond what is necessary; otherwise, security risks can arise.

Types of permissions in Linux:

- **Read** (`r`): File (it can be read) or directory (files inside can be read).
- **Write** (`w`): File (it can be modified) or directory (new files can be created inside).
- **Execute** (`x`): Executable (it can be executed) or directory (in can be entered).

Permissions are granted to 3 types of owners (and should follow the principle of least privilege):

- **User** (`u`): When you create a file, you become the owner of it.
- **Group** (`g`): Group that the owner is part of (every user is part of a certain group/s).
- **Other** (`o`): Anyone else with access to the system.

File permissions are represented with a 10-character string: `drwxrwxrwx` (<file type (`d`, `-`)> <user> <group> <other>).

`chmod`: Changes permissions on files. Two modes (numeric and symbolic). Symbolic mode works like this:
  - `chmod g+wx,o-r file.txt`: For `file.txt`, Group gets `w` and `x` permissions, and Other loses `r` permission.
  - `chmod u=w,g=x, file.txt`: For `file.txt`, User becomes `-w-`, and Other becomes`--x`.

**World-writable file**: File that can be altered by anyone. It can pose a security risk.

New users can be new to an organization or new to a group. Users that move to another group need to be deleter from the original group. Users that leave the organization need to be deleted.

**Root user** (superuser): User with elevated privileges to modify the system. It manages authorization and authentication. Regular users have limitations where the root doesn't. He can create, modify, or delete any file and run any program. Users can be added as root users temporarily to perform specific tasks. Only root users, or users with root privileges, can add new users. 

To become root user you can log in as root user, but running commands as root user is considered bad practice in Linux (use `sudo` instead) due to:

- __Security risks__: Malicious actors would try to breach the root account. We should have root user logins disabled.
- __Irreversible mistakes__: It's easy for root users to make irreversible mistakes (such as permanently deleting a directory).
- __Accountability__: If a users is running as root, there's no way to track who exactly ran a command.

`sudo` (super-user-do): Temporarily grants elevated permissions to specific users. Running it will ask you the password for the user you're currently logged in as. Not all users have sudo access. Users must be granted sudo access through a configuration file (**sudoers file**). Users with the elevated permissions to use sudo might be more at risk in the event of an attack. The following commands are only available for super-users or users with sudo privileges.

- `useradd`: Add a user to the system.
  
  - `sudo useradd <username>`: Create user.
  - `sudo useradd -g <group> <username>`: Create user and set its default group (primary group).
  - `sudo useradd -G <group1> <group2> <group3> <username>`: Create user and add it to additional groups (secondary/supplemental groups). 

- `userdel`: Delete a user from the system.

  - `sudo userdel <username>`: Delete user.
  - `sudo userdel -r <username>`: Delete user and all files in his home directory.

- `groupdel`: Delete a group from the system (`sudo groupdel <group>`).

- `usermod`: Modify existing user accounts.

  - `sudo usermod -g <newgroup> <username>`: Change user's primary group.
  - `sudo usermod -a -G <newgroup> <username>: Add user to a new secondary group (not including `-a` will replace all secondary groups).
  - `sudo usermod -d <new/directory> <username>: Change user's home directory.
  - `sudo usermod -l <newname> <username>: Change user's login name.
  - `sudo usermod -L <username>: Lock the account so the user cannot log in.

- `chown`: Change ownership of a file or directory.

  - `sudo chown <username> file.txt`: Change user owner of *file.txt*.
  - `sudo chown :<group> file.txt`: Change group owner of *file.txt*.

#### Get help

Command-line resources:

- `man` (manual): Displays information of a command and how it works (`man <command>`). Use `Q` to exit manual.
- `whatis`: Displays a description of a command on a single line (`whatis <command>`).
- `apropos`: Searches the man page descriptions for a specified string/s (`apropos -a change password`)

Online resources:

- __Community__: Linux has a large and helpful online community. A simple online search can likely answer your questions.
- [__Unix & Linux Stack Exchange__](https://unix.stackexchange.com/): Answers are ranked with points to show their quality.

## SQL

**Spreadsheets**: Organized collection of information or data. It's designed for a single user or a small team. It doesn't store too much data.

**Database**: Organized collection of information or data. It can be accessed by multiple people simultaneously. It can store massive amounts of data. It can perform complex tasks while accessing data. It contains rows (records) and columns. There're different ways to structure a database (like relational databases).

**Relational database**: Structured database containing multiple tables that are related to each other.

  - **Field** (column): Type of data (example: employee_id).
  - **Table**: It contains fields of information (example: The Employees table contains fields like employee_id, device_id, username, department, office).
  - **Rows** (records): Single group of related data. They're filled with data related to the columns in the table (example: all data of an specific employee).

We can connect 2 tables if they share a common column (**key**). Two types of keys:

- **Primary key**: Column where every row has a unique entry. It cannot be duplicated, null, or empty value. It let us uniquely identify every row in a table.
- **Foreign key**: Column in a table that is a primary key in another table. It can be duplicated or empty value.

A table can have multiple foreign keys, but only one primary key.

**SQL** (Structured Query Language): Programming language used to create, interacts with, and request information from a database. Also useful for data analytics. It can search fast through millions of data points and extract  relevant rows of data using a simple query. Nearly all relational databases rely on some version of SQL to query data. Its different versions only have slight differences in their structure (like where to put quotation marks).

**Operator**: Symbol or keyword that represents an operation (like `=`). In the case of comparison operators, they can be inclusive (includes the value of comparison) or exclusive (doesn't include it).

**Log**: Record of events that occur within an organization's systems. Example: it may contain details on company's machines, or on visitors to your web app and their actions.

Security analysts often have to access databases and logs containing useful information (login attempts, updates, machine's owners...) to support their decisions, analyse when things may go wrong, and do data analytics (identify machines without the latest patch, determine best time to update a machine, ...). 

**Accessing SQL**: There are many SQL interfaces and versions. One way to access SQL is through the Linux command line, just by typing the SQL version to use (example: `sqlite3`). After this, any commands typed in the command line will be directed to SQL instead of Linux commands. Both Linux and SQL allow to filter through data, but they have differences:

- **Linux**: 

  - It filters data in the context of files and directories on a computer system (search files, manipulate file permissions, managing processes…).
  - The commands and syntax varies depending on the tool and purpose (`find`, `sed`, `cut`, `e grep`, …). 
  - Its structure is less tidy than SQL (example: an employee login attempts taken from a log would be printed as a line of text without organization). 
  - It doesn't allow data to be connected to other information.
  - Useful for formats not compatible with SQL (like logs as text files).

- **SQL**: 

  - Used to filter data within a database management system. It’s used for querying and manipulating data stored in tables and retrieving specific information based on defined criteria. 
  - It uses the standardized SQL language which contains keywords and clauses for filtering data across SQL databases (`WHERE`, `SELECT`, `JOIN`, …). 
  - It offers more structure (more tidy and readable) than Linux (example: an employee login attempts taken from a log would be printed as different records separated into columns). 
  - It allows to join multiple tables together when returning data.
  - Useful for data stored in a database format.

Common **data types** in DBs:

- **String**: Ordered sequence of characters (numbers, letters, or symbols).
- **Numeric**: Numbers. Mathematical operations can be used on them. Booleans are usually stored as 1 or 0.
- **Date and time**: Date and/or time. Mathematical operations can be used on them

**Syntax**: Rules that determine what is correctly structured in a computing language. In SQL, keywords are not case-sensitive, and semicolons (`;`) are placed at the end of the statement.

- `;`: Semicolon must be placed where the query ends.
- `SELECT`: Operator that indicates which columns to return. It always comes with `FROM`. For large databases it might be slow to run, and the output difficult to understand.
- `FROM`: Indicates which table to query.
- `ORDER BY`: Sequence in ascending (default) or descending (`DESC`) order the records returned by a query based on a specified column/s.
- `WHERE`: Indicates the condition for a filter. The condition is listed using operators.
- `LIKE`: Similar to `=`, but used with `WHERE` to search for a pattern in a column.
- `BETWEEN`: It filters for numbers or dates within a range (inclusive). Used with `AND`.
- __Comparison operators__: Used for numeric, date, and time data types: `=`, `>`, `<`, `>=`, `<=`, `<>`/`!=` (not equal to).
- __Logical operators__:
  - `AND`: Two conditions must be met simultaneously.
  - `OR`: Either condition can be met.
  - `NOT`: The condition must not be met. It negates a condition.
- __Wildcard__: Special character that can be substituted with any other character. It needs to use `LIKE` operator instead of `=` sign.
  - `%`: Wildcard for an unspecified set of characters. Example: `a%`, `%a`, `%a%`.
  - `_`: Wildcard for an unspecified single character. Example: `a_`, `_a`, `a__`, `_a_`.
- `NULL`: Represents a missing value.

**Query**: Request for data from a database table or a combination of tables.

- `SELECT * FROM employees;`: Return all columns from the "employees" table.
- `SELECT employee_id, device_id FROM employees;`: Return 2 columns from the "employees" table.
- `SELECT customeerid, city, country FROM customers ORDER BY city DESC;`: Sort columns in descending order based on "city" column.
- `SELECT customeerid, city, country FROM customers ORDER BY country, city;`: Sort columns in descending order based on "country" and, for same country, on "city".

**Filtering:** Selecting data that match a certain condition. Choosing the data we want. When filtering for strings, dates, and times, we use quotation marks (''). Example: Filter all log-in attempts from a specific country.

- `SELECT * FROM log_in_attempts WHERE country = 'USA';`: Return all records from table X where field country is equal to USA.
- `SELECT * FROM log_in_attempts WHERE country LIKE 'US%';`: "" field country begins with US.
- `SELECT * FROM log_in_attempts WHERE country LIKE 'US_';`: "" field country is US + another character.
- `SELECT * FROM log_in_attempts WHERE time > '18:00';`: "" field time is greater than 18:00.
- `SELECT * FROM machines WHERE OS_patch_date BETWEEN '2021-03-01' AND '2021-09-01'; "" field OS_patch_date is between 2021-03-01 and 2021-09-01.
- `SELECT * FROM machines WHERE op_system = 'linux' AND browser = 'brave';`: "" field op_system is linux, and field browser is brave.
- `SELECT * FROM machines WHERE op_system = 'linux' OR NOT browser = 'brave';`: "" field op_system is linux, or field is not brave. Alternative: `... AND browser != 'brave';`.
.- `SELECT * FROM machines WHERE op_system = 'linux' AND office LIKE 'East%';`: "" field op_system is Linux, and office is "East...".

**Joins**: Combine 2 tables together. Useful when we need information from 2 tables. It returns all specified columns from all joined tables. If 2 tables are joined with `SELECT *`, all columns in both of the tables are returned. If a column exists in both tables, it's returned twice when using `SELECT *` (this can be avoided by selecting which one to return with `.`, like `employees.device`).

- `SELECT username, op_system, employees.device_id FROM employees INNER JOIN machines ON employees.device_id = machines.device_id;`: Create a table (username, office, device_id) from joining (inner join) employees and machines tables, taking employee_id as common column.
- `SELECT * FROM employees LEFT JOIN machines ON employees.device_id = machines.device_id;`
- `SELECT * FROM employees RIGHT JOIN machines ON employees.device_id = machines.device_id;`
- `SELECT * FROM employees FULL OUTER JOIN machines ON employees.device_id = machines.device_id;`


**Join types**:
- `INNER JOIN`: Returns rows matching on a specified shared column (column existing in both tables). It returns all rows that match in both tables the common column, and all columns in both tables. The order of tables doesn't change the result of the query.
- **Outer join**: It doesn't necessarily require a shared column to return a row.
  - `LEFT JOIN`: Returns all records of first table (left), but only returns rows of second table (right) that match on a specified column.
  - `RIGHT JOIN`: Returns all records of second table (right), but only returns rows of first table (left) that match on a specified column.
  - `FULL OUTER JOIN`: Returns all records from all tables. It's like completely merging two tables. The order of tables doesn't change the result of the query.

Note: You can use `LEFT JOIN` and ``RIGHT JOIN` and return the exact same result if you use the tables in reverse order.

<br>![inner join image](https://raw.githubusercontent.com/AnselmoGPP/Learn_Computer_Science/master/resources/join_inner.jpg)
<br>![left join image](https://raw.githubusercontent.com/AnselmoGPP/Learn_Computer_Science/master/resources/join_left.jpg)
<br>![right join image](https://raw.githubusercontent.com/AnselmoGPP/Learn_Computer_Science/master/resources/join_right.jpg)
<br>![full outer join image](https://raw.githubusercontent.com/AnselmoGPP/Learn_Computer_Science/master/resources/join_full_outer.jpg)

**Aggregate functions**: Functions that perform a calculation over multiple data points and return the result of the calculation. The actual data is not returned. Syntax: Place the aggregate function keyword after SELECT, and then in parentheses, indicate the column you want to perform the calculation on. Some function examples are: 

- `COUNT`: Returns a single number that represents the number of rows, excluding NULL values, returned from your query.
- `AVG`: Returns a single number representing the average of the numerical data in a column.
- `SUM`: Returns a single number that represents the sum of the numerical data in a column.

- `SELECT COUNT(firstname) FROM customers`: Get number of customers.
- `SELECT COUNT(firstname) WHERE country = 'USA'`: Get number of customers from USA.


## Assets, threats, and vulnerabilities

### Asset security

**Risk**: Anything that can impact the __confidentiality__, __integrity__, or __availability__ of an asset (the 3 components of the CIA triad).

**Security risk planning**: First step towards protecting the CIA triad. It's based on the analysis of 3 elements:

- **Assets**: Item perceived as having value to an organization (building, equipment, data, people, reputation, ...).
- **Threats**: Any circumstance or event that can negatively impact assets (thieves, accidents...). Two main types: __intentional__ (malicious hacker gains access privileges) and __unintentional__ (employee opens door to unknown person).
- **Vulnerabilities**: Weakness that can be exploited by a threat. It's like a flaw in an asset. Two main types: __technical__ (misconfigured software) and __human__ (employee loses keys in a parking lot).

The security plans depend upon how an organization defines risk. Since organizations have particular assets, they tend to differ in how they interpret and approach risk. Two ways risk can be interpreted:

- Risk = Potential effects that negative events can have on a business
- **Risk = Likelihood x Impact**

In general, we calculate risk for:

- Preventing costly and disruptive events
- Identifying improvements for systems and processes
- Determining tolerable risks
- Prioritizing critical assets

**Risk factors**: The main ones are __threats__ (a nail puncturing your tire) and __vulnerabilities__ (tires are vulnerable to sharp objects). We try to reduce these risks (by driving on clean roads).

**Asset management**: Process of tracking assets and the risks that affect them (you can only protect what you know you have). All security plans revolve around asset management.

**Asset inventory**: Catalogue of assets that need to be protected. Used for keeping track of assets.

**Asset classification**: Practice of labelling assets based on sensitivity and importance to an organization (this requires answering: what you have? where is it? who owns it? how important is it?) It determines whether an asset can be disclosed, altered, or destroyed. Different levels:

- __Public__: Can be shared with anyone
- __Internal-only__: Can only be shared with anyone in the organization and business partners
- __Confidential__: Can only be accessed by those working on an specific project.
- __Restricted__: Highly sensitive. Need protection. Considered need-to-know. Examples: intellectual property, health/payment information, etc.

**Data**: Information that is translated, processed, or stored by a computer. States of data:

- **In use**: Data being accessed by one or more users.
- **In transit**: Data traveling from one point to another.
- **At rest**: Data not currently being accessed.

**Information security** (InfoSec): Practice of keeping data in all states away from unauthorized users. Information is one the most valuable assets a company can have. Weak InfoSec can lead to identity theft, financial loss, reputation damage, etc. Protecting data depends on where it is and what it's doing.

**Cloud computing**: On-demand, massively scalable service, hosted on shared infrastructure, accessible via the internet.

**Cloud-based services**: On-demand or web-based business solutions. They allow businesses to scale and adapt quickly while lowering costs (by allowing companies connect with customers, employees, and partners via internet), but introduce new cybersecurity challenges. Provided by a cloud service provider (Google Cloud Platform, Microsoft Azure, etc.). Three types of cloud-based services:

- **SaaS** (Software as a service): Front-end applications that users access via a web browser. The service providers host, manage, and maintain the back-end systems of these applications Examples: Gmail, Zoom, Slack, etc.
- **PaaS** (Platform as a service): Back-end application development tools accessible online. Developers use them to write code and build, manage, and deploy apps. The service provider hosts and maintains the back-end hardware and software that the apps use to operate. Examples: Google App Engine, Heroku, VMware Cloud Foundry, etc.
- **IaaS** (Infrastructure as a service): It gives remote access to a range of back-end systems that are hosted by the service provider. Resources are commonly licensed as needed, making it a cost-effective alternative to buying and maintaining on premises. Examples: data processing servers, storage, networking resources, etc.

**Cloud security**: Protection of data, applications, and infrastructure in the cloud. Cloud services complicate keeping data private and safe. Traditionally, organizations had their entire IT infrastructure on premises, so protecting it was up to the internal security team. But, when some operational environment is in the cloud, these responsibilities are not so clearly defined. Example: a PaaS client is responsible for securing the apps he builds, but the servers he access should be protected by the cloud service provider. More information: [UK National Cyber Security Centre](https://www.ncsc.gov.uk/collection/cloud/understanding-cloud-services/cloud-security-shared-responsibility-model), [Cloud Security Alliance](https://cloudsecurityalliance.org/), [CompTIA Cloud+](https://www.comptia.org/blog/your-next-move-cloud-security-specialist). 

**Shared responsibility**: Clients are commonly responsible for securing anything directly within their control (identity and access management, resource configuration, data handling) while some other responsibilities are delegated to the service provider (depending on the service it provides). 

__Challenges__: Much of the provider's success depends on preventing breaches and protecting sensitive information, but several challenges exist (customer not configuring well his security environment, cloud-native breaches due to misconfigured services, monitoring access might be difficult, not meeting regulatory standards, ...).

**Risk categories**: 

- **Damage**: 
- **Disclosure**: 
- **Loss of information**: 

**Security plans** have 3 elements:

- **Policies**: Set of rules that reduces risk and protects information. Focused on the strategic side (identify scope, objectives, and limitations of a security plan).
- **Standards**: References that inform how to set policies. Tactical function (NIST SP 800-63B Password Management Standard, ...).
- **Procedures**: Step-by-step instructions to perform a specific security task (how to set passwords, how to reset them, ...). They create accountability, consistency, and efficiency.

**Compliance**: Process of adhering to internal standards and external regulations. There're many reasons for compliance (trust, reputation, safety, integrity of data, fines, penalties, lawsuits...).

**Regulations**: Rules set by a government or other authority to control the way something is done. Like policies, but on larger scale.

One main role of **NIST** (National Institute of Standards and Technology) is to openly provide companies with a set of frameworks and security standards that reflect key security related regulations. 

- **CSF** (NIST Cybersecurity Framework) (2014): Voluntary framework that consists of standards, guidelines, and best practices to manage cybersecurity risk. It's flexible (adaptable) and applies to any industry. Developed to help businesses secure information. It can help identify and assess risk. It evolves with time, and is influenced by the standards and best practices of some of the largest companies in the world. It helps with regulatory compliance. When using it, always consider current risk, threat, and vulnerability trends. CSF has 3 components:

  - __Core__: Simplified version of the functions (duties, desired outcomes) of a security plan. It identifies 5 core functions (security checklist): Identify, Protect, Detect, Respond, Recover.
  - __Tiers__: Ways of measuring performance across each core function. It identifies 4 levels: 1 (passive, limited), 2 (), 3 (), 4 (exemplary performance).
  - __Profiles__: They provide insights into the current security plan state. They're pre-made NIST CSF templates that address specific risks and help organizations develop a baseline for their cybersecurity plans.

The U.S. **CISA** (Cybersecurity and Infrastructure Security Agency) provides guidance for implementing the CSF. Summary of his recommendations:

- __Create a current profile__ of the security operations and outline the specific needs of your business.
- __Perform a risk assessment__ to identify which of your current operations are meeting business and regulatory standards.
- __Analyse and prioritize existing gaps__ in security operations that place the businesses assets at risk.
- __Implement a plan of action__ to achieve your organization's goals and objectives.

### Assets protection

**Security controls**: Safeguards designed to reduce specific security risks. They include a wide range of tools for protecting assets before, during, and after an event. Types:

- __Technical__: Technologies for protecting assets (encryption, authentication systems...).
- __Operational__: Maintain day-to-day security environment (awareness training, incident response...).
- __Managerial__: Make technical and operational controls reduce risks (policies, standards, procedures...).

**Information privacy**: Protection of unauthorized access and distribution of data. Security controls are the technologies used to regulate information privacy.

**Principle of least privilege** (PoLP): Concept in which a user is only granted the minimum level of access and authorization required to complete a task or function. It's a fundamental security control that supports confidentiality, integrity, and availability (CIA) of information. Limiting access reduces risks (theft, accidental modification, monitoring, administration...). To implement it, you have to know who the user is (person, device, software...) and how much access he needs to a specific resource. Participants: data owners and data custodians. Accounts: guest, user, service, privilege.

**Accounts**: There're different account types (guest, user, service, privilege). It's good practice to determine a baseline access level for each account type before implementing least privilege. The appropriate access level can change from time to time (example: a customer support representative should only have access to your information while helping you, and then it should become inaccessible. Least privilege can only reduce risk if user accounts are routinely and consistently monitored. Also, insecure passwords can compromise your system.

- __Guest account__: External user
- __User account__: Staff
- __Service account: Application or software
- __Privilege account__: Elevated permission or administrative access

**Auditing accounts**: Auditing accounts is key for keeping your company's systems secure. Three common account auditing approaches:

- __Usage audits__: Review which resources each account is accessing and what is the user doing with the resource. Helpful for determining whether users follow the organization's security policies, and for identifying permissions that can be revoked because they're no longer used.
- __Privilege audits__: Asses whether a user's role have access only to the resources he needs. Users tend to accumulate more access privileges than they need over time (privilege creep).
- __Account change audits__: Ensure that all account changes are made by authorized users. Account directory services usually save changes to an account (in record and logs) and can be used to identify suspicious activity (like multiple attempts to change an account password). Most directory services can be configured to alert system administrator of activity.

**Separation of duties**: Security concept that divides tasks and responsibilities among different users to prevent giving a single user a complete control over critical business functions. Closely related to PoLP. Users should not be given levels of authorization that would allow them to misuse a system.

**Data lifecycle**: Model for protecting information. It influences how to set policies that align with business objectives, and the technologies used to make information accessible. It has 5 stages (collect, store, use, archive, destroy) that describe how data flows through an organization from its creation until it's no longer useful. Protecting information at each stage describes the need to keep it accessible and recoverable should something go wrong.

**Data governance**: Set of processes that define how an organization manages information. It often includes policies for keeping data private, accurate, available, and secure throughout its lifecycle. To be efficient, it should be a collaborative activity that relies on people. Data governance policies commonly categorize individuals 3 types and often assign them accountability:

  - __Data owner__: Person/s that decide who can access, edit, use, or destroy their information.
  - __Data custodian__: Anyone/anything responsible for the safe handling, transport, and storage of information. It's main responsibility is to maintain security and privacy rules for the organization.
  - __Data steward__: Person/group that maintains and implements data governance policies set by an organization.

**Data governance policy**: Policy (included in most security plans) outlining how information will be managed across an organization. It defines procedures that should be followed to participate in keeping data safe. They place limits on who or what can access data. Data custodians are responsible for ensuring that data isn't damaged, stolen, or misused.
 
Security professional must always respect a person's data privacy decision. All types of personal information must be protected from unauthorized use and disclosure. Securing data can be challenging, in large part because data owners generate more data than they can manage. Thus, data custodians and stewards sometimes lack specific instructions on how to manage some types of data. Governments and other regulatory agencies have bridged this gap by creating rules that specify they types of information that organizations must protect by default:

- **PII** (Personally Identifiable Information): Information used to infer an individual's identity, or contact or locate someone.
- **PHI** (Protected Health Information): Information related to past, present, or future physical or mental health or condition of an individual. In U.S. it's regulated by the HIPAA (Health Insurance Portability and Accountability Act). In EU, it's regulated by the GDPR (General Data Protection Regulation).
- **SPII** (Sensitive PII): Type of PII that should only be accessed on a need-to-know basis (bank account number, login credentials...). It falls under stricter handling guidelines.

Regarding information, **privacy** is about providing people with control over their personal information and how it's shared, while **security** is about protecting people’s choices and keeping their information safe from potential threats. Both are essential for maintaining customer trust and brand reputation.

- **Information privacy**: Protection of unauthorized access and distribution of data.

- **Information security** (InfoSec): Practice of keeping data in all states away from unauthorized users.

Example: A retail company collects specific kinds of personal information from its customers for marketing purposes. How this information will be used should be disclosed to customers before it's collected, and customers should have the option to opt-out if they decide not to share their data. After obtaining consent to collect personal information, the company might implement specific security controls for protecting that private data from unauthorized access, use, or disclosure, and for respecting the privacy of stakeholders and anyone who chose to opt-out.

Some tips: Encrypt data when it's being stored at rest. Encrypt data when it's being transmitted over the Internet using TLS or SSL. Think clearly about who has access to that data (almost nobody if it's sensitive). If somebody needs access to that data, record the access, who accessed it, and why. You should have a program to look at the audit records for that data. 

Companies store people's data and use it for business purposes. The more data they collect, the more vulnerable it is to be abused, misused, stolen, and to breaches and threats. They have to be transparent about how they collect, store, and use this information. They have to implement security measures for protecting people's data privacy. Regulations protect users from having their information collected, used, or shared without their consent (**privacy regulations**), and describe measures that need to be in place to keep private information away from threats. Most influential industry regulations are:

- **GDPR** (General Data Protection Regulation): Set of rules and regulations developed by EU that puts data owners in total control of their personal information (name, address, phone number, financial information, medical information...). It applies to any business that handles the data of EU citizens or residents, regardless of where it operates.

- **PCI DSS** (Payment Card Industry Data Security Standard): Set of security standards formed by major organizations in the financial industry. It aims to secure credit and debit card transactions against data theft and fraud.

- **HIPAA** (Health Insurance Portability and Accountability Act): U.S. law that requires the protection of sensitive patient health information. It prohibits the disclosure of a person's medical information without their knowledge and consent.

Meeting **compliance standards** is usually a continual process of two parts, which ensures that your systems are effectively protecting everyone's privacy:

- **Security audit**: Review of organization's security controls, policies, and procedures against a set of expectations. It may be performed both internally and externally by different third-party groups. Usually performed once per year.
- **Security assessment**: Check to determine how resilient current security implementations are against threats. Typically performed by internal employees. Usually performed every 3-6 months.

**Algorithm**: Set of rules used that solve a problem.

**Encryption**: Process of converting data from a readable format to an encoded format.

**Cryptography**: Process of transforming information into a form that unintended readers cannot understand (ciphertext). Data is hidden via encryption, and unhidden it via decryption. Every form of encryption relies on both a **cipher** (algorithm that encrypts information) and a **key** (mechanism that decrypts ciphertext). A key should not be stored in public places and should be shared separately from the information it will decrypt.

- **Caesar's cipher**: Cryptographic method where the letters of the message are shifted by a fixed number of spaces. Very unsecure (only about ~26 possible keys). Example: ABC &rarr; DEF. If letters were shifted by 3 spaces to the right, we can decrypt the message with `cat .leftShift3 | tr "d-za-cD-ZA-C" "a-zA-Z"`, which translates text from one set of characters to another, using a mapping.

**Brute force attack**: Trial and error process of discovering private information. Ciphers are vulnerable to them. The longer the key, the more secure it is, but the slower processing times it has. 

**Main types of encryption**: Both methods rely on sharing keys that can be misused, lost, or stolen. Both are used to protect data online and meet compliance regulations.

- **Symmetric encryption**: Use of a single secret key to exchange information. Anybody with the secret key (the owner or anybody he shared the key with) can encrypt and decrypt a message. Faster and simpler process.

- **Asymmetric encryption**: Use of a public (shareable) and private (secret) key pair for encryption and decryption of data. The public key is used by anybody (people, servers...) to encrypt a message, while the private key is used by the owner to decrypt it. This encryption method is used as a secure way to exchange information online. Slower process.

**Digital certificate**: File that verifies the identity of a public key holder. Most online information is exchanged using digital certificates. Users, companies, and networks hold one and exchange them when communicating information online as a way of signalling trust. It's used as an ID badge that's used online to restrict or grant access to information. 

- Example: An online business launching its website wants a digital certificate. When registering its domain, the hosting company sends certain information (company name, country of headquarters...) and a public key for the site over to a trusted certificate authority (CA). The CA verifies the company's identity and encrypts the data with his own private key. Then, the CA creates a digital certificate containing the encrypted company data and the CA's digital signature to prove it's authentic.

**Public key infrastructure** (PKI): Encryption framework that secures the exchange of information online. It involves 2 steps:

- __Exchange of encrypted information__ (asymmetric encryption, symmetric encryption, or both, depending on whether speed of security is the priority). Example: Mobile chat applications use asymmetric encryption to establish a connection between people at the start of a conversation when security in the priority. Afterwards, when speed is priority, symmetric encryption takes over.

- Establish trust using a system of __digital certificates__ between computers and networks. 

Websites tend to use asymmetric encryption to secure small blocks of data that are important. Example: Usernames and passwords are often secured with asymmetric encryption while processing login requests. Once a user gains access, the rest of their web session often switches to using symmetric encryption for its speed.

Using data encryption is increasingly required by law. Regulations like the FIPS 140-3 (Federal Information Processing Standards) and the GDPR (General Data Protection Regulation) outline how data should be collected, used, and handled. 

**Approved algorithms**: Many web applications use a combination of symmetric and asymmetric encryption.

- **Symmetric algorithms**: 

  - **3DES** (Triple Data Encryption Standard): It's known as a block cipher because it converts plaintext into ciphertext in blocks. DES (developed in early 1970s) was one of the earliest symmetric encryption algorithms that generated 64-bit keys. 3DES generates 192-bit keys (64·3=192). Organizations are moving away from 3DES due to limitations on the amount of data that can be encrypted, but it's likely to remain in use for backwards compatibility purposes.

  - **AES** (Advanced Encryption Standard): One of the most secure symmetric algorithms today. It generates keys of 128, 192, or 256 bits. These lengths are considered safe from brute force attacks (brute forcing a 128-bit key could take a computer billions of years).

- **Asymmetric algorithms**: 

  - **RSA** (Rivest Shamir Adleman) (MIT): It's one of the first asymmetric encryption algorithms that produces a public and private key pair. Key sizes are 1024, 2048, 4096 bits. It's mainly used to protect highly sensitive data.

  - **DSA** (Digital Signature Algorithm) (NIST, early 1990s): Widely used as a complement to RSA in public key infrastructure. It also generates key lengths of 2048 bits.

**OpenSSL**: Open-source command line tool (but not the only one) that can be used to generate public and private keys for different algorithms. It's commonly used by computers to verify digital certificates that are exchanged as part of public key infrastructure. In early 2014, OpenSSL disclosed the ["Heartbleed bug"](https://en.wikipedia.org/wiki/Heartbleed) vulnerability, that exposed sensitive data in the memory of websites and applications, which was patched later that year. Example command:

- `openssl aes-256-cbc -pbkdf2 -a -d -in Q1.encrypted -out Q1.recovered -k mypassword`: Decrypt a file with a secure symmetric cipher (`aes-256-cbc`). Different options used: `-pbkdf2` (add extra security to the key), `-a` (desired encoding for the output), `-d` (decrypting), `-in` (input file), `-out` (output file), `-k` (password).

**Obscurity is not security**: A cipher must be proven to be unbreakable before claiming it's secure. According to [Kerchoff's principle](https://en.wikipedia.org/wiki/Kerckhoffs%27s_principle), a cryptographic system should be secure even if everything about the system, except the key, is public knowledge. It should not be considered secure if it requires secrecy around how it works.

**Hash function**: Algorithm that produces a code of fixed size that cannot be decrypted. It's a one-way process that doesn't generate decryption keys, but a unique identifier (hash value, or digest). Generally, standard hash functions that produce longer hashes are considered more secure. The slightest change results in a totally different hash value. In Linux we can generate the hash value for any file on the computer (examples: `sha256sum file.txt`, `sha256sum file.txt >> file1hash`, `cmp file1hash file2hash`).

- Comparing hash values we can validate that two programs are different. 
- Hash values are primarily used to determine the **integrity** of files and applications (authentication and non-repudiation).
- If an attacker replaces a program with a malicious version, its hash function would be different. 
- Hash value of a file can be **compared** with hash values of known viruses. One such database is __VirusTotal__ (useful for analysing suspicious files, domains, IPs, and URLs).

**Non-repudiation**: Concept describing that the authenticity of information cannot be denied. **Data integrity** relates to the accuracy and consistency of information. Hash functions make proven data integrity possible. 

In the early days of computing, hash functions were used for quickly search for data (data is represented by small, fixed-size digests, which are stored in a hash table for efficiently reference it).

**MD5** (Message Digest 5) (MIT, early 1990s): It's one of the earliest hash functions. It was used to verify that files sent over a network matched their source files. It converts data to 128-bit hash values (32 characters). Now, it's considered vulnerable to hash collision.

**Hash collision**: Some inputs can produce the same hash value. There're infinite possible inputs, but only a finite set of available outputs. Hash functions map any input, regardless of its length, into a fixed-size hash value. Hash functions that produce not enough large hash values (like MD5) are vulnerable to hash collision, which attackers can use to fraudulently impersonate authentic data.

**SHA** (Secure Hashing Algorithms): Group of hash functions considered collision resistant because they generate larger hash values. The SHA algorithms are: **SHA-1** (160-bit digest), **SHA-224**, **SHA-256**, **SHA-384**, **SHA-512**.

**Secure password storage**: Passwords are typically stored in a database where they're mapped to a username. The server receives a request for authentications containing the user's credentials. It then looks up the username in the database and compares passwords. If passwords are stored in plaintext, an attacker that gains access to the database could steal them. But hashing them prevents this.

**Rainbow table**: File of pre-generated hash values and their associated plaintext containing weak passwords. Attackers capable of obtaining an organization’s password database can use a rainbow table to compare them against all possible values.

**Salting**: Additional safeguard used to strengthen hash functions. An random string of characters (**salt**) is added to data before it's hashed. This produces a more unique hash value, making salted data resilient to rainbow table attacks. Example: A passwords database might have several hashed entries for password "password". By salting them, each entry would be different.

**Access controls**: Security controls that manage access, authorization, and accountability of information. They maintain data confidentiality, integrity, and availability, and get users the information they need quickly.

The major **security control frameworks** are AAA and IAM. Both systems are designed to authenticate users, determine their access privileges, and track their activities within a system. They each consist of a collection of security controls that ensure that the right user (person, device, software) gets access to the right resources at the right time and for right reasons.

- **AAA framework**: Set of 3 access control systems (authentication, authorization, accounting).
- **IAM framework** (Identity and Access Management): Collection of processes and technologies that helps organizations manage digital identities in their environment. 

**AAA framework**: Set of 3 access control systems:

- **Authentication**: Identifies who is trying to access information.
- **Authorization**: Determines what a user is allowed to do.
- **Accounting**: Monitors access logs of a system.

**Authentication**: Access control that identifies who is trying to access information. In general, there're 3 factors of authentication (knowledge, ownership, characteristics). If the provided authentication information matches information on a file, access is granted; otherwise, access is denied. Authentication proofs:

  - __Knowledge__: Something the user knows (like a password).
  - __Ownership__: Something the user possesses (such as an OTP, one-time passcode: random number sequence a website/application sends you and asks you to provide).
  - __Characteristic__: Something the user is (such as biometrics, like a fingerprint or facial scan).
 
**SSO** and **MFA** are technologies that implement these authentication factors. Usually, both are used in conjunction to provide a secure and convenient access.

- **SSO** (Single sign-on): Technology that combines several different logins into one. Instead of requiring users to authenticate over and over again, SSO establishes identity once, allowing access to company resources faster. 

  - Advantages: It improves user experience (less usernames and passwords to remember), lower costs (by streamlining how connected services are managed), and improves overall security (reduces number of access points attackers can target).
  - SSO solutions use trusted third-parties to prove user's identity, which is done through the exchange of encrypted access tokens, using specific protocols (usually, __LDAP__ and __SAML__ together). 
  - SSO is very vulnerable if it relies on a single factor of authentication. Adding more authentication factors strengthen these systems.

- **MFA** (Multi-factor authentication): Security measure which requires a user to verify his identity in two or more ways (knowledge, ownership, characteristic) to access a system or network. To authenticate an identification a user has to provide 2 (2FA) or 3 factors (3FA). It asks user for proofs (__knowledge__, __ownership__, __characteristic__).

**Authorization**: Access control that determines what a user is allowed to do. Applied principles: Least privilege (access to information only lasts as long as needed) and Separation of duties (users should not have authorization levels that allow misuse, which reduces system failures and inappropriate behaviour from users). Both principles apply to people and all systems (networks, databases, processes...). Some access controls are:

- __Basic auth__: Technology used to establish a user's request to access a server. Some uses:

  - __HTTP__: An identifier is sent every time a user communicates with a website so it can tell if he is authorized or not to access information. It's considered vulnerable because usernames and passwords are transmitted openly over the network.
  - __HTTPS__: It uses encryption to prevent exposing sensitive information while transmitting it.

- __OAuth__: Open-standard authorization protocol that shares designated access between applications. Instead of transmitting sensitive information, an __API token__ (small block of encrypted code that contains user's information) is used to verify access. Access requests are sent and received using API tokens by passing them from a server to a user's device.

**Accounting**: Access control that monitors access logs of a system. 

- **Session**: Sequence of network HTTP basic auth requests and responses associated with the same user. When initiating a session, a __session ID__ is created, and session __cookies__ are exchanged between the server and user's device, so it can read your session ID to determine what information to show you. Exchanging tokens prevent sharing sensitive data. 

  - __Session ID__: Unique token that identifies a user and their device while accessing a system, until it closes his browser or session times out.
  - __Session cookies__: Token that websites use to validate a session and determine how long that session should last. Cookies make web sessions safer (attacker cannot obtain sensitive data) and efficient. However, an stolen cookie can be used to impersonate a user (__session hijacking__: attackers obtains a legitimate user's session ID).

- **Access logs**: Records of sessions that capture the moment a user enters. They contain information such as who accessed a system, when they accessed, what resources they used, etc. They're useful for identifying trends (failed login attempts...), uncovering hackers that gained access to a system, and detecting incidents (data breach...).

**Least privilege** limits the access that an individual receives. **Separation of duties** divides responsibilities among multiple people so nobody has too much control.

**IAM framework** (Identity and Access Management): Collection of processes and technologies that helps organizations manage digital identities in their environment. 

- **User provisioning**: Process of creating and maintaining a user's digital identity. Example: A new user account is created for a recently hired teacher, and it will be configured to provide access to teacher-only resources while they're teaching. Security analysts are routinely involved with provisioning users and their access privileges.

  - __Deprovision users__: Practice that removes a user's access rights when they should no longer have them.

- **Granting authorization**: If the right user has been authenticated, the network should ensure the right resources are made available. There're 3 common frameworks used for handling this step:

  - **MAC** (Mandatory access control, or Non-discretionary control): Authorization is based on a strict need-to-know basis. Access to information must be granted manually by a central authority or system administrator. Example: Often applied in law enforcement, military, and government agencies where users request access through a chain of command.

  - **DAC** (Discretionary access control): Typically applied when a data owner decides appropriate levels of access. Example: The owner of a Google Drive folder shares editor, viewer, or commentor access with someone else.

  - **RBAC** (Role-based access control): Used when authorization is determined by a user's role within an organization. Example: A user in the marketing department has access to user analytics but not network administration.

- [IDPro](https://idpro.org/): Professional organization that shares IAM industry knowledge.

### Vulnerabilities in systems

**Vulnerability**: Weakness that can be exploited by a threat (like a window in a house).

**Exploit**: Way of taking advantage of a vulnerability (like breaking the window).

- **Zero-day**: Exploit that was previously unknown (like using heat to open a door). It's an unexpected threat we don't anticipate and we haven't planned for.

**Vulnerability management**: Process of finding and patching vulnerabilities (fixing their exploits). It helps keep assets safe by stopping threats before they can become a problem. Steps:

- Identify vulnerabilities
- Consider potential exploits
- Prepare defences against threats
- Evaluate those defences 
- Repeat (there're always new vulnerabilities)

For every asset that needs protection, there are many vulnerabilities. To keep assets safe we have to find and fix them before they become a problem (vulnerability management). Assets are protected according to their vulnerabilities and how they can be exploited.

**Defense in depth**: Security framework based on a layered approach to vulnerability management that reduces risk. It's often used for protecting information using a 5 layer design, where each layer features a number of security controls. Information passes through these layers whenever it's exchanged over a network.

- **Perimeter layer**: User authentication layer (username, password...). It only allows trusted partners to reach the next layer.
- **Network layer**: Authorization layer (firewall...).
- **Endpoint layer**: Technologies used (antivirus...) to protect devices that have access on a network (laptop, desktop, server...).
- **Application layer**: Security layers programmed as part of an application (MFA...). It includes the interfaces users interact with.
- **Data layer**: Critical data (stored, in transit, or in use) to be protected (PII...). Asset classification is an important security control here.

Protecting information is a global effort. There are online public libraries (like CVE list) that are used to share and document common vulnerabilities and exposures.

**Exposure**: Mistake that can be exploited by a threat (like putting important documents in an open window).

**[CVE list]** (Common Vulnerabilities and Exposures list): Openly accessible dictionary of known vulnerabilities and exposures. It offers a standard way of identifying and categorizing them. Created by MITRE. Popular resource. Used by many organization to improve their defences. Anybody can report CVEs (independent researchers, technology vendors, ethical hackers...), which then go through a review process by the CNA. They're also reviewed by other online vulnerability databases. 

- **MITRE**: Collection of non-profit research and development centers. Sponsored by US government. It focuses on improving security technologies.

- **CNA** (CVE Numbering Authority): Organization that volunteers to analyse and distribute information on eligible CVEs. It has a stablished record of researching vulnerabilities and security advisory capabilities.

A CVE must meet 4 criteria before it's assigned a CVE ID:

- Independence from other issues (i.e., it can be fixed without fixing something else)
- Recognized as a potential security risk
- Submitted with supporting evidence
- It can only affect one codebase (i.e., only one program's source code)

[**NIST NVD**](https://nvd.nist.gov/) (NIST National Vulnerabilities Database): Online vulnerability database. It uses a CVSS (Common Vulnerability Scoring System), a measurement system that scores (0-10) the severity of a vulnerability. This score can change over time. Scores below 4 are considered low risk, but above 9 are critical risk.

Security teams use CVSS for calculating the impact a vulnerability can have on a system and how quickly it should be patched. They commonly use CVE list and CVSS scores in their vulnerability management system.

**OWASP**: Non-profit foundation that works to improve security of software. Open platform used by security professionals to share information, tools, and events focused on securing the web. One of its most valuable resources is the OWASP Top 10.

- **OWASP Top 10**: List of the web's most targeted vulnerabilities. Many organizations reference to this list during application development to ensure their programs address common security mistakes. It's updated every few years. Rankings are based on how often the vulnerabilities are discovered and their level of risk. Auditors also use this list as a reference when checking for regulatory compliance. The most regularly listed vulnerabilities are:

  - __Broken access control__: Access controls limit what users can do in a web application (example: visitors to a blog can publish but cannot delete an article). Failures here can lead to unauthorized information disclosure, modification, or destruction, or even access to other business applications.
  - __Cryptographic failures__: Privacy laws (like GDPR) require sensitive data to be protected with encryption. Failing to correctly encrypt important information can lead to vulnerabilities (example: using weak hashing algorithm like MD5).
  - __Injection__: Malicious code is inserted in a vulnerable application. It can create a backdoor into an organization's information system. A common target is a website's login form, which can give attackers access to modify or steal user credentials.
  - __Insecure design__: Applications should be designed so they are resilient to attack. Insecure designs have missing or poorly implemented security controls.
  - __Security misconfiguration__: Security settings aren't properly set or maintained (example: network server that uses default settings).
  - __Vulnerable and outdated components__: Open-source libraries are used for developing applications faster. Using vulnerable non-maintained components can lead to great risks. 
  - __Identification and authentication failures__: Applications failing to recognize who has access and what they're authorized to do. Example: home Wi-Fi router failing to keep attackers off the network.
  - __Software and data integrity failures__: Updates or patches inadequately reviewed before implementation. This can lead to downstream effects. Third parties can be infected if a single component is compromised (supply chain attack). Example: during [SolarWinds cyberattack](https://www.gao.gov/blog/solarwinds-cyberattack-demands-significant-federal-and-private-sector-response-infographic) (2020), hackers injected malicious code in software updates that were released later.
  - __Security logging and monitoring failures__: Logging (recording events like login attempts) allows to trace back events, so problems can be found and fixed. Monitoring and incident response is also important.
  - __Server-side request forgery__ (SSRF): Companies store public and private information on web servers. After a user requests data from a server, it validates the user, fetch data, and returns the data. SSRFs are attacks that manipulate the normal operations of a server to read or update other resources on that server. Vulnerable applications on the server may carry malicious code for fetching unauthorized data to the host server.

**OSINT** (Open-Source Intelligence): Collection and analysis of information from publicly available sources to generate usable intelligence. It can be used to provide insights into cyberattacks, detect potential data exposures, evaluate existing defences, identify unknown vulnerabilities, etc. It can be part of vulnerability management process.

- **Information**: Collection of raw data or facts about a specific subject. Example: A new update to the OS has some vulnerabilities.

- **Intelligence**: Analysis of information to produce knowledge or insights that can be used to support decision-making. Intelligence is derived from information through analysis, interpretation, and integration. Example: An analysis of information makes us decide to don't install the update.

- __OSINT tools__: There's a lot of open-source information online (search engines, social media, discussion boards, blogs...). Some tools are:

  - [VirusTotal](https://www.virustotal.com/gui/home/upload): Allows anyone to analyse suspicious files, domains, URLs, and IP addresses for malicious content.
  - [MITRE ATT&CK](https://attack.mitre.org/): knowledge base of adversary tactics and techniques based on real-world observations.
  - [OSINT framework](https://osintframework.com/): Web-based interface where you can find OSINT tools for almost any kind of source or platform.
  - [Have I been Pwned](https://haveibeenpwned.com/): Tool that can be used for searching for breached email accounts.

**Vulnerability assessment**: Internal review process of an organization's security systems. Its main purpose is to identify weak points (vulnerabilities) and prevent attacks, and determine if security controls meet regulatory standards. The organization's security team performs, evaluates, scores, and fix vulnerabilities. Process:

1. __Identification__: Understand current state of a security system. Find vulnerabilities using scanning tools and manual testing.
2. __Vulnerability analysis_: Test the identified vulnerabilities and find the source of the problem.
3. __Risk assessment__: Assign a severity score to each vulnerability depending on the potential severity of exploiting it and the likelihood of this happening. 
4. __Remediation__: Address vulnerabilities depending on their severity score (enforcing new security procedures, update OSs, implement system patches...).

**Vulnerability scanning**: Software that automatically compares known vulnerabilities and exposures against the technologies on the network. In general, they scan systems looking for misconfigurations or programming flaws. Used for analysing each of the 5 attack surfaces from defence in depth. When scanning a layer, it compares the findings against databases of security threats. Found vulnerabilities are added to its database. Each scan adds more information to the database, which improves the tool's analysis. Vulnerability databases are routinely updated by the company that designed the scanning software. These scanners are meant to be non-intrusive (they don't break or take advantage of a system, unlike an attacker), they simply scan and alert of unlocked doors in your systems. There're special cases where a scanner can inadvertently cause issues (system crash...). There're different ways of scanning, based on a threat actor pathway:

- **External vs. internal**: Scans that simulate an attacker's approach.
  - __External scans__ test outward facing systems (websites, firewalls...) to uncover vulnerable things (network ports, servers...).
  - __Internal scans__ examine internal systems (user input management...).

- **Authenticated vs. unauthenticated**: Scans that simulate whether or not a user has access to a system.
  - __Authenticated scans__: Used to check for vulnerabilities (broken access controls...). Example: Test a system by logging in with a user or admin account.
  - __Unauthenticated scans__: Simulate external threat actors that don't have access to business resources. Unauthenticated users should get "access denied" when trying to open them. 

- **Limited vs. comprehensive**: It focuses on particular devices that are accessed by internal and external users. A **discovery scanning** (discover computers, devices, and open ports that are on a network) should be done first.
  - __Limited scans__: Analyse particular devices on a network (like searching for misconfigurations on a firewall).
  - __Comprehensive scans__: Analyse all devices connected to a network (OSs, databases...).

**Updates** usually take place after a vulnerability assessment. A **patch update** is a software and OS update that addresses security vulnerabilities within a program or product. Patches usually contain **bug fixes** that address common security vulnerabilities and exposures. Patches usually address vulnerabilities and exposures before malicious hackers find them, but sometimes they are developed as a result of a zero-day (previously unknown exploit). Two update types:

- **Manual**: IT departments or users have to find, download, and install updates themselves. This process can be handled with a configuration management tool. This gives more control, but critical updates can be forgotten or disregarded entirely.
- **Automatic**: The system or application finds, downloads, and install updates. Requires to enable certain permissions. CISA recommends this option. The deployment process is simplified, and keeps systems and software current with the latest, critical patches; but instability issues may occur if patches are not thoroughly tested by the vendor, resulting in poor performance and user experience.

**EOL software** (End-Of-Life software): Software no longer supported by the manufacturer. There're no more updates available for it.

**Upgrade**: Completely new version of hardware or software that can be purchased.

CISA recommends stop using EOL software because it poses an unfixable risk to systems. However, it's not always done because replacing it can be costly for users and businesses. Example: There're billions of IoT devices connected to home and work networks. A single unpatched device could serve an attacker for gaining access to the network.

**Penetration testing** (Pen test): Simulated attack that helps identify vulnerabilities in systems, networks, websites, applications, and processes. It uses the same tools and techniques as malicious actors use. It's a form of ethical hacking. It exploits weaknesses to determine potential consequences of attacks. Organizations regulated by PCI DSS, HIPAA, or GDPR must routinely perform pen testing to maintain compliance standards. Different approaches to pen testing:

- __Red team__: Simulates attacks (proactive simulation) to identify vulnerabilities in systems, networks, or applications. Red teams are usually made of independent pen testers. They tend to spend more time planning attacks than performing them.
- __Blue team__: Focused on defense and incident response (reactive simulation) to validate an organization's existing security systems. It focuses on gathering information about the assets they protect, usually using vulnerability scanning tools.
- __Purple team__: Combines elements of red and blue team exercises for improving the organization's security posture.

There're 3 common pen testing **strategies**:

- **Open-box testing** (internal, full knowledge, white-box, clear-box): The tester has the same privileged access than an internal developer.
- **Closed-box testing** (external, black-box, zero-knowledge): The tester has little to no access to internal systems, similar to a malicious hacker.  This tends to produce the most accurate simulations of real attacks.
- **Partial knowledge testing** (gray-box): The tester has limited access and knowledge of an internal system. 

Pen tester **skills**:

- Network and application security
- Experience with OSs (Linux...)
- Vulnerability analysis and threat modelling
- Detection and response tools
- Programming languages (Python, BASH...)
- Communication skills

**Bug bounty programs**: Organizations may offer freelance pen testers financial rewards for finding and reporting vulnerabilities in their products. You can find some bug bounties in [HackerOne](https://hackerone.com/bug-bounty-programs).

**Attack surface**: All the potential vulnerabilities that a threat actor could exploit. Analysing it is usually the first thing security teams do. Two types of attack surfaces:

- **Physical**: Made of people and their devices. It can be attacked from inside and outside the organization. Examples: staff, laptop, devices...
- **Digital**: Everything beyond the organization's firewall. Anything that connects to an organization online. Examples: networks, website, cloud servers...

**Attack tree**: Diagram that maps threats to assets.

**Security hardening**: Process of strengthening a system to reduce its vulnerabilities and attack surface. It minimizes the attack surface by limiting its points of entry. The smaller the attack surface, the easier it is to protect. Some security controls (organization policies, access controls...) are used to harden the physical attack surface. Cloud computing has expanded the attack surface (organizations save data on the cloud, not in their own servers).

**Threat actor**: Person or group who presents a security risk. They can be from inside or outside the organization. They can put assets at risk intentionally or accidentally. Types:

- __Competitors__: Rival companies that might benefit from leaked information.
- __State actors__: Government intelligence agencies.
- __Criminal syndicates__: Organized groups that make money from criminal activity.
- __Insider threats__: Individual that has or had authorized access to the organization's resources. They can put assets at risk intentionally or accidentally.
- __Shadow IT__: Individuals who use technologies that lack IT governance.  

**Hacker**: Person who uses computers to gain unauthorized access to computer systems, networks, or data. Types:

- __Unauthorized hackers__: He uses programming skills to commit crimes.
- __Authorized/ethical hackers__: He uses programming skills to improve an organization's overall security (employees, externals, freelances).
- __Semi-authorized hackers__: He violates ethical standards, but are not considered malicious. Example: hacktivist (he uses his skill for achieving a political goal).

**APT** (Advanced Persistent Threat): A threat actor maintains unauthorized access to a system for an extended period of time (instead of leaving after attacking). Mostly associated with nation states and state-sponsored actors. APTs are usually concerned with surveilling a target to gather information, and then use the intel to manipulate government, defense, financial, and telecom services. APTs often target private organizations first before gaining access to larger entities.

**Attack vectors**: Pathways attackers use to penetrate security defences (intentionally or accidentally).

**Access point**:  Attack vectors used by threat actors to gain access to a system. Types:

- __Direct access__: Physical access to the system.
- __Removable media__, including portable hardware (USB flash drives...).
- __Social media platforms__ used for communication and content sharing.
- __Email__, including personal and business accounts.
- __Wireless networks__ on premises.
- __Cloud services__ usually provided by third-party organizations.
- __Supply chains__, like third-party vendors that can present a backdoor into systems.

Security teams think of each attack vector with an attacker mindset. Practicing an attacker mindset provides insight into the best security controls to implement and the vulnerabilities to monitor. Steps:

- Identify a target
- Determine how the target can be accessed
- Evaluate attack vectors that can be exploited
- Find the tools and methods of attack

Defending attack vectors:

- Educating users
- Applying the principle of least privilege
- Using the right security controls and tools
- Building a diverse security team

**Brute force attack**: Trial-and-error process of discovering private information. It can be tedious and time consuming. Types of access credentials brute force attacks:

- __Simple brute force attack__: Attacker guess user's login credentials. He can try any combination he can think of until one works.
- __Dictionary attack__: Similar to simple brute force, but using a list of commonly used credentials to access a system.
- __Reverse brute force attack__: Similar to dictionary attack, but starting with a single credential and trying it in various systems until a match is found.
- __Credential stuffing__: Uses stolen login credentials from previous data breaches to access user accounts at another organization. A special type is __pass the hash__ (reuse stolen, unsalted hashed credentials to trick an authentication system into creating a new authenticated user session on the network).

**Exhaustive key search**: Brute force technique for accessing encrypted information.

Common brute force __tools__:

- Aircrack-ng__
- Hashcat__
- John the Ripper__
- Ophcrack__
- THC Hydra__

Techniques for __defending__ against brute force attacks:

- __Hashing and salting__: Hashing converts information into a unique value that can then be used to determine its integrity. Salting is an additional safeguard for strengthening hash functions (it adds random characters to data, like passwords, increasing length and complexity of hash values, making them harder to brute force and dictionary attacks).
- __MFA__: User verify his identity in two or more ways to access a system or network. It's a layered approach to protecting information. Unauthorized users can hardly meet all authentication requirements.
- __CAPTCHA__ (Completely Automated Public Turing test to tell Computers and Humans Apart): Challenge-response authentication system for proving that you are human and not software that's trying to brute force a password.
- __Password policies__: Organizations use managerial controls to standardize good password practices across their business (example: use passwords with certain characteristics, limit the number of login attempts before suspending account, or require users to create new password after some time). The [NIST SP 800-63B](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-63b.pdf) provide guidance about password policies.

### Threats to asset security

#### Social engineering

**Threat**: Any circumstance or event that can negatively impact assets.

**Social engineering**: Manipulation technique that exploits human error to gain private information, access, or valuables. It can happen anywhere (online, in person, and other interactions). Anyone is vulnerable. Threat actors use many different tactics (fake tech support...). It can happen in a few seconds, or take months or longer. These attacks can be very dangerous because they don't require sophisticated computer skills, and allows to bypass technological defenses. Typical stages:

1. __Prepare__: Gather information about the target to find the best way to exploit him.
2. __Establish trust__ (pretexting): Previously gathered information is used to open communication (usually, to trick the target into a false sense of trust).
3. __Persuasion tactics__: Manipulate the target into volunteering information.
4. __Disconnect from the target__: Disappear to cover tracks.

Example: During the [Twitter hack of 2020](https://www.dfs.ny.gov/Twitter_Report) a group of hackers made phone call to Twitter employees pretending to be from the IT department and gained access to the organization's network and tools, allowing them to take over accounts of high-profile users.

__Defending__ against social engineering attacks requires a multi-layered approach that combines user awareness with technological controls (firewalls, MFA, block lists, email filtering...). Recognizing the __signs of social engineering__ is key for reducing the likelihood of successful attacks:

- __Baiting__: Tempt people into compromising their security. Example: someone finds an infected USB drive and plugs it into his device.
- __Phishing__: Use digital communications to trick people into revealing sensitive data or deploying malicious software. Very common. Usually performed via email.
- __Quid pro quo__: Trick someone into believing that they’ll be rewarded in return for sharing access, information, or money. Example: an attacker impersonates a bank loan officer and offers a low interest rate on your credit card, but needs your account details to claim the deal.
- __Tailgating__ (piggybacking): Unauthorized people follow an authorized person into a restricted area.
- __Watering hole__: A website frequently visited by a specific group of users is compromised. Oftentimes, these sites are infected with malicious software. Example: Holy Water attack (2020) infected various religious, charity, and volunteer websites.

__Preventing__ social engineering:

- Implement managerial controls (policies, standards, procedures...).
- Stay informed of trends.
- Share your knowledge with others.

__Encouraging caution__: Train employees and customers about social engineering threats.

- __Stay alert__ of suspicious communications and unknown people, especially from email.
- __Be cautious__ about sharing information, especially over social media.
- __Control curiosity__ when something seems too good to be true.

Resources (social engineering):

- [OUCH!](https://www.sans.org/newsletters/ouch/): Free monthly newsletter from SANS Institute that reports on social engineering trends and other security topics.
- [Scamwatch](https://www.scamwatch.gov.au/): News and tools for recognizing, avoiding, and reporting social engineering scams.

#### Phishing

**Phishing**: Use of digital communications (usually, email) to trick people into revealing sensitive data or deploying malicious software. Attackers carrying out phishing commonly use __phishing kits__. Some forms of phishing are:

- **Email phishing**: Use of email for sending messages pretending to be a trusted person or entity.
  - **Spear phishing**: Subset of email phishing where specific people is targeted.
    - **Whaling**: Type of spear phishing that targets high-ranking executives in an organization.
  - **Angler phishing**: Impersonate customer service representatives on social media to get sensitive information from customers.
- **Smishing**: Use of __text messages__ to obtain sensitive information or to impersonate a known source. 
- **Vishing**: Exploitation of __electronic voice communication__ (voice call or voice messages) to obtain sensitive information or impersonate a known source.

**Phishing kit**: Collection of software tools needed to launch a phishing campaign. Not much technical background is needed. Each tool is designed to avoid detection. Main tools:

  - __Malicious attachments__: Infected files that can cause harm.
  - __Fake data-collection forms__: Forms looking like legitimate forms (like a survey) and used for asking for sensitive information.
  - __Fraudulent web links__: Malicious web pages looking like trusted brands and built to steal information.

Phishing __security measures__:

- Anti-phishing policies
- Employee training resources
- Email filters (blocklists, allowlists...)
- Intrusion prevention systems (there're monitoring tools that spot suspicious emails, quarantine them, and produce a log of events)  

Resources (phishing):

- [Google's phishing quiz](https://phishingquiz.withgoogle.com/): See how difficult it can be to identify these attacks.
- [Phishing.org](https://www.phishing.org/): Latest phishing trends and free resources.
- [APWG](https://apwg.org/) (Anti-Phishing Working Group): Non-profit security experts that publish a quaterly report on phishing trends.

#### Malware

**Malware**: Software designed to harm devices or networks. Most common types:

- **Virus**: Malicious code written to interfere with computer operations and cause damage to data and software. When the user launches the infected program, the virus clones itself and spreads to other files in the device. It has to be installed by the target user.
- **Worm**: Malware that can duplicate and spread itself across systems on its own (no need of the user executing something). It has to be installed by the target user. It uses an infected device as a host and scan the connected network for other devices. Then, infect everything on the network without requiring an action to trigger the spread.
- **Trojan**: Malware that looks like a legitimate file or program. It is often used to gain access and install a ransomware. It's hidden in file and application downloads.
- **Ransomware**: Attackers encrypt the organization's data and demand payment to restore access (decrypt). It makes himself known to its target in order to collect the payment. Example: [WannaCry](https://en.wikipedia.org/wiki/WannaCry_ransomware_attack).
- **Adware**: Legitimate software that is sometimes used to display digital advertisements in applications. It allows developers monetize their product (software, freeware, shareware) through ad revenue.
- **PUA** (Potentially Unwanted Application): Unwanted software (like malicious adware) bundled in with legitimate programs (bundleware). It displays ads, cause device slowdown, or install other software. Example: Malicious adware monetize ads not for the developer but for somebody else.
- **Spyware**: Type of PUA. Malware used to gather and sell information without consent. Often hidden in bundleware (additional software packaged with other applications).
- **Scareware**: Type of PUA. Malware that frightens users into infecting their own device (like displaying fake warnings). It's spread via email, pop-ups, etc.
- **Fileless malware**: No need to be installed by the user because it uses legitimate programs that are already installed to infect a computer. This infection resides in memory where the malware never touches the disk, instead of being stored in a file on disk. It gets into the OS or hide within trusted applications. It's detected by performing memory analysis.
- **Rootkits**: Malware that provides remote, administrative access to a computer. Mostly used to open a backdoor, allowing malware installation or network security attacks. Often spread using both a __dropper__ and a __loader__.
  - **Dropper**_: Malware packed with malicious code which is delivered and installed onto a target system. It's often disguised as a legitimate file to deceive its target into opening it, which executes the malicious code and it hides itself on the target system.
  - **Loader**: Malware that downloads strains of malicious code from an external source and installs them onto a target system. Often used to setup another type of malware.
- **Botnets**: Collection of computers (robot network) infected by malware that is controlled by a single threat actor (bot-herder). The initial infection is often spread by viruses, worms, and trojans. The attacker then uses file sharing, email, or social media application protocols to create new bots and grow the botnet. When a target opens the malicious file, the computer reports the information back to the bot-herder, who can execute commands on the infected computer.
- **Cryptojacking**: Malware that installs software to illegally mine cryptocurrencies. It's hard to detect. Main signs: slowdown, increased CPU usage, system crashes, fast draining batteries, high electricity costs.

**IDS** (Intrusion Detection System): Application that monitors system activity and alerts on possible intrusions. New forms of malware may remain undetected.

Some measures for reducing likelihood of malware attacks:

- Some browser extensions are designed to block malware.
- Use adblockers
- Disable JavaScript
- Stay alert on the latest trends

#### Web-based exploits

**Web-based exploit**: Malicious code or behaviour that's used to take advantage of coding flaws in a web application.

**Injection attack**: Malicious code inserted into a vulnerable application. Infected applications often appear to work normally because the injected code runs in the background. 

Applications are vulnerable to injections because they are programmed to receive data inputs (something the user types or clicks, something one program is sharing with another...). Applications should be able to interpret and handle user inputs. Example: if an application expects the user to enter a phone number, it should validate that input (make sure it's no more than 10 numbers, without letters). If the input doesn't meet the requirements, the application should know how to handle it (sanitized input).

**XSS** (Cross-site scripting): Injection attack that inserts code into a vulnerable website or web application. Often delivered by exploiting HTML and JavaScript (used by most websites), which can give access to everything loaded on the infected webpage (session cookies, geolocation, webcams, microphones...). Types of XSS attacks:

- **Reflected**: A malicious script is sent to a server and activated during the server's response. Example: A criminal sends his target a web link that appear to go to a trusted site. When the target clicks the link, it sends a HTTP request to the vulnerable site server, which returns the attacker script, which is loaded by the browser because it trusts the server's response, and information (session cookies…) is sent back to the attacker.
- **Stored**: A malicious script is injected directly on the server (unlike reflected XSS, it's not hidden in a link that needs to be sent to the server). Attackers target elements of a site that are served to the user (images, buttons... loaded when the site is visited). Infected elements activate the malicious code when a user visits the site. The user cannot know if the site is infected beforehand.
- **DOM-based**: A malicious script exists in the webpage a browser loads (unlike reflected XSS, this attack doesn't need to be sent to the server to activate). The malicious script can be seen in the URL (a URL containing parameter values that reflect input from the user). Criminals change the parameter that's expecting an input (example: a script modifies `my.website.com/mything?theme=light` to `my.website.com/mything?theme=alert(1)`). The browser would process the HTML and execute the JavaScript.

**SQL injection**: Attack that executes unexpected queries on a database. It's done to modify, delete, or steal information from databases, and even gain unauthorized access to web applications. Some websites, like shopping websites, use databases. Websites don't normally make users enter SQL queries manually, but provide an interface instead (images, menus, buttons...). Sometimes, the backend queries are vulnerable to injection, which is due to a lack of sanitized input. It takes place in a website area designed to accept user input. The best defense is to use code that sanitize the input (like a Prepared statement).

- Example: When a user enters his credentials (`username` and  `password`), a login form might trigger a backend SQL statement (`SELECT id FROM users WHERE user_id = '$username' AND pass_w = '$password';`) that is sent to a server to run the query. User's input should not be inserted exactly as it entered. Otherwise, attackers can exploit this (like injecting SQL code that makes the server run an unexpected harmful query), allowing them to obtain sensitive information, modify tables, gain administrative rights, etc.

- **Prepared statement**: Coding technique that executes SQL statements before passing them on to the database. Useful when user's input is unknown. It executes the code before passing it to the server (code is validated before performing the query).

**SQL queries**: Request for data from a database. SQL injections can occur anywhere within a vulnerable application that can accept a SQL query. Every bit of information that’s accessed online is stored in a database (organized collection of information or data in one place). In SQL, database information is organized in tables. SQL is commonly used for retrieving, inserting, updating, or deleting information in tables using queries. Queries are usually initiated in places where users can input information into an application or a website via an input field, which accepts text input (login forms, search bars, comment submission boxes...). 

SQL injection **categories**:

- **In-band**: It uses the same communication channel to launch the attack and gather the results. Most common type. After the injection, the data returned from the database is displayed back where the malicious code was injected (example: a search box).
- **Out-of-band**: It uses a different communication channel to launch the attack and gather the results. Very uncommon.
- **Inferential**: The attacker is unable to directly see the results of their attack. Instead, he can interpret the results by analyzing the behavior of the system.

**Escape user inputs**: Action of preventing someone from inserting any code that a program isn't expecting. This is key for preventing SQL injection. Different ways:

- **Prepared statements**: Coding technique that executes SQL statements before passing them on to a database. Useful when user's input is unknown. It executes the code before passing it to the server (code is validated before performing the query).
- **Input sanitization**: Programming that removes user input which could be interpreted as code.
- **Input validation**: Programming that ensures user input meets a system's expectations.

More information in [OWASP's SQL injection detection techniques](https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/07-Input_Validation_Testing/05-Testing_for_SQL_Injection).

#### Threat modelling

**Threat actor**: Person or group who presents a security risk. It can be internal (like an employee) or external (like a malicious hacker).

**Attack tree**: Diagram that maps threats to assets.

**Threat modelling**: Process of identifying assets, their vulnerabilities, and how each is exposed to threats. It combines various security activities (vulnerability management, threat analysis, incident response...). This is performed to ensure systems are adequately protected, or for finding ways of reducing risks. It's applied to anything that needs protection (systems, applications, business processes...). It's often performed by experienced security professionals, but almost never done alone. There're several threat modelling frameworks (for network security, information security, application development...). Steps:

1. __Define scope of the model__: Create an inventory of assets and classify them.
2. __Identify threats__: Define potential threat actors. Then, put together an attack tree.
3. __Characterize the environment__: Apply an attacker's mindset to the business. 
4. __Analyze threats__: Examine existing protections and identify gaps. Then, rank threats according to their risk score.
5. __Mitigate risks__: Create a plan for defending against threats. Choices: avoid risk, transfer it, reduce it, or accept it.
6. __Evaluate findings__: Everything done in previous steps is documented, fixes are applied, and teams make note of any success they had and report lessons learned.
7. Repeat

One key to threat modelling is asking the right questions: What are we working on? What kind of things can go wrong? What are we doing about it? Have we addressed everything? Did we do a good job?

In __application development__, ideally, threat modelling should be performed before, during, and after an application is developed (though it takes time and resources). It should be incorporated at every stage of the SDLC.

**Threat modelling methods**: There're different methods (STRIDE, PASTA, Trike, VAST...). Organizations use any one of them to gather intelligence and make decisions to improve their security posture. The right one depends on the situation and types of risks.

- **PASTA** (Process of Attack Simulation and Threat Analysis): Popular threat modelling framework that's used across many industries. It's risk-centric, and is focused on discovering evidence of viable threats and representing this information as a model. It's evidence-based design can be applied when threat modelling an application or the environment supporting it. Developed by 2 OWASP leaders and supported by VerSprite (cybersecurity firm). Stages:

  1. Define business and security __objectives__ (example: protect user's data).
  2. Define the __technical scope__: Identify the application components to evaluate (attack surface).
  3. __Decompose the application__: Identify the existing controls for ensuring the objectives.
  4. Perform a __threat analysis__: Get into the attacker's mindset. Collect up-to-date information on the type of attacks being used.
  5. Perform a __vulnerability analysis__: Investigate potential vulnerabilities by considering the root of the problem.
  6. Conduct __attack modelling__: Test the analysed vulnerabilities by creating an attack tree, which is used to identify attack vectors that need to be tested to validate threats.
  7. __Analyze risk and impact__: Using all the collected information make informed risk management recommendations to business stakeholders that align with their goals.

- **STRIDE** (Spoofing, Tampering, Repudiation, Information disclosure, Denial of service, Elevation of privilege): Commonly used to identify vulnerabilities in 6 specific attack vectors (the acronym represents each vector). Developed by Microsoft. 

- **Trike**: Open source methodology and tool that takes a security-centric approach to threat modeling. It's commonly used to focus on security permissions, application use cases, privilege models, and other elements that support a secure environment.

- **VAST** (Visual, Agile, and Simple Threat): Modelling framework that is part of the ThreatModeler® automated threat-modeling platform. It's often used as a way of automating and streamlining the threat modelling assessments.


## Detection and response


### Introduction

**Frameworks** help develop a standardized approach to the incident response process, so that incidents are managed in an effective and consistent way. There are different types of frameworks that can be adopted and modified according to needs.

**NIST CSF**: Cybersecurity Framework consisting of 5 core functions: identify, protect, detect, respond, recover.

**NIST Incident Response Lifecycle**: NIST framework for incident response (focused on detect, respond, recover). It's a cycle. Phases:

  - __Preparation__
  - __Detection and analysis of events__
  - __Containment__, Eradication and recovery__
  - __Post incident activity__

**Incident**: Occurrence that actually or imminently jeopardizes, without lawful authority, the confidentiality, integrity, or availability of information or an information system; or constitutes a violation imminent threat of violation of law, security policies, security procedures, or acceptable use policies. 

**Event**: Observable occurrence on a network, system, or device. All security incidents are events, but not all events are security incidents.

- Example: A user cannot login because he forgot his password, so it request a password request and successfully change it. This is observable because there's evidence of what happened (systems and applications log password reset requests).
- Example: A malicious actor trying to access the user's account requests a password reset and changes it. This is an event (because is an observable occurrence) and a security incident (security policy was violated to access another's account).

**The 5 W's of an incident**: Keeping track of this information is essential during incident investigation and when writing the final report.

- Who triggered the incident
- What happened
- When the incident took place
- Where the incident took place
- Why the incident occurred

**Incident handler's journal**: Form of documentation used in incident response.

**CSIRT** (Computer Security Incident Response Team) (or IHT: Incident Handling Team) (or SIRT: Security Incident Response Team): Specialized group of security professionals that are trained in incident management and response. Their goals are to manage incidents effectively and efficiently, provide services and resources for response and recovery, and prevent futures incidents from occurring. It works cross-functionally with other departments to share relevant information. 

**Roles in CSIRT**:

- **Security analyst**: Continuously monitor an environment for any security threats. Investigates security alerts to determine if an incident has occurred (analyze and triaging alerts). If so, he will determine the criticality of the incident (perform root-cause investigation). He can remediate some incidents, but critical ones are escalated to the technical lead.
- **Technical lead** (or Ops lead): Provides technical leadership by guiding security incidents through their lifecycle. Determines the root cause of the incident, and then create and implement strategies for containing, eradicating, and recovering from the incident (he manages all technical aspects of the incident response process). 
- **Incident coordinator**: Coordinates with the relevant departments during a security incident (security and nonsecurity professionals from different departments). Tracks and manages the CSIRT activities and other teams involved in the response effort. He ensures that incident response processes are followed and teams are regularly updated on the incident status.
- **Other roles** can be found (communications lead, legal lead, planning lead...).
- **Nonsecurity professionals**: Those consulted to offer their expertise on the incident. They can be from external departments (human resources, public relations, management, IT, legal...).

**Skill for CSIRT** to achieve his goals:

- __Command__: Leadership and direction to eversee the response.
- __Control__: Manage technical aspects during incident response (coordinating resources, assigning tasks...).
- __Communication__: Keep stakeholders informed.

**SOC** (Security Operations Center): Unit dedicated to monitoring networks, systems, and devices for security threats or attacks. It often exists within a CSIRT or as its own separate unit. It's involved in various types of blue team activities (network monitoring, analysis, response to incidents...). It's composed of:

- **Tier 1 SOC analyst**: The least experienced SOC analysts (level 1, L1s). Responsibilities:

  - Monitoring, reviewing, and prioritizing alerts based on criticality or severity
  - Creating and closing alerts using ticketing systems
  - Escalating alert tickets to Tier 2 or Tier 3

- **Tier 2 SOC analyst**: More experienced SOC analysts (level2, L2s). Responsibilities:

  - Receiving escalated tickets from L1 and conducting deeper investigations
  - Configuring and refining security tools
  - Reporting to the SOC Lead

- **Tier 3 SOC lead**: Highly experienced professionals (level3, L3s). Responsibilities:

  - Managing the operations of their team
  - Exploring methods of detection by performing advanced detection techniques, such as malware and forensics analysis
  - Reporting to the SOC manager

- **SOC manager**: Top SOC leader. Responsibilities:

  - Hiring, training, and evaluating the SOC team members
  - Creating performance metrics and managing the performance of the SOC team
  - Developing reports related to incidents, compliance, and auditing
  - Communicating findings to stakeholders such as executive management  

- **Other roles**: 

  - **Forensic investigators** (L2s, L3s): Collect, preserve, and analyze digital evidence related to security incidents to determine what happened.
  - **Threat hunters** (L3s): Detect, analyze, and defend against new and advanced cybersecurity threats using threat intelligence.

**Resources**:

- [Cyber-career pathways tool](https://niccs.cisa.gov/workforce-development/cyber-career-pathways-tool)

**Incident response plan**: Document that outlines the procedures to take in each step of incident response. It may be included in the security plan or be a separated document. Incident processes and procedures must be regularly reviewed and tested . Elements:

- Incident response procedures (instructions on how to respond to incidents)
- System information (network diagrams, data flow diagrams, logging, asset inventory information...)
- Other documents (contact lists, forms, and templates)

**Elements of a security plan**: 

- **Policies**
- **Standards**
- **Procedures**

**Tools of the trade**:

- __Detection and management tools__: To monitor system activity to identify events that require investigation.
- __Documentation tools__: To collect and compile evidence.
- __Investigative tools__: To analyze events (like packet sniffers).

**Documentation**: Any form of recorded content (audio, digital, handwritten, video...) that is used for a specific purpose. It's meant to provide instruction and guidance on a specific topic. There's no industry standard for documentation, so it can vary from one organization to another. Effective documentation reduces uncertainty and confusion; it should be clear, consistent, and accurate.

- __Types of documentation__: playbooks (manual of an operational action), incident handler's journals, policies, plans, final reports, etc.
- __Documenting tools__:

  - __Word processor tool__: Google Docs, OneNote, Evernote, Notepad++, …
  - __Ticketing system__: Jira, …
  - __Others__: Google Sheets, audio recorder, camera, handwritten notes, …

**Detection tools**: They help organizations protect their networks and systems against unwanted and unauthorized access.

- **IDS** (Intrusion Detection System): Application that monitors system and network activity and produces alerts on possible intrusions. It collects and analyses information for abnormal activities. If something unusual is detected, it sends out an alert to appropriate channels and personnel. It detects malicious activity, logs activity, and generates alerts. A detection can be a true positive, true negative, false positive, or false negative. Some IDS tools: Zeek, Kismet

- **IPS** (Intrusion Prevention System): Application that monitors system activity for intrusions and take action to stop the activity. Like IDS, but also prevents intrusions. Some IPS tools: Suricata, Snort, Sagan.

- **EDR** (Endpoint Detection and Response): Like IPS, but also performs behavioural analysis (using AI and ML) to identify threat patterns happening on an endpoint. It's installed on endpoints (devices connected to a network) and monitors it for malicious activity. Some EDR tools: Open EDR, Bitdefender EDR, FortiEDR.

**SIEM tools** (Security Information and Event Management tools): Application that collects and analyses log data to monitor critical activities in an organization and report them. Like an IDS, it also has detection capabilities. It provides a high-level overview of what happens in a network. It looks at data flows between all the systems in a network and analyses them to provide a real-time picture of any potential threats. It provides access to event data in a centralized location (real-time or historical data), monitors systems and networks, analyzes data to detect malicious activity, and alerts if detected. Some SIEM tools: AlienVault OSSIM, Chronicle, Elastic, Exabeam, IBM QRadar Security Intelligence Platform, LogRhythm, Splunk.

Process:

1. Collect data (mostly from logs, which record events on a given source) from different sources (computers, servers, IDS, IPS, databases, firewalls, applications, routers, switches, ...).
2. Aggregate (centralize) that data in one place. Data can be parsed (map data according to their fields and values, making it more readable).
3. Normalize data: Clean up raw data by removing non essential attributes so only relevant data is left. Format data so it is easily searchable and easily processed by the SIEM.
4. Analyze data according to configured rules (including correlation) to detect possible security incidents. If any log activity matches a rule, alerts are sent to cybersecurity teams.
  - Correlation: Comparison of multiple log events to identify common patterns that indicate potential security threats. 

**SOAR tools** (Security Orchestration, Automation, and Response tool): Collection of applications, tools, and workflows that uses automation to respond to security events. It automates analysis and response to security events and incidents. It can also be used to track and manage cases (collection of incidents).


### Network monitoring and analysis

**Network traffic**: Amount of data that moves across a network.

**Network data**: Data that's transmitted between devices on a network

Network monitoring helps detect, prevent, and respond to attacks. Network communication can be noisy. By understanding how data should be flowing across a network, we can know what is the expected network traffic flow. By knowing what's normal (baseline), we can spot what's abnormal. Monitoring for deviations from typical network traffic patterns often yield big results. Traffic abnormalities can be can detected through observation to spot IoC.

- **IoC** (Indicators of Compromise): Observable evidence that suggests signs of a potential security incident.
- **Data exfiltration**: Unauthorized transmission of data from a system.
- **Baseline**: Reference point used for comparison. It helps establish a standard of expected or normal behaviour for systems, devices, and networks. It helps identify abnormal network behaviour. 
- **Monitoring** involves examining network components to detect unusual activities (those that deviate from the baseline).

  - **Flow analysis**: Movement of network communications. Packets travel to ports, which receive and transmit communications. Ports are often (not always) associated with network protocols. Malicious actors can use protocols and ports that are not commonly associated to maintain communication with the compromised system (C2, Command and Control). Organizations must know which ports should be open, and watch out for mismatches between ports and their associated protocols.

  - **Packet payload information**: Actual data that is transmitted (apart from the header and trailer). Organizations can monitor it to uncover unusual activity. 

  - **Temporal patterns**: Network packets contain information relating to time. It can be used to detect abnormal network activity 

**NOC** (Network Operations Center): Organizational unit that monitors the performance of a network and responds to any network disruption (like network outage). It's responsible for maintaining network performance, availability, and uptime. 

Some **network monitoring tools** are:

- **IDS** (Intrusion Detection System): It monitors system activity and alerts on possible intrusions. It will detect and alert on deviations you’ve configured it to detect. Commonly, it monitors the content of packet payload to detect patterns associated with threats (malware, phishing...).

- **Network protocol analyzer** (packet sniffer): It captures and analyzes data traffic within a network. It can be used to analyze network communications manually in detail. Some tools: tcpdump, Wireshark, etc.

**Data exfiltration**: Unauthorized transmission of data from a system.

- Process:

  1. Attacker gains access to a system (via social engineering...)
  2. He tries to  maintain access and remain undetected, often via lateral movement, or pivoting (explore network for expanding and maintaining their access).
  3. He looks for valuable assets. Once identified, he collects, packages, and prepares data for exfiltration outside of the organization.
  4. He often reduces the stolen data size to hide it and bypass security controls.
  5. Data is exfiltrated (through a stolen email account or other means).

- Defensive measures:

  1. Prevent attacker access (using MFA...).
  2. Monitor network activity to identify suspicious activity (like multiple logins from outside the network...).
  3. Protect assets using asset inventories and security controls.
  4. Detect and stop exfiltration. It can be detected via network monitoring (SIEM tools can detect and alert). There're many ways to stop I (like blocking IP addresses using firewall rules). 

Resources:

- [Network traffic (MITRE ATT&CK)](https://attack.mitre.org/datasources/DS0029/)
- [Data exfiltration techniques (MITRE ATT&CK)](https://attack.mitre.org/tactics/TA0010/)

**Ports**: Non-physical locations on a computer that organizes data transmission between devices on a network.

**Packet**: Basic unit of information that travels from one device to another within a network. When data is sent, it's divided into packets, and some delivery information is added to each one. Components:

- **Header**: Information for routing the packet to its destination (network protocol, port used, source and destination IP address, packet type, packet length, packet id...). It varies from one protocol to another.
- **Payload**: Actual data to be delivered.
- **Footer** (or trailer): Signifies the end of the packet. Some protocols use footer (Ethernet use it for error-checking information) while other don't.

**Network protocol analyzer** (packet sniffer): It captures and analyzes data traffic within a network. It can be used to analyze network communications manually in detail, to collect network statistics (bandwidth, speed...), to troubleshoot network performance issues (slowdowns...), or to capture packets containing sensitive data (by malicious hackers). Used to inspect packets for IoC. We can generate a P-cap and then analyze the captured traffic to identify unusual activity on a network.

- __Tools__: tcpdump (CLI), Wireshark (GUI), TShark...

- **P-cap** (Packet capture): File containing data packets intercepted from an interface or network. It can be viewed and analysed using a sniffer. Useful in incident investigation for knowing network interactions and what exactly happened. P-cap files come in many formats depending on the packet capture library used:

  - __Libpcap__: Packet capture library for Unix-like systems (Linux, MacOS...). Used by tcpdmp by default.
  - __WinPcap__: Open-source packet capture library for Windows. Older file format not predominantly used.
  - __Npcap__: Library for Windows used by Nmap (port scanning tool).
  - __PCAPng__: Modern file format that can simultaneously capture packets and store data.

- **NIC** (Network Interface Card): Hardware that connects computers to a network (like a router). It receives and transmit network traffic. By default, it only listen to network traffic addressed to him. It can be configured to capture all visible network traffic (promiscuous or monitoring mode).

- Sniffers collect packets via a NIC configured to promiscuous mode and positioned in an appropriate network segment with access to all traffic between different hosts. Network traffic is collected in raw binary format, but then displayed in a human-readable format.

Resource: [Packet crafting (Infosec)](https://www.infosecinstitute.com/resources/hacking/packet-crafting-a-serious-crime/)

Network evidence like packet captures may need to be analysed to identify IoC. Filtering network traffic using packet sniffers to gather relevant information is an essential skill. Example: A network analyzer tool can be used to filter the packet capture to sort packets in order to identify an event associated with data exfiltration (like large amount of data leaving a database).

**TCP/IP model**: Framework used to visualize how data is organized and transmitted across a network. It's made of 4 layers: Application, Transport, Internet, and Network access.

- **Internet layer**: It accepts and delivers packets for the network. The Internet Protocol (IP) operates here.

**IP** (Internet Protocol): Set of standards used for routing and addressing data packets as they travel between devices on a network. Foundation of all Internet communications. It uses the information in headers to makes sure packets reach their destinations. There're 2 versions: IPv4 (most widely used) and IPv6 (larger address space), each one with a different type of header.

**IPv4 header**: Contains 13 fields:

- __Version__: IP version used (IPv4 or IPv6).
- __IHL__ (Internet Header Length): Length of the header + any options.
- __ToS__ (Type of Service): Information about packet priority for delivery.
- __Total length__: Length of the entire packet.
- __Identification__: Fragment unique identifier (big packets are broken into smaller packets, transmitted, and reassembled at destination). Necessary for reassembling.
- __Flags__: Information about fragmentation (was the original packet was fragmented? Are there more packets in transit?...).
- __Fragment offset__: Used to identify the correct sequence of fragments.
- __TTL__ (Time To Live): How long a packet can live before it's discarded. This prevents packets from being forwarded by routers indefinitely.
- __Protocol__: Protocol used.
- __Header checksum__: Value used for error-checking the header.
- __Source address__
- __Destination address__
- __Options__: Optional field. Commonly used for network troubleshooting and security.

**IPv6 header**: Contains 8 fields:

- __Version__
- __Traffic class__: Similar to ToS. Information about packet priority for delivery.
- __Flow label__: It identifies the packets of a flow (sequence of packets sent from a specific source).
- __Payload length__: Length of the data portion of the packet.
- __Next header__: Type of header that follows the IPv6 header (such as TCP).
- __Hop limit__: Similar to TTL. How long a packet can live before it's discarded. This prevents packets from being forwarded by routers indefinitely.
- __Source address__.
- __Destination address__.

**Wireshark**: Open-source network protocol analyzer that uses a GUI. It provides display filters (filter by specific information: protocol, IP addresses, ports...).

- __Comparison__ (`==`, `!=`, `<`, `>`, `<=`, `>=`) and __boolean__ operators (`and`, `or`...) can be used to create complex display filters.
- `contains` operator can be used to filter packets containing an exact match of a string of text.
- `matches` operator can be used to filter packets based on a specified regular expression (regex) (sequence of characters that form a pattern).
- The __filter toolbar__ can be used to apply filters to a packet capture.
- __Filter for protocol__: Display packets containing a certain protocol just by entering the protocol name in the filter toolbar (`dns`, `http`, `ftp`, `ssh`, `arp`, `telnet`, `icmp`...). Different colors are used to represent protocols. This is customizable.
- __Filter for IP address__: Display packets with a certain IP address (`ip.addr == 172.21.224.8`), source IP address (`ip.src == 10.10.10.10`), or destination IP address (`ip.dst == 4.4.4.4`). 
- __Filter for MAC address__: Display packets with a certain MAC address (unique alphanumeric identifier assigned to each physical device on a network) (`eth.addr == 00:70:f4:23:18:c4`).
- __Filter for ports__: Display packets based on port numbers. Useful for isolating specific types of traffic (example: DNS traffic uses TCP or UDP port 53) (`udp.port == 53`) (`tcp.port == 25`).
- __Follow streams__: Filter for packets specific to a protocol and view streams (stream, or converstion, is the exchange of data between devices using a protocol). Wireshark reassembles the data transferred in the stream to make it more readable. Useful for understanding the details of a conversation (example: view the content of the exchanged request and response messages in a HTTP conversation).
- [Wireshark officia user guide](https://www.wireshark.org/docs/wsug_html/).










### Incident investigation and response

### Network traffic and logs using IDS and SIEM tools


## Python automation



## Cybersecurity job

