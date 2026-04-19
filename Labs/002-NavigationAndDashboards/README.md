# Lab 002 - Navigation & Dashboards

!!! hint "Overview"

    - In this lab, you will master the Jira user interface and navigation.
    - You will create and customize personal dashboards with gadgets.
    - By the end, you will be able to quickly find information and set up your personalized workspace.

## Prerequisites

- Completed Lab 001 or basic familiarity with Jira concepts
- Access to a Jira Cloud instance

## What You Will Learn

- Global navigation bar and its sections
- Quick search and keyboard shortcuts
- Creating and customizing dashboards
- Adding and configuring dashboard gadgets
- Sharing dashboards with your team

---

## Global Navigation

The top navigation bar in Jira provides access to all major areas:

| Element           | Purpose                                            |
| ----------------- | -------------------------------------------------- |
| **Jira logo**     | Return to your default dashboard                   |
| **Your work**     | View recently visited, assigned, and starred items |
| **Projects**      | Browse and switch between projects                 |
| **Filters**       | Access saved search filters                        |
| **Dashboards**    | View and manage dashboards                         |
| **People**        | Find team members and their work                   |
| **Apps**          | Access installed Jira apps/add-ons                 |
| **Create** button | Create a new issue from anywhere                   |
| **Search** bar    | Quick search across all projects                   |
| **Bell** icon     | Notifications                                      |
| **Settings** gear | System settings (admin only)                       |

---

## Keyboard Shortcuts

Jira has built-in keyboard shortcuts to speed up your workflow:

!!! tip "Press `?` on any Jira page to see all keyboard shortcuts"

| Shortcut | Action                 |
| -------- | ---------------------- |
| `c`      | Create a new issue     |
| `/`      | Focus the search bar   |
| `g` `d`  | Go to Dashboard        |
| `g` `b`  | Go to Board            |
| `g` `i`  | Go to Backlog          |
| `j`      | Next issue in list     |
| `k`      | Previous issue in list |
| `o`      | Open selected issue    |
| `a`      | Assign to me           |
| `m`      | Comment on issue       |
| `l`      | Edit labels            |

### Demo: Try Keyboard Shortcuts

1. Open any Jira page
2. Press ++question++ to see the shortcut overlay
3. Press ++c++ to open the Create Issue dialog (then close it)
4. Press ++slash++ to jump to the search bar
5. Press ++g++ then ++d++ to go to your dashboard

---

## Dashboards

Dashboards are customizable pages that display information at a glance using **gadgets**.

### Creating a Dashboard

1. Click **Dashboards** in the top navigation
2. Click **Create dashboard**
3. Enter a name: `My Work Dashboard`
4. Set visibility: **Private** (only you) or share with a group
5. Click **Save**

### Demo: Build a Personal Dashboard

Add the following gadgets to your new dashboard:

| Gadget                  | Purpose                              | Configuration           |
| ----------------------- | ------------------------------------ | ----------------------- |
| **Assigned to Me**      | Shows all issues assigned to you     | Default settings        |
| **Filter Results**      | Displays results of a saved filter   | Choose a saved filter   |
| **Activity Stream**     | Recent activity across your projects | Select project scope    |
| **Pie Chart**           | Visual breakdown by a field          | Group by: Priority      |
| **Created vs Resolved** | Trend of new vs completed issues     | Select project & period |

### Adding a Gadget

1. On your dashboard, click **Add gadget**
2. Search for the gadget name
3. Click **Add** next to the gadget
4. Configure the gadget settings (filter, project, time range)
5. Click **Save**
6. Drag gadgets to rearrange the layout

---

## Your Work View

The **Your work** section provides quick access to:

- **Worked on** — Issues you recently updated
- **Viewed** — Issues you recently opened
- **Assigned to me** — Your current assignments
- **Starred** — Items you bookmarked with a star

### Demo: Star Important Items

1. Open any issue
2. Click the **star** icon (top right of the issue)
3. Go to **Your work** → **Starred** to see it listed
4. Star a project: go to **Projects**, hover over a project, click the star

---

## Exercise

!!! question "Exercise 1: Navigation Speed Run"

    Complete the following as fast as you can using keyboard shortcuts:

    1. Open the Create Issue dialog → close it
    2. Navigate to your Dashboard
    3. Navigate to your Board
    4. Search for the word "test"
    5. Go back to your Dashboard

    Record the time it takes. Repeat until you can do it in under 15 seconds.

!!! question "Exercise 2: Build Your Dashboard"

    1. Create a new dashboard named `Training Dashboard`
    2. Add at least **4 gadgets** from the list above
    3. Arrange them in a two-column layout
    4. Share the dashboard with your team (or keep it private)
    5. Set it as your **default dashboard** (click **⋯** → **Set as default**)

!!! question "Exercise 3: Explore Your Work"

    1. Open **Your work** from the navigation bar
    2. Check each tab: Worked on, Viewed, Assigned to me, Starred
    3. Star at least 3 items (issues, projects, or filters)
    4. Verify they appear in the **Starred** tab
