---
title : "Use Single-Sign-On"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2.2. </b> "
---

## Enable SSO
1. In **AWS Management Console**, Select **IAM Identity Center**
![sso](/images/2.prepare/2.2.1.png)
2. Select **Enable**
![sso](/images/2.prepare/2.2.23.png)
## Create Group
1. In the **SSO** interface
* Select **Groups** from the left panel -> **Create group**
![sso](/images/2.prepare/2.2.2.png)
2. In the **Group** creation interface
* Enter **Group name** : ```DevGroup```
* Select **Create group**
![sso](/images/2.prepare/2.2.3.png)
## Create User
1. In the **SSO** interface
* Select **Users** from the left panel -> **Add user**
![sso](/images/2.prepare/2.2.4.png)
2. In the user creation interface
* Enter **Username** : ```DevUser```
* In **Password** section, select **Send an email**
* Enter email and information
![sso](/images/2.prepare/2.2.5.png)
* Click **Next**
![sso](/images/2.prepare/2.2.6.png)
* Select the box **DevGroup** -> **Next**
![sso](/images/2.prepare/2.2.7.png)
* Scroll to the bottom and select **Add user**
![sso](/images/2.prepare/2.2.8.png)
3. Added user successfully
![sso](/images/2.prepare/2.2.9.png)
4. Check the root account's email
![sso](/images/2.prepare/2.2.10.png)
 * Click **Accept invitation**
![sso](/images/2.prepare/2.2.11.png)
* Set up password for **SSO** account
![sso](/images/2.prepare/2.2.12.png)
* Register for MFA using the Authenticator app method
![sso](/images/2.prepare/2.2.13.png)
* Download the **Goole Authenticator** app and scan the QR code
![sso](/images/2.prepare/2.2.14.png)
## Create Permission sets
1. In the **SSO** interface
* Select **Permission sets** from the left panel -> Select **Create permission set**
![sso](/images/2.prepare/2.2.15.png)
2. In the interface create **permission set**
* In the **type** section, select **Predefined permission set**
* In the **Policy for predefined permission set** section, select **AdministratorAccess -> Next**
![sso](/images/2.prepare/2.2.16.png)
* **Next**
![sso](/images/2.prepare/2.2.17.png)
## Proceed to Assign user organization
1. In the **SSO** interface
* Select **AWS accounts** from the left panel
* Select the **DevUser** box in **OU Dev** -> Select **Assign users or groups**
![sso](/images/2.prepare/2.2.18.png)
2. In the interface **assign users and groups**
* Select the box **DevGroup -> Next**
![sso](/images/2.prepare/2.2.19.png)
* Select the box A**dministratorAccess -> Next**
![sso](/images/2.prepare/2.2.20.png)
* **Submit**
![sso](/images/2.prepare/2.2.24.png)
## Login using SSO
1. In the **SSO** interface
* Select **Dashboard** from the left panel, copy **AWS access portal URL**
![sso](/images/2.prepare/2.2.25.png)
2. In the login interface
* Enter account, password and MFA authentication
* Choose to log in to **DevUser** with **AdministratorAccess** rights
![sso](/images/2.prepare/2.2.21.png)
* Logged in successfully
![sso](/images/2.prepare/2.2.22.png)