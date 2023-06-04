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

In these cases, you may still care about the eventual outcome of the PR, but it becomes clutter sitting around in your regular repositories while no activity is occurring. So you may not want to **Stop Watching** or **Ignore** a PR, but may want to get it out of your way.

This is the case that **Inactive PRs** solves.

## Inactive PRs Dashboard

After some interval, a PR that hasn't had updates moves to the **Inactive PRs** Dashboard. This is simply a list of PRs that have become inactive.

![Screenshot showing the Inactive PRs Dashboard with a list of full-width PR Summary rows](/images/inactive-prs.png)

You can click into the [PR Summary]({{< ref "docs/repositories/view-repository.md#pr-summary" >}}) for an inactive PR to view the [PR Details]({{< ref "docs/pull-requests/view-pr-details.md" >}}).

A PR becoming inactive is one of two ways in which a PR can move out of:

- My PRs
- Assigned PRs
- Reviewing PRs

The only other way a PR can move out of these columns is when it becomes archived, or if you are no longer an assignee or a reviewer.

The default time interval at which a PR becomes inactive is 30 days. You can configure the Days until inactive setting from the User Profile.

### Moving a PR Out of Inactive PRs

There is no way to manually move a PR out of the **Inactive PRs** dashboard and back into your Repository Dashboard and All Repositories Dashboard. 

When a PR receives updates again, it moves out of the **Inactive PRs** dashboard and back into your Repository Dashboard and All Repositories Dashboard.

If you change the value of the `Days until inactive` setting to a longer time interval, PR Focus recalculates whether PRs should be inactive and moves any PRs that no longer meet this setting. In this case, PR Focus moves inactive PRs back into your Repository Dashboard and All Repositories Dashboard.

## Configure Days until inactive

The amount of time that a PR should remain in your Repository Dashboard and All Repositories Dashboard is a global setting you can configure from your **User Profile**.

The default time interval at which a PR becomes inactive is 30 days.

You can set this for any number of days.

To configure the `Days until inactive` setting:

1. Select **User Profile** in the PR Focus sidebar
2. You'll see an "Inactive/Archive" section with the current values for the `Days until inactive` setting and `Days until archive` setting. Change the number of days. 

PR Focus automatically saves your changes, and recalculates whether the status of any PRs currently marked inactive should change.
