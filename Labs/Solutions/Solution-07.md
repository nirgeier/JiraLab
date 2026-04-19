## Solution 07 - Team Management

### Task 1: Workload Distribution

1. Create 12 issues with varied priorities and story points
2. Assign 4 to each of 3 people
3. Check balance: Person A = X points, Person B = Y points, Person C = Z points
4. No person should exceed 40% of the total points
5. Board → Board settings → Swimlanes → "Assignees" to visualize

**Example Distribution:**

| Assignee    | Issues | Points | Percentage |
| ----------- | ------ | ------ | ---------- |
| Developer A | 4      | 15     | 33%        |
| Developer B | 4      | 14     | 31%        |
| Developer C | 4      | 16     | 36%        |
| **Total**   | **12** | **45** | **100%**   |

### Task 2: Capacity Planning

```
Capacity = Developers × Days × Hours/Day × Availability
         = 3 × 10 × 6 × 0.8
         = 144 hours

Story Points = 144 hours ÷ 4 hours/point = 36 points
```

Plan the sprint with approximately 36 story points.

### Task 3: Progress Monitoring Dashboard

1. Create dashboard → **Add gadget** for each:
   - Pie Chart: Statistic = Assignee, Filter = sprint issues
   - Sprint Burndown: select current sprint
   - Filter Results: JQL = `status = "In Progress" AND updated < -3d`
   - Two Dimensional: Filter = sprint issues, Row = Assignee, Column = Status
