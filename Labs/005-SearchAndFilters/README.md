# Lab 005 - Search & Filters

!!! hint "Overview"

    - In this lab, you will master Jira's search capabilities from basic text search to advanced JQL.
    - You will create saved filters and share them with your team.
    - By the end, you will be able to find any issue quickly using JQL queries.

## Prerequisites

- Several issues in your project (created in previous labs)
- Basic understanding of issue fields

## What You Will Learn

- Quick search and basic search
- Introduction to JQL (Jira Query Language)
- Common JQL queries for daily work
- Creating and managing saved filters
- Filter subscriptions and sharing

---

## Quick Search

The search bar at the top of every Jira page supports quick search:

- Type an **issue key** (e.g., `DEV-123`) to jump directly to it
- Type **text** to search across summaries and descriptions
- Use **prefix** to narrow: `my:` (assigned to me), `r:` (recently viewed)

### Demo: Quick Search

1. Click the search bar (or press ++slash++)
2. Type `my open bugs` — Jira interprets natural language
3. Try typing a project key like `DEV-` to see autocomplete suggestions
4. Type a specific issue key to jump directly to it

---

## Basic Search

Click **Filters** → **Advanced issue search** to access the basic search interface.

Use the dropdowns to filter by:

- **Project** — Select one or more projects
- **Type** — Epic, Story, Task, Bug
- **Status** — To Do, In Progress, Done
- **Assignee** — Specific person or Unassigned
- **Priority** — Highest to Lowest
- **More** — Labels, Components, Fix Version, Created date, etc.

---

## JQL — Jira Query Language

JQL is a powerful structured query language for finding issues. Switch to JQL mode by clicking **Switch to JQL** in the search view.

### JQL Syntax

```
field operator value [AND/OR field operator value]
```

### Common Operators

| Operator  | Meaning             | Example                              |
| --------- | ------------------- | ------------------------------------ |
| `=`       | Equals              | `status = "In Progress"`             |
| `!=`      | Not equals          | `priority != Low`                    |
| `IN`      | In a list           | `status IN ("To Do", "In Progress")` |
| `NOT IN`  | Not in a list       | `type NOT IN (Sub-task)`             |
| `~`       | Contains text       | `summary ~ "login"`                  |
| `!~`      | Does not contain    | `summary !~ "test"`                  |
| `>`       | Greater than        | `created > -7d`                      |
| `<`       | Less than           | `due < "2026-05-01"`                 |
| `>=`      | Greater or equal    | `priority >= High`                   |
| `IS`      | Is (for empty/null) | `assignee IS EMPTY`                  |
| `IS NOT`  | Is not              | `assignee IS NOT EMPTY`              |
| `WAS`     | Was at some point   | `status WAS "In Progress"`           |
| `CHANGED` | Field was changed   | `status CHANGED after -1d`           |

### Keywords

| Keyword             | Description                          |
| ------------------- | ------------------------------------ |
| `currentUser()`     | The logged-in user                   |
| `now()`             | Current date/time                    |
| `startOfDay()`      | Midnight today                       |
| `endOfDay()`        | End of today                         |
| `startOfWeek()`     | Monday of current week               |
| `startOfMonth()`    | First day of current month           |
| `-7d`, `-2w`, `-1M` | Relative dates (days, weeks, months) |

### Sorting

```sql
ORDER BY created DESC, priority ASC
```

---

## Essential JQL Queries

### For Users

```sql
-- My open issues
assignee = currentUser() AND status != Done ORDER BY priority DESC

-- My issues due this week
assignee = currentUser() AND due <= endOfWeek() AND status != Done

-- Bugs I reported
reporter = currentUser() AND type = Bug

-- Recently updated in my project
project = DEV AND updated > -1d ORDER BY updated DESC

-- Unassigned high priority issues
project = DEV AND assignee IS EMPTY AND priority IN (Highest, High)
```

### For Managers

```sql
-- Team's open issues
project = DEV AND status != Done ORDER BY assignee, priority DESC

-- Overdue issues
project = DEV AND due < now() AND status != Done

-- Issues created this sprint with no estimate
project = DEV AND sprint IN openSprints() AND "Story Points" IS EMPTY

-- Blocked issues
project = DEV AND status = Blocked

-- Issues without an assignee
project = DEV AND assignee IS EMPTY AND status != Done
```

### For Admins

```sql
-- All issues changed in the last 24 hours
project = DEV AND updated > -24h

-- Issues that have been in "In Progress" for more than 5 days
project = DEV AND status = "In Progress" AND status CHANGED TO "In Progress" BEFORE -5d

-- Issues with no description
project = DEV AND description IS EMPTY AND type != Sub-task
```

---

## Saved Filters

### Creating a Saved Filter

1. Run a JQL query in the search view
2. Click **Save as** (or **Save filter**)
3. Enter a name: `My Open Bugs`
4. Click **Submit**

### Managing Filters

- **Edit**: Open the filter, modify the JQL, click **Save**
- **Share**: Click **Details** → set permissions (project, group, or public)
- **Subscribe**: Click **Details** → **New subscription** → set frequency
- **Favorite**: Star a filter to add it to your **Filters** sidebar

### Demo: Create Key Filters

Create and save these filters:

| Filter Name          | JQL                                                                  |
| -------------------- | -------------------------------------------------------------------- |
| `My Open Issues`     | `assignee = currentUser() AND status != Done ORDER BY priority DESC` |
| `Unassigned Backlog` | `project = DEV AND assignee IS EMPTY AND status = "To Do"`           |
| `This Week's Bugs`   | `type = Bug AND created > startOfWeek() ORDER BY priority DESC`      |
| `Overdue Items`      | `due < now() AND status != Done ORDER BY due ASC`                    |

---

## Exercise

!!! question "Exercise 1: JQL Practice"

    Write JQL queries for each scenario (test them in the search view):

    1. Find all **High** and **Highest** priority issues in your project
    2. Find all **Bugs** assigned to you that are not Done
    3. Find all issues created in the **last 7 days**
    4. Find all issues with the label `frontend`
    5. Find all **Epics** that have child issues still in "To Do"

!!! question "Exercise 2: Create and Share Filters"

    1. Create 3 saved filters using your JQL queries from Exercise 1
    2. Star all 3 filters (they should appear in your Filters sidebar)
    3. Share one filter with your project team
    4. Add one filter to a dashboard as a **Filter Results** gadget

!!! question "Exercise 3: Filter Subscriptions"

    1. Open one of your saved filters
    2. Click **Details** → **New subscription**
    3. Set it to email you **daily** at 9:00 AM
    4. This will send you a daily digest of matching issues
