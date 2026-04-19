## Solution 08 - Reports & Metrics

### Task 1: Sprint Analysis

Navigate to **Reports** → **Sprint Report** → select the completed sprint.

**What to document:**

| Metric             | Value      |
| ------------------ | ---------- |
| Committed points   | X          |
| Completed points   | Y          |
| Completion rate    | Y/X × 100% |
| Added mid-sprint   | N issues   |
| Removed mid-sprint | N issues   |

**Burndown patterns to look for:**

- Flat lines = no progress (blocked? weekends?)
- Upward jumps = scope added mid-sprint
- Steep drops = multiple issues completed at once (batch closing)

### Task 2: Velocity Tracking

- Average velocity = Sum of completed points ÷ Number of sprints
- Trend: Compare each sprint's velocity to the average
- Next sprint target: Use the 3-sprint average (not the best sprint)

### Task 3: Executive Dashboard

Gadgets:

1. Sprint Burndown → select current sprint
2. Velocity Chart → shows automatically if sprints exist
3. Pie Chart → Filter: all open issues, Statistic: Priority
4. Created vs Resolved → Period: last 30 days, project scope
5. Filter Results → JQL: `due < now() AND status != Done`

**Executive Summary example:**
"Sprint 1 completed 80% of committed work (16 of 20 points). Team velocity is stable at 16 points per sprint. There are currently 3 overdue items requiring attention."
