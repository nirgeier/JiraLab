## Solution 10 - Workflow Customization

### Task 1: Design a Workflow

1. **Jira Settings** → **Workflows** → **Add workflow** → Name: `Support Ticket Workflow`
2. Add statuses (click **Add status** for each):
   - Open (To Do), Triaged (To Do), In Progress (In Progress), Awaiting Customer (In Progress), Resolved (Done), Closed (Done), Escalated (In Progress)
3. Add transitions by clicking source status → **Add transition** → target status:
   - Open → Triaged (Triage)
   - Triaged → In Progress (Start Work)
   - In Progress → Awaiting Customer (Request Info)
   - Awaiting Customer → In Progress (Customer Responded)
   - In Progress → Resolved (Resolve)
   - Resolved → Closed (Close)
   - Closed → Open (Reopen)
4. For global Escalate: Add as a **global transition** → targets Escalated

### Task 2: Add Rules

1. Click **Triage** transition → **Conditions** → **User Is In Project Role** → `support-team`
2. Click **Close** transition → **Validators** → **Field Required** → `Resolution`
3. Click **Resolve** transition → **Post Functions** → **Update Issue Field** → Resolution = Done
4. Click **Reopen** transition → **Post Functions** → **Update Issue Field** → Resolution = (clear)
5. Click **Escalate** → **Conditions** → **User Is In Group** → `managers`

### Task 3: Publish and Test

1. **Workflow schemes** → **Add workflow scheme** → Map Bug → Support Ticket Workflow
2. **Project Settings** → **Workflows** → Switch to the new scheme
3. Create a Bug and transition through: Open → Triaged → In Progress → Resolved → Closed
4. Try to Triage without the support-team role → should be blocked
5. Try to Close without Resolution → validator should prevent it
