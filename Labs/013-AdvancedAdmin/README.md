# Lab 013 - Advanced Admin

!!! hint "Overview"

    - In this lab, you will learn advanced Jira administration tasks including bulk operations, archiving, audit logs, and integrations.
    - These are day-to-day tools for maintaining a healthy Jira instance.
    - By the end, you will be able to handle common admin maintenance tasks confidently.

## Prerequisites

- **Jira Administrator** permissions
- Completed Labs 009–012

## What You Will Learn

- Bulk operations (edit, move, transition, delete)
- Project archiving and cleanup
- Audit logs and activity tracking
- Jira integrations (Confluence, Bitbucket, Slack)
- Backup and restore
- Performance and health tips

---

## Bulk Operations

### When to Use Bulk Operations

- Closing a large batch of stale issues
- Reassigning issues when a team member leaves
- Adding labels or components to many issues at once
- Transitioning multiple issues between statuses

### Performing a Bulk Change

1. Run a JQL search to find the target issues:
   ```sql
   project = DEV AND assignee = "former.employee" AND status != Done
   ```
2. Click **Tools** → **Bulk change** (or select issues and click **Bulk change**)
3. Select the issues to modify
4. Choose the operation:
   - **Edit** — Change fields (assignee, priority, labels)
   - **Move** — Move to a different project
   - **Transition** — Change status
   - **Delete** — Permanently remove
5. Configure the changes
6. Review the confirmation screen
7. Click **Confirm**

!!! warning "Bulk Delete"

    Bulk delete is **permanent** and cannot be undone. Always export affected issues before deleting.

### Demo: Bulk Reassign

1. Search: `assignee = "old.user" AND status != Done`
2. Bulk change → Edit → Assignee → `new.user`
3. Check **Send notification** if you want email alerts
4. Confirm and execute

---

## Project Archiving

### Archiving a Project

When a project is no longer active:

1. Go to **Project Settings** → **Details**
2. Click **Archive project**
3. Archived projects:
   - Are hidden from navigation and search
   - Issues are preserved but read-only
   - Can be restored later

### Deleting vs Archiving

| Action      | Data Preserved | Reversible | Use When                           |
| ----------- | -------------- | ---------- | ---------------------------------- |
| **Archive** | Yes            | Yes        | Project is done but data has value |
| **Delete**  | No             | No         | Test projects, accidental creation |

---

## Audit Logs

### System Audit Log

1. Go to **Jira Settings** → **System** → **Audit log**
2. View all administrative actions:
   - Permission changes
   - Scheme modifications
   - User additions/removals
   - Configuration changes
3. Filter by date range, user, or action type

### Project Audit

Track changes within a project:

1. Go to **Project Settings** → **Audit log**
2. View project-specific changes

### What to Monitor

| Event                     | Why It Matters                 |
| ------------------------- | ------------------------------ |
| Permission scheme changes | Security implications          |
| Workflow modifications    | May break existing processes   |
| User role changes         | Access control audit           |
| Bulk deletions            | Data loss prevention           |
| Global permission grants  | Privilege escalation detection |

---

## Integrations

### Confluence Integration

Link Jira issues to Confluence pages:

1. **From Jira**: Open an issue → Click **Link** → **Confluence page**
2. **From Confluence**: Insert a Jira Issues macro in a page
3. **Automatic**: Paste a Jira issue URL in Confluence — it auto-links

### Bitbucket/GitHub Integration

Connect source code to Jira issues:

1. **Smart Commits**: Include issue key in commit messages
   ```
   DEV-123 Fix login validation bug
   DEV-123 #comment Fixed the empty password issue
   DEV-123 #time 2h
   DEV-123 #resolve
   ```
2. **Branch naming**: Name branches with issue keys: `feature/DEV-123-login-fix`
3. Issues automatically show linked commits, branches, and PRs

### Slack Integration

1. Install the **Jira Cloud for Slack** app
2. Connect your Jira instance
3. Set up channel notifications:
   - `/jira connect` in a Slack channel
   - Subscribe to project events: `/jira subscribe`
4. Create issues from Slack: `/jira create`

---

## Backup and Restore

### Cloud Backup

1. Go to **Jira Settings** → **System** → **Backup manager**
2. Click **Create backup**
3. Download the backup file (XML + attachments)
4. Store backups in a secure location

### Backup Schedule

!!! tip "Best Practice"

    Set up regular backups:

    - **Weekly** full backups
    - **Before** major configuration changes
    - **Before** upgrading or migrating

---

## Instance Health

### Common Maintenance Tasks

| Task                           | Frequency   | How                                    |
| ------------------------------ | ----------- | -------------------------------------- |
| Review inactive users          | Monthly     | Deactivate users who haven't logged in |
| Clean up old filters           | Quarterly   | Delete unused saved filters            |
| Archive completed projects     | Per project | Archive when project is done           |
| Review automation rules        | Monthly     | Check audit log for failures           |
| Update permission schemes      | As needed   | When team structure changes            |
| Check for unused custom fields | Quarterly   | Remove fields no one uses              |

### JQL for Health Checks

```sql
-- Issues with no updates in 90 days
updated < -90d AND status != Done

-- Issues assigned to inactive users
assignee IN membersOf("inactive-users")

-- Issues with no assignee for 7+ days
assignee IS EMPTY AND created < -7d AND status != Done

-- Epics with no child issues
type = Epic AND issueFunction NOT IN hasLinks("is parent of")
```

---

## Exercise

!!! question "Exercise 1: Bulk Operations"

    1. Create 10 test issues in your project with the label `bulk-test`
    2. Use JQL to find them: `label = "bulk-test"`
    3. Perform these bulk operations:
        - Bulk edit: Set priority to High for all of them
        - Bulk transition: Move 5 to "In Progress"
        - Bulk edit: Assign all to yourself
    4. Verify the changes on the board

!!! question "Exercise 2: Audit Trail"

    1. Open the system Audit Log
    2. Find the last 10 configuration changes
    3. Document:
        - Who made the change?
        - What was changed?
        - When did it happen?
    4. Filter the audit log for only your own actions

!!! question "Exercise 3: Set Up an Integration"

    Choose one integration and set it up:

    **Option A — GitHub/Bitbucket:**

    1. Connect your repo to Jira
    2. Create an issue in Jira
    3. Make a commit with the issue key in the message
    4. Verify the commit appears on the Jira issue

    **Option B — Slack:**

    1. Install Jira Cloud for Slack
    2. Subscribe a channel to your project
    3. Create an issue and verify the notification appears in Slack
    4. Create an issue from Slack using `/jira create`
