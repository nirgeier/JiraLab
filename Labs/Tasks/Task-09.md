## Task 09 - Project Configuration

### Objective

Create and configure a Jira project from scratch with custom issue types and fields.

---

??? question "Task 1: Create a New Project"

    1. Create a new **Company-Managed** Scrum project
    2. Name: `Lab Config Project`, Key: `LCP`
    3. Set yourself as Project Lead
    4. Verify the project appears in the Projects list
    5. Note the default issue types, workflow, and screens

??? question "Task 2: Custom Issue Types and Fields"

    1. Create a custom issue type: `Spike`
        - Description: A time-boxed research task
    2. Add `Spike` to the project's Issue Type Scheme
    3. Create custom fields:
        - `Environment` — Select List (Dev, QA, Staging, Production)
        - `Business Value` — Number field
        - `Reviewer` — User Picker
    4. Add all 3 fields to the Create and View screens
    5. Create a test issue with each custom field populated

??? question "Task 3: Screen Customization"

    1. Create a custom screen: `Bug Intake Screen`
    2. Add fields: Summary, Description, Priority, Environment, Steps to Reproduce
    3. Remove unnecessary fields from the screen
    4. Create a Screen Scheme that uses this screen for Bug creation
    5. Test by creating a Bug — verify only the intended fields appear
