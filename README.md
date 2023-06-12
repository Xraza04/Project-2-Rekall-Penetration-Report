# Project 2: Rekall Penetration Report

Exploit Vulnerabilities in Rekall Corporation's Web Application, Linux Servers, and Windows Servers
This week, you conducted a penetration test by attacking a fictional organization's web application, Linux servers, and Windows servers. 

**Rekall Corporation: Penetration Test Report**


_Confidentiality Statement_

This document contains confidential and privileged information from Rekall Inc. (henceforth known as Rekall). The information contained in this document is confidential and may constitute inside or non-public information under international, federal, or state laws. Unauthorized forwarding, printing, copying, distribution, or use of such information is strictly prohibited and may be unlawful. If you are not the intended recipient, be aware that any disclosure, copying, or distribution of this document or its parts is prohibited.


_Contact Information_

Company Name: PenDraza Security 

Contact Name: 

Contact Title: Chief Coordination Officer


_Introduction_

In accordance with Rekall policies, our organization conducts external and internal penetration tests of its networks and systems throughout the year. The purpose of this engagement was to assess the networks’ and systems’ security and identify potential security flaws by utilizing industry-accepted testing methodology and best practices.

For the testing, we focused on the following:

> Attempting to determine what system-level vulnerabilities could be discovered and exploited with no prior knowledge of the environment or notification to administrators.

> Attempting to exploit vulnerabilities found and access confidential information that may be stored on systems.

> Documenting and reporting on all findings.

All tests took into consideration the actual business processes implemented by the systems and their potential threats; therefore, the results of this assessment reflect a realistic picture of the actual exposure levels to online hackers. This document contains the results of that assessment.

_Assessment Objective_

The primary goal of this assessment was to provide an analysis of security flaws present in Rekall’s web applications, networks, and systems. This assessment was conducted to identify exploitable vulnerabilities and provide actionable recommendations on how to remediate the vulnerabilities to provide a greater level of security for the environment.

We used our proven vulnerability testing methodology to assess all relevant web applications, networks, and systems in scope. 

Rekall has outlined the following objectives:

_Objective_

> Find and exfiltrate any sensitive information within the domain.

> Escalate privileges.

> Compromise several machines.


**Penetration Testing Methodology**

_Reconnaissance_
 
We begin assessments by checking for any passive (open source) data that may assist the assessors with their tasks. If internal, the assessment team will perform active recon using tools such as Nmap and Bloodhound.

_Identification of Vulnerabilities and Services_

We use custom, private, and public tools such as Metasploit, hashcat, and Nmap to gain perspective of the network security from a hacker’s point of view. These methods provide Rekall with an understanding of the risks that threaten its information, and also the strengths and weaknesses of the current controls protecting those systems. The results were achieved by mapping the network architecture, identifying hosts and services, enumerating network and system-level vulnerabilities, attempting to discover unexpected hosts within the environment, and eliminating false positives that might have arisen from scanning. 

_Vulnerability Exploitation_

Our normal process is to both manually test each identified vulnerability and use automated tools to exploit these issues. Exploitation of a vulnerability is defined as any action we perform that gives us unauthorized access to the system or the sensitive data. 

_Reporting_

Once exploitation is completed and the assessors have completed their objectives, or have done everything possible within the allotted time, the assessment team writes the report, which is the final deliverable to the customer.

**Scope**

Prior to any assessment activities, Rekall and the assessment team will identify targeted systems with a defined range or list of network IP addresses. The assessment team will work directly with the Rekall POC to determine which network ranges are in-scope for the scheduled assessment. 

It is Rekall’s responsibility to ensure that IP addresses identified as in-scope are actually controlled by Rekall and are hosted in Rekall-owned facilities (i.e., are not hosted by an external organization). In-scope and excluded IP addresses and ranges are listed below. 


**Executive Summary of Findings**

_Grading Methodology_

Each finding was classified according to its severity, reflecting the risk each such vulnerability may pose to the business processes implemented by the application, based on the following criteria:

**Critical**:	 Immediate threat to key business processes.

**High**:		 Indirect threat to key business processes/threat to secondary business processes.

**Medium**:	 Indirect or partial threat to business processes. 

**Low**:		 No direct threat exists; vulnerability may be leveraged with other vulnerabilities.

**Informational**:    No threat; however, it is data that may be used in a future attack.

