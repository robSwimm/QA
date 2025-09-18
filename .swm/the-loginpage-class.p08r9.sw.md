---
title: The LoginPage class
---
This document covers the <SwmToken path="PlayWrightAutomation/pageobjects_ts/LoginPage.ts" pos="4:4:4" line-data="export class LoginPage {">`LoginPage`</SwmToken> class. We will explain:

1. What <SwmToken path="PlayWrightAutomation/pageobjects_ts/LoginPage.ts" pos="4:4:4" line-data="export class LoginPage {">`LoginPage`</SwmToken> is and its purpose
2. The constructor function
3. The <SwmToken path="PlayWrightAutomation/pageobjects_ts/LoginPage.ts" pos="19:2:2" line-data="async goTo()">`goTo`</SwmToken> function
4. The <SwmToken path="PlayWrightAutomation/pageobjects_ts/LoginPage.ts" pos="24:2:2" line-data="async validLogin(username:string,password:string)">`validLogin`</SwmToken> function

# What is <SwmToken path="PlayWrightAutomation/pageobjects_ts/LoginPage.ts" pos="4:4:4" line-data="export class LoginPage {">`LoginPage`</SwmToken>

<SwmToken path="PlayWrightAutomation/pageobjects_ts/LoginPage.ts" pos="4:4:4" line-data="export class LoginPage {">`LoginPage`</SwmToken> is a class defined in <SwmPath>[PlayWrightAutomation/pageobjects_ts/LoginPage.ts](PlayWrightAutomation/pageobjects_ts/LoginPage.ts)</SwmPath> that models the login page of a web application for automated testing using Playwright. It encapsulates the elements and actions related to the login page, enabling tests to interact with the page in a structured and reusable way.

<SwmSnippet path="/PlayWrightAutomation/pageobjects_ts/LoginPage.ts" line="10">

---

The constructor function initializes the <SwmToken path="PlayWrightAutomation/pageobjects_ts/LoginPage.ts" pos="4:4:4" line-data="export class LoginPage {">`LoginPage`</SwmToken> instance with a Playwright Page object. It sets up locators for the username input, password input, and sign-in button elements on the page, allowing subsequent methods to interact with these elements.

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

<SwmSnippet path="/PlayWrightAutomation/pageobjects_ts/LoginPage.ts" line="19">

---

The function <SwmToken path="PlayWrightAutomation/pageobjects_ts/LoginPage.ts" pos="19:2:2" line-data="async goTo()">`goTo`</SwmToken> navigates the browser to the login page URL '<https://rahulshettyacademy.com/client>'. This prepares the page for user interaction or testing.

```typescript
async goTo()
{
    await this.page.goto("https://rahulshettyacademy.com/client");
}
```

---

</SwmSnippet>

<SwmSnippet path="/PlayWrightAutomation/pageobjects_ts/LoginPage.ts" line="24">

---

The function <SwmToken path="PlayWrightAutomation/pageobjects_ts/LoginPage.ts" pos="24:2:2" line-data="async validLogin(username:string,password:string)">`validLogin`</SwmToken> performs a login action by filling the username and password fields with provided credentials, clicking the sign-in button, and then waiting for the page to finish loading network activity. This simulates a user logging into the application.

```typescript
async validLogin(username:string,password:string)
{
    await  this.userName.fill(username);
     await this.password.fill(password);
     await this.signInbutton.click();
     await this.page.waitForLoadState('networkidle');

}
```

---

</SwmSnippet>

# Usage

## <SwmToken path="PlayWrightAutomation/pageobjects_ts/LoginPage.ts" pos="4:4:4" line-data="export class LoginPage {">`LoginPage`</SwmToken>

The <SwmToken path="PlayWrightAutomation/pageobjects_ts/LoginPage.ts" pos="4:4:4" line-data="export class LoginPage {">`LoginPage`</SwmToken> class is instantiated within the POManager class, which acts as a manager for various page objects. This instantiation occurs in the constructor of POManager, where a new <SwmToken path="PlayWrightAutomation/pageobjects_ts/LoginPage.ts" pos="4:4:4" line-data="export class LoginPage {">`LoginPage`</SwmToken> object is created using a page parameter. This setup allows the POManager to provide centralized access to the <SwmToken path="PlayWrightAutomation/pageobjects_ts/LoginPage.ts" pos="4:4:4" line-data="export class LoginPage {">`LoginPage`</SwmToken> functionality alongside other page objects like DashboardPage and OrdersHistoryPage.

## Usage in POManager

Within the POManager class, the <SwmToken path="PlayWrightAutomation/pageobjects_ts/LoginPage.ts" pos="4:4:4" line-data="export class LoginPage {">`LoginPage`</SwmToken> instance is stored as a property named loginPage. This design pattern facilitates organized and modular access to the login page's methods and properties, enabling test scripts or other components to interact with the login page through the POManager instance.

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBUUElM0ElM0Fyb2JTd2ltbQ==" repo-name="QA"><sup>Powered by [Swimm](https://staging.swimm.cloud/)</sup></SwmMeta>
