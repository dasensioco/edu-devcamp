# Setup of the Developer Environment

## Overview
In this lab, you will set up an Office 365 Educational trial subscription, populate your School Data Sync environment with demo data, and provision resources in the Azure subscription to use for development of further labs.

**This lab is a requirement for the other hands-on labs.**

## Prerequisites

You will need a cell phone for identity verification.

## Exercises
This hands-on-lab has the following exercises:
* [Exercise 1: Set up Office 365 Educational trial subscription](#ex1)
* [Exercise 2: Set up demo data in the School Data Sync Admin Portal](#ex2)
* [Exercise 3: Provision resources  via ARM](#ex3)
---

## Before you start

> &#x1F53A;If you already have an Office 365 subscription, please **use an alternate browser or use private mode!** This will help avoid any issues with conflicting accounts.
>
> Clear your browsers cache and restart your browser.
>
> **Do not skip exercise 1!** Even if you already have an Office 365 subscription and address, follow exercise 1 and create a new account.
>
> Use the account created in exercise 1 for **all the following exercises and hands-on labs!**
>
> To register for a free trial use an e-mail address and a phone number that has **not been used for a free trial** yet!&#x1F53A;

---

## Exercise 0: Download GIT repository

1. optional?

---
## Exercise 1: Set up Office 365 Educational trial subscription<a name="ex1"></a>

1. Open a InPrivate or Incognito browser window (`Ctrl + Shift + P` in Edge and Internet Explorer and Firefox or `Ctrl + Shift + N` in Google Chrome)
 and browse to the signup page. You will be given an individual link by your instructor that includes a promo code.

    ![image](./media/2018-06-27-16-27-00.jpg)

1. Choose the Country/Region for your tenant (this determines the SDS Schema, and Datacenter deployment). Populate information about yourself and click `Next`.

    ![image](./media/2018-06-27-16-37-00.jpg)

1. Create a user name and password for your company and click `Create my account`.

    ![image](./media/2018-06-28-09-13-00.jpg)
    
1. Enter you phone number, select your method of communication and click `Text me`.

    ![image](./media/2018-06-28-09-16-00.jpg)

1. Once you receive your verification code, enter it and click `Next`.

    ![image](./media/2018-06-28-09-17-00.jpg)

1. Prior to moving forward, make sure to capture the displayed information in order to sign into your new account. Wait for the page to finish loading.

    ![image](./media/2018-06-28-09-18-00.jpg)

1. There is no need to verify eligibility for an Educational pricing plan or register a domain. Click `I'll verify later` and confirm by clicking `Yes`.

    ![image](./media/2018-06-28-09-19-00.jpg)

1. You will be redirected to the Office 365 Admin center to your new subscription. You can skip the offered tour.

    ![image](./media/2018-06-28-09-19-30.jpg)

1. You can access the School Data Sync Ux via the menu. Click `Show more` > `Admin` > `Admin centers` > `School Data Sync`.

    ![image](./media/2018-06-28-09-27-00.jpg)

1. It may take a few minutes before you can access the SDS page.

    ![image](./media/2018-06-28-10-48-00.jpg)

---
## Exercise 2: Set up demo data in the School Data Sync Admin Portal<a name="ex2"></a>

1. Download these CSV files containing the demo data: [School](./assests/School.csv), [Section](./assests/Section.csv), [Student](./assests/Student.csv), [Student Enrollment](./assests/StudentEnrollment.csv), [Teacher](./assests/Teacher.csv) [Teacher Roster](./assests/TeacherRoster.csv). If you have downloaded the Dev Camp content you can find the files in the folder `HOL/HOL0/assets/`.

1. To access the School Data Sync Admin Portal launch a private web browser, navigate to [sds.microsoft.com](https://sds.microsoft.com), click `Sign-In`, then enter your O365 Global Admin account credentials.

1. After logging in, click `+ Add Profile` in the left hand navigation pane to create a `Sync Profile`.

    ![image](./media/2018-06-28-11-05-00.jpg)

1. On the `Choose Connection Type` page, complete the form. Enter a name for your sync profile. This name will be used to identify the sync profile in the SDS Dashboard, and cannot be changed once the profile setup is complete. Select `Upload CVS files` and `CVS files: SDS Format`. Once complete, click `Start`. 

    ![image](./media/2018-06-28-11-21-00.jpg)

1. On the Sync Options page, select the  `new users` option. Then click upload files to upload your 6 CSV files. Once uploaded, click `Next`. In a production scenario you would usually choose to sync existing users. For a more detailed instruction on the sync process see [docs.microsoft.com/en-us/SchoolDataSync/how-to-deploy-school-data-sync-by-using-csv-files](https://docs.microsoft.com/en-us/SchoolDataSync/how-to-deploy-school-data-sync-by-using-csv-files).

    ![image](./media/2018-06-28-11-23-00.jpg)

1. On the `Teacher options` page click `Next`.

    ![image](./media/2018-06-28-11-25-00.jpg)

1. On the `Student options` page click `Next`.

    ![image](./media/2018-06-28-11-34-00.jpg)

1. On the `Review` page click `Next`.

    ![image](./media/2018-06-28-11-36-00.jpg)

1. On the `Review page`, ensure you've made the appropriate selections. If no additional changes are needed, click `Create Profile`. Once you create a sync profile, SDS will begin a pre-sync validation process. During this process, SDS will ensure there are no obvious errors with your CSV files. If any errors are found during the pre-sync validation process, you will have the option to fix them and re-upload the files before clicking the resume sync button and begin the real synchronization process. If you receive errors and choose not to update them, you can still choose to resume sync without fixing the errors. Just be aware that SDS can only sustain up to 15,000 errors before the profile will enter a quarantine status.

    ![image](./media/2018-06-28-11-40-00.jpg)

    ![image](./media/2018-06-28-11-40-30.jpg)

1. The sync process will take some time and you will be prompted to manually refresh the status page. Press `F5` to do so.

    ![image](./media/2018-06-28-11-52-00.jpg)

---
## Exercise 3: Provision resources  via ARM<a name="ex3"></a>
1. ...

1. ...

1. ...

---
## Continue with lab 1

You are now ready to start hands-on lab 1. [View HOL 1 instructions](../HOL1).

---
Copyright 2018 Microsoft Corporation. All rights reserved. Except where otherwise noted, these materials are licensed under the terms of the MIT License. You may use them according to the license as is most appropriate for your project. The terms of this license can be found at https://opensource.org/licenses/MIT.