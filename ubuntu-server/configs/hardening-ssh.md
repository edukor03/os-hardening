# Hardening the SSH Connection
The OpenSSH server reads a configuration file when it is started. Usually, this file is */etc/ssh/sshd_config*, but the location can be changed.

**Objectives:**
* Install OpenSSH server
* Disable root login
* Enable password authentication
* Disable X11 forwarding
* Set idle interval and the certain number of users allowed at the same time

**📁Files accessed:**
* */etc/ssh/sshd_config*
