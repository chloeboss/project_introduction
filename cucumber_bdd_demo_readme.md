#### Author Contact Info
```
Chloe Zeng
chloezeng310@gmail.com
+64 021 183 2827
```
#### Repo link
https://github.com/chloeboss/cucumber-bdd-demo


# Cucumber BDD Demo

This automation framework is to API layer and UI layer. Both projects are using Cucumber BDD Style.

### UI automation introduction
UI part is a _Java Maven_ project which using _Selenium, Junit, Cucumber under Page Object Design Pattern_. 
> Reason behind is Page Object Pattern technique provides a solution for working with multiple web pages and prevents unwanted code duplication and enables an uncomplicated solution for code maintenance


### API automation introduction
There are multiple options to test Api eg: Postman, Swagger. In this Demo, I am using Rest Assured which is one of the most used library for REST API automation testing.

> Rest-Assured is a Java-based library that is used to test RESTful Web Services. This library behaves like a headless Client to access REST web services. We can create highly customize-able HTTP Requests to send to the Restful server. This enables us to test a wide variety of Request combinations and in turn test different combinations of core business logic.

### Test Scenario
Here test two scenarios which covers both UI and Api
1. API endpoint: https://jsonplaceholder.typicode.com/todos
2. UI website https://www.countdown.co.nz/
```Gherkin 
@countdown @testEnv
Feature: This is feature about Website called Countdown

  @chrome
  Scenario: This is close easyEmailSignup page
    Given "Countdown" website
    When I close "easyEmailSignup"
    Then I should in "Countdown" Page

  @chrome @headless
  Scenario Outline: This is Login Scenario
    Given "CountdownLogin" website
    When Login with incorrect "<EmailAddress>" and "<password>" in "Countdown" Page
    Then Error would show up in "CountdownLogin" Page

    Examples:
      | EmailAddress             | password  |
      | chloezeng310@gmail.com   | password  |
      | tester@gmail.com         | invalid   |
```
```Gherkin 
@api @testEnv
Feature: This is feature about API-Todo

  @api
  Scenario: Get post example : Get the list of all todos
    When Send GET http request
    Then I should receive SUCCESS response code 200

  @api
  Scenario: Get post example : GET a to-do
    When Send GET http request with Id 25
    Then I should receive SUCCESS response code 200

  @api
  Scenario: Post post example : Post a to-do
    When Send POST http request with Id 25
    Then I should receive SUCCESS response code 201

  @api
  Scenario: Put post example : Update a to-do
    When Send PUT http request with Id 25
    Then I should receive SUCCESS response code 200

  @api
  Scenario: Delete post example : delete a to-do
    When Send DELETE http request with Id 25
    Then I should receive SUCCESS response code 200

```
### What contains in project?
* It can run with different browsers, also provides **_Headless_** option.
 (default by **_chrome_** you can find setting in **_config.properties_**)
* It allows parallel test execution by using _maven-surefire-plugin_
* In `RunCucumber` file, you can run scenarios with a particular tag. like @chrome, @headless, @api, @countdown
* Using `dynamic XPath` and `Wait till` to locate UI elements
* Using `PicoContainer` as Dependency Injection (DI) Containers to Sharing Test Context between Cucumber Step Definitions
* Using `ScenarioContext` & `Java Hash Map`to store and share test date between steps

### Reporting
* Report would be auto generated when run via maven. Please see attachment report1.
* Or you can find here under Target file _**testReport.html**_, Please see attachment report2.


### Way to execute the tests
1. `mvn clean test` (please see note if it doesn't work)
2. run from `feature` file
3. run `RunCucumberTest` with Junit


### Run in Cloud Environment
Run in Azure Pipeline
https://dev.azure.com/chlozeng/MyFirstProject/_release?_a=releases&view=mine&definitionId=9

![Test Image 6](images/cucumberBdddemoAzure.png)


### Mock Data & Log
TBD









