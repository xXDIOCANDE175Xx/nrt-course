# Basic concept
## Summary
- [Basic concept](#basic-concept)
  - [Summary](#summary)
  - [What we are testing?](#what-we-are-testing)
  - [Directory files explanation](#directory-files-explanation)
    - [cucumber.js](#cucumberjs)
    - [environment.js](#environmentjs)
    - [e2e-test/models](#e2e-testmodels)
    - [e2e-test/step-definitions](#e2e-teststep-definitions)
    - [e2e-test/features](#e2e-testfeatures)
    - [e2e-test/Utils](#e2e-testutils)
  - [Work with PlayWright](#work-with-playwright)
    - [Pages](#pages)
    - [Selectors](#selectors)

  

## What we are testing?
Automatic testing is a process in which software tests are automatically run by a computer, without the need for human intervention. 
## Directory files explanation

The directory will have a tree similar to this
```sh
.
├── cucumber.js
├──  e2e-test
|   ├── debugfeatures
│   ├── features
│   ├── models
│   ├── step-definitions
│   └── Utils
├── environment.js
├── node_modules
├── package.json
├── package-lock.json
└── tsconfig.json
```
### cucumber.js

This file contains the runner parameter configuration ([See runner](./running.md))

We can find all parameters of the target environment listed as a module export

### environment.js

In this file all the test target environments are listed, the syntax is like this:
```javascript
module.exports = { 
    AUTO_Parameters: {
        basePPOUrl: "url",
        basePIUrl: "url2",
        mockANIAUrl: "url3",
        baseDBUrl: "url connection",
        credentialDB: { username: "username", password: "password" },
        PIContext: "PASS INS Context"
  },
  ...
 }
```

### e2e-test/models

This folder contains all the pages or cards scripts . They are typescript classes that extend the ModelPage class ([See RGI Common](./rgi_common.md)). 

These files can have different suffixes based on the type of item they are (*.page.ts* in case it's a page or *.card.ts* if it's a card inside a page ).

### e2e-test/step-definitions

In this folder, we insert the files containing the cucumber steps, all files will have a suffix like *.steps.ts*.

### e2e-test/features


This folder contains the feature files written in Gherkin language that describe our test case.

By convention, the names of the feature files must be explanatory of their function, written in Italian and with the first capital letter

### e2e-test/Utils

This folder is used to collect those libraries tailored to the project and which will have a general utility *(e.g. a function that generates a valid license plate)*

## Work with PlayWright

### Pages
The class we are working on and which refers to the page/card is extended by the ModelPage class. Each page has a method to instantiate it. To use the page and its methods we must first call this method passing an object of type Page as a parameter
```typescript
check(page:Page){}
```

### Selectors

All classes contain private attributes called selectors which uniquely identify the objects on the page

Selector uses most common jQuery syntax but PlayWright adds very interesting element localization functions, such as being able to use the page layout to search for elements with the most difficult to identify selectors (More info on the PlayWright [docs](https://playwright.dev/docs/locators)). 

















---

[[Return to main page](./main-page-nrt.md)] - [[Previuous chapter (Setup)](./setup.md)] - [[Next chapter (RGI common)](./rgi_common.md)]