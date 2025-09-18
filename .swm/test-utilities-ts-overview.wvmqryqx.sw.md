---
title: Test Utilities TS Overview
---
# Overview of Test Utilities TS

Test Utilities TS is a collection of TypeScript utility modules located in the <SwmPath>[PlayWrightAutomation/utils_ts/](PlayWrightAutomation/utils_ts/)</SwmPath> directory. These utilities provide reusable functions and helpers designed to support and streamline automation testing using Playwright.

The utilities encapsulate common testing tasks such as API interactions, base test setups, and test data management. By abstracting these repetitive operations, they help maintain cleaner and more maintainable test scripts.

# Purpose and Benefits

The primary purpose of Test Utilities TS is to facilitate efficient test development by providing shared modules that handle routine tasks. This modular design promotes code reuse across different test cases and reduces duplication, allowing developers to focus on test logic rather than setup and infrastructure.

# Usage in the Codebase

Developers incorporate Test Utilities TS by importing the relevant utility modules into their test files. For example, API helper modules can be imported to perform backend requests, while base test setup modules prepare the test environment consistently before tests run. This approach ensures that tests start with a uniform configuration and reduces boilerplate code.

# Example Usage

A common use case is importing a base test setup utility to initialize the test environment prior to executing Playwright tests. This guarantees consistent test conditions and simplifies test maintenance by centralizing setup logic.

<SwmSnippet path="/PlayWrightAutomation/utils_ts/APiUtils.ts" line="13">

---

Test Utilities TS includes modules that handle API endpoints critical for testing workflows. For instance, the login endpoint is accessed via a POST request to '<https://rahulshettyacademy.com/api/ecom/auth/login>'. This endpoint authenticates users by sending login credentials and returns a token used for subsequent authenticated requests.

```typescript
    async getToken()
     {
        const loginResponse =  await  this.apiContext.post("https://rahulshettyacademy.com/api/ecom/auth/login",
        {
            data:this.loginPayLoad
         } )//200,201,
        const loginResponseJson = await loginResponse.json();
        const token =loginResponseJson.token;
        console.log(token);
        return token;

    }
```

---

</SwmSnippet>

<SwmSnippet path="/PlayWrightAutomation/utils_ts/APiUtils.ts" line="26">

---

Another key endpoint is the create order endpoint, accessed via a POST request to '<https://rahulshettyacademy.com/api/ecom/order/create-order>'. This endpoint requires an authorization token obtained from the login endpoint and an order payload containing order details. The response includes order information such as the order ID, which is extracted and returned along with the token.

```typescript
    async createOrder(orderPayLoad:string)
    {
        let response = {token : String,orderId : String};
       response.token = await this.getToken();
    const orderResponse = await this.apiContext.post("https://rahulshettyacademy.com/api/ecom/order/create-order",
   {
    data : orderPayLoad,
    headers:{
                'Authorization' :response.token,
                'Content-Type'  : 'application/json'
            },

   })
   const orderResponseJson =await orderResponse.json();
   console.log(orderResponseJson);
  const orderId = orderResponseJson.orders[0];
   response.orderId = orderId;

   return response;
}
```

---

</SwmSnippet>

# Summary

In summary, Test Utilities TS provides a modular set of TypeScript utilities that abstract common testing tasks such as API calls, test setup, and data handling. These utilities enhance test maintainability and efficiency by promoting code reuse and consistent test environments.

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBUUElM0ElM0Fyb2JTd2ltbQ==" repo-name="QA"><sup>Powered by [Swimm](https://staging.swimm.cloud/)</sup></SwmMeta>
