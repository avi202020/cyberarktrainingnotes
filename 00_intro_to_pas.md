# Introduction to CyberArk Privileged Access Security

https://training.cyberark.com/user/consume/course_pathway/91cae047-31e0-301c-a982-bf80725f7094/652/65454f6d-886f-3562-add4-b4dad777bc4f?complete=0&tab=overview

Great, more ServiceRocket training.

# Introduction to User Accounts and Privileged Account Security

## user accounts

* standard user account
    * combines username and privileges
    * credential types:
        * username and password combination
        * ssh key (used in sso, and automated processes)
* super user:
    * special user account used for administration
    * capable of making unrestricted, potentially adverse, system-wide changes.
    * example usernames:
        * root, administrator, admin, supervisor, sa (MSSQL), sys (oracle), enable (cisco) <-- wat.
    * username may not be the sole identifier of the user account type.
        * *nix: root account has a user identifier of 0
        * RBAC: (Windows, etc)
            * anyone who has capabilities of a super user, is a super user.
* application account:
    * special user accounts for a computer application or group of applications
    * applications need to automatically connect to various systems, DBs, networks and other applications.
* service account:
    * a special user account htat an application or service uses to interact with the OS.
    * services use the service account to log on and make changes to the OS or config.


## privileged account security:
* what is a privileged account?
    * any account that can access important or sensitive data, PHI, CC#, SSN, IP.
    * types:
        * elevated personal user accounts
            * define
                * operational access
                * unrestricted access
            * type of accounts:
                * it personnel accounts
                * executive accounts
                * SaaS administrators
                * Local admin account
            * used by:
                * IT satff
                * executives
                * any employee
            * used for:
                * privileged operations
                * access to sensitive data
                * managing web-based apps
        * shared privileged accounts
            * define:
                * Windows administrator, *nix root, corporate media accounts, registrar, ARIN, etc.
                    * business critical applications
                    * sensitive data
                    * social media
            * type of accounts:
                * admin/root/cisco enable/oracle sys/mssql sa/local admin
            * used by:
                * applications/scripts
                * windows services
                * scheduled tasks
                * batch jobs, scripts, other
                * developers
            * used for:
                * privleged operations
                * disaster recovery
                * emergency
                * administration
                * access to sensitive data
        * Application accounts:
            * define:
                * application accounts, service accounts
                    * communicate and share data
            * type of accounts
                * service accounts
                * hard coded / embedded app IDs
            * used by:
                * applications/scripts
                * windows services
                * scheduled tasks
                * batch jobs, scripts, other
                * developers
            * used for:
                * Online DB access
                * batch processing
                * inter-application communication

## what can a privileged account be used for?
    * access sensitive data
        * good: accountant ERP system for salary, people who access intellectual property
        * evil: data can leak causing financial and reputational data
    * change system configurations
        * good: starting or stopping services, or connecting endpoints to authorized mapped drives.
        * evil: connect to c2 servers, capture user activity
    * install software / apply updates
        * good: install a/v, or applications
        * evil: malware install
    * access and change accounts
        * good: change passwords, enforce organizational privilege policies
        * evil: lock true users out of machines

## privileged account in the organization:
    * privileged accounts exist everywhere
        * not only IT accounts
        * broaden your horizon: social media, employees all have accounts
        * count of privileged accounts are three times that of employees
        * personally, everyone has privileged accounts: social media, login to bank.
    * access a network segment, or changes firewall rules, access to DC, or dump DB data
        * unprotected, unmonitored, privileged accounts are the way to go
    * mandiant:
        * go after privileged accounts
        * 100% of breaches involved stolen creds

    
# Business Risk – Insider Threat

## objectives
* what is an insider threat?
* are they always malicious?
* what are they after?
* why do insiders turn rogue?
* how do insiders cause damage?

## who is the insider threat?

* surveys show that most insider threats occur by inadvertant employee behavior
* there are four malicious insiders as follows

### exploited insider:
* example:
  * 225000 residents in western ukraine
    * attackers exploited legitimate users
* common targets are high value employees with spearphishing campaigns
  * it admins, execs, helpdesk
  * can pivot throughout organization and establish a foothold

### malicious insider:
* example:
  * sage employee used an internal login to gain unauthed access to information
* just 26% of incidents
  * most difficult to detect
  * most costly
  * knowledge of and access to sensitive info
  * can often legitimately bypass security controls

### unintentional insiders:
* phishing request for w2 forms
* no malicious intent but they can unintentionally put data and systems at risk
* 

### external insider:
* example:
  * Healthcare company example:
  * a third party that has high levels of access to the system
* at least 60% of orgs allow remote access to internal networks from third party vendors
  * these users can turn into bad actors: exploited insiders, unintentional insiders, malicious insiders...
    * But they aren't managed by your organization

## why do insiders turn rogue?
* you can identify high risk users prior to an attack
  * Outside influence: their actions are coerced by a crime ring or nation-state.
  * Anger: they feel as if their employer or manager has done somethign wrong.
  * Hacktivism: they are motificated by political or religious beliefs.
  * Financial: they have a large debt.

## how malicious insiders cause damage:
* they do not need to compromise the perimeter
* they utilize their existing access to escalate privleges, perform recon, move laterally, then either disrupt business or exfiltrate data.

## reducing risk & quickly detecting insider threats
* utilize these five recommendations:
  * practice least privilege:
    * reduce the attack surfaec to limit insider threat by restricting standard user privileges based on role.
  * secure privileged accounts
    * store privileged account credentials in a secure, central repo that supports strong access control, multi-factor auth and full availability.  Rotate creds on a regular basis.
  * apply segregation of duties
    * segregate admin duties based on privileged user specific roles.
  * educate users:
    * train users to be aware of phishing threats and how to identify fraudulent emails.
  * monitor & audit usage
    * monitor an analyze privileged user and account behavior to learn what's normal so you can more easily identify abnormalities that may indicate an attack or breach is in process.



