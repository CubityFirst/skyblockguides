---
sidebar_position: 1
---
:::danger[This is a work in progress document]
Please be aware, I'm still actively writing this document. Please let me know if there's any mistakes that you find, or issues, or other related problems.
:::

## Why farm in a VM?

Playing inside of a VM has one major benefit. You can bind additional HID periphals from outside of the VM to the VM exclusively. This allows you to input on the game seperately to any other application on your computer, allowing you to play multiple games at once, navigate around your computer, or use your computer for more than literally just farming.

As of recent updates, Broadcom has made the professional version of VMWare workstation available for free, however, you need to create an account and download it from their site.
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

![ISO.png](./assets/ISO.png)

9. Press Next until it asks you for a password.
10. Enter a password that you will remember. This is required for the VM to be created.
11. Choose a disk size. (64GB is fine. Changing this to a single file will slightly help performance.)
12. Press Next  / Complete this creation process.
13. Turn the VM off under `VM` > `Power` > `Shut Down Guest`
![RemoveTPM.png](./assets/TPMBIOS.png)
14. Start the VM. 

:::warning[Mouse Stuck?]
If your mouse is stuck inside of the Window, you can press `Ctrl + Alt` to release it.
:::

15. Click next, and click the button that says `I don't have a product key`.
16. Select `Windows 11 Pro`
17. Before you press Next, press `Shift + F10`. This will open the Command Prompt.
18. Type `regedit`
19. Navigate to `HKEY_LOCAL_MACHINE\SYSTEM\Setup`
20. Right click the `Setup` folder and create a new `Key`.
21. Rename this Key on the left hand side `LabConfig`.
22. Right click in the blank space in the right, and create a new `DWORD (32-bit) Value` called `BypassTPMCheck`
23. Double click `BypassTPMCheck`, and set it to `1`, and click `OK`
24. Right click in the blank space in the right, and create a new `DWORD (32-bit) Value` called `BypassSecureBootCheck`
25. Double click `BypassSecureBootCheck`, and set it to `1`, and click `OK`

:::info[Double check!]

If these entries are not correct, Windows will complain about not being compatible with this device.
![RegistryKeys.png](./assets/RegistryKeys.png)
:::
27. Close Regedit, and Command Prompt, and click `Next`.
28. Accept the EULA & Click `Customised: Install Windows only (advanced)`
29. Click `Next`.

Windows will now install, and restart itself! Congratulations!

### Setting up Windows

You should be able to progress through the Windows installation as you would with any normal device. Please select the appropriate keyboard layout as you would, name your device,

If you want to avoid making a Microsoft account, you can follow the below steps.

![DomainAccount.png](./assets/DomainAccount.png)

Once this is done, you can choose the name of your account, password, security questions, and privacy settings.

Windows will now restart... *again*.
### Installing VMWare Tools

VMWare Tools is a suite of additional tweaks and modifications that fix the performance characteristics, and other quirks of a virtual machine.

On the bottom of your VM, you should see a yellow bar prompting you to install VMWare Tools. Press `Install Tools`, and a Drive should appear in your Windows install. Navigate to `D:\` and run `setup64.exe`.  

![VMWareToolsBanner.png](./assets/VMWareToolsBanner.png)

![VMWareToolsDrive.png](./assets/VMWareToolsDrive.png)

Accept the Windows UAC prompt, and press `Next` until you get to the end of the installer and press `Yes` to reboot. 

## What now?

You have a virtual machine for whatever you want to use it for. If you want to install Minecraft, or other mods. I recommend that you read [How to Install Mods](./InstallingMods).

If you want to pass a Keyboard & Mouse through to the VM directly, you can do that by going to `VM` -> `Removeable Devices` -> `TheDeviceYouWant` -> `Connect (Disconnect From Host)`. 


---

## Things to keep in mind

1. Make sure to install VMWare Tools, this will allow the window to resize and will increase performance dramatically.
2. If you're assigning multiple cores, make sure to assign multiple cores per socket, instead of multiple sockets.