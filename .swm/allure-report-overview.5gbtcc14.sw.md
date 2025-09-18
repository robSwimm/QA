---
title: Allure Report Overview
---
# What is Allure Report

Allure Report is a comprehensive test reporting tool designed to collect, aggregate, and visualize automated test results. It provides teams with an intuitive web-based interface to analyze the quality and stability of their software by presenting detailed insights from test executions.

# How Allure Report Works

Automated test frameworks generate result files in formats such as JSON and CSV. Allure Report consumes these files to build an interactive dashboard that displays detailed information about test runs. This includes statistics, execution environments, test categories, and trends over time, enabling teams to monitor software quality effectively.

# Report Structure and Data Storage

The report organizes test data and results within specific directories. The <SwmToken path="PlayWrightAutomation/allure-report/plugins/behaviors/index.js" pos="139:5:5" line-data="            url: &#39;data/behaviors.json&#39;,">`data`</SwmToken> directory contains JSON and CSV files representing suite structures, timelines, categories, and behaviors. Historical test data is stored in the `history` directory, allowing users to analyze trends and changes across multiple test runs. This structured storage supports comprehensive reporting and trend analysis.

# Widgets and Their Roles

Allure Report features a variety of widgets that present different aspects of test results. These include summary, duration, behaviors, launch, history trend, severity, categories trend, retry trend, suites, status chart, duration trend, executors, and categories widgets. Each widget corresponds to a JSON file located in the <SwmToken path="PlayWrightAutomation/allure-report/plugins/behaviors/index.js" pos="145:7:7" line-data="allure.api.addWidget(&#39;widgets&#39;, &#39;behaviors&#39;, allure.components.WidgetStatusView.extend({">`widgets`</SwmToken> directory, facilitating modular and extensible reporting.

# Example of Widget Usage

For instance, the summary widget, defined in <SwmPath>[PlayWrightAutomation/…/widgets/summary.json](PlayWrightAutomation/allure-report/widgets/summary.json)</SwmPath>, provides an overview of aggregated test results. The main dashboard, accessible via <SwmPath>[PlayWrightAutomation/allure-report/index.html](PlayWrightAutomation/allure-report/index.html)</SwmPath>, displays these widgets interactively, allowing users to explore test outcomes in detail. Additionally, the report supports exporting features such as <SwmPath>[PlayWrightAutomation/…/export/mail.html](PlayWrightAutomation/allure-report/export/mail.html)</SwmPath> in the export directory, which enables sharing summary reports via email.

# Extending Allure Report with Plugins

Allure Report supports plugin endpoints to extend its interface with custom tabs and widgets. For example, the behaviors tab is registered using <SwmToken path="PlayWrightAutomation/allure-report/plugins/behaviors/index.js" pos="129:0:4" line-data="allure.api.addTab(&#39;behaviors&#39;, {">`allure.api.addTab`</SwmToken>`(`<SwmToken path="PlayWrightAutomation/allure-report/plugins/behaviors/index.js" pos="129:7:7" line-data="allure.api.addTab(&#39;behaviors&#39;, {">`behaviors`</SwmToken>`, ...)` in the plugin code. This tab is accessible through a specific route and renders a <SwmToken path="PlayWrightAutomation/allure-report/plugins/behaviors/index.js" pos="133:9:9" line-data="        return new allure.components.TreeLayout({">`TreeLayout`</SwmToken> component that loads data from <SwmPath>[PlayWrightAutomation/…/data/behaviors.json](PlayWrightAutomation/allure-report/data/behaviors.json)</SwmPath> and <SwmPath>[PlayWrightAutomation/…/data/behaviors.csv](PlayWrightAutomation/allure-report/data/behaviors.csv)</SwmPath>. This feature allows users to interact with test behaviors grouped by stories or features.

<SwmSnippet path="/PlayWrightAutomation/allure-report/plugins/behaviors/index.js" line="129">

---

The behaviors tab plugin defines a new tab in the report interface with a route pattern that supports navigation through test groups and results. It uses the <SwmToken path="PlayWrightAutomation/allure-report/plugins/behaviors/index.js" pos="133:9:9" line-data="        return new allure.components.TreeLayout({">`TreeLayout`</SwmToken> component to visualize behavior data, enhancing the report's ability to present test results in a structured and meaningful way.

```javascript
allure.api.addTab('behaviors', {
    title: 'tab.behaviors.name', icon: 'fa fa-list',
    route: 'behaviors(/)(:testGroup)(/)(:testResult)(/)(:testResultTab)(/)',
    onEnter: (function (testGroup, testResult, testResultTab) {
        return new allure.components.TreeLayout({
            testGroup: testGroup,
            testResult: testResult,
            testResultTab: testResultTab,
            tabName: 'tab.behaviors.name',
            baseUrl: 'behaviors',
            url: 'data/behaviors.json',
            csvUrl: 'data/behaviors.csv'
        });
    })
});
```

---

</SwmSnippet>

<SwmSnippet path="/PlayWrightAutomation/allure-report/plugins/packages/index.js" line="75">

---

Similarly, the packages tab is registered via <SwmToken path="PlayWrightAutomation/allure-report/plugins/packages/index.js" pos="75:0:4" line-data="allure.api.addTab(&#39;packages&#39;, {">`allure.api.addTab`</SwmToken>`(`<SwmToken path="PlayWrightAutomation/allure-report/plugins/packages/index.js" pos="75:7:7" line-data="allure.api.addTab(&#39;packages&#39;, {">`packages`</SwmToken>`, ...)`, adding a tab titled 'Packages' with an icon. This tab loads a <SwmToken path="PlayWrightAutomation/allure-report/plugins/packages/index.js" pos="79:9:9" line-data="        return new allure.components.TreeLayout({">`TreeLayout`</SwmToken> component with data from <SwmPath>[PlayWrightAutomation/…/data/packages.json](PlayWrightAutomation/allure-report/data/packages.json)</SwmPath>, enabling users to browse test results organized by package structure, which helps in understanding test coverage across different code modules.

```javascript
allure.api.addTab('packages', {
    title: 'tab.packages.name', icon: 'fa fa-align-left',
    route: 'packages(/)(:testGroup)(/)(:testResult)(/)(:testResultTab)(/)',
    onEnter: (function (testGroup, testResult, testResultTab) {
        return new allure.components.TreeLayout({
            testGroup: testGroup,
            testResult: testResult,
            testResultTab: testResultTab,
            tabName: 'tab.packages.name',
            baseUrl: 'packages',
            url: 'data/packages.json'
        });
    })
});
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBUUElM0ElM0Fyb2JTd2ltbQ==" repo-name="QA"><sup>Powered by [Swimm](https://staging.swimm.cloud/)</sup></SwmMeta>
