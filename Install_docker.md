# Install Docker on Windows;

1. Download the Docker Desktop installer from the official Docker website.
   
2. Double-click the downloaded installer to start the installation process.
   
3. Follow the on-screen instructions to complete the installation and restart the computer.
   
4. Once installed, Docker Desktop should be accessible from the Start menu.

5. To check if it has been installed go to the Terminal and type the command docker --version. If installed correctly it will give you the version

![Alt text](<images/docker version.png>)

# After installing Docker;

1. Go to start and search for Docker app 
2. Follow the link
3. Step 3: Enable Windows Subsystem for Linux (WSL)
Open PowerShell as Administrator and run the following command:
```
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```
4. Step 6: Check if your Windows version supports WSL 2
Make sure you have Windows 10 version 1903 or later, or Windows 11. Check your version by pressing Windows logo key + R, type winver, and press Enter. Update Windows if needed.

5. Step 5: Enable Virtual Machine feature
In PowerShell as Administrator, run:
```
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

5. #### **Restart your computer after this step.**


6.  Set WSL 2 as the default version
Open PowerShell and run:
```
wsl --set-default-version 2
```

Now, WSL 2 is installed on your Windows machine and set as the default version. You can install Linux distributions from the Microsoft Store or other sources to use WSL 2.