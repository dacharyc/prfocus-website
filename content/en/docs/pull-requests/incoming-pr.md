---
title: "Incoming PRs"
date: 2023-06-04
weight: 2
description: >
  Find out about new PRs in a repository, and decide whether to watch or ignore them.
---

PR Focus automatically fetches new pull requests and updates to existing pull requests:

- When you start PR Focus
- When you watch a solo pull request or repository
- At regular intervals while the app is open

You can also manually fetch PRs at any time.

If a PR already exists in PR Focus matching the PR number, PR Focus retrieves the most up-to-date version of the PR from GitHub and updates the details in PR Focus. If an open PR does not match a PR number that PR Focus already knows about, it creates a new PR.

## Assigned, Reviewer, or My PR

If you are an assignee, a reviewer, or if the PR was made by you, the incoming PR goes directly into one of those columns, bypassing your **Inbox**. For more details about how PR Focus determines these states, refer to [View a Repository]({{< ref "docs/repositories/view-repository.md#the-repository-dashboard" >}}).

## Inbox

When the PR was made by somebody other than you, and you're not an assignee or a reviewer, the PR goes to your **Inbox**. You'll see a [PR Summary]({{< ref "docs/repositories/view-repository.md#pr-summary" >}}) giving you information about the PR, and you can click into it to view more details.

![Screenshot showing a PR Summary](/images/pr-summary.png)

The list of PR Summaries in your **Inbox** let you quickly scan a list of new PRs and decide whether they require action from you or you can safely ignore them. You can view PRs in your **Inbox** on a per-repository basis, or see a list of all incoming PRs in the **All Pull Requests** view.

## Watch, Ignore PR, or Archive PRs

You can watch, ignore, or achive a PR in one of three ways:

- If you can tell from the PR Summary what action you want to take, right-click on the PR Summary and select **Watch PR**, **Ignore PR**, or **Archive PR** from the context menu. **Archive PR** is only available if the PR is closed.
- Click into the PR Summary to view the PR Details and decide what action you want to take. Press the **Watch**, **Ignore**, or **Archive** buttons.
- Click the **Perform bulk operations** button to enable multi-selection. Select multiple PRs, and press the **Watch**, **Ignore**, or **Archive** buttons. The **Archive** button becomes disabled if you select a PR that is still open, as you can only archive closed PRs. Press the **Perform bulk operations** button again to hide the bulk operation buttons and disable multi-select in the list. You can only perform bulk operations in the aggregate Inbox.

You can also select the "Open in GitHub" option if you want to view details about the PR that are not available in PR Focus, such as looking at the PR diff.

### Watch or Ignore a PR from the PR Summary

![Screenshot showing the Watch and Ignore options in a right-click context menu from the PR Summary](/images/watch-or-ignore-pr-context-menu.png)

### Watch or Ignore a PR from the PR Detail View

![Screenshot showing the Watch and Ignore buttons at the top of a PR Detail view](/images/watch-or-ignore-buttons.png)

### Perform Bulk Operations from the Aggregate Inbox List

When you press the **Perform bulk operations** button, this enables multi-selection in the Inbox list. The PR Summary switches to a less information-dense view with a few basic details:

- PR Name
- PR Status
- PR Number
- Repository

While in this view, select PRs and press the relevant button to perform a bulk operation. Press **Perform bulk operations** again to disable multi-selection and return the list to its normal behavior.

![Screenshot showing the Watch, Ignore, and Archive buttons and multiple PRs selected when performing bulk operations](/images/perform-bulk-operations.png)

### When to Watch or Ignore PRs

You might want to watch a PR if:

- You're dependent on the work being merged
- You need to follow the status of the work for reporting reasons
- You may need to review the PR in the future
- Purely for personal interest because you're curious about the feature

You might want to ignore a PR if:

- The work is internal to the originating team and you don't need to know the outcome
- You haven't interacted with the PR and don't care about its progress

When you watch a PR, it goes into your **Watched PRs** list, both in the Repository Dashboard and in the **All Pull Requests** Dashboard.

When you ignore a PR, it goes into the [**Ignored PRs** Dashboard]({{< ref "docs/pull-requests/ignored-prs.md" >}}).

### Watch or Ignore Cannot Override Assigned, Reviewing, or My PR

When you are assigned to a PR, you are a PR reviewer, or the PR was made by you, Watch or Ignore has no effect. Watching such a PR does not move it into your **Watched PRs** list, and ignoring such a PR does not move it to the **Ignored PRs** dashboard.

This is an intentional design decision so you don't miss important work that requires your attention. If you have a use case for changing this functionality, please send me an email or file a feature request.

If you Watch or Ignore an incoming PR, and later you become a reviewer or an assignee, it moves from your **Watched PRs** list or your **Ignored PRs** dashboard to the respective column.

## Changing Watch or Ignore Status

Watch and Ignore are mutually exclusive options. If you have previously watched a PR, and then press the **Ignore** button, PR Focus stops watching the PR and moves it into the **Ignored PRs** dashboard. If you have previously ignored a PR, and then press the **Watch** button, PR Focus stops ignoring it and moves it from the **Ignored PRs** dashboard back to the **Watched PRs** list.

You can change the watch or ignore status in the same ways you can set it - from right-clicking on a PR Summary or while viewing the PR Details.

If you choose to **Stop Watching** or **Stop Ignoring** a PR, the behavior varies depending on whether it came into PR Focus through watching a repository, or whether it's a PR you added as a solo PR.

### In a Watched Repository

If the PR is still open, it goes back to your **Inbox**. If the PR is no longer open, it disappears until it eventually becomes *archived* at the interval you've configured. Once it is archived, it appears in the **Archived PRs** dashboard.

You might stop watching a PR if you're undecided if you need to pay attention to it. You might choose this option instead of going directly to **Ignore** if you want to see upcoming changes to a PR before deciding how to react to it.

### When it's a solo PR

If you have added a pull request that isn't part of a repository you're watching, it automatically goes into your **Watched PRs** list. PR Focus assumes that when you **Stop Watching** one of these pull requests, you no longer care about it, and PR Focus deletes it. This is the only scenario where PR Focus makes it possible to delete a pull request that isn't closed.
