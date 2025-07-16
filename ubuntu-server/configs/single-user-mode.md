# Single User Mode
The majority of Linux distros allow admins to access the single-user mode when there are some technical problems in the system. This mode boots into minimal environment where only essential services are running. However, this could be a serious problem when users with malicious intent get physical access to the system. It can be done by accessing grub console and editing the bootloader.

## Accessing Single User Mode
As soon as the boot process starts press **ESC** to bring up GRUB boot prompt. In this stage press E to edit the first boot option where you can edit the Linux kernel.
Find a kernal line that starts with "*linux*". Then at the end of that kernal line add either (systemd.unit=rescue.target) or (init=/bin/bash), both of commands will take you into single user mode.
> [!Note]
> Sometimes it may not boot up properly when going into Single User Mode, if it does so add "nomodeset" at the end of kernel line where you added previous instructions instructions.

![GRUB boot prompt](screenshots/single-user-mode1.png)
![Kernel line edit](screenshots/single-user-mode3.png)

The photo above shows how the "*linux*" line looks like in boot entry. Then press **ctrl + x** or **F10** to boot. It will boot into a recovery/single user mode without asking for any passwords. Now I will show why it could be a serious problem if someone who is not authorised access it. In this example I will change the root password, which can be a way to recover or get access to root user.

![](screenshots/single-user-mode4.png)

> mount -o remount,rw /

Before making changes to the root password we need to remount the root directory into read and write mode. This will allow to perform changes to the root file system. 

> passwd

Before making changes to the root password we need to remount the root directory into read and write mode. This will allow to perform changes to the root file system. 

> exec /sbin/init

Once everything is done we can use the command above, it will boot the system normally which will allow us to log into any users.
The following image shows that the change to the root user password was successful.

![](screenshots/single-user-mode5.png)




