---
title: Screen Diff UI Plugin for Allure Report
---
# introduction

This document explains the design and implementation of a UI plugin that adds screen diff visualization to the Allure report. The plugin shows differences between screenshots in test results, helping to identify visual regressions.

We will cover:

1. How images are retrieved and rendered in the plugin.
2. How different diff display modes are handled.
3. How the UI component manages user interaction and state.
4. How the plugin integrates into the Allure report framework.

# image retrieval and rendering

The plugin fetches images attached to test results by name: "diff", "actual", and "expected". This is done by filtering attachments in the test stage data to find the relevant images. If none of these images are present, the UI shows a message indicating the absence of images.

<SwmSnippet path="/PlayWrightAutomation/allure-report/plugins/screen-diff/index.js" line="10">

---

Image rendering is done by wrapping the image source in a container div with a specific class for styling. This encapsulation allows consistent layout and styling of the images within the plugin UI.

```javascript
    function renderDiffContent(type, data) {
        function findImage(name) {
            if (data.testStage && data.testStage.attachments) {
                return data.testStage.attachments.filter(function (attachment) {
                    return attachment.name === name;
                })[0];
            }
            return null;
        }

        var diffImage = findImage('diff');
        var actualImage = findImage('actual');
        var expectedImage = findImage('expected');

        if (!diffImage && !actualImage && !expectedImage) {
            return '<span>Diff, actual and expected image have not been provided.</span>';
        }
```

---

</SwmSnippet>

# handling diff display modes

The plugin supports two main display modes: "diff" and "overlay".

- In "diff" mode, if a diff image is available, it is shown; otherwise, the actual image is displayed.
- In "overlay" mode, the expected image is shown as the base, with the actual image overlaid on top inside a container that allows dynamic width adjustment to reveal differences interactively.

<SwmSnippet path="/PlayWrightAutomation/allure-report/plugins/screen-diff/index.js" line="28">

---

This design allows users to switch between a straightforward diff view and an interactive overlay that highlights differences by moving the mouse.

```javascript
        if (type === 'diff') {
            if (!diffImage) {
                return renderImage(actualImage.source);
            }
            return renderImage(diffImage.source);
        }
        if (type === 'overlay') {
            return '<div class="screen-diff__overlay screen-diff__container">' +
                '<img class="screen-diff__image" src="data/attachments/' + expectedImage.source + '">' +
                '<div class="screen-diff__image-over">' +
                '<img class="screen-diff__image" src="data/attachments/' + actualImage.source + '">' +
                '</div>' +
                '</div>';
        }
    }
```

---

</SwmSnippet>

# UI component and user interaction

The main UI component is a <SwmToken path="PlayWrightAutomation/allure-report/plugins/screen-diff/index.js" pos="44:7:9" line-data="    var ScreenDiffView = Backbone.Marionette.View.extend({">`Backbone.Marionette`</SwmToken> view that renders the screen diff section in the test result pane. It only renders if the test is labeled as a screenshot diff type, ensuring it appears only where relevant.

The component renders radio buttons to switch between "Show diff" and "Show overlay" modes. It listens for clicks on these inputs to update the display mode setting and re-render the view accordingly.

For the overlay mode, it listens to mouse movement events over the overlay container. The width of the overlay image is adjusted dynamically based on the mouse position, creating an interactive reveal effect.

<SwmSnippet path="/PlayWrightAutomation/allure-report/plugins/screen-diff/index.js" line="44">

---

Additionally, when the overlay image loads, its width is fixed to prevent layout shifts during interaction.

```javascript
    var ScreenDiffView = Backbone.Marionette.View.extend({
        className: 'pane__section',
        events: {
            'click [name="screen-diff-type"]': 'onDiffTypeChange',
            'mousemove .screen-diff__overlay': 'onOverlayMove'
        },
        templateContext: function () {
            return {
                diffType: settings.get('diffType')
            }
        },
        template: function (data) {
            var testType = data.labels.filter(function (label) {
                return label.name === 'testType'
            })[0];

            if (!testType || testType.value !== 'screenshotDiff') {
                return '';
            }

            return '<h3 class="pane__section-title">Screen Diff</h3>' +
                '<div class="screen-diff__content">' +
                '<div class="screen-diff__switchers">' +
                '<label><input type="radio" name="screen-diff-type" value="diff"> Show diff</label>' +
                '<label><input type="radio" name="screen-diff-type" value="overlay"> Show overlay</label>' +
                '</div>' +
                renderDiffContent(data.diffType, data) +
                '</div>';
        },
        adjustImageSize: function (event) {
            var overImage = this.$(event.target);
            overImage.width(overImage.width());
        },
        onRender: function () {
            const diffType = settings.get('diffType');
            this.$('[name="screen-diff-type"][value="' + diffType + '"]').prop('checked', true);
            if (diffType === 'overlay') {
                this.$('.screen-diff__image-over img').on('load', this.adjustImageSize.bind(this));
            }
        },
        onOverlayMove: function (event) {
            var pageX = event.pageX;
            var containerScroll = this.$('.screen-diff__container').scrollLeft();
            var elementX = event.currentTarget.getBoundingClientRect().left;
            var delta = pageX - elementX + containerScroll;
            this.$('.screen-diff__image-over').width(delta);
        },
        onDiffTypeChange: function (event) {
            settings.save('diffType', event.target.value);
            this.render();
        }
    });
```

---

</SwmSnippet>

# integration with allure report

<SwmSnippet path="/PlayWrightAutomation/allure-report/plugins/screen-diff/index.js" line="96">

---

Finally, the plugin registers the <SwmToken path="PlayWrightAutomation/allure-report/plugins/screen-diff/index.js" pos="96:7:7" line-data="    allure.api.addTestResultBlock(ScreenDiffView, {position: &#39;before&#39;});">`ScreenDiffView`</SwmToken> as a test result block in the Allure report UI, positioning it before other blocks. This integration point ensures the screen diff UI appears in the correct place within the test result details.

```javascript
    allure.api.addTestResultBlock(ScreenDiffView, {position: 'before'});
})();
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBUUElM0ElM0Fyb2JTd2ltbQ==" repo-name="QA"><sup>Powered by [Swimm](https://staging.swimm.cloud/)</sup></SwmMeta>
