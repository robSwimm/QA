---
title: test VScode
---
# Introduction

This document walks you through the configuration choice made for Playwright in the file <SwmPath>[PlayWrightAutomation/playwright.config1.js](/PlayWrightAutomation/playwright.config1.js)</SwmPath>. We will cover:

1. Why screenshots are enabled on test failures.
2. How this setting fits into the overall test automation strategy.

# enabling screenshots on test failures

The configuration sets the screenshot option to 'on'. This means Playwright will capture a screenshot automatically whenever a test fails. This helps quickly identify what the UI looked like at the moment of failure without needing to reproduce the issue manually.

<SwmSnippet path="PlayWrightAutomation/playwright.config1.js" line="24">

---

This choice improves debugging efficiency by providing visual context directly from the test run. It also aids in tracking intermittent UI issues that might not be obvious from logs alone.

```
        screenshot : 'on',
```

---

</SwmSnippet>

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBUUElM0ElM0Fyb2JTd2ltbQ==" repo-name="QA"><sup>Powered by [Swimm](https://staging.swimm.cloud/)</sup></SwmMeta>
