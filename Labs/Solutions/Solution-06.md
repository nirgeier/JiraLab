## Solution 06 - Boards & Sprints

### Task 1: Sprint Planning

1. Go to **Backlog** view
2. Verify issues have story points: open each and set if missing
3. Click **Create sprint** (button above backlog)
4. Drag issues into the sprint — watch the point counter
5. Click **Start sprint** → Name: `Sprint 1`, Duration: 1 week, Goal: `Complete user registration`
6. The board now shows sprint issues

### Task 2: Sprint Execution

1. On the board, drag 3 issues to "In Progress"
2. Drag 4 issues to "Done" (these are your completed items)
3. Leave 2 in "To Do"
4. To comment: open issue → scroll to Comments → write → Save
5. Click **Complete sprint** (top right of board)
6. Select "Move to backlog" for incomplete issues → **Complete**
7. The Sprint Report auto-generates showing completed vs incomplete

### Task 3: Board Configuration

1. Board → **⋯** → **Board settings**
2. **Quick filters** → **Add quick filter**:
   - Name: `Only Bugs`, JQL: `type = Bug`
   - Name: `My Issues`, JQL: `assignee = currentUser()`
3. **Swimlanes** → select **Epics**
4. **Columns** → click "In Progress" → set Min/Max constraint → Max: 3
