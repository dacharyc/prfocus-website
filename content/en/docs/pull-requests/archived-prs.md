---
title: "Archived PRs"
date: 2023-06-04
weight: 6
description: >
  When a PR is closed, it becomes archived after a time interval you set. You can still view archived PRs.
---

Some workflows call for you to be able to view PRs after they have been closed or merged. You may still want to see those PRs in your Repository Dashboard or All Repositories Dashboard for a period of time after the PR status has become closed or merged.

PR Focus is optimized for this case. PRs do not disappear from your repository views immediately when they get closed. Instead, they remain in your repository views for a number of days until they are archived. The default value for this setting is 10 days, but you can configure the number of days until a PR is archived.

## Archived PRs Dashboard

After some interval, a PR that has been closed or merged moves to the **Archived PRs** Dashboard. This dashboard is a list of PRs that have become archived.

![Screenshot showing the Archived PRs Dashboard with a list of full-width PR Summary rows](/images/archived-prs.png)

You can click into the [PR Summary]({{< ref "docs/repositories/view-repository.md#pr-summary" >}}) for an archived PR to view the [PR Details]({{< ref "docs/pull-requests/view-pr-details.md" >}}).

A PR becoming archived is one of two ways in which a PR can move out of:

- My PRs
- Assigned PRs
- Reviewing PRs

The only other way a PR can move out of these columns is when it becomes inactive, or if you are no longer an assignee or a reviewer.

**Watched PRs** also become archived, which automatically moves them from your **Watched PRs** list to the **Archived PRs** dashboard.

### Configure the Archive Interval

You can configure the *Days until archive* setting from:

- [Global Default Settings]({{< ref "docs/settings/_index.md" >}})
- [Repository Settings]({{< ref "docs/repositories/manage-repository.md" >}})

Unless you have customized either the global or the repository setting for days until inactive, the default value for this setting is 10 days.

### Immediately Archive a PR

You don't have to wait until a PR moves to archived automatically. You can immediately archive a closed or merged PR:

- Right click on a closed or merged PR summary in a repository dashboard, and you'll see the `Archive PR` option.
- Enter a PR detail view, and you'll see the **Archive PR** option alongside the **Watch** and **Ignore** buttons.
- In the aggregate Inbox, you can press the **Perform bulk operations** button to enable multi-select. Select multiple closed PRs, and you can archive them all. If you select a PR that is not closed, the **Archive** button becomes disabled.

This option is not available for open PRs.

![Screenshot showing the "Archived PR" selection in the context menu of a PR Summary rows](/images/archive-pr-immediately.png)

### Un-Archiving a PR

You can un-archive a PR from the PR Detail view. Pressing the **Un-Archive** button returns the PR to whichever column it was previously in. Note that if the PR was archived automatically, un-archiving it is only temporary until the archive job runs again. For more details, refer to Configure the Archive Interval above.

![Screenshot showing the "Un-Archive PR" button in a PR Detail view](/images/un-archive-pr.png)

## Deleting Archived PRs

PR Focus v0.5 provides the ability to delete archived PRs. When you're viewing the **Archived PRs** dashboard, you can press the **Delete PRs** button to delete all PRs that are archived. 

This button is disabled when a background job is running. If you're unable to press the **Delete PRs** button, wait for background jobs to finish and try again.

![Screenshot showing the "Delete PRs" button in the Archived PRs dashboard](/images/delete-archived-prs.png)
