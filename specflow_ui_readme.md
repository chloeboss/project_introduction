#### Author Contact Info
```
Chloe Zeng
chloezeng310@gmail.com
+64 021 183 2827
```

#### Repo link
https://github.com/chloeboss/specflow-demo/tree/develop/WebAutomation

# Specflow ui demo
Build in .NETFramework472

Here is the example ui scenario
```Gherkin 
@UI
Feature: UI1

@UI	
Scenario: SignIn Automation Practice Website
	Given Automation Practice Website
	When Try to login
	Then Error should come out

@UI
Scenario: Shopping Website
	Given Automation Practice Website
	When Add item to shopping cart
```


### What contains in project?
* ParallelExecution using Context dependency Injection Bodi
* Extent Report
* Tracking log using Nlog, see in folder specflow-uis
  

### Way to execute tests
1. from VS, open Test Explorer, run the tests, if you wish to run parallel, then select multiple tests to run



### Note
1. if driver version not supported, please update @NugetPackage
