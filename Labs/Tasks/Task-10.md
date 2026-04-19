## Task 10 - Workflow Customization

### Objective

Design and implement a custom workflow with conditions, validators, and post functions.

---

??? question "Task 1: Design a Workflow"

    Create a custom workflow for a **Support Ticket** process:

    **Statuses**: Open → Triaged → In Progress → Awaiting Customer → Resolved → Closed

    **Transitions**:
    - Open → Triaged (Triage)
    - Triaged → In Progress (Start Work)
    - In Progress → Awaiting Customer (Request Info)
    - Awaiting Customer → In Progress (Customer Responded)
    - In Progress → Resolved (Resolve)
    - Resolved → Closed (Close)
    - Closed → Open (Reopen)
    - Any → Escalated (Escalate — global transition)

    Build this workflow in the Jira workflow editor.

??? question "Task 2: Add Rules"

    Add these rules to your workflow:

    1. **Condition** on Triage: Only users in the `support-team` role can Triage
    2. **Validator** on Close: Resolution field must be set
    3. **Post Function** on Resolve: Set Resolution to "Done"
    4. **Post Function** on Reopen: Clear Resolution field
    5. **Condition** on Escalate: Only Managers can escalate

??? question "Task 3: Publish and Test"

    1. Create a Workflow Scheme mapping Bug → your Support Ticket Workflow
    2. Associate the scheme with your project
    3. Create a Bug and walk it through the complete lifecycle
    4. Test each condition and validator:
        - Try to Triage without the right role
        - Try to Close without a Resolution
    5. Document any issues and how you resolved them
