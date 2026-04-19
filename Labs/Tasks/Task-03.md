## Task 03 - Creating Issues

### Objective

Create a realistic set of well-structured Jira issues.

---

??? question "Task 1: Build a Project Backlog"

    Create the following issues for a fictional **Online Bookstore** project:

    **Epic**: `User Account Management`

    **Stories** (under the Epic):

    1. `As a user, I want to register with email and password`
       - Priority: High, Points: 5, Label: `auth`
    2. `As a user, I want to log in to my account`
       - Priority: High, Points: 3, Label: `auth`
    3. `As a user, I want to reset my forgotten password`
       - Priority: Medium, Points: 5, Label: `auth`
    4. `As a user, I want to update my profile information`
       - Priority: Low, Points: 3, Label: `profile`

    **Bug**: `Registration form accepts invalid email format`
    - Priority: High, Link: "is caused by" → Story #1

    **Task**: `Set up email service for password reset notifications`
    - Priority: Medium, Points: 2

??? question "Task 2: Add Descriptions"

    For each issue created in Task 1:

    1. Add a detailed description using the appropriate template:
        - Stories: Use the User Story template (As a / I want / So that + Acceptance Criteria)
        - Bug: Use the Bug template (Steps to Reproduce, Expected, Actual)
        - Task: Include technical requirements and acceptance criteria
    2. Each description should be at least 5 lines

??? question "Task 3: Sub-tasks and Links"

    1. Add sub-tasks to Story #1 (Registration):
        - Design registration form mockup
        - Implement frontend form with validation
        - Create backend registration API endpoint
        - Write unit and integration tests
    2. Link Story #2 (Login) as "blocks" Story #3 (Password Reset)
    3. Verify all links appear correctly on each issue
