# AutomationTest-Rest-API
AutomationTest-Rest-API
This project provides Backend APIs for properties rental websites , IOS and Android devices.

## Getting Started

### Prerequisites

- [Git](https://git-scm.com/) Source Code Management
- [JDK8](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) JDK 1.8
- [Spring Boot](http://projects.spring.io/spring-boot/) Get App up and running as quickly as possible.
- [Maven 3](https://maven.apache.org/download.cgi) Maven Build Tool
- [Junit 4](http://junit.org/junit4/) Unit Testing Tool
- [Mysql](https://www.mysql.com/) - Databse
- [Swagger](http://swagger.io/swagger-ui/) - Swagger UI is a dependency-free collection of HTML, Javascript, and CSS assets that dynamically generate beautiful documentation and sandbox from a Swagger-compliant API.
- [Postman](http://www.getpostman.com) - Postman, tool for API testing (Manual, Automation)

### Install Postman

1. Open a Google chrome.

2. Click on: http://www.getpostman.com, click the gray button 「Chrome App (Free)」 to install it.
![](https://raw.githubusercontent.com/lilliancheng2012/lilliancheng2012.github.io/master/public/img/posts/19-09-16/install%20postman.PNG)

### Run Rent API Application
Run `mvn spring-boot:run` to start Rest Rent APi service. After server starting, type `http://localhost:8080/api/swagger-ui.html` to check the APIs in the Swagger Pages.
![](https://raw.githubusercontent.com/lilliancheng2012/lilliancheng2012.github.io/master/public/img/posts/18-09-16/Swagger.PNG)

### Prepare Test Cases

1. Open Postman form Chrome.

2. Click the new folder button 'Create a new collection' and named your project.
![](https://raw.githubusercontent.com/lilliancheng2012/lilliancheng2012.github.io/master/public/img/posts/19-09-16/Create%20a%20new%20collection.PNG)

3. Create new case for API call in 'New Tab': 1) Select an URL

4. Create new case for API call in 'New Tab': 2) Select API Call (GET/Put/POST/DELETE)

5. Create new case for API call in 'New Tab': 3) Set Authorization, Header, Body Information accordingly your API call (Please refer `http://localhost:8080/api/swagger-ui.html` for details)
![](https://raw.githubusercontent.com/lilliancheng2012/lilliancheng2012.github.io/master/public/img/posts/19-09-16/Header.PNG)
![](https://raw.githubusercontent.com/lilliancheng2012/lilliancheng2012.github.io/master/public/img/posts/19-09-16/Body.PNG)

6. Create new case for API call in 'New Tab': 4) Set Tests to verify according your API
![](https://raw.githubusercontent.com/lilliancheng2012/lilliancheng2012.github.io/master/public/img/posts/19-09-16/Tests%20verify.PNG)

7. Create new case for API call in 'New Tab': 5) Click on send to perform your API call
![](https://raw.githubusercontent.com/lilliancheng2012/lilliancheng2012.github.io/master/public/img/posts/19-09-16/click%20on%20send.PNG)

8. Save the case, you can add Each API call in collection.
![](https://raw.githubusercontent.com/lilliancheng2012/lilliancheng2012.github.io/master/public/img/posts/19-09-16/Save%20request.PNG)

### Example for set parameter

1. For this createInfo API, eg: if you want to get this response id to use for other test case's data
![](https://raw.githubusercontent.com/lilliancheng2012/lilliancheng2012.github.io/master/public/img/posts/20-09-16/0.PNG)
 
2. You can add parameter in 'Manage Environments' if needed:
![](https://raw.githubusercontent.com/lilliancheng2012/lilliancheng2012.github.io/master/public/img/posts/20-09-16/Manage%20Env.1.PNG)

3. After added, the environment display like this:
![](https://raw.githubusercontent.com/lilliancheng2012/lilliancheng2012.github.io/master/public/img/posts/20-09-16/Manage%20Env.2.PNG)

4. Choose and make sure we used the correct environment when execute test case.
![](https://raw.githubusercontent.com/lilliancheng2012/lilliancheng2012.github.io/master/public/img/posts/20-09-16/6.PNG)

5. Add command to capture the id `registeredInfoID` in 'Tests':
![](https://raw.githubusercontent.com/lilliancheng2012/lilliancheng2012.github.io/master/public/img/posts/20-09-16/2.PNG)

6. Click on Send button to execute this case, and then click the eye, you will see the `registeredInfoID` had been recorded there.
![](https://raw.githubusercontent.com/lilliancheng2012/lilliancheng2012.github.io/master/public/img/posts/20-09-16/1.PNG)

7. Use this id in other API's test case, for example updateInfo API, update `"id":"{{registeredInfoID}}"` in Body Information.
![](https://raw.githubusercontent.com/lilliancheng2012/lilliancheng2012.github.io/master/public/img/posts/20-09-16/3.PNG)

8. Executed this updateInfo API test case, and click on the eye to check the recorded `registeredInfoID` is the same one.
![](https://raw.githubusercontent.com/lilliancheng2012/lilliancheng2012.github.io/master/public/img/posts/20-09-16/4.PNG)

9. You can check in DB, the fields' value have been updated.
![](https://raw.githubusercontent.com/lilliancheng2012/lilliancheng2012.github.io/master/public/img/posts/20-09-16/5.PNG)

10. Use this id in deleteInfoById API, update the URL `/id` to `/{{registeredInfoID}}` .
![](https://raw.githubusercontent.com/lilliancheng2012/lilliancheng2012.github.io/master/public/img/posts/20-09-16/7.PNG)

11. Execute this deleteInfoById API's case, then click on the eye to check the recorded `registeredInfoID` is the same one.

12. Check on the DB, this id been deleted already.

13. You can edit your parameter in 'Manage Environments':
![](https://raw.githubusercontent.com/lilliancheng2012/lilliancheng2012.github.io/master/public/img/posts/20-09-16/Manage%20Env.3.PNG)


### Run the test suite.
![](https://raw.githubusercontent.com/lilliancheng2012/lilliancheng2012.github.io/master/public/img/posts/19-09-16/Postman%20run%20test%20suite.PNG)

### Testing REST API Report

After executing the test cases, postman auto generated report.
![](https://raw.githubusercontent.com/lilliancheng2012/lilliancheng2012.github.io/master/public/img/posts/19-09-16/Poseman%20report.PNG)