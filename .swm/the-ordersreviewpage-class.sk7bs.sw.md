---
title: The OrdersReviewPage class
---
This document will provide a comprehensive overview of the <SwmToken path="PlayWrightAutomation/pageobjects/OrdersReviewPage.js" pos="3:2:2" line-data="class OrdersReviewPage">`OrdersReviewPage`</SwmToken> class. We will cover:

1. What <SwmToken path="PlayWrightAutomation/pageobjects/OrdersReviewPage.js" pos="3:2:2" line-data="class OrdersReviewPage">`OrdersReviewPage`</SwmToken> is and its purpose in the codebase.
2. The variables defined in <SwmToken path="PlayWrightAutomation/pageobjects/OrdersReviewPage.js" pos="3:2:2" line-data="class OrdersReviewPage">`OrdersReviewPage`</SwmToken>.
3. The functions implemented in <SwmToken path="PlayWrightAutomation/pageobjects/OrdersReviewPage.js" pos="3:2:2" line-data="class OrdersReviewPage">`OrdersReviewPage`</SwmToken>.

# What is <SwmToken path="PlayWrightAutomation/pageobjects/OrdersReviewPage.js" pos="3:2:2" line-data="class OrdersReviewPage">`OrdersReviewPage`</SwmToken>

<SwmToken path="PlayWrightAutomation/pageobjects/OrdersReviewPage.js" pos="3:2:2" line-data="class OrdersReviewPage">`OrdersReviewPage`</SwmToken> is a class defined in the <SwmPath>[PlayWrightAutomation/pageobjects/OrdersReviewPage.js](PlayWrightAutomation/pageobjects/OrdersReviewPage.js)</SwmPath> file. It is used to manage the order review process in the application, providing methods to interact with various elements on the orders review page.

<SwmSnippet path="/PlayWrightAutomation/pageobjects/OrdersReviewPage.js" line="7">

---

The variable <SwmToken path="PlayWrightAutomation/pageobjects/OrdersReviewPage.js" pos="7:3:3" line-data="    this.page = page;">`page`</SwmToken> is used to store the reference to the Playwright page object, allowing interaction with the web page elements.

```javascript
    this.page = page;
```

---

</SwmSnippet>

<SwmSnippet path="/PlayWrightAutomation/pageobjects/OrdersReviewPage.js" line="8">

---

The variable <SwmToken path="PlayWrightAutomation/pageobjects/OrdersReviewPage.js" pos="8:2:2" line-data="this.country = page.locator(&quot;[placeholder*=&#39;Country&#39;]&quot;);">`country`</SwmToken> is used to locate the input field for entering the country name on the orders review page.

```javascript
this.country = page.locator("[placeholder*='Country']");
```

---

</SwmSnippet>

<SwmSnippet path="/PlayWrightAutomation/pageobjects/OrdersReviewPage.js" line="9">

---

The variable <SwmToken path="PlayWrightAutomation/pageobjects/OrdersReviewPage.js" pos="9:2:2" line-data="this.dropdown = page.locator(&quot;.ta-results&quot;);">`dropdown`</SwmToken> is used to locate the dropdown menu that appears when selecting a country.

```javascript
this.dropdown = page.locator(".ta-results");
```

---

</SwmSnippet>

<SwmSnippet path="/PlayWrightAutomation/pageobjects/OrdersReviewPage.js" line="10">

---

The variable <SwmToken path="PlayWrightAutomation/pageobjects/OrdersReviewPage.js" pos="10:2:2" line-data="this.emailId = page.locator(&quot;.user__name [type=&#39;text&#39;]&quot;).first();">`emailId`</SwmToken> is used to locate the email input field where the user can enter their email address.

```javascript
this.emailId = page.locator(".user__name [type='text']").first();
```

---

</SwmSnippet>

<SwmSnippet path="/PlayWrightAutomation/pageobjects/OrdersReviewPage.js" line="11">

---

The variable <SwmToken path="PlayWrightAutomation/pageobjects/OrdersReviewPage.js" pos="11:2:2" line-data="this.submit =  page.locator(&quot;.action__submit&quot;);">`submit`</SwmToken> is used to locate the submit button on the orders review page.

```javascript
this.submit =  page.locator(".action__submit");
```

---

</SwmSnippet>

