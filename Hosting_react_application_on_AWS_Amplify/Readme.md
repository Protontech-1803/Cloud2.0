# Hosting react application on AWS Amplify

React is a web appication framework that enables developers to quickly build performant single-page applications using JavaScript. AWS Amplify is an open-source framework fully integrsted with Aws, works with multiple databases, and allows mobile and web development. AWS Amplify provides a Git-based CI/CD workflow for building, deploying, and hosting single-page web applications. This POC illustrates how to host/deploy react applications on AWS amplify.

The following are the steps to host react application on AWS amplify.

1. **Creating a react Project:** create a react-login project. Open VS code and create two folders named client and server. Install all necessary packages and execute the code. The project structure is shown below.

     ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Hosting_react_application_on_AWS_Amplify/1.1.png)
     
2. **Creating GitHub repository:** Open GitHub and create a new repository, provide the repository name and commit the changes. AWS Amplify uses GitHub to obtain access to your GitHub code repositories.

     ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Hosting_react_application_on_AWS_Amplify/1.2.png)
     
3. **Commands to commit the changes to the git repository:** Once the application and git repository is created, now run git commands to commit the changes.

 	3.1 git init

 	3.2 git add .

 	3.3 git commit -m "first commit"
 
 	3.4 git remote add origin < github repository path >
 	
 	3.5 git push origin HEAD:main

4. **Steps to deploy react application on AWS Amplify**

4.1 In the AWS management console, click sign in to the console and provide Root user credentials.

   ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Hosting_react_application_on_AWS_Amplify/1.3.png)
   
   ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Hosting_react_application_on_AWS_Amplify/1.4.png)
   
4.2 Search for AWS Amplify in the services and select it.

   ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Hosting_react_application_on_AWS_Amplify/1.5.png)
   
4.5 Click the new app and select host web app to start deployment.

   ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Hosting_react_application_on_AWS_Amplify/1.6.png)
   
4.6 Choose GitHub and click continue. Now add the updated repositories and click Next.

   ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Hosting_react_application_on_AWS_Amplify/1.7.png)
   
   ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Hosting_react_application_on_AWS_Amplify/1.8.png)

4.7	Now verify the application details and click Save and deploy.

   ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Hosting_react_application_on_AWS_Amplify/1.9.png)

4.8	The deployment of the application has been started.

   ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Hosting_react_application_on_AWS_Amplify/1.10.png)
   
4.9 Deployment of react project has been completed.

   ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Hosting_react_application_on_AWS_Amplify/1.11.png)
   
4.10 Click the link or copy the link from the AWS console and open it in the browser to view the react project which is hosted on AWS Amplify.

   ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Hosting_react_application_on_AWS_Amplify/1.12.png)
   
   ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Hosting_react_application_on_AWS_Amplify/13.png)
