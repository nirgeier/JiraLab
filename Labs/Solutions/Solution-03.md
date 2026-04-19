## Solution 03 - Creating Issues

### Task 1: Build a Project Backlog

Create the Epic first, then reference it in child issues:

1. Press ++c++ → Issue Type: Epic → Summary: `User Account Management` → Create
2. For each Story: Press ++c++ → Issue Type: Story → Set Epic Link → Fill in fields
3. For the Bug: Set Priority High, then after creation → **Link** → "is caused by" → select Story #1
4. All story points should be set in the **Story Points** field (not a custom field)

### Task 2: Add Descriptions

**Story template example:**

```
## User Story
As a new user, I want to register with my email and password so that I can access the bookstore.

## Acceptance Criteria
- [ ] Registration form has email and password fields
- [ ] Email validation (proper format)
- [ ] Password must be at least 8 characters
- [ ] Confirmation email is sent after registration
- [ ] User is redirected to login page after registration
```

**Bug template example:**

```
## Steps to Reproduce
1. Go to /register
2. Enter "not-an-email" in the email field
3. Enter a valid password
4. Click Register

## Expected: Form shows validation error
## Actual: Form submits successfully with invalid email
```

### Task 3: Sub-tasks and Links

- Open Story #1 → **Create sub-task** (button below the description) → fill in each sub-task
- To link: Open Story #2 → **Link** → Type: "blocks" → Search: Story #3
- The "blocks" relationship means Login must be done before Password Reset
