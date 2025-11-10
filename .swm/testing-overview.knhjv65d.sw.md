---
title: Testing overview
---
## Testing god&nbsp;

We use {{UNITTEST FRAMEWORK (e.g., jest)}} for unit tests, and {{E2E FRAMEWORK (e.g., cypress)}} for our end-to-end tests.

## Running what what in my&nbsp;

### Configure automation user and password

To run the tests, you first need to configure the user and password.

### Run the tests

<SwmSnippet path="/PlayWrightAutomation/playwright.config.js" line="8">

---

Here we set the maximum duration for a test to run with `timeout` and the maximum wait time for expectations with `expect.timeout`.

```javascript
  /* Maximum time one test can run for. */
  timeout: 30 * 1000,
  expect: {
  
    timeout: 5000
  },
  
```

---

</SwmSnippet>

`yarn test`

## Writing tests

### Assertions

{{Add examples of common assertions used by tests}}

<SwmSnippetPlaceholder>

For example, in this test we...

</SwmSnippetPlaceholder>

### Best Practices

When writing tests, we follow a few guidelines.

A group of tests is called a "suite". We now have several test suites, each one aims to test a certain set of features in the app. For example, {{path for a test file}} tests the {{feature's name}} feature.

{{Add specific best practices you would like to share}}

<SwmSnippetPlaceholder>

For example, in this test - notice how we...

</SwmSnippetPlaceholder>

<SwmSnippetPlaceholder>

In this test, we...

</SwmSnippetPlaceholder>

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBUUElM0ElM0Fyb2JTd2ltbQ==" repo-name="QA"><sup>Powered by [Swimm](https://staging.swimm.cloud/)</sup></SwmMeta>
