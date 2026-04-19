## Task 13 - Advanced Admin

### Objective

Perform advanced administration tasks: bulk operations, auditing, and integrations.

---

??? question "Task 1: Bulk Operations"

    1. Create 8 test issues with the label `admin-test`
    2. Bulk edit: Set priority to **High** for all 8
    3. Bulk transition: Move 4 to **In Progress**
    4. Bulk edit: Assign all 8 to yourself
    5. Bulk transition: Move the 4 "In Progress" ones to **Done**
    6. Verify all changes on the board

??? question "Task 2: Audit and Health Check"

    1. Open the system Audit Log
    2. Find the last 5 configuration changes
    3. For each, document: Who, What, When
    4. Run these health-check JQL queries and record the counts:
        - Issues with no updates in 30+ days
        - Unassigned issues older than 7 days
        - Issues with empty descriptions
    5. Suggest cleanup actions for each category

??? question "Task 3: Integration Setup"

    Set up ONE of the following integrations:

    **Option A — GitHub:**
    1. Connect your GitHub repo to Jira
    2. Create a Jira issue
    3. Make a commit referencing the issue key
    4. Verify the commit appears on the Jira issue

    **Option B — Slack:**
    1. Install Jira Cloud for Slack
    2. Subscribe a channel to project notifications
    3. Create an issue and verify the Slack notification
    4. Create an issue from Slack using `/jira create`

    Document the steps you took and any issues encountered.
