---
title: "Inactive PRs"
date: 2023-06-04
weight: 5
description: >
  Stale PRs become inactive after a time interval you set. They move back into your dashboard when updates occur.
---

Sometimes, a PR sits for a long time without progress. This may be because:

- A PR is blocked while waiting for external dependencies
- A PR is waiting for other contributors
- For business reasons, work on the PR is paused
- Many other reasons

In these cases, you may still care about the eventual outcome of the PR, but it becomes clutter sitting around in your regular PR Focus dashboards while no activity is occurring. You may not want to **Stop Watching** or **Ignore** a PR, but may want to get it out of your way.

This is the case that **Inactive PRs** solves.

## Inactive PRs Dashboard

After some interval, a PR that hasn't had updates moves to the **Inactive PRs** Dashboard. This dashboard is a list of PRs that have become inactive, sorted by the repository where they originated.

![Screenshot showing the Inactive PRs Dashboard with a list of full-width PR Summary rows](/images/inactive-prs.png)

You can click into the [PR Summary]({{< ref "docs/repositories/view-repository.md#pr-summary" >}}) for an inactive PR to view the [PR Details]({{< ref "docs/pull-requests/view-pr-details.md" >}}).

A PR becoming inactive is one of two ways in which a PR can move out of:

- My PRs
- Assigned PRs
- Reviewing PRs

The only other way a PR can move out of these columns is when it becomes archived, or if you are no longer an assignee or a reviewer.

You can configure the *Days until inactive* setting from:

- [App Settings]({{< ref "docs/settings/_index.md" >}})
- [Repository Settings]({{< ref "docs/repositories/manage-repository.md" >}})

The default value for this setting is 30 days.

### Moving a PR Out of Inactive PRs

There is no way to manually move a PR out of the **Inactive PRs** dashboard and back into your Repository Dashboard and **All Pull Requests** Dashboard. 

When a PR receives updates again, it moves out of the **Inactive PRs** dashboard and back into your Repository Dashboard and **All Pull Requests** Dashboard.

If you change the value of the `Days until inactive` setting to a longer time interval, PR Focus recalculates whether PRs should be inactive and moves any PRs that no longer meet this setting. In this case, PR Focus moves inactive PRs back into your Repository Dashboard and **All Pull Requests** Dashboard.
