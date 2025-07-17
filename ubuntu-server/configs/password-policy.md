# Password Policy Configuration
Password policies exist to ensure that a strong password is set for users and as a Linux user, you should be mindful to enforce these policies to make it difficult for breaches to occur. You surely do not want users configuring weak or guessable passwords which can be brute-forced by hackers in a matter of seconds. In this file I investigate how to enforce password policies in a Linux environment.

**Objectives:**
* Install libpam-pwquality package.
* Configure password complexity requirements.
* Configure password reuse limit.
* Make sure password hashing is enabled.
* Ensure minimum days between password changes are configured.

**📁Files accessed:**
* */etc/security/pwquality.conf*
* */etc/pam.d/common-password*
* */etc/login.defs*

## Make sure Password Complexity Requirements are configured
First of all before we can configure complexity of the password we need to install **pam** package by using the following command:

> sudo apt install libpam-pwquality

The **pam_pwquality.so** module is used for strength checking for passwords. Once the user types the password it will check its strength against system dictionary and a set of rules that have been defined by system administrator or user. The module itself is based on **pam_cracklib** module and its backwards compatible with its options.
To configure the set of rules for the strength checking for password, navigate to */etc/security/pwquality.conf*.
