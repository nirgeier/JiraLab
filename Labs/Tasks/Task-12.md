## Task 12 - Automation Rules

### Objective

Build automation rules that eliminate repetitive Jira tasks.

---

??? question "Task 1: Basic Automation Rules"

    Create these 3 rules:

    1. **Auto-label Bugs**: When a Bug is created, add label `needs-triage`
    2. **Welcome Comment**: When any issue is created, add a comment:
       `👋 Issue {{issue.key}} has been created. Please add acceptance criteria and set priority.`
    3. **Assignment Notification**: When an issue is assigned, add a comment:
       `📋 {{issue.key}} has been assigned to {{issue.assignee.displayName}}`

    Test each rule by triggering the event.

??? question "Task 2: Advanced Automation"

    Create a rule:

    **When a Story transitions to "In Development":**
    1. Auto-create sub-task: `Code Review - {{issue.key}}`
    2. Auto-create sub-task: `Testing - {{issue.key}}`
    3. Add a comment listing the created sub-tasks

    Test by transitioning a Story.

??? question "Task 3: Scheduled Automation"

    Create a scheduled rule that runs daily at 9:00 AM:

    1. Find all issues in "In Progress" for more than 3 days (JQL lookup)
    2. Add a comment: `⚠️ This issue has been in progress for {{issue.status.duration}} days. Please update.`
    3. Verify the rule in the Automation audit log
    4. Test manually and check the audit log for execution details
