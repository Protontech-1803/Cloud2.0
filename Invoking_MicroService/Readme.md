# Invoking Micro Process from a Dynamic Process in Oracle Process Cloud

This POC shows how a Micro Process can be invoked from a Dynamic Main Process in Oracle Process Cloud. 
Micro processes-based process application consists of multiple independent, domain-driven processes. Micro process are typically smaller processes with quick execution time, with their output consumed in the main process. Micro Process can be invoked either synchronously or asynchronously. Within an application, create a link to a deployed micro process present in another application, and invoke this link in the main or parent process. The following steps illustrates how to create a Micro Process link in an Process Application and invoke them in a Dynamic Process.

1.	Sign in to the Oracle Integration Cloud, navigate to Process Application and Create a Process Application. 

2.	In the Application Home tab, Click on Processes and Click Create, from the menu select the option Use Micro Process.

3.	In the Link Micro Process Dialog, select a deployed (activated) version of a process and click Link.

4.	Define the Properties settings with the following options and click Create.

    Name: The Deployed Micro Process
    Operation: Select an operation to invoke from the drop-down list. 
    Callback Operation: In case of asynchronous links, specify a callback operation.
    Type: Specify if the micro process link is a synchronous or asynchronous invoke. A synchronous invoke halts the main process until the execution of the micro process element       completes. An asynchronous invoke enables parallel execution of both micro process and main process. 
    Security Type: Select APP Id - Basic Authentication to apply basic authentication to the micro process link. 
    KeyStore Credentials: Complete the fields that is displayed. To create a new key, select New Key and enter a key name, user name, and password. 

     ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Invoking_MicroService/JPG_images/1.jpg) 
 
5.	This will create a Micro Process link to the deployed process in the Process Application.

6.	Create a Dynamic Process in the Process Application.

7.	As part of the Dynamic Process, add an activity based on Micro Process.

8.	Open the properties of Micro Process activity, under General option, Select a micro process link from the Implementation Micro Process drop-down list. All the links that has been created within the application are listed here.

9.	Select the Micro Process Link that has to be invoked as part of the activities in the dynamic process.

      ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Invoking_MicroService/JPG_images/2.jpg)

 


