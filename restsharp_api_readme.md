
#### Author Contact Info
```
Chloe Zeng
chloezeng310@gmail.com
+64 021 183 2827
```

#### Repo link
https://github.com/chloeboss/specflow-demo/tree/develop/ApiAutomation


# Restsharp specflow Api Demo
There are multiple options to test Api eg: Postman, Swagger. In this Demo, I am using RestSharp which is one of the most used library for REST API automation testing. Also, this project is using BDD style
> RestSharp is a c# based library that is used to test RESTful Web Services. This library behaves like a headless Client to access REST web services.

> Rest-Sharp library also provides ability to validate the HTTP Responses received from server. For e.g. we can verify the Status code, Status message, Headers and even the Body of the response. This makes Rest-Assured a very flexible library that can be used for testing.
### Test Scenario
Here is the example Api scenario
```Gherkin 
API endpoint: https://jsonplaceholder.typicode.com/todos
@Api
Feature: API feature

@Api
Scenario: GET Todos
When Send GET method
Then success code 200
```

### What contains in project?
* Validate Response Status and Header using RestSharp
* Read JSON Response Body using RestSharp
* Send Post/Get/Delete/Put HTTP request 
* Deserialize Json Response
* ParallelExecution using Context dependency Injection Bodi


### Way to execute the tests
1. VS from Test Explorer


### Run in Cloud Environment
Run in Azure Pipeline
https://dev.azure.com/chlozeng/MyFirstProject/_release?_a=releases&view=mine&definitionId=9

![Test Image 6](images/specflow_demo_azure.png)


### Todo
Mock Data & Log
JWT token

### useful links
https://restsharp.dev/
