# UI Test Case Template (Zephyr/Jira Standard)

| Field              | Description                                                      |
|--------------------|------------------------------------------------------------------|
| Test Case ID       | Unique Jira/Zephyr Test Case ID                                  |
| Title              | Brief, descriptive title                                         |
| Description        | What is being tested? Purpose of the test                        |
| Preconditions      | Any setup or state required before test execution                |
| Steps to Execute   | Numbered list of actions to perform                              |
| Test Data          | Data required for the test, if applicable                        |
| Expected Result    | The expected outcome after executing the steps                   |
| Actual Result      | (To be filled after execution)                                   |
| Status             | Pass/Fail (to be filled after execution)                         |
| Comments           | Any notes, links, or clarifications                              |

**Example:**

| Field              | Example                                                          |
|--------------------|------------------------------------------------------------------|
| Test Case ID       | TC_UI_001                                                        |
| Title              | Login with valid credentials                                     |
| Description        | Verify that a user can login with valid username and password    |
| Preconditions      | User is on the login page                                        |
| Steps to Execute   | 1. Enter valid username<br>2. Enter valid password<br>3. Click Login   |
| Test Data          | username: testuser, password: Pass123                            |
| Expected Result    | User is redirected to the homepage                               |
| Actual Result      |                                                                  |
| Status             |                                                                  |
| Comments           |                                                                  |