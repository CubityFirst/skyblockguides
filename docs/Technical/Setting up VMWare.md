:::danger[This is a work in progress document]
Please be aware, I'm still actively writing this document. Please let me know if there's any mistakes that you find, or issues, or other related problems.
:::

## Why farm in a VM?

Playing inside of a VM has one major benefit. You can bind additional HID periphals from outside of the VM to the VM exclusively. This allows you to input on the game seperately to any other application on your computer, allowing you to play multiple games at once, navigate around your computer, or use your computer for more than literally just farming.

As of recent updates, Broadcom has made the professional version of VMWare workstation available for free, however, you need to create an account and download it from their site.

You can find the download [here](https://support.broadcom.com/group/ecx/productdownloads?subfamily=VMware%20Workstation%20Pro).

## Requirements

- A modern computer that is capable of Virtualization.
	- If your computer is older, it might not support the required technologies to use this. You can check [here](https://ark.intel.com/content/www/us/en/ark.html) for Intel chips, and [here](https://www.amd.com/en/products/specifications/processors.html) for AMD chips.


---

## Steps

1. Download [VMWare Workstation Pro](https://support.broadcom.com/group/ecx/productdownloads?subfamily=VMware%20Workstation%20Pro) from Broadcom. You will need to make an account.
2. Download a [Windows 11 ISO](https://www.microsoft.com/software-download/windows11) from Microsoft. (Under the header "Download Windows 11 Disk Image (ISO) for x64 devices")
3. Run the installer for VMWare Workstation Pro
4. Skip through & install the application.
5. Open VMWare Workstation Pro
6. Select `Use VMWare Workstation 17 for Personal Use` and press `Continue`.

You should now see a screen that looks like this.

![VMWare.png](./assets/blankVMWare.png)

7. Press `Create a New Virtual Machine` and confirm with `Next`.
8. Select the Windows ISO that you downloaded in step 2.

![ISO.png](assets/ISO.png)

9. Press Next until it asks you for a password.
10. Enter a password that you will remember. This is required for the VM to be created.
11. Choose a disk size. (64GB is fine. Changing this to a single file will slightly help performance.)
12. Press Next  / Complete this creation process.
13. Turn the VM off under `VM` > `Power` > `Shut Down Guest`
![RemoveTPM.png](./assets/TPMBIOS.png)
14. Start the VM. Windows will now install.
15. Click next, and click the button that says `I don't have a product key`.
16. Select `Windows 11 Pro`
17. Before you press Next, 





---

### Things to keep in mind

1. Make sure to install VMWare Tools, this will allow the window to resize and will increase performance dramatically.
2. If you're assigning multiple cores, make sure to assign multiple cores per socket, instead of multiple sockets.
3. If it complains about no EFI, turn off the VM, go to settings, advanced and turn Firmware from EFI to BIOS. This will fix this issue. You may need to delete TPM.