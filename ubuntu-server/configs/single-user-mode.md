# Single User Mode
The majority of Linux distros allow admins to access the single-user mode when there are some technical problems in the system. This mode boots into minimal environment where only essential services are running. However, this could be a serious problem when users with malicious intent get physical access to the system. It can be done by accessing grub console and editing the bootloader.

## Accessing Single User Mode
As soon as the boot process starts press **ESC** to bring up GRUB boot prompt. In this stage press E to edit the first boot option where you can edit the Linux kernel.
Find a kernal line that starts with "*linux*". Then at the end of that kernal line add either (systemd.unit=rescue.target) or (init=/bin/bash), both of commands will take you into single user mode.
> [!Note]
> Sometimes it may not boot up properly when going into Single User Mode, if it does so add "nomodeset" at the end of kernel line where you added previous instructions instructions.
