# Install macOS on VMware Workstation
### Step 1. Install Unlocker427
###### This is an add-on to VMware Workstation. To get the installer for Workstation and instructions to install it, head [here](https://github.com/WillUHD/InstallWorkstation/). 
Unlocker will unlock the macOS feature for Workstation. 
1. Download Unlocker 4.2.7 [here](https://github.com/DrDonk/unlocker/releases/tag/v4.2.7).
2. Extract "unlocker427.zip" in your Downloads folder
3. Go to "windows" folder and open "unlock.exe"
4. If Windows Defender pops up, hit "Learn More" and click "Open This Unsafe Program" to open it.
5. Once opened, grant it administrator privileges to let it modify the VMware files. When it has finished, close the program. You have successfully unlocked VMware for Workstation! 
### Step 2. Download a macOS ISO
You need a macOS ISO in order to install the system. You can download ISOs from Apple or 3rd party sources. 
### Step 3. Create the Mac VM
1. When you open Workstation, go ahead and create a new virtual machine.

![image](https://github.com/WillUHD/macOSonWorkstation/assets/134638202/c22d2362-01c9-4e1b-8aca-2fd6e3e72ac6)

2. Click "Typical".

![image](https://github.com/WillUHD/macOSonWorkstation/assets/134638202/79932a56-36bb-4a4c-80f1-e919a2a1a632)

3. Click "Installer Disk Image File (ISO)" and head to the directory of your macOS ISO.

![image](https://github.com/WillUHD/macOSonWorkstation/assets/134638202/0ebc8af9-1e22-4cb7-9396-cdc140fc1281)

4. Select Apple Mac OS X and select your operating system. You should have the option to select Mac OS X once Unlocker427 has successfully installed. If not, you may want to install it again.

![image](https://github.com/WillUHD/macOSonWorkstation/assets/134638202/416f8157-ee75-426e-be27-63352b5fc9fe)

5. Specify your disk space. I'll use 96GB.

![image](https://github.com/WillUHD/macOSonWorkstation/assets/134638202/9da35813-04d1-424b-a758-9d7c8ab6514b)

6. You can finish here, but I'll customize my hardware to 12 cores and 12GB RAM.

![image](https://github.com/WillUHD/macOSonWorkstation/assets/134638202/60099bbe-4216-4bd4-a392-29ee48b0a48c)

7. Go to your VM folder (that you've created) and go to the .VMX file. Open it using Notpad (or any other text editing software).

![Screenshot 2024-06-09 142745](https://github.com/WillUHD/macOSonWorkstation/assets/134638202/4a20b74d-bc6f-4937-ba4a-f4d4431fa9df)

8. Now, enter the configurations for macOS.

For Intel CPUs
```vmx-for-intel
smc.version = "0"
smbios.reflectHost = "TRUE"
hw.model = "MacBookPro14,3"
```
For AMD CPUs
```vmx-for-amd
smc.version = "0"
cpuid.0.eax = "0000:0000:0000:0000:0000:0000:0000:1011"
cpuid.0.ebx = "0111:0101:0110:1110:0110:0101:0100:0111"
cpuid.0.ecx = "0110:1100:0110:0101:0111:0100:0110:1110"
cpuid.0.edx = "0100:1001:0110:0101:0110:1110:0110:1001"
cpuid.1.eax = "0000:0000:0000:0001:0000:0110:0111:0001"
cpuid.1.ebx = "0000:0010:0000:0001:0000:1000:0000:0000"
cpuid.1.ecx = "1000:0010:1001:1000:0010:0010:0000:0011"
cpuid.1.edx = "0000:0111:1000:1011:1111:1011:1111:1111"
smbios.reflectHost = "TRUE"
hw.model = "MacBookPro14,3"
```

![image](https://github.com/WillUHD/macOSonWorkstation/assets/134638202/00a3c9cf-693d-40b2-bd59-55f6cf363537)

9. Close Notepad and run the virtual machine. MacOS should boot up as regularly.

![image](https://github.com/WillUHD/macOSonWorkstation/assets/134638202/45dad3b6-0cd5-40ff-aa97-800a33f54349)

10.Choose your language and wait for macOS Recovery to run.

![image](https://github.com/WillUHD/macOSonWorkstation/assets/134638202/1c0f34f7-ba99-4aa0-8837-008a85b3a2ab)

11. When macOS Recovery runs, go to Disk Utility, select the VMware SATA drive, and erase it. While erasing, select AFPS file system with GUID partition map. 

![image](https://github.com/WillUHD/macOSonWorkstation/assets/134638202/d0a186f4-25a5-4e86-aaa9-aef56b737451)

(Disk Utility is at the bottom of the Recovery Menu)

![image](https://github.com/WillUHD/macOSonWorkstation/assets/134638202/d924e0d5-8d18-4e57-b6a5-894b4fed3c7d)

(Select VMware Virtual SATA drive, which is at the top of the Disk Utility window)

![image](https://github.com/WillUHD/macOSonWorkstation/assets/134638202/6d77b384-9943-48bc-88a1-3f7951eeabd5)

(Select "Erase", which is at the top center bar of the GUI)

12. Close Disk Utility (by pressing the red close button at the top left), and enter Install macOS.

![image](https://github.com/WillUHD/macOSonWorkstation/assets/134638202/a5bf5310-f761-4087-9c55-4e9cad8977ed)

13. Follow the directions to install (accept the agreements, etc). Your VM should restart. Wait for around 30 minutes for this to complete, and customize your Mac. 

![image](https://github.com/WillUHD/macOSonWorkstation/assets/134638202/2e2f4b6a-e27f-4923-bf68-5ec0dd41f8f6)

![image](https://github.com/WillUHD/macOSonWorkstation/assets/134638202/f3b7f0d7-ef27-44f1-9f3b-6f124bfc0e17)

(The system should install by itself)

![image](https://github.com/WillUHD/macOSonWorkstation/assets/134638202/0cf9e89b-ebc7-4a70-9499-2612e7740c6f)

![image](https://github.com/WillUHD/macOSonWorkstation/assets/134638202/9f7c665d-7db3-4765-a157-53870a290067)

(Follow the installer guide and create a new user)

### Step 4. Install VMware Tools

1. When you are in your macOS desktop, eject the Install macOS disk (at the top right disk icon, select and right click and choose "Eject")

![Screenshot 2024-06-09 144343](https://github.com/WillUHD/macOSonWorkstation/assets/134638202/581cf268-1a82-420e-8c6b-540b2e97dd17)

2. Go to VM > Install VMware Tools in your VMware Workstation window

![image](https://github.com/WillUHD/macOSonWorkstation/assets/134638202/69b0e746-bf5c-4add-9593-ac2426843be1)

3. Open the installer and go through the installation process. During this process, you may have to go to System Preferences and enable a helper tool.

![image](https://github.com/WillUHD/macOSonWorkstation/assets/134638202/8315c0f1-09f9-4ced-958d-4b550a2adca8)

(Double click the installer)

![image](https://github.com/WillUHD/macOSonWorkstation/assets/134638202/1905d429-9f08-48af-9e04-3a8f2859f69f)

(Enter your computer login passcode)

![image](https://github.com/WillUHD/macOSonWorkstation/assets/134638202/06937392-5387-45f5-8352-9e8c445f2cc6)

(Go to Security Preferences)

![image](https://github.com/WillUHD/macOSonWorkstation/assets/134638202/b629a67b-7323-42e6-a59d-bdaaf692d9bd)

(Enable the tool by opening the lock and entering your login passcode. Click on the lock to open it and enter your passcode.)

![image](https://github.com/WillUHD/macOSonWorkstation/assets/134638202/acdc3131-ac65-4420-b9e6-06043e6356e1)

(Click "Allow" to allow the tool. After you're done, you can close the lock by clicking on it again to prevent further changes from happening.)

4. When the process has finished, it will ask you to restart. Restart your machine.

5. Now you have it, you have fully installed macOS on your Workstation! VMware Tools allows you to resize the window, drag and drop files, and copy and paste text seamlessly between the systems.

![image](https://github.com/WillUHD/macOSonWorkstation/assets/134638202/2cddf5e7-83c2-4b53-9fc7-57c4756fee5c)

###### Created by Will C
