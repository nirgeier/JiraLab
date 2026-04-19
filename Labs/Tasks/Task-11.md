## Task 11 - Permissions & Schemes

### Objective

Configure a complete permission model for a project.

---

??? question "Task 1: Permission Scheme"

    Design and create a permission scheme with these roles:

    | Role            | Browse | Create | Edit | Delete | Assign | Manage Sprints |
    | --------------- | ------ | ------ | ---- | ------ | ------ | -------------- |
    | Admin           | ✓      | ✓      | ✓    | ✓      | ✓      | ✓              |
    | Developer       | ✓      | ✓      | ✓    | ✗      | ✗      | ✗              |
    | QA              | ✓      | ✓      | ✓    | ✗      | ✗      | ✗              |
    | Stakeholder     | ✓      | ✗      | ✗    | ✗      | ✗      | ✗              |

    1. Create the Permission Scheme
    2. Map permissions to Project Roles
    3. Associate with your project

??? question "Task 2: Issue Security Levels"

    1. Create an Issue Security Scheme with 3 levels:
        - **Public** — All project members can see
        - **Internal** — Only Developers and Admins
        - **Confidential** — Only Admins
    2. Associate with your project
    3. Create one issue at each security level
    4. Verify access restrictions work correctly

??? question "Task 3: Notification Scheme"

    1. Create a custom Notification Scheme: `Minimal Notifications`
    2. Configure:
        - Issue Created → Reporter, Project Lead
        - Issue Assigned → Assignee only
        - Comment Added → Watchers, Assignee
        - Issue Resolved → Reporter
    3. Remove all other notification events
    4. Associate with your project
    5. Test by performing actions and checking notifications
