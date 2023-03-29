# What is GAM (Google Apps Application)?
GAM is an open source command line tool that allows you to govern your Google Workspace environment. GAM uses Google's APIs (Application Programming Interface), which allows us to manage common tasks for our Google Apps domain. In this tutorial, I'll provide a "how to install GAM" and the command that deprovisions Chromebooks in bulk. For this tutorial, we will be installing GAM using a Windows operating system. If you want to know more about GAM, you can read more about the tool [here](https://github.com/GAM-team/GAM).

# Download/Installing GAM
## Linux/MacOS
Open your terminal and run the follow command:
<br/>
```bash <(curl -s -S -L https://gam-shortn.appspot.com/gam-install)```
<br/><br/>
This will start the download for GAM and install the setup.

## Windows
If you go to the [GitHub Release Page](https://github.com/GAM-team/GAM/releases), you will be able to locate multiple MSI installers. Locate the one that fits the requirement of your device.
![image](https://user-images.githubusercontent.com/73561003/228594998-c58b03ed-51f9-4b2a-ac3f-f6f1a6aef250.png)

# Setting Up GAM
1. Once you have run the MSI installer, the command prompt application should have opened just like this:
![image](https://user-images.githubusercontent.com/73561003/228596439-c479f5f6-8825-4637-af0a-015bac20a1de.png)

2. Type in ```n``` for a new install.
![image](https://user-images.githubusercontent.com/73561003/228597089-94c12cb3-a82e-409d-8119-f06b7ad0f21a.png)

3. Type in ```y``` to set up a new Google API project for GAM.
![image](https://user-images.githubusercontent.com/73561003/228597746-617ef71d-c2a6-4530-9f2b-190c94926e0c.png)

4. GAM will now prompt you to enter your Google Workspace admin email address. After entering your email address, you will be redirected to a browser asking you to sign in. After signing in to your admin account, select allow. After you select allow, you should be prompted ```The authentication flow has completed. You may close this browser window and return to GAM``` and be redirected to your command prompt. GAM is now creating a new Google API project and enabling the different APIs for the project.
![image](https://user-images.githubusercontent.com/73561003/228599367-3826b0d7-0089-417e-85c3-e21c7dfaa6cb.png)
![image](https://user-images.githubusercontent.com/73561003/228599669-3c1af8ee-65fc-48e6-80c9-ca95841bf142.png)
![image](https://user-images.githubusercontent.com/73561003/228600207-95f03e8e-b73d-441c-941b-60a43c502bf0.png)

5. After enabling the APIs, GAM will now prompt you with a new link to the project that we just created. Copy the link and paste onto a new tab. Select ```Desktop app``` and rename the project to what you like and hit ```create```. After we have created the project, we are provided with the ```Client ID``` and the ```Client Secret```. Paste your ```Client ID``` first in our command prompt, then the ```Client Secret```. Once you're done, GAM will prompt you to Authorize GAM so that we can perform operations on our Google Workspace environment. Select ```y```
![image](https://user-images.githubusercontent.com/73561003/228601443-ec2a2918-26fc-4158-ad9a-3315e9414b7d.png)
![image](https://user-images.githubusercontent.com/73561003/228601875-21332e7b-328c-4387-91a1-ea26313c6bb1.png)
![image](https://user-images.githubusercontent.com/73561003/228602581-bcca55db-2152-444a-93ef-96ea3a3c8b93.png)
![image](https://user-images.githubusercontent.com/73561003/228603967-b4095613-25ab-4f0e-8f8b-9137fb9a1afd.png)

6. GAM will ask you which APIs would you like to enable. We want to select ```c``` for continue with default settings. The three options that are unselected, require billing for Google Cloud Platform. We will not be enabling those options. Once you hit continue, GAM will prompt to a new link. After selecting the admin account, GAM is requesting different types of scopes that only admins/super admins have access to. We want to allow these scopes so that GAM can access these as well. Once you have selected ```allow```, you will be prompted ```The authentication flow has completed. You may close this browser window and return to GAM``` and GAM will prompt you if you are ready to authorize GAM to manage user data/settings in Google Workspace. Select ```y```.
![image](https://user-images.githubusercontent.com/73561003/228604939-55a83ab3-5ee6-4f4d-b756-c4e17919c5c7.png)
![image](https://user-images.githubusercontent.com/73561003/228605727-eccbb26b-50fb-46bb-98d9-cff13ff682b6.png)
![image](https://user-images.githubusercontent.com/73561003/228606077-96079337-27ab-4230-8024-9bfee595af9d.png)
![image](https://user-images.githubusercontent.com/73561003/228607678-e534487b-4f30-4256-bd0e-309730317a3a.png)

7. GAM will prompt you to enter the email address of a REGULAR user. Enter a regular user from your Google Workspace. On the first initial try, GAM will state that some of the scopes have failed. We will need to go to the link provided and authorize the scopes. **YOU MUST BE A SUPER ADMIN TO ACCESS THIS PAGE.** Select ```AUTHORIZE```, wait a few minutes for the system to sync and go back to command prompt. Once you are there, select ```y``` to authroize GAM to manage user data/settings and enter the email address of the regular Google Workspace user again. All these scopes should pass and once they all pass, you are all done with the setup!
![image](https://user-images.githubusercontent.com/73561003/228608194-616ac19e-6324-4e39-a2ba-037d283a4604.png)
![image](https://user-images.githubusercontent.com/73561003/228608448-4dbf7153-b7ae-43d7-b413-2ae38ce7bd68.png)
![image](https://user-images.githubusercontent.com/73561003/228608971-c5bf5032-c77d-40ff-9931-1c371b5a7b36.png)
![image](https://user-images.githubusercontent.com/73561003/228609478-a90f6ad6-cac0-4464-8fb0-a37bd13b7d21.png)

# Deprovisioning Chromebooks in Bulk
In this phase of the tutorial, I'll show you how to collect your Chromebook data and filter them so we have a final list of Chromebooks that needs to be deprovisioned.

1. We want to first login to our Google Admin Console and go to the Devices tab -> Chrome -> Devices. Once we are on this page, we want to export all the provisioned devices. After downloading the exported CSV filled with provisioned Chromebooks, we then want to filter from the list what Chromebooks need to be deprovisioned (keep the as the original). Create a new CSV file called devices.csv, containing the filtered list of Chromebooks that need to be deprovisioned.
![image](https://user-images.githubusercontent.com/73561003/228612684-0f1cc8dd-288a-4f3c-8de2-058571614a6f.png)

2. Once we have the devices.csv file ready, we want to open a new command prompt and change directory to where the devices.csv file is located. For the final step, here is the GAM command to deprovision Chromebooks in the devices.csv by ```deviceId```: 

    ```gam csv devices.csv gam update cros ~deviceId action deprovision_retiring_device acknowledge_device_touch_requirement```
    
3. Once you have entered this code in your command prompt you can sit back and watch the magic unfold. **Note that when using GAM, you're making API requests/calls. This can be an issue if you are trying to automate a task that requires thousands of API requests. If this is the case, some of the API calls WILL FAIL. You will have to double check whether number of Chromebooks deprovisioned align with the number of Chromebooks in your devices.csv. If some of the devices are not provisioned, filter the list one more time and run the GAM command again.**
![image](https://user-images.githubusercontent.com/73561003/228615923-0da2fe26-b7c6-426e-8743-7436a4aea6a2.png)

## Useful Links for GAM Commands:
[GAMADV-XTD3](https://sites.google.com/jis.edu.bn/gam-commands/hardware/chromeos?authuser=0)
<br/>
[4 Chromebook Management Tools](https://gatlabs.com/education/blog/5-chromebook-management-tools-admins/)

## Useful Links for GAM Installation:
[YouTube Tutorial by The Cloud Nerd](https://www.youtube.com/watch?v=RJ5E56GIcdI)
<br/>
[GAM GitHub Page](https://github.com/GAM-team/GAM/wiki)
