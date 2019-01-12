### cukes
---
https://github.com/ctco/cukes

```java
Feature: Gadgets are great!
  Background:
    Given baseUri is http://my-server.com/rest/
  Scenario: Should create another Gadget object
    Given request body from file gadgets/requests/newGadget.json
    And content type is "application/json"
    
    When the client performs POST request on /gadgets
    Then status code is 201
    And header Location contains "http://localhost:8080/gadgets/"
    
    When the client performs GET request on {(header.Location)}
    Then status code is 200
    And response contains property "id" with value other than "2000"
    And response contains property "name" with value "Nexus 9"
    And response does not contain property "updateDate"
```

```
<dependency>
  <groupId>lv.ctoco.cukes</groupId>
  <artifactId>cukes-rest</artifactId>
  <version>${cukes-rest.version}</version>
</dependency>

<dependency>
  <groupId>lv.ctco.cukes</groupId>
  <artifactId>cukes-rest-loadrunner</artifactId>
  <version>${cukes-rest.version}</version>
</dependency>
```


```
```
