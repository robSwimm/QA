---
title: 'Automation Test Cases coverage  '
---
&nbsp;

| Test File Name                                                                                                                                                                                        | Result                   | Priority | Failed/Key Test Cases                                                                                                                                  |   |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------ | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ | - |
| [add-repo-flow.spec.ts](https://staging.swimm.cloud/workspaces/iLNvqyclvhXqiwC1lldi/repos/Z2l0aHViJTNBJTNBUUElM0ElM0Fyb2JTd2ltbQ==/branch/main/docs/ai72mprr/edit#test-file-name-add-repo-flowspects) | pass 1/1                 | High     |                                                                                                                                                        |   |
| auth-page.spec                                                                                                                                                                                        | pass 10/10               | High     |                                                                                                                                                        |   |
| autosync-flow.spec.ts                                                                                                                                                                                 | pass 2/2                 | Medium   |                                                                                                                                                        |   |
| backwards-compatibility-flow.spec.ts                                                                                                                                                                  | pass 1/1                 | Low      |                                                                                                                                                        |   |
| basic-flow.spec.ts                                                                                                                                                                                    | pass 1/1                 | Medium   |                                                                                                                                                        |   |
| commit-file.spec.ts                                                                                                                                                                                   | **pass 2/2**             | High     | fixed&nbsp;                                                                                                                                            |   |
| cross-repo-doc.spec.ts                                                                                                                                                                                | pass 2/2                 | Medium   |                                                                                                                                                        |   |
| demo.spec.ts                                                                                                                                                                                          | pass 2/2                 | Low      |                                                                                                                                                        |   |
| discard-draft.spec.ts                                                                                                                                                                                 | pass 5/5                 | Low      |                                                                                                                                                        |   |
| doc.spec.ts                                                                                                                                                                                           | fail 1/5                 | High     | test fail:&nbsp;<br>1. create a doc and verify we can commit and load it properly                                                                      |   |
| dummy-repo.spec.ts                                                                                                                                                                                    | **fail 3/4**             | High     | Env issue "Faild to create workspace"&nbsp;<br>                                                                                                        |   |
| editor-hyper-links.spec.ts                                                                                                                                                                            | pass 1/4(2 skipped)      | Medium   | issues:<br>1. with the "toBeInViewport" commond ( need to find other why to test it)&nbsp;<br>2. seems the data links are damaged&nbsp;                |   |
| editor-sidebar.spec.ts                                                                                                                                                                                | **pass 2/2**             | Medium   | known issue - issue with the mentions options&nbsp;&nbsp;                                                                                              |   |
| editor-swimmlinks.spec.ts                                                                                                                                                                             | pass 1/1                 | Medium   |                                                                                                                                                        |   |
| folders.spec.ts                                                                                                                                                                                       | **fail 2/6**             | High     | Flakey:&nbsp;<br>playwright performance (too fast)&nbsp;                                                                                               |   |
| import-md.spec.ts                                                                                                                                                                                     | pass 2/2                 | Medium   |                                                                                                                                                        |   |
| mermaid.spec.ts                                                                                                                                                                                       | pass 1/1                 | Low      |                                                                                                                                                        |   |
| path.spec.ts                                                                                                                                                                                          | pass 1/1                 | Medium   |                                                                                                                                                        |   |
| paywall.spec.ts                                                                                                                                                                                       | **fail 2/2**             | High     | Env issue "Faild to create workspace"                                                                                                                  |   |
| performance.spec.ts                                                                                                                                                                                   | **fail 1/3 (4 skipped)** | High     | Flakey&nbsp;<br>test : "switch branch from repo page"                                                                                                  |   |
| pr-to-doc.spec.ts                                                                                                                                                                                     | **fail2/4**              | High     | Flakey :&nbsp;<br>playwright performance (too fast)&nbsp;<br>tests :<br>1.create doc from PR and save<br>2.create doc from PR by PR number and discard |   |
| sidebar.spec.ts                                                                                                                                                                                       | pass 6/6                 | Medium   |                                                                                                                                                        |   |
| snippet-studio.spec.ts                                                                                                                                                                                | **fail 1/7**             | High     | Flakey:&nbsp;<br>Test "should select two snippets from the same file"                                                                                  |   |
| status-tab.spec.ts                                                                                                                                                                                    | pass 1/1                 | Low      |                                                                                                                                                        |   |
| tags.spec.ts                                                                                                                                                                                          | **fail 1/3**             | Medium   | Flakey<br>Tests :&nbsp;<br>1. Multiple tags flow<br>2.Tags flow inside doc                                                                             |   |
| templates.spec.ts                                                                                                                                                                                     | pass 2/2                 | Low      |                                                                                                                                                        |   |
| trial.spec.ts                                                                                                                                                                                         | **fail 1/1**             | High     | Env issue "Faild to create workspace"                                                                                                                  |   |
| workspace.spec.ts                                                                                                                                                                                     | **fail 1/2**             | High     | Env issue "Faild to create workspace"                                                                                                                  |   |

# Test file name: "add-repo-flow.spec.ts"

&nbsp;

### pass/ fail :   pass

### **Edge Cases and Suggestions**

1. verify massage toster exist&nbsp;
2. verify all button/tabs  exist on the repo&nbsp;
3. verify rep is empty&nbsp;

### Test Case Coverage Table

| Test cases&nbsp;           | Test steps&nbsp;                                                                                                                                                                                                                                                 | expected result&nbsp; |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------- |
| add repo flow&nbsp;        | 1\. click on button '+ add new token'<br>2. will dispaly dropdown option&nbsp;<br>3. select repo&nbsp;<br>4.pop up window will pop&nbsp;<br>5. search for 'add-repo-flow-test'<br>6. click on the first option&nbsp;<br>7. click on button 'connect repository ' |                       |
| remove repo from workspace |                                                                                                                                                                                                                                                                  |                       |

&nbsp;

---

&nbsp;

# Test file name: "auth-page.spec"

### pass/ fail:   pass 10/10&nbsp;

### **Edge Cases and Suggestions**

- **Test for session persistence (user stays logged in after refresh)**

- **Test for invalid email formats during login**

- **Test logout flow**

- **Accessibility check for forms**

- **UI responsiveness/mobile check**

- **Password visibility toggle**

- **Rate limiting/lockout after multiple failed attempts**

&nbsp;

### Naming Improvements

Suggested clearer titles for each test:

- Change `"login page"` to **"test login page UI"**

- Change `"register page"` to **"test register page UI"**

- Change `"home page -> register -> login -> register"` to **"test navigation between auth pages"**

- Make other test titles explicit about their purpose, e.g.\
  `"signup with email"` → **"test successful signup with email"**\
  `"forgot password"` → **"test forgot password flow"**\
  `"register page form"` → **"test registration form validation and submission"**\
  `"login flow for existing user"` → **"test login flow for existing user"**\
  `"should fail register already existing email"` → **"test registration failure with existing email"**\
  `"should fail login non-existing user"` → **"test login failure with non-existing user"**\
  `"should fail login existing user with a wrong password"` → **"test login failure with wrong password"\`**

&nbsp;

### Test Case Coverage Table

| Test Case                                        | Test Steps (Summary)                              | Expected Result                           |
| ------------------------------------------------ | ------------------------------------------------- | ----------------------------------------- |
| test login page UI                               | Go to /login, check UI & focus                    | Elements correct & focused                |
| test register page UI                            | Go to /register, check UI elements                | Elements correct                          |
| test navigation between auth pages               | Navigate home → register → login → register       | Navigation correct                        |
| test successful signup with email                | Go to register, fill all fields, check options    | Fields/options visible/correct            |
| test forgot password flow                        | Go to login, trigger forgot password, check reset | Reset flow works, message & email correct |
| test registration form validation and submission | Go to register, fill bad/good values, submit      | Errors show/hide, success redirects       |
| test login flow for existing user                | Go to login, fill real credentials, submit        | Redirected to workspace                   |
| test registration failure with existing email    | Register with existing email                      | Error shown                               |
| test login failure with non-existing user        | Try logging in with non-existing user             | Error shown                               |
| test login failure with wrong password           | Try logging in with wrong password, variations    | Error shown                               |

&nbsp;

---

&nbsp;

# Test file name: "autosync-flow.spec.ts"

### pass/ fail:   pass 2/2&nbsp;

### **Edge Cases and Suggestions**

### Test Case Coverage Table

| Test Case                        | Test Steps (Summary)                                     | Expected Result                                 |
| -------------------------------- | -------------------------------------------------------- | ----------------------------------------------- |
| test autosync review - view mode | Open doc, verify all UI, check tokens/paths in view/edit | Elements correct in both modes, actions correct |
| test autosync review - edit mode | Open doc in edit, verify counters, review all actions    | Actions update state/counters, commit works     |

---

&nbsp;

# Test file name: "backwards-compatibility-flow.spec.ts"

### pass/ fail:   pass 1/1

### **Edge Cases and Suggestions**

### Test Case Coverage Table

| Test Case                                        | Test Steps (Summary)                          | Expected Result                                   |
| ------------------------------------------------ | --------------------------------------------- | ------------------------------------------------- |
| test editing backward compatibility doc (v0.7.3) | Read doc, edit doc, add new text, commit/save | UI updates correctly, can edit and commit changes |

&nbsp;

# Test file name: "basic-flow.spec.ts"

### pass/ fail : pass 1/1

### **Edge Cases and Suggestions**

- **Test closing the knowledge base by clicking outside the panel.**

- **Accessibility: Keyboard navigation, ARIA labels, focus order.**

- **Test persistence: Does panel state persist after page reload?**

- **Test multiple rapid toggles (debounce/animation bugs).**

- **Test opening knowledge base on different sub-pages (not just** `/workspaces`).

- **Test that clicking links in the panel works as expected (e.g., feedback, Slack, VS Code extension).**

- **Responsiveness/mobile UI checks.**

- **Check if videos/resources load properly on slow network**

### Test Case Coverage Table

| Test Case                          | Test Steps (Summary)                         | Expected Result                                |
| ---------------------------------- | -------------------------------------------- | ---------------------------------------------- |
| test knowledge base/help center UI | Pulse animation, show resources, show videos | UI and options correct, animations as expected |

---

&nbsp;

# Test file name: "commit-file.spec.ts"

### pass/ fail :   1/2 faills

### **Edge Cases and Suggestions**

- **Negative case:** Try committing with empty doc/title, assert error message

- **Cancel commit mid-way (before save) and check for data loss**

- **Permission/role check:** Try as read-only or unauthorized user

- **Edit/commit to a protected branch (e.g., main) and assert restriction**

- **Concurrent edit/commit (two users/parallel)**

- **Check for draft persistence after page reload**

- **PR flow: check what happens if PR creation fails (network error, etc.)**

### Naming Improvements

| Current Title        | Suggested Improved Title                   |
| -------------------- | ------------------------------------------ |
| commit doc to branch | test commit doc to new and existing branch |
| commit doc with PR   | test commit doc with pull request          |

### Test Case Coverage Table

| Test Case                                  | Test Steps (Summary)                                                             | Expected Result                                                            |
| ------------------------------------------ | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| test commit doc to new and existing branch | Create new doc, commit to new branch (w/o PR), re-edit and commit to same branch | Doc saved in new branch, can be edited and saved again, both texts visible |
| test commit doc with pull request          | Create new doc, commit to new branch with PR, check PR screen and details        | PR is created, has correct branch name and title                           |

---

&nbsp;

# Test file name: "cross-repo-doc.spec.ts"

### pass/ fail:  pass 2/2

### **Edge Cases and Suggestions**

- **Negative test:** Open non-existent cross-repo doc (404/permission)

- **Edit and save cross-repo doc, then validate updates**

- **Check referenced file links actually navigate correctly**

- **Access as unauthorized user (check for permission error)**

- **Test for large cross-repo docs (pagination/scroll/long content)**

- **Check what happens if referenced repo/file is deleted or moved**

- **Accessibility: ARIA, keyboard navigation in cross-repo file lists**

### Naming Improvements

| Current Title          | Suggested Title                          |
| ---------------------- | ---------------------------------------- |
| open cross doc to view | test view cross-repo doc page            |
| open cross doc to edit | test edit cross-repo doc page (UI loads) |

### Test Case Coverage Table

| Test Case                     | Test Steps (Summary)                                                        | Expected Result                              |
| ----------------------------- | --------------------------------------------------------------------------- | -------------------------------------------- |
| test view cross-repo doc page | Go to doc view page, check title, referenced files, hunks, and review state | All sections render, cross-repo refs correct |
| test edit cross-repo doc page | Go to doc edit page, check title, referenced files, hunks, and review state | All sections render, cross-repo refs correct |

---

&nbsp;

# Test file name: "demo.spec.ts"

### pass/ fail :   pass 2/2

### **Edge Cases and Suggestions**

- **Negative/Edge:**

  - Attempt to visit with wrong doc ID (expect 404/permission error)

  - Visit as unauthorized or read-only user

- **Manual Autosync Trigger:**

  - Test user manually triggers autosync (if supported)

- **Edit-and-commit flow:**

  - Make changes and verify status indicators update

- **Autosync UI across different screen sizes (responsive)**

- **Accessibility:**

  - Focus order, ARIA labels, keyboard navigation

- **Diagram:**

  - Check for SVG rendering errors or malformed diagrams

- **Snippets:**

  - Test what happens if snippet source file is missing or changed

&nbsp;

### Naming Improvements

| Current Title                                          | Suggested Improved Title                             |
| ------------------------------------------------------ | ---------------------------------------------------- |
| visit the demo doc on the demonstration branch         | test demo doc autosync state (up-to-date)            |
| visit the demo doc on the demonstration-changes branch | test demo doc autosync state (outdated/needs review) |

### Test Case Coverage Table

| Test Case                                            | Test Steps (Summary)                                                                                                         | Expected Result                                                                             |
| ---------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| test demo doc autosync state (up-to-date)            | Go to demo doc, check autosync false, sidebar empty, validate content, tokens, snippets, diagram                             | All status indicators, content, diagram and tokens as expected, everything up-to-date       |
| test demo doc autosync state (outdated/needs review) | Go to demo doc (changes branch), check autosync false, review/description visible, check token/snippet/applicability/diagram | Outdated/autosyncable indicators, review section populated, content reflects outdated state |

---

&nbsp;

# Test file name: "discard-draft.spec.ts

pass/fail: pass 5/5

### **Edge Cases and Suggestions**

- **Edge:**

  - Try discarding a draft after making changes (not just empty)

  - Discard draft, then use browser back—should not restore draft

  - Discard as a user without edit rights (permission)

  - Discard with network error (simulate failure)

  - Attempt to discard when no drafts exist (UI state)

  - Mobile/responsive UI, accessibility for discard dialog

### Naming Improvements

| Current Title                                        | Suggested Improved Title                                       |
| ---------------------------------------------------- | -------------------------------------------------------------- |
| discard new empty draft from doc page                | test discard single empty draft from doc page                  |
| discard all with 1 new empty draft from doc page     | test discard all with one draft from doc page                  |
| discard a new draft from another draft doc page      | test discard a draft from another draft doc page (multi-draft) |
| discard current draft when multiple drafts available | test discard current draft when multiple drafts exist          |
| discard all drafts when multiple drafts available    | test discard all drafts when multiple drafts exist             |

### Test Case Coverage Table

| Test Case                                                      | Test Steps (Summary)                                                                                | Expected Result                             |
| -------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| test discard single empty draft from doc page                  | Create new doc, open drafts, discard, confirm delete, check draft count                             | Draft is deleted, count is 0                |
| test discard all with one draft from doc page                  | Create new doc, open drafts, discard all, confirm, check draft count                                | All drafts deleted, count is 0              |
| test discard a draft from another draft doc page (multi-draft) | Create 2 drafts, open drafts, discard non-current, confirm, assert navigates to current, count is 1 | Discarded draft removed, right navigation   |
| test discard current draft when multiple drafts exist          | Create 2 drafts, open drafts, discard current, confirm, assert navigates to other draft, count is 1 | Discarded current draft, correct navigation |
| test discard all drafts when multiple drafts exist             | Create 2 drafts, open drafts, discard all, confirm, check count is 0                                | Both drafts deleted, count is 0             |

---

&nbsp;

# Test file name: "doc.spec.ts"

### pass/fail: fail 1/4

### **Edge Cases and Suggestions**

- **Create doc with invalid/duplicate title (error case)**

- **Cancel commit/discard doc after changes**

- **Permissions: Try as unauthorized/read-only user**

- **Edit doc, lose connection, re-connect and check for draft save**

- **Try deleting a doc that does not exist (UI/state)**

- **Accessibility: tab order, ARIA, screen reader**

- **Mobile/responsive UI for CRUD flows**

&nbsp;

### Naming Improvements

| Current Title                                              | Suggested Improved Title                       |
| ---------------------------------------------------------- | ---------------------------------------------- |
| create a doc from the repo page                            | test create empty doc from repo page           |
| create a doc and verify we can commit and load it properly | test create, commit, and load doc with content |
| click a doc link in a doc                                  | test navigation using doc link                 |
| edit and save an existing document                         | test edit and commit existing doc              |
| delete an existing doc                                     | test delete existing doc and verify removal    |

### Test Case Coverage Table

| Test Case                                      | Test Steps (Summary)                                                                        | Expected Result                                   |
| ---------------------------------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------- |
| test create empty doc from repo page           | Go to repo page, open create doc, assert empty doc in edit                                  | Doc is empty and in edit mode                     |
| test create, commit, and load doc with content | Create doc with title/content, add links/snippets/smart tokens, commit, load, check content | Doc content/structure is preserved after commit   |
| test navigation using doc link                 | Open doc with link, click link, verify navigation and content, go back                      | Link works, correct doc loaded, navigation works  |
| test edit and commit existing doc              | Open doc in edit, change snippets/lines, commit to new branch, verify updates               | Doc changes are committed and appear after reload |
| test delete existing doc and verify removal    | Find doc card, delete via menu, commit, assert doc no longer appears                        | Doc is deleted, not visible in repo/docs listing  |

&nbsp;

---

# Test file name: "dummy-repo.spec.ts"

passed/ falls :   faill 3/4

### **Edge Cases and Suggestions**

- **Negative cases:**

  - Fail to create a workspace with duplicate name (error message)

  - Attempt to remove dummy repo when it’s the only repo (UI disabled)

  - Attempt to access workspace as unauthorized user (permission error)

- **Edge cases:**

  - Delete workspace and verify dummy repo cleanup

  - Invite multiple users, check repo visibility per user

  - Edit and commit docs in demo repo, reload, verify persistence

- **Accessibility:**

  - Focus order, keyboard navigation, ARIA

&nbsp;

### Naming Improvements

| Current Title                            | Suggested Improved Title                            |
| ---------------------------------------- | --------------------------------------------------- |
| dummy repo with new user / existing user | test dummy repo onboarding flow (new/existing user) |
| empty workspace with only dummy repo     | test empty workspace (dummy repo only)              |
| empty workspace without dummy repo       | test empty workspace (no dummy repo)                |

&nbsp;

### Test Case Coverage Table

| Test Case                                           | Test Steps (Summary)                                                                      | Expected Result                                                                                |
| --------------------------------------------------- | ----------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| test dummy repo onboarding flow (new/existing user) | Sign in/out, create workspace, check repo/sidebar, check docs/playlist, edit/commit, etc. | Dummy repo visible, docs/playlist/statuses correct, edit/commit works, no unauthorized banners |
| test empty workspace (dummy repo only)              | Create workspace with only dummy repo, open settings, check remove option unavailable     | Remove option not shown, workspace created                                                     |
| test empty workspace (no dummy repo)                | Open empty workspace, check add repo message, creation options, and GitHub auth message   | Add-repo message, options enabled, GitHub auth prompt                                          |

&nbsp;

&nbsp;

---

&nbsp;

# Test file name: "editor-hyper-links.spec.ts"

passed/ falls :   pass 1/1&nbsp;

4 in skip&nbsp;

### **Edge Cases and Suggestions**

- **Negative case:** Copy anchor on doc with no headings/snippets (should not error)

- **Edge:** Copy anchor in edit mode vs view mode

- **Mobile/Accessibility:** Keyboard/ARIA/clipboard support

- \*\*Clipboard permission denied/error

- \*\*Multiple anchors with same name (disambiguation)

- \*\*Paste anchor link in various editors (should never auto-transform)

&nbsp;

### Naming Improvements

| Current Title                                                                    | Suggested Improved Title                                      |
| -------------------------------------------------------------------------------- | ------------------------------------------------------------- |
| links to an heading section and snippet section in the same doc should scroll... | test same-doc anchor links scroll to section/snippet          |
| link to an heading section in other doc should navigate and scroll to it         | test cross-doc heading anchor link navigates and scrolls      |
| link to a snippet section in other doc should navigate and scroll to it          | test cross-doc snippet anchor link navigates and scrolls      |
| copying anchors                                                                  | test copy anchor link copies correct url to clipboard         |
| pasting link to section should not transform it to swimmdoc                      | test pasting section link remains plain url (not transformed) |

&nbsp;

### Test Case Coverage Table

| Test Case                                                           | Steps (Summary)                                                              | Expected Result                            |
| ------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ------------------------------------------ |
| test same-doc anchor links scroll to section/snippet&nbsp;          | Open doc, click anchor links to heading/snippet, assert viewport scrolls     | Page scrolls to target, no new tab         |
| test cross-doc heading anchor link navigates and scrolls&nbsp;      | Open doc, click heading anchor link, new page, check heading is in viewport  | Navigates, scrolls to heading              |
| test cross-doc snippet anchor link navigates and scrolls&nbsp;      | Open doc, click snippet anchor link, new page, check snippet is in viewport  | Navigates, scrolls to snippet              |
| test copy anchor link copies correct url to clipboard               | Open doc, hover heading, click copy, assert clipboard content is url#heading | Clipboard contains correct anchor url      |
| test pasting section link remains plain url (not transformed)&nbsp; | Paste section link in editor, assert stays as link, not auto-converted       | Remains as hyperlink, not special doc link |

&nbsp;

---

&nbsp;

# Test file name: "editor-sidebar.spec"

pass/ faill : fail 1/2

### **Edge Cases and Suggestions**

- **Edge/Negative:**

  - TOC/Sidebar with no headings, no files, no mentions (initial empty doc)

  - Add/remove multiple mentions or tags

  - Attempt to remove referenced file when only one remains (should not break)

  - Collapse/expand sidebar multiple times (stress)

  - Accessibility: focus order, ARIA roles, keyboard nav for sidebar/TOC/tags

- **Permissions:** Try as read-only/unauthorized user (edit controls should not appear)

### Naming Improvements

| Current Title                      | Suggested Improved Title                                                  |
| ---------------------------------- | ------------------------------------------------------------------------- |
| Check sidebar sections in readonly | test doc sidebar sections (readonly/view mode)                            |
| Check sidebar sections in edit     | test doc sidebar sections (edit mode: toc, refs, tags, mentions, actions) |

### Test Case Coverage Table

| Test Case                                      | Steps (Summary)                                                                                                      | Expected Result                                                                                                            |
| ---------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| test doc sidebar sections (readonly/view mode) | Go to doc view, check sidebar, review state, TOC, referenced files, tags, mentions, actions, collapse/expand         | Sidebar sections present, TOC clickable, referenced files/tag/mentions/actions all work, collapse/expand toggles correctly |
| test doc sidebar sections (edit mode)          | Go to edit, add headline, verify TOC, remove headline, add/remove files, mentions, remove all, verify sidebar resets | TOC updates with headlines, files/tags/mentions update dynamically, sidebar resets on clearing all, mention add works      |

---

&nbsp;

# Test file name: "editor-swimmlinks.spec.ts"

### pass/faill : pass&nbsp;

### **Edge Cases and Suggestions**

- **Negative/Edge:**

  - Insert a Swimm link to a non-existent or deleted doc (should error or show as broken)

  - Change the linked doc’s title/content, refresh link—should update or show out-of-date if not

  - Delete the linked doc, check if Swimm link is marked as broken/outdated

  - Multiple links in same doc (check all stay up-to-date)

  - Add Swimm link, discard changes, verify not persisted

- **Accessibility:** Keyboard navigation/focus/ARIA for links

- **Permissions:** Try as unauthorized user (Swimm link UI disabled)

### Naming Improvements

| Current Title                                                     | Suggested Improved Title                                   |
| ----------------------------------------------------------------- | ---------------------------------------------------------- |
| Create a Swimm Link and validate it stays up to date after commit | test swimm link remains up-to-date after commit and reload |

### Test Case Coverage Table

| Test Case                                                  | Steps (Summary)                                                                                        | Expected Result                                                           |
| ---------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------- |
| test swimm link remains up-to-date after commit and reload | Create doc A, create new doc B, add Swimm link to A in B, check link, commit, reload, check link again | Swimm link is present, marked as “verified,” persists after reload/commit |

---

&nbsp;

# Test file name: "folders.spec.ts"

### pass/fail : fail 2/6

### **Edge Cases and Suggestions**

- **Edge/Negative Cases:**

  - Try to create folder/doc with empty name (should show error)

  - Try to create nested folders beyond allowed depth (if limit exists)

  - Move folder into itself or its own subfolder (should not be allowed)

  - Delete folder containing docs/subfolders, confirm all removed (and ask for confirmation)

  - Rename/move/delete doc or folder as unauthorized/readonly user (should be blocked)

  - Concurrent rename/move actions by two users (conflict resolution)

- **UI/Accessibility:**

  - Keyboard navigation in folder structure

  - ARIA/labels for folder/doc controls

### Naming Improvements

| Current Title                                           | Suggested Improved Title                            |
| ------------------------------------------------------- | --------------------------------------------------- |
| docs are shown for a repo without root folder in the db | test docs list visible when repo has no root folder |
| create a new folder and create a folder inside it       | test create nested folders                          |
| folder rename and name conflict                         | test folder rename and conflict handling            |
| create draft in folder                                  | test create new draft inside folder                 |
| move draft to folder                                    | test move draft doc to folder                       |
| move commited doc to folder                             | test move committed doc to folder                   |

### Test Case Coverage Table

| Test Case                                           | Steps (Summary)                                                        | Expected Result                                |
| --------------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------- |
| test docs list visible when repo has no root folder | Go to demo repo without root folder                                    | Docs list is visible                           |
| test create nested folders                          | Create folder, open it, add subfolder                                  | Nested folders visible, breadcrumbs correct    |
| test folder rename and conflict handling            | Create two folders, try rename to conflict, then rename to unique name | Conflict error shown, unique rename succeeds   |
| test create new draft inside folder                 | Create folder, open, add blank doc, set title                          | Draft created in correct folder, visible in UI |
| test move draft doc to folder                       | Create draft in repo, create folder, move draft to folder              | Draft moves, appears in folder in UI           |
| test move committed doc to folder                   | In demo repo, create folder, move committed doc to folder              | Doc moves, appears in folder in UI             |

---

&nbsp;

# Test file name: "import-md.spec.ts"

### pass/fail ; pass 2/2&nbsp;

### **Edge Cases and Suggestions**

- **Edge/Negative:**

  - Try to upload an invalid/non-Markdown file (should fail gracefully)

  - Try uploading a .md file with unsupported content (e.g., broken image, script tags, binary content)

  - Try importing duplicate file (existing doc with same name), see if warning appears

  - Upload a .md with missing images (should show image error placeholder)

  - Import from repo with no .md files (should show empty state)

  - Permissions: Try as unauthorized or readonly user (should be blocked)

- **UI/Accessibility:**

  - File picker keyboard navigation and ARIA labels

  - Drag-and-drop upload, if supported

### Naming Improvements

| Current Title               | Suggested Improved Title              |
| --------------------------- | ------------------------------------- |
| upload local file           | test upload local .md file as doc     |
| upload file from repository | test import .md file from repo as doc |

### Test Case Coverage Table

| Test Case                             | Steps (Summary)                                                                 | Expected Result                                  |
| ------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------ |
| test upload local .md file as doc     | Open creation hub → imports → Upload .md, select file, upload, complete wizard  | New doc draft created, content and image visible |
| test import .md file from repo as doc | Open creation hub → imports → Repo import, select file, import, complete wizard | New doc draft created, correct headings/images   |

---

&nbsp;

# Test file name: "mermaid.spec.ts"

### pass/fail : pass 1/1&nbsp;

### **Edge Cases and Suggestions**

- **Edge/Negative:**

  - Mermaid syntax error (should display an error or warning, not crash UI)

  - File with *no* mermaid diagrams (should not render any SVGs, no errors)

  - Malformed SVG (should not crash, should show error)

  - Performance/stability with very large/complex diagrams

- **UI/Accessibility:**

  - Diagrams are accessible to screen readers (alt text, ARIA labels)

  - Diagrams resize responsively

### Naming Improvements

| Current Title       | Suggested Improved Title                     |
| ------------------- | -------------------------------------------- |
| mermaids everywhere | test render multiple mermaid diagrams in doc |

### Test Case Coverage Table

| Test Case                                    | Steps (Summary)                       | Expected Result                            |
| -------------------------------------------- | ------------------------------------- | ------------------------------------------ |
| test render multiple mermaid diagrams in doc | Go to specific doc page with mermaids | 14 SVG mermaid diagrams rendered, 0 errors |

---

&nbsp;

# Test file name: "path.spec.ts"

### pass/fail : pass 1/1&nbsp;

### **Edge Cases and Suggestions**

- **Negative paths:**

  - Search for a non-existent file (should show zero results)

  - Add a path, then remove it (should be removed from the doc)

  - Try adding the same path twice (should not duplicate)

  - UI: Modal cancel/close should not add a path

- **Cross-repo error:**

  - Cross-repo search fails/no results (should show empty state, not error)

- **Permissions:**

  - Attempt path selection as a user with restricted access (should restrict tree)

- **Performance/UI:**

  - Test with a large repo tree

  - Accessibility: tree navigation via keyboard

### Naming Improvements

| Current Title   | Suggested Improved Title                        |
| --------------- | ----------------------------------------------- |
| SmartPaths test | test smart paths modal and path selection flows |

### Test Case Coverage Table

| Test Case                                       | Test Steps (Summary)                                                                                                    | Expected Result                                               |
| ----------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------- |
| test smart paths modal and path selection flows | Go to new doc → open path modal → verify tree loads → select & add path from tree → search & add from search/cross-repo | Tree visible, file selectable, search works, cross-repo works |

---

&nbsp;

# Test file name: "paywall.spec.ts"

### pass/fail: fail 2/2&nbsp;

### **Edge Cases and Suggestions**

- **Edge cases for paywall:**

  - Try adding more than two repos at once (should see paywall)

  - Remove a repo and try adding again (should reset counter/allow)

  - Add repo, hit paywall, start trial, confirm limit is lifted

  - Invite, hit paywall, start trial, confirm more invites allowed

- **UI/UX:**

  - Cancel/close paywall and retry action (UI recovers correctly)

  - Attempt actions with network errors (paywall appears as fallback)

  - Verify error messages for invalid repo/user actions

- **Permissions:**

  - Add repo/invite users as non-admin (should restrict or error)

  - Invite user already invited (should not count twice)

### Naming Improvements

| Current Title           | Suggested Improved Title                      |
| ----------------------- | --------------------------------------------- |
| paywall on adding repos | test paywall on repo add (multi/single cases) |
| paywall on users invite | test paywall on user invite (limit reached)   |

### Test Case Coverage Table

| Test Case                                     | Test Steps (Summary)                                                                                                                                 | Expected Result                                |
| --------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------- |
| test paywall on repo add (multi/single cases) | \- Create workspace, create two repos<br>- Add 2 repos (see paywall), close paywall<br>- Add 1 repo (no paywall)<br>- Add another repo (see paywall) | Paywall is triggered at correct times          |
| test paywall on user invite (limit reached)   | \- Open add users modal<br>- Invite up to user limit (no paywall)<br>- Invite extra user (see paywall)                                               | Paywall is triggered when exceeding user limit |

---

&nbsp;

&nbsp;

&nbsp;

# Test file name: "performance.spec.ts"

### pass/fail: fail 1/3

4 in skip&nbsp;

## Test Case Coverage Table

| Test Name                              | Description/Steps                                                                 | Expected Result                   | Time Limit (ms) | Iterations |
| -------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------- | --------------- | ---------- |
| load document from repo page           | Go to repo page → Click doc card → Wait for doc title                             | Loads doc within 10,000 ms        | 10,000          | 3          |
| go back to repo page from doc page     | Go to doc page → Click breadcrumb (repo) → Wait for repo title                    | Loads repo within 3,000 ms        | 3,000           | 3          |
| switch branch from repo page           | Go to repo page → Click branch selector → Switch to "main" → Wait for empty state | Switch completes within 11,000 ms | 11,000          | 3          |
| load a doc in view mode&nbsp;          | Go to doc page (view) → Wait for doc title                                        | Loads in 12,000 ms                | 12,000          | 3          |
| load a doc in edit mode&nbsp;          | Go to doc page (edit) → Wait for title in edit field                              | Loads in 12,000 ms                | 12,000          | 3          |
| load the repo page&nbsp;               | Go to repo page → Wait for repo title                                             | Loads in 12,000 ms                | 12,000          | 3          |
| load the workspace page&nbsp;          | Go to workspace page → Wait for workspace name                                    | Loads in 12,000 ms                | 12,000          | 3          |
| create a doc from repo page&nbsp;      | Go to repo page → Click create doc → Wait for new doc page                        | New doc page in 5,000 ms          | 5,000           | 3          |
| create a playlist from repo page&nbsp; | Go to repo page → Click create playlist → Wait for playlist creation UI           | Playlist created in 5,000 ms      | 5,000           | 3          |

&nbsp;

---

&nbsp;

# Test file name: "pr-to-doc.spec.ts"

### pass/fail : fail 1/4&nbsp;

## Test Case Coverage Table

| Test Name                                         | Description/Steps                                                                                                 | Expected Result                                                  | Edge Cases/Notes                   |
| ------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------- |
| create doc from PR and save                       | Open repo branch, use "PR to doc" tool, pick PR from list, create doc, check snippets, save and create PR for doc | Doc created with correct title, referenced files, snippets, save | Covers accepting/removing snippets |
| create doc from PR by PR number and discard       | Use PR number search to create doc, then discard                                                                  | Doc created and discarded, all UI behaves correctly              |                                    |
| error creating doc from PR with only deletions    | Search for PR with only deletions, try to create doc                                                              | Warns user ("no snippets"), button disabled                      |                                    |
| error creating doc from PR with invalid PR number | Enter bogus PR number, try to create doc                                                                          | Error dialog: "PR not found"                                     |                                    |

# Test file name: "sidebar.spec.ts"

### **Edge Cases and Suggestions**

- **Edge cases/Negative paths:**

  - Try creating a folder with an existing name (should show error)

  - Try renaming a folder to an existing folder's name (should show error)

  - Attempt to delete a folder containing subfolders/docs (should handle/ask for confirmation)

  - Attempt to move a doc to a folder where a doc of the same name exists (should show conflict)

  - Try navigating when repo is collapsed (should expand or block navigation)

  - Permissions: Test as a read-only user (should restrict create/rename/delete)

- **UX/UI:**

  - Verify tooltips for sidebar actions

  - Accessibility: Keyboard navigation of tree/sidebar

### Naming Improvements

| Current Title                                      | Suggested Improved Title                       |
| -------------------------------------------------- | ---------------------------------------------- |
| repo items are shown and hidden when repo collapse | test sidebar repo collapse/expand toggles      |
| doc navigation from sidebar                        | test doc view/edit navigation via sidebar      |
| create sub folder and move a doc into it           | test creating/moving docs in nested folders    |
| rename and delete a folder                         | test folder rename and delete actions          |
| add draft under a folder                           | test draft doc creation under folder           |
| quick search                                       | test sidebar quick search for docs and folders |

---

# Test file name: "snippet-studio.spec.ts"

### pass/fail : fail 1/7&nbsp;

### Naming Improvements

| Current Test Name                                    | Suggested Title (for better reporting)                  |
| ---------------------------------------------------- | ------------------------------------------------------- |
| should open and close                                | open and close snippet studio                           |
| should use search to find a file                     | search for file and open snippet tab                    |
| should choose a snippet at the top of the file       | select snippet at file top and add to document          |
| should select a snippet from the middle of the file  | select snippet from file middle and add                 |
| should select two snippets from the same file        | add multiple snippets from same file, verify state      |
| should click on a file to select it and open new tab | open second file in new snippet tab                     |
| should be able to switch tabs                        | switch between multiple snippet tabs and verify content |

### Test Case Coverage Table

| Test Name                                     | Summary                                                     |
| --------------------------------------------- | ----------------------------------------------------------- |
| should open and close                         | Open/close snippet studio                                   |
| should use search to find a file              | Search and select a file for snippets                       |
| should choose a snippet at the top of file    | Select lines at the top of file, add snippet                |
| should select a snippet from the middle       | Select lines from the middle of a file, add snippet         |
| should select two snippets from the same file | Add two non-contiguous line ranges from same file           |
| should click on a file to open new tab        | Open a second file in a new snippet studio tab              |
| should be able to switch tabs                 | Add multiple snippets (files), switch between them via tabs |

---

&nbsp;

&nbsp;

# Test file name: "status-tab.spec.ts"

pass /fail : pass

## Test Case Coverage Table

| Test Name                         | Steps                                                                                                                                                 | Expected Result(s)                                                                                   |
| --------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| status page shows an outdated doc | 1\. Go to repo docs page<br>2. Click "Review outdated" tab<br>3. Check outdated notification<br>4. Open outdated doc<br>5. Check autosyncable snippet | 1\. Outdated notification is visible<br>2. Outdated doc in list<br>3. Doc shows autosyncable snippet |

&nbsp;

&nbsp;

---

&nbsp;

# Test file name: "tags.spec.ts"

pass /fail : fail 1/3

### Test Case Coverage Table

| Test Name                      | Steps & Coverage                                                                          | Main Assertions / Results                                                     |
| ------------------------------ | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| Multiple tags flow (repo page) | Add multiple tags via doc card. Only first is shown; "+1" is visible for additional tags. | Tags added/visible on doc card. Additional tag hidden; "+1" badge is visible. |
| Tags flow inside doc           | Add new tag, rename tag, remove tag, add existing tag, delete tag from workspace.         | Tag appears, renamed, removed, can't re-add deleted tag.                      |
| Draft tags persist to commit   | Create draft, add tag, commit doc, check tag persists post-commit.                        | Tag remains visible after commit.                                             |

### **Edge Cases and Suggestions**

1. **Duplicate Tag Add:** Try adding the same tag twice—should only see one tag.

2. **Special Characters:** Add a tag with special characters/emoji—UI renders OK.

3. **Tag Limit:** Try adding more tags than the UI limit (if any)—see if it fails gracefully.

4. **Cross-Doc:** Tag with same name on two docs, delete from workspace—ensure removed everywhere.

5. **Permissions:** Try tag actions as read-only user (should not be allowed).

6. **Filter/Sort by Tag:** If repo/docs list can filter by tag, validate tags as filter work.

7. **Undo Rename/Remove:** (If feature exists) Undo a tag rename/remove, check recovery.

8. **API Error Handling:** Simulate tag service fail—UI should handle gracefully.

9. **Mobile/Responsive:** Add/remove tags on mobile view, check UI integrity.

---

&nbsp;

# Test file name: "templates.spec.ts"

pass /fail : pass 2/2

### Test Case Coverage Table

| Test Name                                    | Steps & Coverage                                                                                                  | Main Assertions / Results                                                                                               |
| -------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| use a template                               | \- Create doc from template- Edit doc title- Fill snippet placeholders- Delete snippet placeholder- Commit via PR | \- Elements and placeholders count- Title changes- Snippet added/deleted- Commit flow- Placeholders removed post-commit |
| doc remains a template after draft save/load | \- Create doc from template- Save as draft- Reload draft- Verify editor state and placeholders                    | \- Editor row and placeholder counts are preserved after reload                                                         |

### **Edge Cases and Suggestions**

- **Multiple Placeholders**: Try adding and removing snippets in multiple places (different orders).

- **Text Placeholder**: As per your TODO—add tests for text (non-snippet) placeholders.

- **Draft with Edits**: Edit content between placeholders, save draft, reload—ensure no loss.

- **Edit After Commit**: Edit a committed doc and add/remove snippets again—UI should update.

- **Concurrent Drafts**: Start two drafts from the same template, change in parallel, save/load both.

- **Error Handling**: Try to add a snippet from a non-existent file—UI should show error.

- **Role Permissions**: If templates are limited by role, try as a restricted user.

---

&nbsp;

&nbsp;

# Test file name: "trial.spec.ts"

### pass/fail : fail 1/1

&nbsp;

### Test Case Coverage Table

| Step                          | Action                                                | Expected Outcome           |
| ----------------------------- | ----------------------------------------------------- | -------------------------- |
| Navigate to `/workspaces/new` | Directs to new workspace creation screen              | Page loads successfully    |
| `createNewWorkspace()`        | Creates a new workspace (helper method)               | Workspace is created       |
| Open workspace settings       | Clicks workspace menu → settings                      | Settings modal opens       |
| Navigate to billing tab       | Clicks on "Billing" tab                               | Billing page loads         |
| Click "Change Plan"           | Triggers plan change UI                               | Plan list is shown         |
| Check for plan availability   | Looks for `Teams` plan header and 14-day trial button | Elements are visible       |
| Click trial CTA               | Clicks “Start 14 day trial” on Small Teams plan       | Trial starts               |
| Verify tag                    | Confirms `.tag.small-teams` contains `Small teams`    | Tag confirms selected plan |

&nbsp;

### **Edge Cases and Suggestions**

| Improvement Area           | Suggestion                                                                 |
| -------------------------- | -------------------------------------------------------------------------- |
| Trial Reuse Block          | Add a test that verifies user **cannot start trial again** after starting  |
| Trial Expiry Edge Case     | Add test for trial expiry message or lockout after 14 days (can be mocked) |
| Tier Switching             | Add test to downgrade/upgrade between plans post-trial                     |
| UI Errors                  | Test network errors or plan fetch errors handling                          |
| Email/Billing Info Missing | Test what happens if required billing info is not filled in                |

---

&nbsp;

&nbsp;

# Test file name: "workspace.spec.ts"

#### pass/fail : fail 1/2

#### **Test Case Coverage Table**

| **Title**                              | **Preconditions**     | **Test Steps**                                                    | **Expected Result**                                         |
| -------------------------------------- | --------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------- |
| Visit existing workspace page          | Existing workspace ID | Navigate to `/workspaces/${TEST_WORKSPACE_ID}`                    | Workspace page loads and shows name `"E2E home"`            |
| Create a new workspace                 | User is logged in     | Trigger workspace creation via `createNewWorkspace()` helper      | New workspace is created with unique name                   |
| Validate workspace appears in dropdown | Workspace created     | Click workspace menu > check if `selected-workspace-name` matches | New workspace name appears and is selected                  |
| Delete a workspace                     | Workspace exists      | Go to settings → Delete → Confirm                                 | Workspace is removed and no longer in dropdown              |
| Verify deleted workspace is not listed | Workspace was deleted | Open dropdown again                                               | `selected-workspace-name` does **not** contain deleted name |

### **Edge Cases and Suggestions**

| **Edge Case**                                              | **Risk**                                          | **Recommendation**                             |
| ---------------------------------------------------------- | ------------------------------------------------- | ---------------------------------------------- |
| Creating a workspace with a **duplicate name**             | Might allow duplicates or fail silently           | Add a test that tries creating duplicate names |
| Creating a workspace with **invalid characters or length** | Could crash UI or throw backend errors            | Add input validation tests                     |
| **Canceling workspace deletion** midway                    | If cancel fails, workspace might still be deleted | Add flow: click "delete", then "cancel"        |
| Navigating to a **non-existent workspace ID**              | Should return 404 or friendly error               | Add negative test for invalid workspace ID     |
| Workspace deletion with **open editors/tabs**              | Might leave user in broken state                  | Test UI behavior after deletion                |
| **Concurrency**: multiple workspaces created quickly       | Could cause race conditions                       | Add stress test for creation                   |

---

# 

&nbsp;

&nbsp;

&nbsp;

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBUUElM0ElM0Fyb2JTd2ltbQ==" repo-name="QA"><sup>Powered by [Swimm](https://staging.swimm.cloud/)</sup></SwmMeta>
