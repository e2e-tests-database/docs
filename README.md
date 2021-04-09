# E2E Tests Database

E2E Tests Database is a collection of reproducible regressions in real applications and end to end tests.

# Table of contents

- [The Projects](#the-projects)    
- [Requirements](#requirements)    
- [Docker enviroment](#docker-enviroment)
- [Webapp 1](#webapp-1)
    - [Steps to set up Webapp-1 (Only if not use the Docker image)](#steps-to-set-up-webapp-1-only-if-not-use-the-docker-image)
    - [Components of the application](#components-of-the-application)
    - [Regressions](#regressions)
        - [Regression 1](#regression-1)
            - [Move to tags](#move-to-tags)
            - [Run test by hand](#run-test-by-hand)
            - [Run test using Docker image provided](#run-test-using-docker-image-provided)
            - [Check Logs and Videos](#dataset)
        - [Regression 2](#regression-2)
            - [Move to tags](#move-to-tags-1)
            - [Run test by hand](#run-test-by-hand-1)
            - [Run test using Docker image provided](#run-test-using-docker-image-provided-1)
            - [Check Logs and Videos](#dataset-1)
- [Webapp 2](#webapp-2)
    - [Steps to set up Webapp-1 (Only if not use the Docker image)](#steps-to-set-up-webapp-1-only-if-not-use-the-docker-image-1)
    - [Components of the application](#components-of-the-application-1)
    - [Regressions](#regressions-1)
        - [Regression 1](#regression-1-1)
            - [Move to tags](#move-to-tags-2)
            - [Run test by hand](#run-test-by-hand-2)
            - [Run test using Docker image provided](#run-test-using-docker-image-provided-2)
            - [Check Logs and Videos](#dataset-2)
        - [Regression 2](#regression-2-1)
            - [Move to tags](#move-to-tags-3)
            - [Run test by hand](#run-test-by-hand-3)
            - [Run test using Docker image provided](#run-test-using-docker-image-provided-3)
            - [Check Logs and Videos](#dataset-3)
        - [Regression 3](#regression-3)
            - [Move to tags](#move-to-tags-4)
            - [Run test by hand](#run-test-by-hand-4)
            - [Run test using Docker image provided](#run-test-using-docker-image-provided-4)
            - [Check Logs and Videos](#dataset-4)
- [Webapp 3](#webapp-3)
    - [Steps to set up Webapp-1 (Only if not use the Docker image)](#steps-to-set-up-webapp-1-only-if-not-use-the-docker-image-2)
    - [Components of the application](#components-of-the-application-2)
    - [Regressions](#regressions-2)
        - [Regression 1](#regression-1-2)
            - [Move to tags](#move-to-tags-5)
            - [Run test by hand](#run-test-by-hand-5)
            - [Run test using Docker image provided](#run-test-using-docker-image-provided-5)
            - [Check Logs and Videos](#dataset-5)

# The Projects

We have used projects developed in Spring and Angular, the projects simulate real applications.

| Project  | URL | Number of Regressions |
| -------- | --- | :-------------------: |
| Webapp-1 | https://github.com/e2e-tests-database/webapp-1 | 2 |
| Webapp-2 | https://github.com/e2e-tests-database/webapp-2 | 3 |
| Webapp-3 | https://github.com/e2e-tests-database/webapp-3 | 1 |


## Requirements

If you use the database in local you will need the following tools:

* Maven (All projects)
* Git (All projects)
* Java 1.8 (All projects)
* Node 8.x (Webapp-1 and Webapp-2)

The applications Webapp-1 and Webapp-2 using a back-end in Spring and front-end in Angular. The application Webapp-1 use a back-end Spring, and front-end with moustache.

## Docker enviroment

If you don't want to use the local database you can use the docker's image with the all enviroment. The image and explications for running the image are in this page https://github.com/e2e-tests-database/images

## Webapp 1

### Steps to set up Webapp-1 (Only if not use the Docker image)

1. Clone Webapp-1 
* `git clone https://github.com/e2e-tests-database/webapp-1`

2. Install Angular dependencies
* `cd webapp-1/Angular`
* `npm install`

### Components of the application

The application is compose of a back-end in Spring and front-end in angular.

| Part | Folder |
| ---- | ------ |
| back-end | webapp-1/TrackOrJargh |
| front-end | webapp-1/Angular |

The application contains a script for create a Docker image of the application. The script is in the folder `webapp-1/Docker`. To run the script use `create-image.sh name-image`

### Regressions

This application contains two regressions that we can see below:

#### Regression 1

| Documentation for the regression |
| ------------ | 
| **Branch where introduced regression** |
| The name of the branch where introduced regression is *fixed-footer* |
| **Link to branch** |
| https://github.com/e2e-tests-database/webapp-1/tree/fixed-footer |
| **Test failed** |
| com.trackorjargh.e2e.TestE2EFront.java (TestE2EFront.java:27)
| **Link to test** |
| https://github.com/e2e-tests-database/webapp-1/blob/master/TrackOrJargh/src/test/java/com/trackorjargh/e2e/TestE2EFront.java#L27 |
| **File modified** |
| src/app/profile/profile.html | 
| **Link to changes** |
| https://github.com/e2e-tests-database/webapp-1/commit/f29161ce86418e7c23f1d9a26d3327980c21d88f#diff-40ad886a9beb70f673ce1d05d73d7978R100 |
| **Regression description**
| The problem in this bug is the method called when click the button add new list, this method activate variable for collapse and uncollapse the div. The method change the variable “showAddList” but the event collapse listen the variable “isCollapsed”. |

##### Move to tags

We move to the commit where we can see exist a regression and we can also move to the commit where regression fixed using the command `git checkout tag`. 

The tags that we can use: 

| Type tag | Tag |
| -------- | --- |
| **Regression:** | regression-1
| **Regression Fixed:** | regression-fixed-1 |


##### Run test by hand

To run the test, follow these steps:

1. Move to the backend folder.
* `cd webapp-1/TrackOrJargh`
2. Run the test
* `mvn -Dtest=TestE2EFront test`

##### Run test using Docker image provided

To run the regression test:

```
docker run --rm -v /tmp/e2e-dataset/logs:/home/dataset/logs \
		codeurjc/e2e-dataset webapp-1 regression-1
```

To run the regression fixed test:

```
docker run --rm -v /tmp/e2e-dataset/logs:/home/dataset/logs \
		codeurjc/e2e-dataset webapp-1 regression-fixed-1
```

##### Logs and Videos

We also provide logs, videos and comparative logs between the commit with regression and regression fixed commit. This files we can find in this link https://github.com/e2e-tests-database/logsAndVideos/tree/master/Webapp-1/regression-1.

#### Regression 2

| Documentation for the regression |
| ------------ | 
| **Branch where introduced regression** |
| The name of the branch where introduced regression is *refactor-index-charts* |
| **Link to branch** |
| https://github.com/e2e-tests-database/webapp-1/tree/refactor-index-charts |
| **Test failed** |
| com.trackorjargh.e2e.api.TestGraphics.java (TestGraphics.java:56) |
| **Link to test** |
| https://github.com/e2e-tests-database/webapp-1/blob/master/TrackOrJargh/src/test/java/com/trackorjargh/e2e/api/TestGraphics.java#L56 |
| **File modified** |
| com.trackorjargh.apirestcontrolers.ApiGenderController.java |
| **Link to changes** |
| https://github.com/e2e-tests-database/webapp-1/commit/5d21489430545fe4d6e3201876b6ada556e59431#diff-54e63438903cb13be10bf4f44213d2fbR48 |
| **Regression description** |
| The problem in this bug is the method of the api that return the num of genres (shows, films, books). The method failed counting the genres (the variable of count accumulated all). |  

##### Move to tags

We move to the commit where we can see exist a regression and we can also move to the commit where regression fixed using the command `git checkout tag`. 

The tags that we can use: 

| Type tag | Tag | 
| -------- | --- |
| **Regression:** | regression-2
| **Regression Fixed:** | regression-fixed-2 |

##### Run test by hand

To run the test, follow these steps:

1. Move to the backend folder.
* `cd webapp-1/TrackOrJargh`
2. Run the test
* `mvn -Dtest=TestAPIRestTemplate test`

##### Run test using Docker image provided

To run the regression test:

```
docker run --rm -v /tmp/e2e-dataset/logs:/home/dataset/logs \
		codeurjc/e2e-dataset webapp-1 regression-2
```

To run the regression fixed test:

```
docker run --rm -v /tmp/e2e-dataset/logs:/home/dataset/logs \
		codeurjc/e2e-dataset webapp-1 regression-fixed-2
```

##### Logs and Videos

We also provide logs, videos and comparative logs between the commit with regression and regression fixed commit. This files we can find in this link https://github.com/e2e-tests-database/logsAndVideos/tree/master/Webapp-1/regression-2.

## Webapp 2

### Steps to set up Webapp-1 (Only if not use the Docker image)

1. Clone Webapp-2
* `git clone https://github.com/e2e-tests-database/webapp-2`

2. Install Angular dependencies
* `cd webapp-2/Angular`
* `npm install`

### Components of the application

The application is compose of an back-end in Spring and front-end in angular.

| Part | Folder |
| ---- | ------ |
| back-end | webapp-2/AMICOServer |
| front-end | webapp-2/Angular |

The application contains a script for create a Docker image of the application. The script is in the folder `webapp-2/Docker`. To run the script use `create-image.sh name-image`

### Regressions

This application contains two regressions that we can see below:

#### Regression 1

| Documentation for the regression |
| ------------ |
| **Branch where introduced regression** |
| The name of the branch where introduced regression is *fixed-profile* |
| **Link to branch** |
| https://github.com/e2e-tests-database/webapp-2/tree/fixed-profile |
| **Test failed** |
| com.example.demo.integration.TestAPI.java (TestAPI.java:44) |
| **Link to test** |
| https://github.com/e2e-tests-database/webapp-2/blob/master/AMICOServer/src/test/java/com/example/demo/e2e/TestE2EFront.java#L155 |
| **File modified** |
| com.example.demo.security.RestSecurityConfig.java |
| **Link to changes** |
| https://github.com/e2e-tests-database/webapp-2/commit/fef94f4f82819a4e1d2267421a0065866f8cf8a0#diff-b2026ef1d30ddb56a9020ffc15ca1379R32 |
| **Bug description** |
| The problem in this bug is that any person can see the profile of any other person. This problem is in the class at control of the role of users.

##### Move to tags

We move to the commit where we can see exist a regression and we can also move to the commit where regression fixed using the command `git checkout tag`. 

The tags that we can use: 

| Type tag | Tag | 
| -------- | --- |
| **Regression:** | regression-1
| **Regression Fixed:** | regression-fixed-1 |

##### Run test by hand

To run the test, follow these steps:

1. Move to the backend folder.
* `cd webapp-2/AMICOServer`
2. Run the test
* `mvn -Dtest=TestE2EFront#checkShowProfile test`

##### Run test using Docker image provided

To run the regression test:

```
docker run --rm -v /tmp/e2e-dataset/logs:/home/dataset/logs \
		codeurjc/e2e-dataset webapp-2 regression-1
```

To run the regression fixed test:

```
docker run --rm -v /tmp/e2e-dataset/logs:/home/dataset/logs \
		codeurjc/e2e-dataset webapp-2 regression-fixed-1
```

##### Logs and Videos

We also provide logs, videos and comparative logs between the commit with regression and regression fixed commit. This files we can find in this link https://github.com/e2e-tests-database/logsAndVideos/tree/master/Webapp-2/regression-1.

#### Regression 2

| Documentation for the regression |
| ------------ | 
| **Branch where introduced regression** |
| The name of the branch where introduced regression is *changes-admin-page* |
| **Link to branch** |
| https://github.com/e2e-tests-database/webapp-2/tree/changes-admin-page |
| **Test failed** |
| com.example.demo.e2e.TestE2EFront.java (TestE2EFront.java:35) |
| **Link to test** |
| https://github.com/e2e-tests-database/webapp-2/blob/master/AMICOServer/src/test/java/com/example/demo/e2e/TestE2EFront.java#L35 |
| **File modified** |
| com.example.demo.security.RestSecurityConfig.java |
| **Link to changes** |
| https://github.com/e2e-tests-database/webapp-2/commit/3366a5450401ea656b38bb3f251065d0f883da86#diff-b2026ef1d30ddb56a9020ffc15ca1379R40 |
| **Bug description** |
| The problem in this bug is that it can’t delete any course in admin mode. This problem is in the class of control role users, and in the class that contains the restcontroller of remove courses. |

##### Move to tags

We move to the commit where we can see exist a regression and we can also move to the commit where regression fixed using the command `git checkout tag`. 

The tags that we can use: 

| Type tag | Tag | 
| -------- | --- |
| **Regression:** | regression-2
| **Regression Fixed:** | regression-fixed-2 |

##### Run test by hand

To run the test, follow these steps:

1. Move to the backend folder.
* `cd webapp-2/AMICOServer`
2. Run the test
* `mvn -Dtest=TestE2EFront#checkCreateCourse test`

##### Run test using Docker image provided

To run the regression test:

```
docker run --rm -v /tmp/e2e-dataset/logs:/home/dataset/logs \
		codeurjc/e2e-dataset webapp-2 regression-2
```

To run the regression fixed test:

```
docker run --rm -v /tmp/e2e-dataset/logs:/home/dataset/logs \
		codeurjc/e2e-dataset webapp-2 regression-fixed-2
```

##### Logs and Videos

We also provide logs, videos and comparative logs between the commit with regression and regression fixed commit. This files we can find in this link https://github.com/e2e-tests-database/logsAndVideos/tree/master/Webapp-2/regression-2.

#### Regression 3

| Documentation for the regression |
| ------------ |
| **Branch where introduced regression** |
| The name of the branch where introduced regression is *fixed-moodle* |
| **Link to branch** |
| https://github.com/e2e-tests-database/webapp-2/tree/fixed-moodle |
| **Test failed** |
| com.example.demo.e2e.TestE2EFront.java (TestE2EFront.java:130) |
| **File modified** | 
| src/app/moodle/moodleContents.component.html |
| **Link to changes** |
| https://github.com/e2e-tests-database/webapp-2/commit/fe75b4a256b64b74de316f85c6b099a94bb1bfb1#diff-3003678b380b45b18c6ae98f1e460c3aR10 <br> https://https://github.com/e2e-tests-database/webapp-2/commit/fe75b4a256b64b74de316f85c6b099a94bb1bfb1#diff-3003678b380b45b18c6ae98f1e460c3aR211 |
| **Bug description** |
| The problem in this bug is that any user can’t download the contents of the courses. This problem is due to the method of download the pdf is misspelled and the browser launch an exception. |

##### Move to tags 

We move to the commit where we can see exist a regression and we can also move to the commit where regression fixed using the command `git checkout tag`. 

The tags that we can use: 

| Type tag | Tag | 
| -------- | --- |
| **Regression:** | regression-3
| **Regression Fixed:** | regression-fixed-3 |

##### Run test by hand

To run the test, follow these steps:

1. Move to the backend folder.
* `cd webapp-2/AMICOServer`
2. Run the test
* `mvn -Dtest=TestE2EFront#checkDownload test`

##### Run test using Docker image provided

To run the regression test:

```
docker run --rm -v /tmp/e2e-dataset/logs:/home/dataset/logs \
		codeurjc/e2e-dataset webapp-2 regression-3
```

To run the regression fixed test:

```
docker run --rm -v /tmp/e2e-dataset/logs:/home/dataset/logs \
		codeurjc/e2e-dataset webapp-2 regression-fixed-3
```

##### Logs and Videos

We also provide logs, videos and comparative logs between the commit with regression and regression fixed commit. This files we can find in this link https://github.com/e2e-tests-database/logsAndVideos/tree/master/Webapp-2/regression-3.

## Webapp 3

### Steps to set up Webapp-1 (Only if not use the Docker image)

1. Clone Webapp-3
* `git clone https://github.com/e2e-tests-database/webapp-3`


### Components of the application

The application is compose of an back-end in Spring.

| Part | Folder |
| ---- | ------ |
| back-end | webapp-2/BREMS |

The application contains a script for create a Docker image of the application. The script is in the folder `webapp-3/Docker`. To run the script use `create-image.sh name-image`

### Regressions

This application contains two regressions that we can see below:

#### Regression 1

| Documentation for the regression |
| ------------ | 
| **Branch where introduced regression** |
| The name of the branch where introduced regression is *improvement-to-profile* |
| **Link to branch** |
| https://github.com/e2e-tests-database/webapp-3/tree/improvement-to-profile |
| **Test failed** |
| com.brems.e2e.TestE2EFront.java (TestE2EFront.java:27) |
| **Link to test** |
| https://github.com/e2e-tests-database/webapp-3/blob/improvement-to-profile/BREMS/src/test/java/com/brems/e2e/TestE2EFront.java#L27 |
| **File modified** |
| appSpring.security.SecurityConfiguration.java | 
| **Link to changes** |
| https://github.com/e2e-tests-database/webapp-3/commit/218c5bf20d3a58df2119338b64b54b79809d46e6#diff-736e54c81e6fb4e39639a611b132b965R33 |
| **Regression description**
| The problem in this bug is that any user of the application can see administration panel and realize changes in the platform. |

##### Move to tags 

We move to the commit where we can see exist a regression and we can also move to the commit where regression fixed using the command `git checkout tag`. 

The tags that we can use: 

| Type tag | Tag | 
| -------- | --- |
| **Regression:** | regression-1
| **Regression Fixed:** | regression-fixed-1 |

##### Run test by hand

To run the test, follow these steps:

1. Move to the backend folder.
* `cd webapp-2/BREMS`
2. Run the test
* `mvn -Dtest=TestE2EFront#checkShowAdminPage test`

##### Run test using Docker image provided

To run the regression test:

```
docker run --rm -v /tmp/e2e-dataset/logs:/home/dataset/logs \
		codeurjc/e2e-dataset webapp-3 regression-1
```

To run the regression fixed test:

```
docker run --rm -v /tmp/e2e-dataset/logs:/home/dataset/logs \
		codeurjc/e2e-dataset webapp-3 regression-fixed-1
```

##### Logs and Videos

We also provide logs, videos and comparative logs between the commit with regression and regression fixed commit. This files we can find in this link https://github.com/e2e-tests-database/logsAndVideos/tree/master/Webapp-3/regression-1.
