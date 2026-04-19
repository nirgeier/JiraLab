## Solution 04 - Workflow Basics

### Task 1: Full Lifecycle Walkthrough

**Issue A (Board drag & drop):**

1. Open the Board → find the issue card in "To Do"
2. Click and drag to "In Progress" column → release
3. Click and drag to "Done" column → release

**Issue B (Status button):**

1. Open the issue detail
2. Click the status badge (e.g., "TO DO")
3. Select "In Progress" from dropdown
4. Click status again → "In Review" (if available) → "Done"

**Issue C (Bulk):**

1. Go to the Board or use a filter
2. Select multiple issues (checkboxes)
3. Right-click → **Bulk change** → **Transition** → select "In Progress"

### Task 2: Workflow Investigation

View the workflow: Open issue → click Status → **View workflow**

Document format:

- **Statuses**: To Do, In Progress, In Review, Done
- **Transitions**: To Do → In Progress, In Progress → In Review, In Review → Done, In Review → In Progress (backward)
- Backward transitions usually exist: Done → Reopened/To Do

### Task 3: Resolution and Reopen

- When moved to **Done**: Resolution is auto-set to "Done"
- When **Reopened**: Resolution should be cleared (empty)
- If Resolution is not cleared, this is configured via workflow **post functions**