<SwmSnippet path="/PlayWrightAutomation/pageobjects/OrdersReviewPage.js" line="12">

---

The variable <SwmToken path="PlayWrightAutomation/pageobjects/OrdersReviewPage.js" pos="12:2:2" line-data="this.orderConfirmationText = page.locator(&quot;.hero-primary&quot;);">`orderConfirmationText`</SwmToken> is used to locate the text element that confirms the order submission.

```javascript
this.orderConfirmationText = page.locator(".hero-primary");
```

---

</SwmSnippet>

<SwmSnippet path="/PlayWrightAutomation/pageobjects/OrdersReviewPage.js" line="13">

---

The variable <SwmToken path="PlayWrightAutomation/pageobjects/OrdersReviewPage.js" pos="13:2:2" line-data="this.orderId = page.locator(&quot;.em-spacer-1 .ng-star-inserted&quot;);">`orderId`</SwmToken> is used to locate the element that displays the order ID after submission.

```javascript
this.orderId = page.locator(".em-spacer-1 .ng-star-inserted");
```

---

</SwmSnippet>

<SwmSnippet path="/PlayWrightAutomation/pageobjects/OrdersReviewPage.js" line="16">

---

The function <SwmToken path="PlayWrightAutomation/pageobjects/OrdersReviewPage.js" pos="16:2:2" line-data="async searchCountryAndSelect(countryCode,countryName)">`searchCountryAndSelect`</SwmToken> is used to search for a country in the dropdown and select it based on the provided country name.

```javascript
async searchCountryAndSelect(countryCode,countryName)
{
    await this.country.pressSequentially("ind");
   // await this.country.fill(countryCode,{delay:100});
    await this.dropdown.waitFor();
    const optionsCount = await this.dropdown.locator("button").count();
    for(let i =0;i< optionsCount; ++i)
    {
      const  text =  await this.dropdown.locator("button").nth(i).textContent();
        if(text.trim() === countryName)
        {
           await this.dropdown.locator("button").nth(i).click();
           break;
        }
    }

```

---

</SwmSnippet>

<SwmSnippet path="/PlayWrightAutomation/pageobjects/OrdersReviewPage.js" line="34">

---

The function <SwmToken path="PlayWrightAutomation/pageobjects/OrdersReviewPage.js" pos="34:2:2" line-data="async VerifyEmailId(username)">`VerifyEmailId`</SwmToken> is used to verify that the email ID entered matches the expected username.

```javascript
async VerifyEmailId(username)
{
    await expect(this.emailId).toHaveText(username);
}
```

---

</SwmSnippet>

<SwmSnippet path="/PlayWrightAutomation/pageobjects/OrdersReviewPage.js" line="39">

---

The function <SwmToken path="PlayWrightAutomation/pageobjects/OrdersReviewPage.js" pos="39:2:2" line-data="async SubmitAndGetOrderId()">`SubmitAndGetOrderId`</SwmToken> is used to submit the order and retrieve the order ID from the confirmation message.

```javascript
async SubmitAndGetOrderId()
{
 await this.submit.click();
 await expect(this.orderConfirmationText).toHaveText(" Thankyou for the order. ");
 return await this.orderId.textContent();
}
```

---

</SwmSnippet>

# Usage

## <SwmToken path="PlayWrightAutomation/pageobjects/OrdersReviewPage.js" pos="3:2:2" line-data="class OrdersReviewPage">`OrdersReviewPage`</SwmToken> Usage

The <SwmToken path="PlayWrightAutomation/pageobjects/OrdersReviewPage.js" pos="3:2:2" line-data="class OrdersReviewPage">`OrdersReviewPage`</SwmToken> class is instantiated in the `POManager` file, where it is assigned to the `ordersReviewPage` property. This indicates that it plays a role in managing the order review process within the application.

## Method Interaction

In the <SwmToken path="PlayWrightAutomation/pageobjects/OrdersReviewPage.js" pos="3:2:2" line-data="class OrdersReviewPage">`OrdersReviewPage`</SwmToken> class, a method retrieves the text content of the order ID, showcasing its functionality in displaying order details.

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBUUElM0ElM0Fyb2JTd2ltbQ==" repo-name="QA"><sup>Powered by [Swimm](https://bosch-test.swimm.cloud/)</sup></SwmMeta>
