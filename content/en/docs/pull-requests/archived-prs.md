---
title: "Archived PRs"
date: 2023-06-04
weight: 6
description: >
  When a PR is closed, it becomes archived after a time interval you set. You can still view archived PRs.
---

Some workflows call for you to be able to view PRs after they have been closed or merged. You may still want to see those PRs in your Repository Dashboard or All Repositories Dashboard for a period of time after the PR status has become closed or merged.

PR Focus is optimized for this case. PRs do not disappear from your repository views immediately when they get closed. Instead, they remain in your repository views for a number of days until they are archived. The default value for this setting is 3 days, but you can configure the number of days until a PR is archived.

## Archived PRs Dashboard

After some interval, a PR that has been closed or merged moves to the **Archived PRs** Dashboard. This is simply a list of PRs that have become archived.

![Screenshot showing the Archived PRs Dashboard with a list of full-width PR Summary rows](/images/archived-prs.png)

You can click into the [PR Summary]({{< ref "docs/repositories/view-repository.md#pr-summary" >}}) for an archived PR to view the [PR Details]({{< ref "docs/pull-requests/view-pr-details.md" >}}).

A PR becoming archived is one of two ways in which a PR can move out of:

- My PRs
- Assigned PRs
- Reviewing PRs

The only other way a PR can move out of these columns is when it becomes inactive, or if you are no longer an assignee or a reviewer.

**Watched PRs** also become archived, which automatically moves them from your **Watched PRs** list to the **Archived PRs** dashboard.

The default time interval at which a PR becomes archived after closing or merging is 3 days. You can configure the Days until archive setting from the User Profile.

### Un-Archiving a PR

There is no way to manually move a PR out of the **Archived PRs** dashboard and back into your Repository Dashboard and All Repositories Dashboard. 

If you change the value of the `Days until archive` setting to a longer time interval, PR Focus recalculates whether PRs should be archived and moves any PRs that no longer meet this setting. In this case, PR Focus moves archived PRs back into your Repository Dashboard and All Repositories Dashboard.

## Configure Days until archive

The amount of time that a PR should remain in your Repository Dashboard and All Repositories Dashboard after being closed or merged is a global setting you can configure from your **User Profile**.

The default time interval at which a PR becomes archived is 3 days.

You can set this for any number of days.

To configure the `Days until archive` setting:

1. Select **User Profile** in the PR Focus sidebar
2. You'll see an "Inactive/Archive" section with the current values for the `Days until inactive` setting and `Days until archive` setting. Change the number of days. 

PR Focus automatically saves your changes, and recalculates whether the status of any PRs currently marked archived should change. If a PR that has been archived no longer meets the updated time interval, it moves back into your Repository Dashboard and All Repositories Dashboard.

## Deleting Archived PRs

The early alpha version of PR Focus does not provide a way to delete archived PRs. This functionality is planned for a beta version of PR Focus.
