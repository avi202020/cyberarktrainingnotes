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



# Business Risk – Targeted Attacks and the "attack life-cycle"

# Business Risk – Ransomware The CyberArk Solutions

# CyberArk Blueprint for PAS Success

# Introduction to DevOps and Secrets Management

#  CyberArk and the CyberArk Solution