As the following grid shows, each threat is assessed in terms of both its potential impact on the business and the likelihood of exploitation:
![image](https://github.com/pedrazzzaaa/Project2/assets/107894378/3daf1ca2-384a-4c8e-b740-96f169d7916b)

**Summary of Strengths**

While the assessment team was successful in finding several vulnerabilities, the team also recognized several strengths within Rekall’s environment. These positives highlight the effective countermeasures and defenses that successfully prevented, detected, or denied an attack technique or tactic from occurring. 

> Security Awareness

> Resilience to Exploits

> Information Security Obscurity

> Limited Attack Surface


**Summary of Weaknesses**

We successfully found several critical vulnerabilities that should be immediately addressed in order to prevent an adversary from compromising the network. These findings are not specific to a software version but are more general and systemic vulnerabilities.

> Vulnerable to XSS & SQL Injection

> Vulnerable to Local File Inclusion

> Credentials in Source Code 

> Command Injection

> File Spoofing

> Directory Transversal/sensitive data Exposure 

> Open Port

> SLMail server is vulnerable to exploits which allow access to shell 

**Executive Summary**

PenDraza Security was able to find multiple vulnerabilities during the penetration testing of Rekall’s web application along with its Linux/Windows servers. Some of these vulnerabilities are very critical and deserve immediate attention, for they can have a huge impact on the business’s assets and data. This implies that if the critical vulnerabilities are not addressed promptly, they could result in severe consequences for Rekall. These consequences may involve unauthorized access, data breaches, loss of sensitive information, financial loss, reputational damage, or other detrimental effects.
First, we spent time reviewing and testing the web application. This is due to the fact that it receives the most attention and interaction from consumers, as well as being the simplest to obtain. 
Our first findings were discovered on the welcome tab of the website, where we were able to run a script in the Begin by entering your name below! toolbar. This vulnerability is called Cross-Site scripting (XSS), which can be harmful if a malicious script is inputted. This vulnerability can also be found within the, Please leave your comment on our website! section. 
Continuing on the website, it was also discovered that it is additionally vulnerable to, Local File Inclusion (LFI), which could allow malicious files to be uploaded within the VR Planner web page. Along with file uploading, the vulnerability of file spoofing was permitted. This allowed us to disguise or malicious file with a .jpg for it to be acceptable within the Choose your location by uploading a picture section. Our findings continued within the Login.php page of the web application, which allowed us to identify another set of vulnerabilities. An SQL injection attack was executable within the toolbar for login inputs. Along with the Login.php section, we were able to reveal Admin credentials  within the source code of the web page. Alongside SQL Injections came Command injections, which allowed the possibility of submitting a malicious website to gather more information. While remaining on the website, the vulnerability, Directory Transversal, was accomplished through the URL. We were able to navigate to the passwd file of the host machine, which shows all users and if they have passwords.  
Finally, after finding multiple vulnerabilities within the web application, the team at PenDraza Security  decided to do further testing on the company's servers. Within the Linux environment, we were able to run a scan on the company's IP address and locate other IP addresses and open ports on two hosted machines. Pendraza Security was able to discover that port 21/TCP was open and allowed Anonymous FTP login, which allowed us to log in to the FTP server with ease. It was also discovered that the SLMail server was vulnerable to exploits that granted us access to the machine through a shell.
In conclusion, while the penetration testing revealed potential deficiencies that could be exploited to impair the company's operations and assets, Rekall exhibits notable strengths in their security posture. Their proactive Security Awareness initiatives, demonstrated Resilience to Exploits, commitment to Information Security Obscurity, and Limited Attack Surface highlight their dedication to protecting their systems and data. By leveraging these strengths and addressing any identified vulnerabilities, Rekall can fortify their security measures, safeguard their operations, and maintain the integrity of their assets. 

**Summary Vulnerability Overview**

![image](https://github.com/pedrazzzaaa/Project2/assets/107894378/efce3d2f-ff55-461e-90be-98b454092bf3)

The following summary tables represent an overview of the assessment findings for this penetration test:

![image](https://github.com/pedrazzzaaa/Project2/assets/107894378/d6582ce1-7240-46fb-9b0f-c9a36aa4c0b3)


**Vulnerability Findings**


![image](https://github.com/pedrazzzaaa/Project2/assets/107894378/0c53d612-648f-47e2-a34e-72e4d8624c62)

![image](https://github.com/pedrazzzaaa/Project2/assets/107894378/45f09794-b657-4b63-9358-a3cfe968654c)

![image](https://github.com/pedrazzzaaa/Project2/assets/107894378/2c211276-d44c-4ba1-a039-5fc150e9ad4a)

![image](https://github.com/pedrazzzaaa/Project2/assets/107894378/ebd1f82d-9364-40e8-8960-fd96c889542a)

![image](https://github.com/pedrazzzaaa/Project2/assets/107894378/6913a3de-25dc-495a-8ac2-4a73bb276972)

![image](https://github.com/pedrazzzaaa/Project2/assets/107894378/206743bd-403a-498a-9f84-54657923df3d)

![image](https://github.com/pedrazzzaaa/Project2/assets/107894378/3c44676f-cac2-48ee-bb07-6e7c078aef23)

![image](https://github.com/pedrazzzaaa/Project2/assets/107894378/beaca044-2f5d-4a80-a563-3d766ade86f2)

![image](https://github.com/pedrazzzaaa/Project2/assets/107894378/416cd313-2d47-4c5e-8d8e-abcc21580567)

![image](https://github.com/pedrazzzaaa/Project2/assets/107894378/f3f3a1b6-0c17-4ce9-91da-43ee2846a7b0)

![image](https://github.com/pedrazzzaaa/Project2/assets/107894378/297cd48c-d998-4122-9b11-a5719ea5747e)

![image](https://github.com/pedrazzzaaa/Project2/assets/107894378/9f30cf12-91ec-4ced-b798-0d136698b8e3)

![image](https://github.com/pedrazzzaaa/Project2/assets/107894378/f7a63f71-81eb-44d2-9094-8ae711c86795)

![image](https://github.com/pedrazzzaaa/Project2/assets/107894378/ce7a138e-ec5e-4e8e-b6db-01b60406362f)

![image](https://github.com/pedrazzzaaa/Project2/assets/107894378/7cd0a073-a08b-4bce-94c2-d4dca0729426)

![image](https://github.com/pedrazzzaaa/Project2/assets/107894378/174b10b0-374b-4d93-8839-4db513928bf2)

![image](https://github.com/pedrazzzaaa/Project2/assets/107894378/99c9adde-9eb7-437a-abcd-e003604b472b)

![image](https://github.com/pedrazzzaaa/Project2/assets/107894378/75642490-c424-431c-9615-280bdcc9b034)

