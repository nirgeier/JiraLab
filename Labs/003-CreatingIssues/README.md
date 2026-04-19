# Lab 003 - Creating Issues

!!! hint "Overview"

    - In this lab, you will create various issue types in Jira with proper fields and metadata.
    - You will learn about Epics, Stories, Tasks, Bugs, and Sub-tasks.
    - You will practice linking issues and organizing work hierarchically.

## Prerequisites

- Completed Lab 001 & 002 or basic Jira navigation skills
- A project where you have permission to create issues

## What You Will Learn

- How to create different issue types
- Required and optional fields
- Writing effective summaries and descriptions
- Setting priority, labels, and components
- Linking issues together
- Creating sub-tasks
- Using the Epic hierarchy

---

## The Create Issue Dialog

Press ++c++ or click the **Create** button to open the issue creation form.

### Required Fields

| Field          | Description                          |
| -------------- | ------------------------------------ |
| **Project**    | Which project this issue belongs to  |
| **Issue Type** | Epic, Story, Task, Bug, or Sub-task  |
| **Summary**    | A concise title describing the issue |

### Common Optional Fields

| Field            | Description                                          |
| ---------------- | ---------------------------------------------------- |
| **Description**  | Detailed information, acceptance criteria, steps     |
| **Assignee**     | Who is responsible for this issue                    |
| **Priority**     | Highest, High, Medium, Low, Lowest                   |
| **Labels**       | Tags for categorization (e.g., `frontend`, `urgent`) |
| **Components**   | Subsystems of your project (e.g., `API`, `UI`)       |
| **Sprint**       | Which sprint this issue belongs to                   |
| **Story Points** | Effort estimate (for Stories)                        |
| **Fix Version**  | Release this issue should be part of                 |
| **Due Date**     | Deadline for completion                              |

---

## Writing Good Summaries

!!! tip "Summary Best Practices"

    - Start with the **what**: `Add login form validation`
    - Be specific: `Fix 500 error on /api/users when email is empty` (not `Fix bug`)
    - Keep it under 80 characters
    - Use consistent naming: `[Component] Action description`

### Good vs Bad Summaries

| :material-check: Good                              | :material-close: Bad |
| -------------------------------------------------- | -------------------- |
| `Add email validation to registration form`        | `Fix form`           |
| `[API] Return 404 when user not found`             | `API bug`            |
| `Update deployment docs for Kubernetes migration`  | `Docs update`        |
| `As a user, I want to reset my password via email` | `Password stuff`     |

---

## Writing Descriptions

Use Jira's rich text editor or Markdown to write clear descriptions:

### Story Description Template

```markdown
## User Story

As a [role], I want [feature] so that [benefit].

## Acceptance Criteria

- [ ] Criterion 1
- [ ] Criterion 2
- [ ] Criterion 3

## Technical Notes

- Implementation details or constraints

## Design

- Link to mockup or wireframe
```

### Bug Description Template

```markdown
## Description

Brief description of the bug.

## Steps to Reproduce

1. Go to '...'
2. Click on '...'
3. Scroll down to '...'
4. See error

## Expected Behavior

What should happen.

## Actual Behavior

What actually happens.

## Environment

- Browser: Chrome 120
- OS: macOS 14.2
- Jira version: Cloud

## Screenshots

Attach screenshots or screen recordings.
```

---

## Demo: Create a Full Set of Issues

Follow these steps to create a realistic set of linked issues:

### Step 1: Create an Epic

1. Press ++c++ to open Create Issue
2. **Issue Type**: Epic
3. **Summary**: `User Authentication Module`
4. **Description**: `Implement complete user authentication including login, registration, password reset, and session management.`
5. Click **Create**

### Step 2: Create Stories Under the Epic

Create these stories, setting the **Epic Link** to `User Authentication Module`:

| Story Summary                            | Priority | Story Points |
| ---------------------------------------- | -------- | ------------ |
| `Add login page with email and password` | High     | 5            |
| `Add registration form with validation`  | High     | 8            |
| `Implement password reset via email`     | Medium   | 5            |
| `Add session timeout and auto-logout`    | Low      | 3            |

### Step 3: Create a Bug

1. **Issue Type**: Bug
2. **Summary**: `Login form accepts empty password`
3. **Priority**: High
4. **Description**: Use the Bug template above
5. **Link**: `is caused by` → the login page Story

### Step 4: Create Sub-tasks

Open the login page Story and create sub-tasks:

1. `Design login page mockup` — 2 points
2. `Implement login form HTML/CSS` — 3 points
3. `Add form validation logic` — 2 points
4. `Write unit tests for login` — 2 points

---

## Issue Linking

Link issues to show relationships:

| Link Type                         | Meaning                             |
| --------------------------------- | ----------------------------------- |
| **blocks / is blocked by**        | Issue A must be done before Issue B |
| **clones / is cloned by**         | Issue is a copy of another          |
| **duplicates / is duplicated by** | Issues describe the same thing      |
| **relates to**                    | General relationship                |
| **causes / is caused by**         | Root cause relationship             |

### How to Link Issues

1. Open an issue
2. Click **Link** in the issue actions
3. Choose the link type
4. Search for the target issue
5. Click **Link**

---

## Exercise

!!! question "Exercise 1: Create an Epic with Child Issues"

    1. Create an Epic: `E-commerce Shopping Cart`
    2. Under the Epic, create:
        - 3 Stories (Add to cart, View cart, Checkout)
        - 1 Task (Set up payment gateway integration)
        - 1 Bug (Cart total doesn't update when quantity changes)
    3. Add sub-tasks to the "Checkout" story:
        - Design checkout flow
        - Implement shipping address form
        - Add payment processing
        - Write integration tests
    4. Link the Bug as "is caused by" the "Add to cart" Story

!!! question "Exercise 2: Practice Descriptions"

    1. Open each issue you created in Exercise 1
    2. Add a proper description using the templates above
    3. Set appropriate **Priority** and **Labels** on each issue
    4. Assign at least 2 issues to yourself
