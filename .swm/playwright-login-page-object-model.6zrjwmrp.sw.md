---
title: Playwright Login Page Object Model
---
# Introduction

This document explains the design choices behind the Playwright Login Page Object Model implementation. It answers these questions:

1. Why use a Page Object Model (POM) for the login page?
2. How are page elements encapsulated and initialized?
3. How does the login flow get automated through this model?

# why use a page object model for the login page

The <SwmToken path="PlayWrightAutomation/pageobjects_ts/LoginPage.ts" pos="4:4:4" line-data="export class LoginPage {">`LoginPage`</SwmToken> class abstracts the login page details into a reusable object. This keeps test code clean by separating page structure and interaction logic from test assertions. It also centralizes locator definitions, so if the UI changes, only this class needs updates. This approach improves maintainability and readability.

# how page elements are encapsulated and initialized

<SwmSnippet path="/PlayWrightAutomation/pageobjects_ts/LoginPage.ts" line="10">

---

The constructor takes a Playwright Page object and uses it to initialize locators for the username input, password input, and login button. This ties the page elements directly to the Playwright API, enabling interaction methods to use these locators without redefining them. This encapsulation hides the selector details from test scripts.

```typescript
constructor(page:Page)
{
    this.page = page;
    this.signInbutton= page.locator("[value='Login']");
    this.userName = page.locator("#userEmail");
    this.password = page.locator("#userPassword");

}
```

---

</SwmSnippet>

# how the login flow is automated

The <SwmToken path="PlayWrightAutomation/pageobjects_ts/LoginPage.ts" pos="24:2:2" line-data="async validLogin(username:string,password:string)">`validLogin`</SwmToken> method fills in the username and password fields, clicks the login button, and waits for the network to be idle, indicating the login process completed. This method bundles the login steps into a single call, making tests simpler and less error-prone by reusing this flow.

<SwmSnippet path="/PlayWrightAutomation/pageobjects_ts/LoginPage.ts" line="19">

---

The <SwmToken path="PlayWrightAutomation/pageobjects_ts/LoginPage.ts" pos="19:2:2" line-data="async goTo()">`goTo`</SwmToken> method navigates to the login page URL, isolating the navigation step from tests and allowing easy updates if the URL changes.

```typescript
async goTo()
{
    await this.page.goto("https://rahulshettyacademy.com/client");
}

async validLogin(username:string,password:string)
{
    await  this.userName.fill(username);
     await this.password.fill(password);
     await this.signInbutton.click();
     await this.page.waitForLoadState('networkidle');
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBUUElM0ElM0Fyb2JTd2ltbQ==" repo-name="QA"><sup>Powered by [Swimm](https://staging.swimm.cloud/)</sup></SwmMeta>
