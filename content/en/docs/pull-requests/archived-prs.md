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

You can configure the *Days until archive* setting from:

- [Global Default Settings]({{< ref "docs/settings/_index.md" >}})
- [Repository Settings]({{< ref "docs/repositories/manage-repository.md" >}})

Unless you have customized either the global or the repository setting for days until inactive, the default value for this setting is 10 days.

### Un-Archiving a PR

There is no way to manually move a PR out of the **Archived PRs** dashboard and back into your Repository Dashboard and All Repositories Dashboard. 

## Deleting Archived PRs

The early beta version of PR Focus does not provide a way to delete archived PRs. This functionality is planned for a later beta version of PR Focus.
