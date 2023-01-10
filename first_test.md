# First test

## Youtube search

The first test you can try to perform to understand the NRT mechanism is a simple youtube search and click on the first result

Your working directory  

```gherkin
#e2e-test/features/myFirstTest.feature

Feature: My test case
    Scenario: Youtube search
        Given Open youtube page
        Then Fill the search bar with "Hello World"
        And Click on first element
        And Close page
```
Each step is referenced in a typescript file where the name has the suffix *.steps.ts* and its structure will be like

```typescript
//e2e-test/steps-definition/mySteps.steps.ts

import { MyTestPage } from '../models/MyTest.page.ts';

Then("Open browser page", async function(this:OurWorld){
    await this.page.goto("http://youtube.com/")
    await MyTestPage.check(this.page)
})
```
The appearance of a page in which operations will be performed is like this:
```typescript
//e2e-test/models/MyTest.page.ts

import { ModelPage } from '@rgi/playwright-common-base-lib';

export class MyTestPage extends ModelPage {
    private static cardSelector: string = 'div#content';
    private static searchBar: string = this.cardSelector + ' >> input[id="search"]';

    static async check(currentPage: any) {
        MyTestPage.setPage(currentPage);
        await this.page.waitForSelector(this.cardSelector);
    }

    static async fillInputBox(text:string){
        await this.page.locator(this.searchBar).fill(text)
    }

    static async pressEnterForSearch(){
        await Promise.all([
            this.page.waitResponseByMethod('youtubei/v1/search','POST',20000),
            this.page.locator(this.searchBar).press('Enter')  
        ]) 
        
    }

    ...
}

```


---

[[Return to main page](./0_NRT.md)] - [[Previuous chapter (Setup)](./1_SETUP.md)] - [[Next chapter (Running)](./2_FIRST_TEST.md)]