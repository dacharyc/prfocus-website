---
title: "Settings"
linkTitle: "Settings"
weight: 5
date: 2023-06-04
description: >
  Configure PR Focus Settings
---

PR Focus has a few global settings you can configure from the **Settings** menu option in the **PR Focus** menu.

![Screenshot showing the "Settings" menu option in the **PR Focus** menu](/images/settings-menu-option.png)

Selecting this option opens a window where you can customize global default settings for PR Focus for:

- Checkboxes to show Reviewing or Assignee columns
- An option to select how often to fetch updates from GitHub
- Options to customize how long to wait before moving PRs from the Repository Dashboard to the Inactive or Archived dashboards

![Screenshot showing configurable settings in Global Settings](/images/global-settings.png)

## Customize Lists in Dashboard Views

You can customize the lists displayed in your Repository Dashboard and **All Pull Requests** Dashboard. Check or uncheck the `Show Assigned PRs` or `Show Reviewing PRs` checkboxes to show or hide those lists in your dashboards. 

This is a global setting that defaults to showing the **Reviewing PRs** list and hiding the **Assigned PRs** list.

You can override these global settings on a per-repository basis. For example, if you watch many repositories in which you are a reviewer, but only one in which you may be an assignee, you may want to leave the global **Assigned PRs** setting unchecked, and specify it only for the repository where you need this information.

For more information about customizing settings for a repository, refer to [Repository Settings]({{< ref "docs/repositories/manage-repository.md" >}}).

## Days until inactive/archive

The `Days Until Inactive` and `Days Until Archive` settings are used to determine the time interval for when PR Focus should move PRs into the [Inactive PRs]({{< ref "docs/pull-requests/inactive-prs.md" >}}) or [Archived PRs]({{< ref "docs/pull-requests/archived-prs.md" >}}) dashboards.

The global settings default to 30 days until inactive and 10 days until archive.

You can override these global settings on a per-repository basis. For example, if you watch many repositories in which you want to archive PRs right away, but one repository in which you want to leave closed or merged PRs in your dashboard view for a period of time, you can set the global *days until archive* setting to a low value, and customize the repo where you want it to have a longer value.

For more information about customizing settings for a repository, refer to [Repository Settings]({{< ref "docs/repositories/manage-repository.md" >}}).
