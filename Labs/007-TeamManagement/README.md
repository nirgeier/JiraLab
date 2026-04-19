# Lab 007 - Team Management

!!! hint "Overview"

    - In this lab, you will learn how managers use Jira to manage teams and track progress.
    - You will practice work assignment, capacity planning, and team velocity tracking.
    - By the end, you will be able to manage a team's workload effectively in Jira.

## Prerequisites

- A project with multiple team members (or simulate with multiple assignees)
- Completed the User Track (Labs 001–006) or equivalent knowledge

## What You Will Learn

- Assigning and distributing work across a team
- Backlog prioritization strategies
- Capacity planning for sprints
- Monitoring team progress and blockers
- Using the Timeline (Gantt) view
- Managing team workload balance

---

## Work Assignment

### Assignment Strategies

| Strategy            | When to Use                         | How                                   |
| ------------------- | ----------------------------------- | ------------------------------------- |
| **Direct assign**   | Clear ownership, specialized skills | Set Assignee on issue creation        |
| **Self-assign**     | Team picks from prioritized backlog | Team members grab from "To Do" column |
| **Round-robin**     | Even distribution                   | Alternate assignments across members  |
| **Component-based** | Technical specialization            | Set default assignee per component    |

### Demo: Set Up Component-Based Assignment

1. Go to **Project settings** → **Components**
2. Create components:
   - `Frontend` — Default assignee: Developer A
   - `Backend` — Default assignee: Developer B
   - `Infrastructure` — Default assignee: DevOps engineer
3. When creating issues, select a component — the default assignee is auto-set

---

## Backlog Prioritization

### MoSCoW Method

| Priority        | Description                             | Action                             |
| --------------- | --------------------------------------- | ---------------------------------- |
| **Must Have**   | Critical for the sprint/release         | Label: `must-have`, top of backlog |
| **Should Have** | Important but not critical              | Label: `should-have`               |
| **Could Have**  | Nice to have, if time permits           | Label: `could-have`                |
| **Won't Have**  | Explicitly excluded from this iteration | Move to future sprint or backlog   |

### Demo: Prioritize a Backlog

1. Go to **Backlog** view
2. Use **Labels** to tag issues with MoSCoW priorities
3. Drag to reorder: Must Have → Should Have → Could Have
4. Use **Quick Filters** to view one priority level at a time

---

## Capacity Planning

### Calculating Sprint Capacity

```
Team Capacity = (Team Members × Sprint Days × Hours/Day) × Availability Factor

Example:
- 4 developers × 10 days × 6 productive hours × 0.8 (meetings, etc.)
= 192 hours ≈ 38 story points (at ~5 hours per point)
```

### Velocity Tracking

Velocity measures how much work a team completes per sprint.

1. Go to **Reports** → **Velocity Chart**
2. Review the last 3-5 sprints
3. Use the **average** as your planning baseline
4. Don't plan above the average — leave buffer for unknowns

### Demo: Sprint Capacity Check

1. Open your sprint in the **Backlog** view
2. Note the total story points in the sprint
3. Compare to your team's average velocity
4. If over capacity: move lower-priority items back to backlog
5. If under capacity: pull items from backlog

---

## Timeline View

The **Timeline** (Gantt-like) view shows work over time:

1. Navigate to **Timeline** in the left sidebar
2. Epics appear as bars spanning their duration
3. Child issues appear nested under Epics
4. Drag to adjust dates and dependencies
5. Use this for:
   - Release planning
   - Identifying scheduling conflicts
   - Communicating timelines to stakeholders

---

## Monitoring Progress

### Daily Check-In JQL Queries

```sql
-- What's blocked?
project = DEV AND status = Blocked ORDER BY priority DESC

-- What's been idle for 3+ days?
project = DEV AND status = "In Progress" AND updated < -3d

-- What's due soon?
project = DEV AND due <= 3d AND status != Done

-- Who has too much work?
project = DEV AND status = "In Progress" AND assignee IS NOT EMPTY
ORDER BY assignee ASC
```

### Workload View

1. Go to **Board** → enable **Swimlanes by Assignee**
2. Visually check each team member's lane
3. Look for:
   - Overloaded members (too many "In Progress" items)
   - Idle members (empty lanes)
   - Bottlenecks (items stuck in review)

---

## Exercise

!!! question "Exercise 1: Team Sprint Planning"

    1. Create 15 issues across 3 Epics with story points
    2. Assign issues to 3 different team members (or use dummy assignees)
    3. Calculate sprint capacity assuming velocity of 25 points
    4. Plan a sprint with balanced workload across team members
    5. Verify no team member has more than 10 points assigned

!!! question "Exercise 2: Progress Monitoring"

    1. Start your planned sprint
    2. Move some issues to "In Progress" and "Done"
    3. Leave 2 issues as "Blocked"
    4. Use the JQL queries above to create a "Manager Dashboard"
    5. Add gadgets: Workload Pie Chart, Sprint Health, Blocker List

!!! question "Exercise 3: Timeline Planning"

    1. Open the **Timeline** view
    2. Set start and end dates for each Epic
    3. Ensure child stories fall within their Epic's timeframe
    4. Identify any scheduling overlaps or gaps
    5. Adjust dates to create a realistic delivery plan
