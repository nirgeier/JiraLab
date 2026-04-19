## Solution 01 - Jira Overview

### Task 1: Identify Project Components

Navigate to **Projects** in the top navigation. For each project, click into it and check:

- **Project key**: Found in the URL and issue prefixes (e.g., `DEV`)
- **Project type**: Visible in Project Settings → Details (Scrum or Kanban)
- **Issue count**: Run JQL `project = DEV` and note the total results

### Task 2: Explore Issue Types

When creating issues:

- **Epic**: `User Authentication Module` — Priority: High, Label: `auth`
- **Story**: `Add login page with email/password` — Priority: High, Label: `frontend`
- **Task**: `Set up CI/CD pipeline` — Priority: Medium, Label: `devops`
- **Bug**: `Login form accepts empty password` — Priority: High, Label: `bug`

### Task 3: Issue Hierarchy

1. Create Epic first, note its key (e.g., `DEV-1`)
2. Create Stories — set **Epic Link** field to `DEV-1`
3. Open each Story → click **Create sub-task**
4. To link: open a Story → click **Link** → select "relates to" → search for the Bug
5. The Epic detail view should show all child issues in the **Child issues** section
