Migrating VM from GCP TO AWS
This POC illustrates how to migrate a VM server from google cloud platform to the AWS. The migration process will create an instance in AWS to replicate the VM from GCP to AWS.
While launching the target machine, an instance will be creating for converting the GCP VM snapshot into the Image and then the machine will be launched.

Prerequisite: 
An AWS and GCP account with Admin Privileges.                    
The following are the steps to migrate a VM server from google cloud platform to the AWS.
1.	Create a VM instance in Google Cloud Platform (GCP).
a.	Login to the GCP account using the credentials and select Project.
b.	Navigate to the Compute Engine and select VM instance.
 
c.	Click Create Instance to create a instance.
 
d.	Enter the name for VM, select the region and AZ and select the Machine type.
 
e.	Select the Image, firewall rules and click to create the VM.
Note: Image type can be select any and firewall rules are not mandatory.
 

2.	Login and setup the user account in AWS cloud.
a.	Login to the AWS Root user account.
b.	Navigate to the IAM, Select policies and click Create Policy.
 
c.	Select JSON tab on policy page and paste the policy in JSON format from the given IAMPolicy.json file. Click Next: Tags.
 
d.	Enter the Name and description for Policy and click Create Policy.
 
e.	Navigate to Users and click Add User to add a AWS user.
 
f.	Enter the name for the user, select the access as programmatic access and click Next: Permission.
 
g.	Select the Attach existing Policies, click filter policies as Customer Managed Policies and select the policy created in previous step. Click Next.
 
h.	Click Create user in review page.
 
i.	Click download .csv to download the Access Key ID and Secret Access Key ID.
 

3.	Register for an account in Cloud endure using the following URL.
https://console.cloudendure.com/#/register/register
4.	Verify the Email account and login to the Cloud Endure website.
5.	Create a migration project in the Cloud endure.
a.	Click to add a project in cloud endure home page.
 
b.	Enter the name for the project and click Create Project the click Start.
 
c.	Enter the Access Key ID and Secret Access Key ID of the user created in previous step and click Save.
 
d.	In Replication Settings, Select Migration Source as Other Infrastructure, Migration Target as AWS Asia Pacific (Mumbai), Select the Replication Instance type as t3.medium  
 
e.	Let the other preference as default and click Save Replication Settings.
 
f.	On Congratulation dialog box, click SHOW ME HOW.
 
g.	This page contains the migration agent installation token and command to install Agent.
 

6.	Install Migration Agent in the GCP VM to migrate it into the AWS cloud.
a.	Navigate to the GCP VM and Click to generate the Password.
 
b.	Click Set Windows Password to setup the password.
 
c.	Enter the user and click Set to generate the password.
 
d.	Click copy and paste the generated password into a file for next step.
 
e.	Click to dropdown beside RDP and select Download RDP file to download the RDP file.
 
f.	Open the RDP file and click Connect to connect with the windows VM and enter the user name and password to login to the VM.
 
g.	In Windows Server Manager, Select Local Server, Select the IE Enhanced Security Configuration and turn it off.
 
h.	Open the browser and paste the given link to download Migration Agent in Windows VM and Click Save.( https://console.cloudendure.com/installer_win.exe)
 
i.	Navigate to the Download Directory, In windows navigation bar type CMD and press enter to open command prompt in directory location.
 
j.	Navigate to the Cloud endure page, copy the command with token to install agent in windows.
 
k.	Paste the command on command prompt to install the agent in the windows VM.
 
l.	The Command will open another command prompt and the agent will be install in the VM. Installing the replication will start the replication of the Vm
 

7.	View the replication process in Cloud Endure console and setup the Blueprint for target instance.
a.	Navigate to the Cloud Endure console it will automatically update with the same machine name of the GCP VM. Click on machine name to view the replication process.
 
b.	The process of the migration will be updated in machine dashboard as it is show initiating the Data replication. This will take 40-50 min time depends on the replication instance configuration.
 c
c.	In machine dashboard, select the Blueprint tab and select the target machine type as t3.xlarge, launch type as On demand, select the subnet.
 
d.	Select the security group for the target instance and private IP as create New.
 
e.	Select the disk type as Standard SSD and click Save Blueprint.
 
8.	Create the instance using the migrated VM.
a.	Click Launch Target Machine and select Cutover to create replica of the migrated server after finishing the replication job.
 
b.	Click Continue on Launch Target Machine dialog box. The job to launch target machine will be initated.
 
c.	Click Job Progress in side navigation Menu of Cloud Endure machine dashboard.
 
d.	Navigate to the AWS EC2 console after finishing the job. Instance with the name of windows-server will be created.
 



