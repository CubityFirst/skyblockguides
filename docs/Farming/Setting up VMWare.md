As of recent updates, Broadcom has made the professional version of VMWare workstation available for free, however, you need to create an account and download it from their site.

You can find the download [here](https://support.broadcom.com/group/ecx/productdownloads?subfamily=VMware%20Workstation%20Pro).

---

A few things to note ; 

- Download [VMWare Workstation Pro](https://support.broadcom.com/group/ecx/productdownloads?subfamily=VMware%20Workstation%20Pro)
- Download a [Windows 11 ISO](https://www.microsoft.com/software-download/windows11)
### Things to Note

1. Make sure to install VMWare Tools, this will allow the window to resize and will increase performance.
2. If you're assigning multiple cores, make sure to assign multiple cores per socket, instead of multiple sockets.
3. If it complains about no EFI, turn off the VM, go to settings, advanced and turn Firmware from EFI to BIOS. This will fix this issue. You may need to delete TPM.