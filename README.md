# E2E Tests Database


# The Projects

We have used projects developed in Spring and Angular, the projects simulate real applications.

| Project  | URL | Number of Regressions |
| -------- | --- | :-------------------: |
| Webapp-1 | https://github.com/e2e-tests-database/webapp-1 | 2 |
| Webapp-2 | https://github.com/e2e-tests-database/webapp-2 | 3 |
| Webapp-3 | https://github.com/e2e-tests-database/webapp-3 | 1 |


## Requirements

If you use the database in local you will need the following tools:

* Git (All projects)
* Java 1.8 (All projects)
* Node 8.x (Webapp-1 and Webapp-2)

The applications Webapp-1 and Webapp-2 using a back-end in Spring and front-end in angular. The application Webapp-1 use a back-end Spring, and front-end with moustache.

## Docker enviroment

If you don't want to use the local database you can use the docker's image with the all enviroment. The image and explications for running the image they're in this page https://github.com/e2e-tests-database/images

## Webapp 1

| Regression 1 |
| ------------ | 
| **Test failed** |
| com.trackorjargh.e2e.TestE2EFront.java (TestE2EFront.java:31) |
| **File modified** |
| src/app/profile/profile.component.ts <br> src/app/profile/profile.html | 
| **Link to changes** |
| https://github.com/elastest-experiments/webapp-1/commit/ff464c9b692cde97bfd816177493e04617aa4a4d#diff-40ad886a9beb70f673ce1d05d73d7978R101 |
| **Bug description**
| The problem in this bug is the method called when click the button add new list, this method activate variable for collapse and uncollapse the div. The method change the variable “showAddList” but the event collapse listen the variable “isCollapsed”. |
    
Tag Regression: regression-1
Tag regression fixed: regression-fixed-1

| Regression 2 |
| ------------ | 
| **Test failed** |
| com.trackorjargh.integration.TestGraphics.java (TestGraphics.java:56) |
| **File modified** |
| com.trackorjargh.apirestcontrolers.ApiGenderController.java |
| **Link to changes** |
| https://github.com/elastest-experiments/webapp-1/commit/dcf5c4bf5d7935098d6bce6c07bc5de564b9a3ce#diff-54e63438903cb13be10bf4f44213d2fbR30 |
| **Bug description** |
| The problem in this bug is the method of the api that return the num of genres (shows, films, books). The method failed counting the genres (the variable of count accumulated all). |  

Tag Regression: regression-2
Tag regression fixed: regression-fixed-2

## Webapp 2

| Regression 1 |
| ------------ | 
| **Test failed** |
| com.example.demo.e2e.TestE2EFront.java (TestE2EFront.java:35) |
| **File modified** |
| com.example.demo.restControllers.CourseRestController.java <br> com.example.demo.security.RestSecurityConfig.java |
| **Link to changes** |
| https://github.com/elastest-experiments/webapp-2/commit/06ab88c1a7c4c32b3259d5ddb9167ef9c683263a#diff-9e05c0f97be73543993267d2dee21878L247 <br> https://github.com/elastest-experiments/webapp-2/commit/06ab88c1a7c4c32b3259d5ddb9167ef9c683263a#diff-b2026ef1d30ddb56a9020ffc15ca1379R40 |
| **Bug description** |
| The problem in this bug is that it can’t delete any course in admin mode. This problem is in the class of control role users, and in the class that contains the restcontroller of remove courses. |

Tag Regression: regression-1
Tag regression fixed: regression-fixed-1


| Regression 2 |
| ------------ |
| **Test failed** |
| com.example.demo.integration.TestAPI.java (TestAPI.java:44) |
| **File modified** |
| com.example.demo.security.RestSecurityConfig.java |
| **Link to changes** |
| https://github.com/elastest-experiments/webapp-2/commit/3696fe15760f6ea888d48f95ea290d765d1862ea#diff-b2026ef1d30ddb56a9020ffc15ca1379R32 |
| **Bug description** |
| The problem in this bug is that any person can see the profile of any other person. This problem is in the class at control of the role of users.

Tag Regression: regression-2
Tag regression fixed: regression-fixed-2

| Regression 3 |
| ------------ |
| **Test failed** |
| com.example.demo.e2e.TestE2EFront.java (TestE2EFront.java:130) |
| **File modified** | 
| src/app/moodle/moodleContents.component.html |
| **Link to changes** |
| https://github.com/elastest-experiments/webapp-2/commit/4243b6e046210c06b5951b3423c59818d91d0bd4#diff-3003678b380b45b18c6ae98f1e460c3aR10 <br> https://github.com/elastest-experiments/webapp-2/commit/4243b6e046210c06b5951b3423c59818d91d0bd4#diff-3003678b380b45b18c6ae98f1e460c3aR21 |
| **Bug description** |
| The problem in this bug is that any user can’t download the contents of the courses. This problem is due to the method of download the pdf is misspelled and the browser launch an exception. |

Tag Regression: regression-3
Tag regression fixed: regression-fixed-3

## Webapp 3

| Regression 1 |
| ------------ | 

Tag Regression: regression-1
Tag regression fixed: regression-fixed-1