---
title: "Incoming PRs"
date: 2023-06-04
weight: 2
description: >
  Find out about new PRs in a repository, and decide whether to watch or ignore them.
---

When you start PR Focus, when you add a repository, or at intervals you can configure while the app is open, PR Focus retrieves a list of open pull requests for the repositories you watch. You can also manually fetch PRs at any time.

If a PR already exists in PR Focus matching the PR number, PR Focus retrieves the most up-to-date version of the PR from GitHub and updates the details in PR Focus. If an open PR does not match a PR number that PR Focus already knows about, it creates a new PR.

## Assigned, Reviewer, or My PR

If you are an assignee, a reviewer, or if the PR was made by you, the incoming PR goes directly into one of those columns, bypassing your **Inbox**. For more details about how PR Focus determines these states, refer to [The Repository Dashboard]({{< ref "docs/repositories/view-repository.md#the-repository-dashboard" >}}).

## Inbox

When the PR was made by somebody other than you, and you're not an assignee or a reviewer, the PR goes to your **Inbox**. You'll see a [PR Summary]({{< ref "docs/repositories/view-repository.md#pr-summary" >}}) giving you information about the PR, and you can click into it to view more details.

![Screenshot showing a PR Summary](/images/pr-summary.png)

The list of PR Summaries in your **Inbox** let you quickly scan a list of new PRs and decide whether they require action from you or you can safely ignore them. You can view PRs in your **Inbox** on a per-repository basis, or see a list of all incoming PRs in the **All Repositories** view.

## Watch or Ignore PRs

You can watch or ignore a PR in one of two ways:

- If you can tell from the PR Summary whether you want to watch or ignore the PR, right-click on the PR Summary and select **Watch PR** or **Ignore PR** from the context menu.
- Click into the PR Summary to view the PR Details and decide whether you want to watch or ignore the PR. Press the **Watch** or **Ignore** button.

### Watch or Ignore a PR from the PR Summary

![Screenshot showing the Watch and Ignore options in a right-click context menu from the PR Summary](/images/watch-or-ignore-pr-context-menu.png)

### Watch or Ignore a PR from the PR Detail View

![Screenshot showing the Watch and Ignore buttons at the top of a PR Detail view](/images/watch-or-ignore-buttons.png)

### When to Watch or Ignore PRs

You might want to watch a PR if:

- You're dependent on the work being merged
- You need to follow the status of the work for reporting reasons
- You may need to review the PR in the future
- Purely for personal interest because you're curious about the feature

You might want to ignore a PR if:

- The work is internal to the originating team and you don't need to know the outcome
- You haven't interacted with the PR and don't care about its progress

When you watch a PR, it goes into your **Watched PRs** list, both in the Repository Dashboard and in the All Repositories Dashboard.

When you ignore a PR, it goes into the [**Ignored PRs** Dashboard]({{< ref "docs/pull-requests/ignored-prs.md" >}}).

### Watch or Ignore Cannot Override Assigned, Reviewing, or My PR

When you are assigned to a PR, you are a PR reviewer, or the PR was made by you, Watch or Ignore has no effect. Watching such a PR does not move it into your **Watched PRs** list, and ignoring such a PR does not move it to the **Ignored PRs dashboard**.

This is an intentional design decision so you don't miss important work that requires your attention. If you have a use case for changing this functionality, please send me an email or file a feature request.

If you Watch or Ignore an incoming PR, and later you become a reviewer or an assignee, it moves from your **Watched PRs** list or your **Ignored PRs** dashboard to the respective column.

## Changing Watch or Ignore Status

Watch and Ignore are mutually exclusive options. If you have previously watched a PR, and then press the **Ignore** button, PR Focus stops watching the PR and moves it into the **Ignored PRs** dashboard. If you have previously ignored a PR, and then press the **Watch** button, PR Focus stops ignoring it and moves it from the **Ignored PRs** dashboard back to the **Watched PRs** list.

If you choose to **Stop Watching** or **Stop Ignoring** a PR, and the PR is open, it goes back to your **Inbox**, or to your **Inactive PRs** dashboard. If the PR is closed, it goes back to your **Inbox** or **Archived PRs** dashboard.

You can change the watch or ignore status in the same ways you can set it - from right-clicking on a PR Summary or while viewing the PR Details.
