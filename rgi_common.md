# RGI Common
This section contains the common operativity libraries and steps for NRT Automation test stack.
- [RGI Common](#rgi-common)
  - [Libraries](#libraries)
    - [GlobalShare](#globalshare)
    - [Common Base Lib](#common-base-lib)
    - [Cucumber Runner Lib](#cucumber-runner-lib)
    - [Performance Lib](#performance-lib)
  - [Steps](#steps)
    - [Open login page](#open-login-page)
    - [Change portal board](#change-portal-board)
    - [Remove session](#remove-session)

## Libraries 
All common Playwright libraries are listed below, each with a short description of its capabilities; for further details on installation and usage use the provided GitLab link for every library.
### GlobalShare
This project contains a common set of utilities for playwright tests to add common share area between scenarios inside a single feature file.

[link to GitLab](https://git.ad.rgigroup.com/tes/automatic-test-utils/playwright-globalshare-lib)
### Common Base Lib
This project contains a set of base standard class to be used to implement the Page Object classes with playwright.

[link to GitLab]((https://git.ad.rgigroup.com/tes/automatic-test-utils/playwright-common-base-lib))
### Cucumber Runner Lib
This project contains a common set of utilities for playwright tests with cucumber runner.
The library contains the hooks to start and initialize the browser and some basic functions.

[link to GitLab](https://git.ad.rgigroup.com/tes/automatic-test-utils/playwright-cucumber-runner-lib)
### Performance Lib

This library allows to send to an ElasticSearch document to collect the following metrics:

* Browser Memory Statistics:
  * jsHeapSizeLimit
  * usedJSHeapSize
  * totalJSHeapSize
* Test/Steps duration and Status

[link to GitLab](https://git.ad.rgigroup.com/tes/automatic-test-utils/playwright-performance-lib)

## Steps
This section contains a few simple snippets to begin use our common libraries for some common and simple Pass Portal Operations.
Proper import of PortalPage is required

```typescript
import { PortalPage } from "../models/cross/portal.page";
```

### Open login page

```typescript
Given("Open login page", async function (this: OurWorld) {
    this.attach("PPO URL: " + this.parameters.basePPOUrl);
    await this.page.goto(this.parameters.basePPOUrl + 'portal/#!/login');
    await LoginPage.check(this.page);
})

```

### Change portal board 

```typescript
Then("Select board {string}", async function (this: OurWorld, boardName: string) {
    await PortalPage.openBoard(boardName)
})
```
### Remove session

```typescript
Then("Logout", async function (this: OurWorld) {
    await PortalPage.logout();
})

```



[[Return to main page](./main-page-nrt.md)] - [[Previuous chapter (Basic Concept)](./basic_concept.md)] - [[Next chapter (First Test)](./first_test.md)]