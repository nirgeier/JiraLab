## Solution 13 - Advanced Admin

### Task 1: Bulk Operations

1. Create 8 issues: use Quick Create (++c++), add label `admin-test` to each
2. Search: `labels = "admin-test"`
3. Select all → **Bulk change** → **Edit** → Priority = High → Confirm
4. Search again → select 4 → **Bulk change** → **Transition** → "In Progress" → Confirm
5. Reassign all: **Bulk change** → **Edit** → Assignee = yourself → Confirm
6. Select the 4 "In Progress" → **Bulk change** → **Transition** → "Done" → Confirm

### Task 2: Audit and Health Check

**Audit Log:** **Jira Settings** → **System** → **Audit log**

| #   | Who   | What                      | When        |
| --- | ----- | ------------------------- | ----------- |
| 1   | admin | Updated permission scheme | Today 10:00 |
| 2   | admin | Created workflow          | Today 09:30 |
| 3   | ...   | ...                       | ...         |

**Health Check JQL:**

```sql
-- 30+ days stale
updated < -30d AND status != Done

-- Unassigned 7+ days
assignee IS EMPTY AND created < -7d AND status != Done

-- Empty descriptions
description IS EMPTY AND type NOT IN (Sub-task)
```

**Cleanup actions:**

- Stale issues: Review and close or reassign
- Unassigned: Triage and assign during next standup
- Empty descriptions: Require descriptions via workflow validator

### Task 3: Integration Setup

**GitHub Integration:**

1. Go to **Apps** → **Find new apps** → search "GitHub for Jira"
2. Install and connect your GitHub organization
3. Create issue DEV-100
4. Commit: `git commit -m "DEV-100 Fix login validation"`
5. The commit and branch appear on the Jira issue under **Development** panel

**Slack Integration:**

1. In Slack: search for "Jira Cloud" app → install
2. In a channel: `/jira connect`
3. `/jira subscribe` → choose project and events
4. Create an issue → notification appears in channel
5. `/jira create` → fill in the modal form → issue is created
