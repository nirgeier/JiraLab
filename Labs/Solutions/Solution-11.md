## Solution 11 - Permissions & Schemes

### Task 1: Permission Scheme

1. **Jira Settings** → **Permission schemes** → **Add permission scheme**
2. Name: `Training Permission Scheme`
3. Add permissions:

| Permission      | Admin Role | Developer Role | QA Role | Stakeholder Role |
| --------------- | ---------- | -------------- | ------- | ---------------- |
| Browse Projects | ✓          | ✓              | ✓       | ✓                |
| Create Issues   | ✓          | ✓              | ✓       | ✗                |
| Edit Issues     | ✓          | ✓              | ✓       | ✗                |
| Delete Issues   | ✓          | ✗              | ✗       | ✗                |
| Assign Issues   | ✓          | ✗              | ✗       | ✗                |
| Manage Sprints  | ✓          | ✗              | ✗       | ✗                |

4. **Project Settings** → **Permissions** → switch to the new scheme

### Task 2: Issue Security Levels

1. **Jira Settings** → **Issue security schemes** → **Add**
2. Name: `Training Security Scheme`
3. Add levels:
   - Public → Grant to: Project Role = Member
   - Internal → Grant to: Project Roles = Developers, Admin
   - Confidential → Grant to: Project Role = Admin
4. Associate with project in Project Settings
5. Create issues: set Security Level field on each

### Task 3: Notification Scheme

1. **Jira Settings** → **Notification schemes** → copy Default → rename to `Minimal Notifications`
2. Remove all events except: Created, Assigned, Comment Added, Resolved
3. Set recipients per the task requirements
4. Associate with project
5. Test: create an issue → check that only the intended people get notified
