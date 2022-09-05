# Using Cloud Firestore Database in Flutter

Flutter is Google's UI toolkit for creating beautiful, natively built mobile, web, and desktop applications from a single codebase. Cloud Firestore is a flexible, scalable database for mobile, web, and server development from Firebase and Google Cloud. This POC illustrates how to implement Crud Operation in flutter using Firebase FireStore Database.

**The Following are the steps to implement to use Cloud FireStore DB with flutter.**

1. **Creating a Flutter Project:** Create a folder and choose a location to put the App. Open vs code then open the created folder. Project structure is shown below

     ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Using_Cloud_Firestore_Database_in_Flutter/1.1.png)
 
2. **A Building the User Interface:** UI of the app written in the main.dart file and create necessary pages inside lib.

3. **Creating Firebase Project:** Register and create a project on the Firebase website, Add the desired name for the project, accept the Firebase terms, Enable Google Analytics, choose location and create project.

    ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Using_Cloud_Firestore_Database_in_Flutter/1.2.png)

4. **Add Firebase to Android app:** Provide application ID and SHA1 from flutter project and register app. Further download config file that is google-services.json file in App folder.

5.	**Add Firebase Dependencies to Flutter Project:** Add Firebase SDK dependencies in build.gradle 

6.	**Enable the Cloud Firestore database:** create database in test mode and enable cloud firestore location. Further create a collection.

    ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Using_Cloud_Firestore_Database_in_Flutter/1.3.png)

7. **Getting Firebase Plugins:** Add firebase plugins for firebase_core and cloud_firestore.

    ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Using_Cloud_Firestore_Database_in_Flutter/1.4.png)

8. **Retrieving data from Firebase:** Fetch data from the created collection to the app
    
    ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Using_Cloud_Firestore_Database_in_Flutter/1.5.png)

9. **Adding new Item:** Add new item by clicking add button. fill details and click on Register button

    ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Using_Cloud_Firestore_Database_in_Flutter/1.6.png)

10. **Added Item will update in DB:** The added item will get updated in the firestore database and the UI table.

    ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Using_Cloud_Firestore_Database_in_Flutter/1.7.png)

11. **Deleting Item from the table:** Last two items were deleted from the table, which is also deleted from the database 

    ![Alt text](https://github.com/Protontech-1803/Cloud2.0/blob/main/Using_Cloud_Firestore_Database_in_Flutter/1.8.png)
