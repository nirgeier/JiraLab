## Solution 09 - Project Configuration

### Task 1: Create a New Project

1. **Projects** → **Create project** → **Scrum** → **Company-managed**
2. Name: `Lab Config Project`, Key: `LCP`
3. Lead: Your user
4. The project comes with default: issue types (Epic, Story, Task, Bug, Sub-task), simplified workflow, default screens

### Task 2: Custom Issue Types and Fields

**Create Spike issue type:**

1. **Jira Settings** → **Issues** → **Issue types** → **Add issue type**
2. Name: `Spike`, Type: Standard, submit
3. **Issue type schemes** → edit your project's scheme → add Spike

**Create custom fields:**

1. **Jira Settings** → **Issues** → **Custom fields** → **Create custom field**
2. Select List → Name: `Environment` → Options: Dev, QA, Staging, Production
3. Number → Name: `Business Value`
4. User Picker → Name: `Reviewer`
5. On each: select which screens to add it to (Create Screen, View Screen)

### Task 3: Screen Customization

1. **Jira Settings** → **Issues** → **Screens** → **Add screen**
2. Name: `Bug Intake Screen`
3. Add fields: Summary, Description, Priority, Environment, Steps to Reproduce
4. **Screen schemes** → **Add screen scheme** → Map: Create Issue → Bug Intake Screen
5. **Issue type screen schemes** → associate Bug with the new screen scheme
6. Test: Create a Bug → verify only the intended fields appear
