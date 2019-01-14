# Microsoft Teams

## Content<a name="content"></a>
* [Overview](#overview)
* [Prerequisites](#prerequisites)
* [Exercise 1: Set up Microsoft Teams](#ex1)
* [Exercise 2: Create a new team](#ex2)
    * [Create a team](#ex2a)
    * [Create a Class Notebook](#ex2b)
    * [Create an Assignment](#ex2c)
* [Exercise 3: View demo data as teacher and student](#ex3)
* [Exercise 4: Create a Teams app](#ex4)
    * [Create an app service in Azure](#ex4a)
    * [Register a new app](#ex4b)
    * [Write your app](#ex4c)
    * [Allow external apps in Teams](#ex4d)
    * [Upload and test your new tab](#ex4e)
    * [Install your app in teams](#ex4f)
* [Continue with lab 3](#continue)

---

## Overview<a name="overview"></a>
In this lab, you will set up Microsoft Teams on your system, create your first team and create a custom Teams app hosted in Microsoft Azure.

**This lab is a requirement for hands-on lab 6!**

[Back to top](#content)

---

## Prerequisites<a name="prerequisites"></a>

* Complete [HOL 0](./../HOL0) to set up demo data in the School Data Sync Admin Portal.

[Back to top](#content)

---

## Exercise 1: Set up Microsoft Teams<a name="ex1"></a>

1. Open a InPrivate or Incognito browser window (`Ctrl + Shift + P` in Edge and Internet Explorer and Firefox or `Ctrl + Shift + N` in Google Chrome)
 and browse to [teams.microsoft.com/download](https://teams.microsoft.com/download). Click `Downloads` and select `Desktop (Windows 7+)` and click `DOWNLOAD NOW (64-BIT)`.

    ![image](./media/2018-06-28-13-33-00.jpg)

1. Execute the downloaded installer and when prompted login with your O365 Global Admin account credentials.

    ![image](./media/2018-06-28-13-34-00.jpg)

1. After the installation finished, complete the welcome wizard.

    ![image](./media/2018-06-28-13-35-00.jpg)


[Back to top](#content)

---

## Exercise 2: Create a new team<a name="ex2"></a>

### Create a team<a name="ex2a"></a>

1. On the menu on the left click `Teams` and then click the `Create team` button in the center.

    ![image](./media/2018-06-28-15-41-00.jpg)

1. Select `Classes` as the team type. Note that you will only see these choices if you are logged in an educational tenant.

    ![image](./media/2018-06-28-15-41-30.jpg)

1. Enter a `Name` for your team.

    ![image](./media/2018-06-28-15-42-00.jpg)

1. Find some students by entering a letter in the search box and add them to your team by clicking the names and clicking `Add`.

    ![image](./media/2018-06-28-15-43-00.jpg)

### Create a Class Notebook<a name="ex2b"></a>

1. Click `Set up Class Notebook`.

    ![image](./media/2018-06-28-15-45-00.jpg)

1. Follow the wizard by clicking `Next`.

    ![image](./media/2018-06-28-15-53-00.jpg)

1. Keep all the preselected features and click `Create`.

    ![image](./media/2018-06-28-15-58-00.jpg)

1. Wait for the wizard to finish.

    ![image](./media/2018-06-28-15-58-30.jpg)

### Create an Assignment<a name="ex2c"></a>

1. Go to the team's `Assignment` tab and click `Create` and `+ New assignment`.

    ![image](./media/2018-07-18-10-23-00.jpg)

1. Enter all required fields and click `Save`.

    ![image](./media/2018-06-28-16-03-00.jpg)

1. The assignment has been added to your list of assignments.You can edit it by clicking it.

    ![image](./media/2018-06-28-16-05-00.jpg)

You have manually created an assignment for your class. In a later hands-on-lab you will create assignments automatically.

[Back to top](#content)

---

## Exercise 3: View demo data as teacher and student<a name="ex3"></a>
To see the demo data you created in [HOL 0](./../HOL0) you have to use Teams as one of the created users that have classes assigned to them. Please be aware that classes will be added to teams and are visible to students as soon as a teacher for that class logs into teams. To log in as a teacher or student you will need to know their login names.

1. Launch a private web browser, navigate to [admin.microsoft.com/AdminPortal](https://admin.microsoft.com/AdminPortal/) and sign in using your O365 Global Admin account credentials. Click `Users`.

    ![image](./media/2018-08-29-13-01-00.jpg)

1. Click `Active users`.

    ![image](./media/2018-08-29-13-04-00.jpg)

1. `Bill Sluss` teaches the `Technology - Programming 2` class. Click his name.

    ![image](./media/2018-08-29-13-08-00.jpg)

1. You can see the classes Bill teaches as group memberships. His username is `billsluss@yourdomain.onmicrosoft.com`.

    ![image](./media/2018-08-29-13-20-00.jpg)

1. Return to the list of active users and repeat the process for one of Bill's students in the `Technology - Programming 2` class: `Jane Doe`.

1. On the menu on the left click `Settings` > `Services & add-ins`. Select `Microsoft Teams` from the list. Under `Settings by user/license type` select `Education - Student` and check `Turn Microsoft Teams on or off for all users of this type`. Click `Save`. All students are now allowed to use Teams.

    ![image](./media/2018-12-03-16-08-00.jpg)

1. Start the Teams client. Click the initials of the logged in user in the upper right corner and select `Sign out`.

    ![image](./media/2018-08-29-13-27-00.jpg)

1. Teams will automatically restart and display the login dialog. Login as `Bill Sluss` (`billsluss@yourdomain.onmicrosoft.com`) using the password `P@ssword`.

    ![image](./media/2018-08-29-13-29-00.jpg)

1. Note the classes in the list of teams that Bill teaches. Select `Technology - Programming 2` and create a new assignment.

    ![image](./media/2018-08-29-13-31-00.jpg)

    ![image](./media/2018-08-29-13-36-00.jpg)

    ![image](./media/2018-08-29-13-39-00.jpg)

1. Log out and log in again as `Jane Doe` (`jdoe@yourdomain.onmicrosoft.com`), again using the password `P@ssword`.

    ![image](./media/2018-08-29-13-46-00.jpg)

1. Note that the `Technology - Programming 2` class and the assignment show up for the student.

    ![image](./media/2018-08-29-13-48-00.jpg)

[Back to top](#content)

---

## Exercise 4: Create a Teams app<a name="ex4"></a>
Now you will add your own tab app to Teams. A tab app is a web application that runs within the teams client. The app will be hosted as an Azure app service. Some preparations are necessary before you can start coding.

### Create an app service in Azure<a name="ex4a"></a>

You need the Azure trial subscription created in HOL 0.

1. Open a InPrivate or Incognito browser window (`Ctrl + Shift + P` in Edge and Internet Explorer and Firefox or `Ctrl + Shift + N` in Google Chrome) and browse to [portal.azure.com](https://portal.azure.com/). Click `App Services` on the left menu and `Add` at the top of the page.

    ![image](./media/2018-09-05-10-50-00.jpg)

1. We will create a simple HTML based app with inline JavaScript code so it will be sufficient to use the `Web App` template. Select it and click `Create`.

    ![image](./media/2018-09-05-10-59-00.jpg)

1. Enter a name for your new app, select the resource group you used to create the virtual machine in HOL 0 and click `Create`.

    ![image](./media/2018-09-05-11-01-00.jpg)

1. A notification will tell you when the deployment finished.

    ![image](./media/2018-09-05-11-10-00.jpg)

1. Navigate to your web app and click `Browse` at the top of the page.

    ![image](./media/2018-09-05-11-12-00.jpg)

1. A new browser tab will open and tell you that your app service is running. Now you can upload your app to be hosted in Azure. Note the URL of your app service. You will need to add it to your code.

    ![image](./media/2018-09-05-11-14-00.jpg)

### Register a new app<a name="ex4b"></a>

For your app to be able to gain permissions to Microsoft Graph API you will need an app id.

1. Open a InPrivate or Incognito browser window (`Ctrl + Shift + P` in Edge and Internet Explorer and Firefox or `Ctrl + Shift + N` in Google Chrome) and browse to [apps.dev.microsoft.com](http://apps.dev.microsoft.com) and sign in.

    ![image](./media/2018-09-06-15-36-00.jpg)

1. Click `Add an app`, enter a name for your app and click `Create`.

    ![image](./media/2018-09-06-15-39-00.jpg)

1. Note the `Application Id` value.

    ![image](./media/2018-09-06-15-41-00.jpg)

1. Scroll down to the `Platforms` section and click `Add Platform`.

    ![image](./media/2018-09-06-15-43-00.jpg)

1. Select `Web`.

    ![image](./media/2018-09-06-15-46-00.jpg)

1. Paste the URL to your web app that you noted when you created the Azure app service and add `/silent-end.html` (a page you will be creating as part of your app). This is the URL that the authentication service will redirect to after the authentication has been completed.

    ![image](./media/2018-09-06-15-48-00.jpg)

1. Scroll down to the `Microsoft Graph Permissions section` and click `Add` next to `Delegated Permissions`.

    ![image](./media/2018-09-06-16-00-00.jpg)

1. Select `EduRoster.Read`, `Group.Read.All`, `User.Read.All` and click `OK`.

1. To finish the configuration click `Save` at the bottom of the screen.

    ![image](./media/2018-09-06-16-02-00.jpg)

### Write your app<a name="ex4c"></a>

This simple sample app will demonstrate the abilities of tabs and demonstrate how to access the Graph API from within the context of an integrated app. It is based on [this blog post](https://gsexdev.blogspot.com/2018/06/building-microsoft-teams-tab.html) by Glen Scales.

1. Download the HTML files from the [app](./assets/app) folder.

1. Start Visual Studio and click `File` -> `Open` -> `Folder...`.

    ![image](./media/2018-09-06-16-18-00.jpg)

1. The `Solution Explorer` shows the loaded HTML files.

    ![image](./media/2018-09-06-16-25-00.jpg)

1. Open `auth.html`. Look for the line `clientId: "YOURAPPID",` and replace `YOURAPPID` with the `Application Id` you noted earlier when registering the app. The `auth.html` will handle the authentication of the app using ADAL (`Azure ActiveDirectory Library for JS`)

1. Open `silent-end.html` and repeat the process. The `silent-end.html` is the redirect target for the authentication. For further information on authentication in a tab app check out [this blog post](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Authentication-SSO-and-Microsoft-Graph-in-Microsoft-Teams-Tabs/ba-p/125366) which explains in detail how to do a silent authentication when possible and fall back to an explicit login window when necessary.

1. Open `config.html` and replace the three occurrences of `YOURAPPNAME` for the values of `contentUrl`, `websiteUrl` and `removeUrl` with the name you choose for your Azure app. The `config.html` is called when your app is installed and sets the URLs to the content pages of the app.

1. Open `tab.html` and again replace `YOURAPPID` with the `Application Id`. `tab.html` contains the actual content of your app. It connects to the Graph API and using the context of the current class/group gets all the team members which are then displayed on the tab. A second call to the Graph API gets information about the class and displays its time frame. A third call gets the profile pictures of the users. To see these start the Teams client and login as the teachers and students and choose a profile picture.

1. Save all changes. Take the six HTML files in the folder and turn them into a zip compressed folder. Name it `app.zip`.

1. You need a manifest file that will tell Teams all about your app. Download the 3 files from the [manifest](./assets/manifest) folder and use Visual Studio to open `manifest.json`.

1. Go to `Tools` -> `Create GUID` to create a new unique guid for your app. Copy it and replace the guid next to `"id":`.

    ![image](./media/2018-09-06-16-51-00.jpg)

1. Set you e-mail address next to `"name":` and replace the five occurrences of `YOURAPPNAME` for the values of `websiteUrl`, `privacyUrl`, `termsOfUseUrl`, `configurationUrl` and `validDomains`.

1. Save all changes.

1. Take the three files in the folder (`manifest.json`, `32.png`, `192.png`) and turn them into a zip compressed folder. Name it `manifest.zip`.

### Allow external apps in Teams<a name="ex4d"></a>

You must configure your Office 365 to allow Teams the use of external apps (that you uploaded yourself).

1. Open a InPrivate or Incognito browser window (`Ctrl + Shift + P` in Edge and Internet Explorer and Firefox or `Ctrl + Shift + N` in Google Chrome)
 and browse to [admin.microsoft.com](https://admin.microsoft.com) and enter your O365 Global Admin account credentials. 

1. Click `Services & add-ins` and select `Microsoft Teams`.

    ![image](./media/2018-06-28-16-16-00.jpg)

1. Expand the `Apps` section .

    ![image](./media/2018-06-28-16-17-00.jpg)

1. Check `Allow external apps in Microsoft Teams` and `Allow sideloading of external apps` and `Enable new external apps by default`. Click `Save`.

    ![image](./media/2018-06-28-16-17-30.jpg)

### Upload and test your new tab<a name="ex4e"></a>

There are many ways to deploy an Azure web app. If you develop in Visual Studio you can use the publish feature to upload your apps. Azure also features support for VSTS integration, Github, OneDrive, FTP and some other services. The most hassle-free way to deploy this simple web app is to use the Zip Deploy feature of Azure's Kudu UI.

1. Open a InPrivate or Incognito browser window (`Ctrl + Shift + P` in Edge and Internet Explorer and Firefox or `Ctrl + Shift + N` in Google Chrome) and browse to `https://YOURAPPNAME.scm.azurewebsites.net/ZipDeployUI` ( again replace `YOURAPPNAME` with the name you choose for your Azure app) and sign in. You are now seeing the Advanced Tools for development. You can also reach this page via the Azure portal UI by navigating to your App Service and selecting `Advanced Tools`.

    ![image](./media/2018-09-10-09-39-00.jpg)

1. From the menu select `Tools` -> `Zip Push Deploy`.

    ![image](./media/2018-09-10-09-37-00.jpg)

1. Drag and drop the `app.zip` you created earlier in the explorer part of the page. The content of the zip file will replace all of the existing content.

    ![image](./media/2018-09-10-09-16-00.jpg)

1. Your app has been deployed. To deploy updates simply drag and drop a new zip file here. Browse to the app by opening `https://YOURAPPNAME.azurewebsites.net/tab.html`.

    ![image](./media/2018-09-10-09-44-00.jpg)

1. If your deployment succeeded you will see the `Show classmates` button.

### Install your app in teams<a name="ex4f"></a>

Now it is time to add your app as a tab in Microsoft Teams. Since some of the Graph API calls (currently) require admin rights you will first elevate a teacher to admin level to test your app.

1. Launch a private web browser, navigate to [admin.microsoft.com](https://admin.microsoft.com) and sign in using your O365 Global Admin account credentials. Click `Users`.

    ![image](./media/2018-08-29-13-01-00.jpg)

1. Click `Active users`.

    ![image](./media/2018-08-29-13-04-00.jpg)

1. Click the name `Bill Sluss`.

    ![image](./media/2018-08-29-13-08-00.jpg)

1. In the `Roles` section click `Edit`.

    ![image](./media/2018-09-11-08-29-00.jpg)

1. Select `Global administrator` and click `Save`.

    ![image](./media/2018-09-11-09-00-00.jpg)

1. Start the teams client and login as `Bill Sluss`.

1. Click `Store` on the bottom of the left menu and then `Upload a custom app` at the end of the list (if another pop-up appears select `Upload for me or my team`).

    ![image](./media/2018-09-10-11-31-00.jpg)

1. Select the `manifest.zip` file you created earlier.

    ![image](./media/2018-09-10-11-39-00.jpg)

1. Select the team `Technology - Programming 2` (note that Bill Sluss does not have permissions to add apps to teams where he is not the teacher) and click `Install`.

    ![image](./media/2018-09-10-11-39-00.jpg)

1. The (nearly empty) configuration page will be displayed. Click `Save`.

    ![image](./media/2018-09-10-11-55-00.jpg)

1. Click `Set up`. Your app has now been added to the `General` section of the selected class.

    ![image](./media/2018-09-10-12-26-00.jpg)

1. Go to `General` and click `My classmates`. You will see the `Show classmates` button. Once you press it you will be first prompted to enter your credentials and then prompted to grant permissions to the app. Once you click `Accept` the team member data will be loaded via the Graph API.

    ![image](./media/2018-09-10-16-34-00.jpg)

Your app is now running as a tab in Microsoft teams. Whenever you update the files in the Azure App Service the tab will change accordingly.


[Back to top](#content)

---

## Continue with lab 3<a name="continue"></a>

You are now ready to start hands-on lab 3. [View HOL 3 instructions](../HOL3).

[Back to top](#content)

---

Copyright 2018 Microsoft Corporation. All rights reserved. Except where otherwise noted, these materials are licensed under the terms of the MIT License. You may use them according to the license as is most appropriate for your project. The terms of this license can be found at https://opensource.org/licenses/MIT.