## Solution 12 - Automation Rules

### Task 1: Basic Automation Rules

**Rule 1 — Auto-label Bugs:**

1. Trigger: Issue created
2. Condition: Issue type = Bug
3. Action: Edit issue fields → Labels → Add `needs-triage`

**Rule 2 — Welcome Comment:**

1. Trigger: Issue created
2. Action: Add comment → Text:
   `👋 Issue {{issue.key}} has been created. Please add acceptance criteria and set priority.`

**Rule 3 — Assignment Notification:**

1. Trigger: Field value changed → Field: Assignee
2. Action: Add comment → Text:
   `📋 {{issue.key}} has been assigned to {{issue.assignee.displayName}}`

### Task 2: Advanced Automation

1. Trigger: Issue transitioned → To status: "In Development"
2. Condition: Issue type = Story
3. Action 1: Create sub-task → Summary: `Code Review - {{issue.key}}`
4. Action 2: Create sub-task → Summary: `Testing - {{issue.key}}`
5. Action 3: Add comment → `Sub-tasks created: Code Review and Testing`

### Task 3: Scheduled Automation

1. Trigger: Scheduled → Cron: `0 9 * * *` (daily at 9 AM)
2. Lookup issues: JQL → `status = "In Progress" AND updated < -3d`
3. For each: Add comment → `⚠️ This issue has been in progress since {{issue.status.categoryChangeDate}}. Please update.`
4. Check **Automation** → **Audit log** to verify executions
