---
title: The LoginPage class
---
This document will cover the <SwmToken path="PlayWrightAutomation/pageobjects_ts/LoginPage.ts" pos="4:4:4" line-data="export class LoginPage {">`LoginPage`</SwmToken> class in the PlayWrightAutomation project. We will cover:

1. What is <SwmToken path="PlayWrightAutomation/pageobjects_ts/LoginPage.ts" pos="4:4:4" line-data="export class LoginPage {">`LoginPage`</SwmToken>
2. Variables and functions in <SwmToken path="PlayWrightAutomation/pageobjects_ts/LoginPage.ts" pos="4:4:4" line-data="export class LoginPage {">`LoginPage`</SwmToken>

# What is <SwmToken path="PlayWrightAutomation/pageobjects_ts/LoginPage.ts" pos="4:4:4" line-data="export class LoginPage {">`LoginPage`</SwmToken>

<SwmToken path="PlayWrightAutomation/pageobjects_ts/LoginPage.ts" pos="4:4:4" line-data="export class LoginPage {">`LoginPage`</SwmToken> is a class defined in <SwmPath>[PlayWrightAutomation/pageobjects_ts/LoginPage.ts](PlayWrightAutomation/pageobjects_ts/LoginPage.ts)</SwmPath> that models the login page of a web application for automated testing using Playwright. It encapsulates the elements and actions related to the login page, providing an abstraction to interact with the page during tests.

<SwmSnippet path="/PlayWrightAutomation/pageobjects_ts/LoginPage.ts" line="10">

---

The constructor function initializes the <SwmToken path="PlayWrightAutomation/pageobjects_ts/LoginPage.ts" pos="4:4:4" line-data="export class LoginPage {">`LoginPage`</SwmToken> instance by accepting a Playwright Page object. It sets up the page property and initializes locators for the username input, password input, and sign-in button elements on the login page.

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

The async function <SwmToken path="PlayWrightAutomation/pageobjects_ts/LoginPage.ts" pos="19:2:2" line-data="async goTo()">`goTo`</SwmToken> navigates the Playwright page to the login page URL '<https://rahulshettyacademy.com/client>'. This function is used to open the login page before performing any login actions.

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

The async function <SwmToken path="PlayWrightAutomation/pageobjects_ts/LoginPage.ts" pos="24:2:2" line-data="async validLogin(username:string,password:string)">`validLogin`</SwmToken> performs a login action by filling in the username and password fields with the provided arguments, clicking the sign-in button, and then waiting for the page to reach a network idle state. This function automates the login process for valid credentials.

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

The <SwmToken path="PlayWrightAutomation/pageobjects_ts/LoginPage.ts" pos="4:4:4" line-data="export class LoginPage {">`LoginPage`</SwmToken> class is instantiated within the POManager class, which acts as a manager for different page objects. This instantiation occurs in the constructor of POManager, where a new <SwmToken path="PlayWrightAutomation/pageobjects_ts/LoginPage.ts" pos="4:4:4" line-data="export class LoginPage {">`LoginPage`</SwmToken> object is created using the provided page instance. This setup allows the POManager to provide centralized access to the <SwmToken path="PlayWrightAutomation/pageobjects_ts/LoginPage.ts" pos="4:4:4" line-data="export class LoginPage {">`LoginPage`</SwmToken> functionality along with other page objects like DashboardPage, OrdersHistoryPage, and OrdersReviewPage.

## Usage in POManager

Within the POManager class, the <SwmToken path="PlayWrightAutomation/pageobjects_ts/LoginPage.ts" pos="4:4:4" line-data="export class LoginPage {">`LoginPage`</SwmToken> instance is stored as a property named loginPage. This design pattern facilitates the management of page objects in automated testing or browser interaction scenarios, enabling easy access to the <SwmToken path="PlayWrightAutomation/pageobjects_ts/LoginPage.ts" pos="4:4:4" line-data="export class LoginPage {">`LoginPage`</SwmToken> methods and properties through the POManager instance.

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBUUElM0ElM0Fyb2JTd2ltbQ==" repo-name="QA"><sup>Powered by [Swimm](https://staging.swimm.cloud/)</sup></SwmMeta>
