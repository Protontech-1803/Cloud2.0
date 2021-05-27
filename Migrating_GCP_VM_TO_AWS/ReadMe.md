# Migrating VM from GCP TO AWS
This POC illustrates how to migrate a VM server from google cloud platform to the AWS. The migration process will create an instance in AWS to replicate the VM from GCP to AWS.
While launching the target machine, an instance will be creating for converting the GCP VM snapshot into the Image and then the machine will be launched.

**Prerequisite: An AWS and GCP account with Admin Privileges.**
    
### The following are the steps to migrate a VM server from google cloud platform to the AWS.

1.	Create a VM instance in Google Cloud Platform (GCP).
     - Login to the GCP account using the credentials and select Project. 
       
     -  Navigate to the Compute Engine and select VM instance.
     ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/1.png)
 
 
     -  Click Create Instance to create a instance.
     ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/2.png)
 
 
     -  Enter the name for VM, select the region and AZ and select the Machine type.
     ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/3.png)
 
 
      - Select the Image, firewall rules and click to create the VM.
      - Note: Image type can be select any and firewall rules are not mandatory.
        ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/4.png)
 
 
2. Login and setup the user account in AWS cloud.

      -  Login to the AWS Root user account.
       
      -  Navigate to the IAM, Select policies and click Create Policy.
       ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/5.png)
       
      -  Select JSON tab on policy page and paste the policy in JSON format from the given IAMPolicy.json file. Click Next: Tags.
       ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/6.png)
 
      -  Enter the Name and description for Policy and click Create Policy.
        ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/7.png)
        
      -  Navigate to Users and click Add User to add a AWS user.
       ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/8.png)
       
      -  Enter the name for the user, select the access as programmatic access and click Next: Permission.
        ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/9.png)
        
      -  Select the Attach existing Policies, click filter policies as Customer Managed Policies and select the policy created in previous step. Click Next.
        ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/10.png)
      -  Click Create user in review page.
        ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/11.png)
      -  Click download .csv to download the Access Key ID and Secret Access Key ID.
        ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/12.png)
        
3.	Register for an account in [Cloud Endure](https://console.cloudendure.com/#/register/register) using the URL.
4.	Verify the Email account and login to the Cloud Endure website.
5.	Create a migration project in the Cloud endure.
      -  Click to add a project in cloud endure home page.
        ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/13.png)
      -  Enter the name for the project and click Create Project the click Start.
        ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/14.png)
      -  Enter the Access Key ID and Secret Access Key ID of the user created in previous step and click Save.
        ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/15.png)
      -  In Replication Settings, Select Migration Source as Other Infrastructure, Migration Target as AWS Asia Pacific (Mumbai), Select the Replication Instance type as t3.medium  
        ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/16.png)
      -  Let the other preference as default and click Save Replication Settings.
        ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/17png)
      -  On Congratulation dialog box, click SHOW ME HOW.
        ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/18.png)
      -  This page contains the migration agent installation token and command to install Agent.
        ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/19.png)

6.	Install Migration Agent in the GCP VM to migrate it into the AWS cloud.
      -  Navigate to the GCP VM and Click to generate the Password.
        ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/20.png)
      -  Click Set Windows Password to setup the password.
        ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/21.png)
      -  Enter the user and click Set to generate the password.
        ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/22.png)
      -  Click copy and paste the generated password into a file for next step.
        ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/23.png)
      -  Click to dropdown beside RDP and select Download RDP file to download the RDP file.
        ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/24.png)
      -  Open the RDP file and click Connect to connect with the windows VM and enter the user name and password to login to the VM.
        ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/25.png)
      -  In Windows Server Manager, Select Local Server, Select the IE Enhanced Security Configuration and turn it off.
        ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/26.png)
      -  Open the browser and paste the given link to download Migration Agent in Windows VM and Click Save.
      ( https://console.cloudendure.com/installer_win.exe)
        ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/27.png)
      -  Navigate to the Download Directory, In windows navigation bar type CMD and press enter to open command prompt in directory location.
        ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/28.png)
      -  Navigate to the Cloud endure page, copy the command with token to install agent in windows.
        ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/29.png)
      -  Paste the command on command prompt to install the agent in the windows VM.
        ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/30png)
      -  The Command will open another command prompt and the agent will be install in the VM. Installing the replication will start the replication of the Vm
        ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/31png)

7.	View the replication process in Cloud Endure console and setup the Blueprint for target instance.
      -  Navigate to the Cloud Endure console it will automatically update with the same machine name of the GCP VM. Click on machine name to view the replication process.
        ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/32png)
      -  The process of the migration will be updated in machine dashboard as it is show initiating the Data replication. This will take 40-50 min time depends on the replication instance configuration.
       ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/33png)
      -  In machine dashboard, select the Blueprint tab and select the target machine type as t3.xlarge, launch type as On demand, select the subnet.
        ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/34png)
      -  Select the security group for the target instance and private IP as create New.
        ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/35png)
      -  Select the disk type as Standard SSD and click Save Blueprint.
        ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/36png)
        
8.	Create the instance using the migrated VM.
      -  Click Launch Target Machine and select Cutover to create replica of the migrated server after finishing the replication job.
        ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/37)
      -  Click Continue on Launch Target Machine dialog box. The job to launch target machine will be initated.
        ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/38ng)
      -  Click Job Progress in side navigation Menu of Cloud Endure machine dashboard.
        ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/39ng)
      -  Navigate to the AWS EC2 console after finishing the job. Instance with the name of windows-server will be created.
       ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Migrating_GCP_VM_TO_AWS/jpeg/40ng)


