# Introduction to CyberArk Privileged Access Security

Great, more ServiceRocket training.

# Introduction to User Accounts and Privileged Account Security

## basic terminology

### user accounts

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


### privileged account security:
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

* what can a privileged account be used for?
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
* privileged account in the organization:
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
    * 

# Business Risk – Targeted Attacks and the "attack life-cycle"

# Business Risk – Ransomware The CyberArk Solutions

# CyberArk Blueprint for PAS Success

# Introduction to DevOps and Secrets Management

#  CyberArk and the CyberArk Solution