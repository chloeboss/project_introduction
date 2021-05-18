# Cucumber BDD Demo
[![Build Status](https://dev.azure.com/chlozeng/MyFirstProject/_apis/build/status/chloeboss.cucumber-bdd-demo?branchName=master)](https://dev.azure.com/chlozeng/MyFirstProject/_build/latest?definitionId=11&branchName=master)

<a href="https://dev.azure.com/chlozeng/MyFirstProject/_dashboards/dashboard/0b27603f-ca0a-4ddd-a108-85bae3788ac8"><a href="https://dev.azure.com/chlozeng/MyFirstProject/_dashboards/dashboard/0b27603f-ca0a-4ddd-a108-85bae3788ac8"><img src="https://vsrm.dev.azure.com/chlozeng/_apis/public/Release/badge/d03ef986-5372-4396-a097-e68e1d803625/14/14"/>

#### Author Contact Info
```
Chloe Zeng
chloezeng310@gmail.com
+64 021 183 2827
```
#### Repo link
https://github.com/chloeboss/cucumber-bdd-demo

### UI automation introduction
UI part is a _Java Maven_ project which using _Selenium, Junit, Cucumber under Page Object Design Pattern_. 
> Reason behind is Page Object Pattern technique provides a solution for working with multiple web pages and prevents unwanted code duplication and enables an uncomplicated solution for code maintenance

### Test Scenario
UI website https://www.countdown.co.nz/
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


### Continuous Integration
Run in Azure Pipeline
https://dev.azure.com/chlozeng/MyFirstProject/_release?view=all&_a=releases&definitionId=14
<img src="images/cucumberBdddemoAzure.png" alt="cucumberBdddemoAzure" width="700"/>



### Mock Data & Log
TBD









