# Lab 008 - Reports & Metrics

!!! hint "Overview"

    - In this lab, you will explore Jira's built-in reports and learn to extract actionable insights.
    - You will create custom dashboards for team and stakeholder reporting.
    - By the end, you will know which reports to use for different management questions.

## Prerequisites

- A project with at least one completed sprint (or data from previous labs)
- Manager-level access to the project

## What You Will Learn

- Built-in Jira reports and when to use each
- Burndown and Burnup charts
- Velocity and Sprint reports
- Cumulative Flow Diagrams
- Creating executive dashboards
- Exporting data for external reporting

---

## Built-In Reports

Navigate to your project → **Reports** to access all available reports.

### Scrum Reports

| Report              | Question It Answers                              | How to Read It                      |
| ------------------- | ------------------------------------------------ | ----------------------------------- |
| **Burndown Chart**  | Are we on track to complete the sprint?          | Line should trend toward zero       |
| **Sprint Report**   | What did we complete vs. plan?                   | Green = completed, red = incomplete |
| **Velocity Chart**  | How much work does the team complete per sprint? | Bars show completed vs committed    |
| **Cumulative Flow** | Where are bottlenecks in our process?            | Widening bands = bottleneck         |

### Kanban Reports

| Report              | Question It Answers                  | How to Read It                        |
| ------------------- | ------------------------------------ | ------------------------------------- |
| **Control Chart**   | How long do issues take to complete? | Dots above the line = slower than avg |
| **Cumulative Flow** | Is work flowing smoothly?            | Parallel bands = healthy flow         |

---

## Burndown Chart

The Burndown Chart tracks remaining work in the current sprint.

### Reading the Chart

- **Gray line**: Ideal burndown (straight line from total to zero)
- **Red/Blue line**: Actual remaining work
- **Above the gray line**: Behind schedule
- **Below the gray line**: Ahead of schedule
- **Flat sections**: No progress (weekends, blocked work)
- **Jumps up**: Scope was added mid-sprint

### Demo: Analyze a Burndown

1. Go to **Reports** → **Burndown Chart**
2. Select a completed sprint
3. Identify:
   - Was the team ahead or behind schedule?
   - Were there scope changes (upward jumps)?
   - Were there periods of no progress?
4. Discuss what caused deviations

---

## Velocity Chart

Velocity measures the total story points completed per sprint.

### Using Velocity for Planning

1. Go to **Reports** → **Velocity Chart**
2. Look at the last 3-5 sprints
3. Calculate the **average** completed points
4. Use this average as your sprint planning baseline
5. Note the **commitment vs completion** ratio:
   - Consistently under-committing? Plan more ambitiously
   - Consistently over-committing? Reduce sprint scope

### Velocity Trends

| Pattern             | Meaning                                      | Action                           |
| ------------------- | -------------------------------------------- | -------------------------------- |
| Increasing velocity | Team is improving or estimates are inflating | Verify estimation consistency    |
| Decreasing velocity | Technical debt, distractions, or burnout     | Investigate root cause           |
| Stable velocity     | Healthy, predictable team                    | Continue current practices       |
| Wildly variable     | Inconsistent estimation or disruptions       | Improve estimation, reduce noise |

---

## Cumulative Flow Diagram (CFD)

The CFD shows how issues move through statuses over time.

### Reading the CFD

- Each colored band represents a status (To Do, In Progress, Done)
- **Band width** = number of issues in that status
- **Growing bands** = work accumulating (potential bottleneck)
- **Narrowing bands** = work flowing through
- **Parallel bands** = healthy, steady flow

### Demo: Identify Bottlenecks

1. Go to **Reports** → **Cumulative Flow Diagram**
2. Look for:
   - Is the "In Progress" band growing wider? → WIP too high
   - Is the "In Review" band growing? → Review bottleneck
   - Is the "Done" band growing steadily? → Healthy delivery

---

## Custom Dashboards for Stakeholders

### Executive Dashboard

Create a dashboard with these gadgets:

| Gadget                     | Configuration                          |
| -------------------------- | -------------------------------------- |
| **Sprint Health**          | Current sprint, show burndown          |
| **Velocity Chart**         | Last 6 sprints                         |
| **Pie Chart**              | Group by Priority, filter: open issues |
| **Two Dimensional Filter** | Rows: Assignee, Columns: Status        |
| **Created vs Resolved**    | Last 30 days, project scope            |
| **Filter Results**         | Show overdue issues                    |

### Team Lead Dashboard

| Gadget                 | Configuration                 |
| ---------------------- | ----------------------------- |
| **Assigned to Me**     | Default                       |
| **Sprint Burndown**    | Current sprint                |
| **Filter Results**     | Blocked issues filter         |
| **Activity Stream**    | Project activity, last 2 days |
| **Workload Pie Chart** | Group by Assignee             |

---

## Exporting Data

### Export Options

1. **CSV Export**: From any filter results, click **Export** → **CSV**
2. **Dashboard PDF**: Use browser print to PDF
3. **Confluence Integration**: Embed Jira gadgets directly in Confluence pages

---

## Exercise

!!! question "Exercise 1: Analyze Sprint Performance"

    1. Open the **Sprint Report** for your last completed sprint
    2. Document:
        - How many story points were committed?
        - How many were completed?
        - Which issues were not completed and why?
        - What was the completion rate percentage?
    3. Open the **Burndown Chart** for the same sprint
    4. Identify at least 2 patterns (scope changes, flat periods, etc.)

!!! question "Exercise 2: Build an Executive Dashboard"

    1. Create a new dashboard: `Project Status - Executive`
    2. Add the 6 gadgets from the Executive Dashboard table above
    3. Arrange them in a clean layout
    4. Share the dashboard with your team/project group
    5. Export it as a PDF

!!! question "Exercise 3: Velocity Analysis"

    1. Open the **Velocity Chart** for your project
    2. If you have 3+ sprints, calculate:
        - Average velocity
        - Commitment accuracy (committed vs completed)
        - Velocity trend (increasing, decreasing, stable)
    3. Based on the analysis, recommend a story point target for the next sprint
