# Extra Configurations to Secure Ubuntu
In this file we will look at some smaller changes that can be made to make the Ubuntu system, or any Linux distro, more secure.

**Objectives:**
* Disable Automounting
* Local warning login banner
* Disable IPv6
* Enable Audit Service

**📁Files accessed:**
* 

## Disable Automounting**
**Autofs** allows the automatic mounting of devices, typically including CD/DVDs and USB drives. With automounting enabled, anyone with physical access could attach a USB drive or disc and have its contents available in the system even if they lacked permission to mount it themselves. **autofs** should be removed or disabled.
To verify if the **autofs** is not enabled, run the following command:

> systemctl is-enabled autofs

It should say: "disabled"
or run the following command to verify that autofs is not installed

> dpkg -s autofs

In my case its not installed.


