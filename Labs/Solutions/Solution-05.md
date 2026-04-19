## Solution 05 - Search & Filters

### Task 1: JQL Query Challenge

```sql
-- 1. My issues sorted by priority
assignee = currentUser() ORDER BY priority ASC

-- 2. Bugs created in last 7 days
type = Bug AND created > -7d

-- 3. In Progress with no due date
status = "In Progress" AND due IS EMPTY

-- 4. Epics with label auth
type = Epic AND labels = "auth"

-- 5. Issues updated today
updated > startOfDay()

-- 6. High+ priority not Done
priority IN (High, Highest) AND status != Done

-- 7. Summary contains login
summary ~ "login"

-- 8. Unassigned older than 3 days
assignee IS EMPTY AND created < -3d
```

!!! note
Priority ordering in JQL: `ORDER BY priority ASC` puts Highest first because priority values are 1=Highest, 5=Lowest.

### Task 2: Create Saved Filters

1. Run each JQL query
2. Click **Save as** → enter the filter name
3. Click the ☆ icon to star each filter
4. Filters appear in **Filters** sidebar under "Starred"

### Task 3: Dashboard Integration

1. Go to your dashboard → **Add gadget** → **Filter Results** → select "My Open Work" filter
2. **Add gadget** → **Pie Chart** → Filter: "Team Bugs", Statistic Type: Priority
3. Open "Overdue" filter → **Details** → **New subscription** → Schedule: Daily, 9:00 AM
4. Open "Sprint Scope" → **Details** → **Edit permissions** → Add your project group
