# Lab 009 - Project Configuration

!!! hint "Overview"

    - In this lab, you will learn how Jira administrators create and configure projects.
    - You will set up issue types, screens, fields, and project schemes.
    - By the end, you will be able to configure a project from scratch.

## Prerequisites

- **Jira Administrator** permissions on your instance
- Understanding of Jira concepts from the User Track

## What You Will Learn

- Creating projects from templates and from scratch
- Configuring issue types and issue type schemes
- Custom fields and field configurations
- Screens and screen schemes
- Project categories and defaults

---

## Creating a New Project

### From a Template

1. Click **Projects** → **Create project**
2. Choose a template:
   - **Scrum** — Sprint-based agile development
   - **Kanban** — Continuous flow
   - **Bug Tracking** — Simple issue tracking
   - **Project Management** — Business project tracking
3. Set:
   - **Name**: `Training Project`
   - **Key**: `TRAIN`
   - **Project lead**: Yourself
4. Click **Create**

### Team-Managed vs Company-Managed

| Feature               | Team-Managed             | Company-Managed              |
| --------------------- | ------------------------ | ---------------------------- |
| **Configuration**     | Simplified, per-project  | Full control, shared schemes |
| **Who can configure** | Project admins           | Jira admins only             |
| **Custom fields**     | Limited to the project   | Shared across projects       |
| **Workflows**         | Simplified               | Fully customizable           |
| **Best for**          | Small teams, quick setup | Enterprises, standardization |

!!! tip "Recommendation"

    Use **Company-Managed** projects for production environments where consistency across projects matters. Use **Team-Managed** for experimentation and small teams.

---

## Issue Types

### Default Issue Types

| Issue Type | Use Case                    |
| ---------- | --------------------------- |
| Epic       | Large feature or initiative |
| Story      | User-facing requirement     |
| Task       | General work item           |
| Bug        | Defect report               |
| Sub-task   | Breakdown of a parent issue |

### Creating Custom Issue Types

1. Go to **Jira Settings** (gear icon) → **Issues** → **Issue types**
2. Click **Add issue type**
3. Configure:
   - **Name**: `Spike` (for research/investigation tasks)
   - **Description**: `A time-boxed research task to reduce uncertainty`
   - **Type**: Standard (or Sub-task)
   - **Icon**: Choose an appropriate icon
4. Click **Create**

### Issue Type Schemes

An Issue Type Scheme defines which issue types are available in a project.

1. Go to **Jira Settings** → **Issues** → **Issue type schemes**
2. Click **Add issue type scheme**
3. Name: `Software Development Scheme`
4. Drag issue types from Available to Selected:
   - Epic, Story, Task, Bug, Sub-task, Spike
5. Set the **Default issue type**: Task
6. Associate the scheme with your project

---

## Custom Fields

### Creating a Custom Field

1. Go to **Jira Settings** → **Issues** → **Custom fields**
2. Click **Create custom field**
3. Choose the field type:

| Type              | Use Case            | Example                     |
| ----------------- | ------------------- | --------------------------- |
| **Text (single)** | Short text input    | `Customer Name`             |
| **Text (multi)**  | Long text input     | `Root Cause Analysis`       |
| **Select List**   | Dropdown selection  | `Environment` (Dev/QA/Prod) |
| **Number**        | Numeric value       | `Business Value`            |
| **Date Picker**   | Date selection      | `Go-Live Date`              |
| **Checkbox**      | Multiple selections | `Affected Platforms`        |
| **User Picker**   | Select a Jira user  | `QA Reviewer`               |

4. Name: `Environment`
5. Description: `The target deployment environment`
6. Select which screens to display this field on
7. Click **Create**

---

## Screens

Screens define which fields appear when creating, viewing, or editing an issue.

### Screen Types

| Screen     | When It Shows                  |
| ---------- | ------------------------------ |
| **Create** | When creating a new issue      |
| **Edit**   | When editing an existing issue |
| **View**   | When viewing issue details     |

### Demo: Customize a Screen

1. Go to **Jira Settings** → **Issues** → **Screens**
2. Click on a screen (e.g., `Default Screen`)
3. Add fields: click **Select Field** → choose `Environment`
4. Reorder fields by dragging
5. Remove unnecessary fields by clicking the **X**

### Screen Schemes

Screen Schemes map issue operations (Create, Edit, View) to specific screens:

1. Go to **Jira Settings** → **Issues** → **Screen schemes**
2. Create a new scheme or edit an existing one
3. Map:
   - Create → `Bug Create Screen` (simplified fields)
   - Edit → `Default Edit Screen`
   - View → `Default View Screen`

---

## Exercise

!!! question "Exercise 1: Create a Project from Scratch"

    1. Create a new **Company-Managed** Scrum project
    2. Name: `Lab Training Project`, Key: `LTP`
    3. Configure the issue type scheme to include: Epic, Story, Task, Bug, Sub-task
    4. Create a custom issue type: `Spike`
    5. Add it to the project's issue type scheme

!!! question "Exercise 2: Custom Fields"

    1. Create these custom fields:
        - `Environment` (Select List: Dev, QA, Staging, Production)
        - `Business Value` (Number)
        - `Go-Live Date` (Date Picker)
    2. Add all 3 fields to the project's Create and View screens
    3. Create a test issue and verify the fields appear

!!! question "Exercise 3: Screen Configuration"

    1. Create a custom screen: `Bug Report Screen`
    2. Add fields: Summary, Description, Priority, Environment, Steps to Reproduce, Expected Behavior, Actual Behavior
    3. Create a screen scheme that uses this screen for Bug creation
    4. Associate it with your project
    5. Test by creating a Bug — verify the correct fields appear
