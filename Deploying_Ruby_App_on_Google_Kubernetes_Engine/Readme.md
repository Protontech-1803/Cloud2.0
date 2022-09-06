# Deploying Ruby App on Google Kubernetes Engine (GKE)

Ruby on Rails gained popularity among developers by offering a platform for rapidly developing database-backed web apps. Kubernetes is an open-source framework, Google Kubernetes Engine (GKE) offers a managed environment for deploying, maintaining, and scaling containerized applications using Google infrastructure. This POC illustrates taking DevOps to the next level by demonstrating how developers can use the Kubernetes cluster GKE to build Ruby applications.

The Following are the steps for Deploying Ruby App on Google Kubernetes Engine (GKE):

1. **Creating a Cloud Project:** Set up a Google Cloud account. Select or create a Google Cloud project from the project selector page in the Google Cloud dashboard. 

2. **Enable Billing for the Cloud Project:** Project usage is charged to the linked Cloud Billing account. The associated Cloud Billing account is operational and in good standing, which means it has not been closed or suspended.

3. **Enable GKE APIs:** Enable the Artifact Registry, Cloud Build, and Google Kubernetes Engine APIs.

4. **Install and initialize the Google Cloud CLI:** Download the Google Cloud CLI installer to manage Google Cloud resources.

5. **Install Kubectl by using gcloud:** kubectl is used to manage Kubernetes, the cluster orchestration system used by GKE by proving below command in cloud shell.

    ``gcloud components install kubectl``

6. **Create a sample App:** Create a new directory and a file app.rb to write the code to create a web server that listens on the port defined by the PORT environment variable. 

     ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Deploying_Ruby_App_on_Google_Kubernetes_Engine/1.1.png)
     
7. **Create Gem file:** Further create a ‘gemfile’ which allows user to interact with Ruby Gems.

    ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Deploying_Ruby_App_on_Google_Kubernetes_Engine/1.2.png)
    
    ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Deploying_Ruby_App_on_Google_Kubernetes_Engine/1.3.png)
    
8. **Containerizing an app with Cloud Build** To containerize the sample app, create a new file named Docker file in the same directory as the source files, and Get Google Cloud project ID. Create gcloud artifacts repository and provide project ID and location.
   
9. **Creating a GKE cluster:** Create the cluster. Verify that you have access to the cluster. The following command lists the running nodes in your container cluster and indicates that you have access to the cluster.

    ``gcloud container clusters create-auto helloworld-gke
      region us-central1`` 
            
    ``kubectl get nodes``

10. **Deploying to GKE:** Two Kubernetes objects are required to deploy your app to the GKE cluster you constructed, A Deployment to specify your app, and a Service that defines how your app can be accessed.

       ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Deploying_Ruby_App_on_Google_Kubernetes_Engine/1.4.png)
   
10.1 **Deploy an app:** Create the deployment.yaml file in the same directory and provide Google Cloud project ID and the repository location and deploy the resource to the cluster.

   ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Deploying_Ruby_App_on_Google_Kubernetes_Engine/1.5.png)

10.2 The Deployment is complete when all of the AVAILABLE deployments are READY

   ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Deploying_Ruby_App_on_Google_Kubernetes_Engine/1.6.png)
  
10.3 when the Deployment is completed, you can see the Pods that it created.

   ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Deploying_Ruby_App_on_Google_Kubernetes_Engine/1.7.png)
  
   ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Deploying_Ruby_App_on_Google_Kubernetes_Engine/1.8.png)
  
10.4 **Deploy a Service:** Services provide a single point of access to a set of Pods. Create the file service.yaml in the same directory and Get the external IP address of the Service. The external IP address is listed under the column ‘EXTERNAL-IP’ for the Service.

10.5 **View a deployed app:** All the resources required to operate the Hello World app on GKE have now been deployed. To view your running app in the web browser, load the app using the external IP address from the previous step, alternatively, you can make a curl call to the Service's external IP address to display the output.

   ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Deploying_Ruby_App_on_Google_Kubernetes_Engine/1.9.png)