# Business Risk – Targeted Attacks and the attack life-cycle"

## agenda
* overview of targeted attacks
* actors & tactics
* cyber attack lifecycle

## what are targeted attacks

* attack can be considered targeted:
  * attackers focus on a group of orgs, an org, or specific employees
  * objective is infiltrate target network, to exfiltrate data or disrupt business
  * maintain persistence
  * considerable effort to make sure that their goals are acheived

### actors & tactics

* key findings from 2017 VZ data breach investigation
  * 75% of breaches were carried out by outsiders that infilitrated perimeter
  * 81$ of breaches leveraged either stolen and/or weak passwords

### the cyber attack lifecycle

* Internal team at cyberark studies attacks and have derived a general attack pattern

#### external recon
* collect enough intelligence to successfully attack target org
* attack surface: total sum of vulns in a network that are accessible to the internet
  * unpatched systems
  * ip address ranges
  * open ports
  * target endpoints

#### breach
* methods:
  * spear-phishing attack
    * electronic communication scam to target specific people
      * may install malware
      * may end up in data exfilitration
  * zero-day exploits
    * any flaw that is unknown to the vendor
  * customized malware
    * malware customized to get around various security technologies
  * drive-by-download
    * infects a computer by having a user visit a web site that is running malicious code. 
  * social engineering
    * manipulating people to give up confidential info or access to the network.

#### internal recon
* using privileges that attacker obtained
* purpose: id accounst that can get them closer to their goal
  * checks which assets he can access
  * checks who the privileged users are
  * checks what privileges they have
  * goal is to move laterally

#### lateral movement
* goal: take control other OS instances, includign DCs
* move around the network
  * mapping internal systems
    * discovery actions
  * harvesting creds

#### domain compromised
* one priv esc occurs, continue to gather information and/or implant software, etc.

#### exfiltration / end game
* it's possible that if the attacker is seeking PII/PHI/IP, etc, exfil of data is possible

#### privilege is at the center of the attack

![](2020-05-13-09-21-09.png)

* attackers are resident over average for 146 days
* remember path of life cycle
  * external --> internal
  * enum/recon
  * priv esc
  * enum/recon
  * priv esc --> Golden ticket attack for instance
  * result: disrupt business/data exfil


## recommendations

### implement endpoint protection
* remove local admin rights from standard users
* control applications to minimize malware infection risks
* patch systems to remediate known vulns
* encourage usres to be suspicious of phishing

### monitor and detect privileged threat
* examine privileged session activity to detect insider threats
* analyze user and account behavior to detect anomalous activity
* 

### secure and control credentials
* use MFA
* change admin passwords frequently
* require unique local admin passwords on each system
* protectively secure and monitor the use of high-value accounts
* segement the network to limit access to sensitive IT systems
* isolate and restrict access to critical systems


# Business Risk – Ransomware The CyberArk Solutions

* ransomware makes up 40% of attacks.
* 1989 is first recorded ransomware attack

## agenda
* ransomware attack landscope
* how ransomeware works
* what makes randomware successful
* app control
* recommendations

## what is ransomware
* a type of malware: that focuses on revealing data publicly, or encrypting data to make it unavailable.

## ransomware can impact orgs of all types
* attack impact
* $325 million was paid in 2015
* estimation that cyber incidents will result in $6 trillion by 2021.

## ransomware in action

### how does a machine get infected
* malicious email
  * sender email address
  * link dst
* advertising service compromise
* once infected, the ransomware may spread
  * it may wait for a specific application to run
  * it may wait for a time

### retrieve an encryption key
* connection may be made to external resource to obtain encryption key
  * 20% of ransomware would stop immediately if this connection was blocked
  * 70% of ransomeware would use a default key that was embedded in the ransomware itself

### build a file inventory
* scans for files local on the machine or on shared drives

### attmpts to propagate
* scans for connected machines
* scans for user creds

### spread through network
* often uses captured creds to install itself on more machines

### encrypt, notify, repeat
* it will utilize the file inventory to encrypt files

## what makes ransomware so successful
* polymorphic malware helps attacker evade detection
  * evading traditional AV.
* ransomware doesn't need admin creds
  * it mimics a user.

## where can you break the attack chain?
* protect the perimeter
  * difficult to catch as the files are polymorphic
* block the conversation to the key server 
  * damage still possible
* protection at file level
  * which proved to be most effective in lab tests

## file protection using application control
* protecting at file level
  * application control
    * whitelist
      * known, trusted, and good
      * for servers that run the same application over time
      * impractical for endpoints (this is argubly WRONG!)
    * blacklist
      * known, not trusted, and malicious
      * often not complete
    * greylist (99.97% effective)
      * specify policies for unknown applications
        * ex: invoke restricted mode
          * no internet access, etc
          * no access to network shares
          * restrict file rights

## recommendations
* whitelist apps on servers
* restrict permissions for greylisted applications
* remove local admin rights from standard users
  * blocks most malware from running
  * 10% of ransomware to fail immediately
* follow general best practices for AV
* data backups

# CyberArk Blueprint for PAM Success

## agenda
* review current challenges desigining a PAM program
* learn what cyberark blueprint is and how it was developed.
* Understand hwow the blueprint phased approach helps design a successful PAM program roadmap.
* Learn where to get more info on cyberark blueprint

# Introduction to DevOps and Secrets Management

#  CyberArk and the CyberArk Solution