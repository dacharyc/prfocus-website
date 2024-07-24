---
title: "Settings"
linkTitle: "Settings"
weight: 5
date: 2023-06-04
description: >
  Configure PR Focus Settings
---

You can configure app-wide settings from the **Settings** menu option in the **PR Focus** menu.

![Screenshot showing the "Settings" menu option in the **PR Focus** menu](/images/settings-menu-option.png)

Selecting this option opens a window where you can customize global default settings for PR Focus for:

- A navigation override for improved accessibility.
- How long to wait before moving PRs from your main dashboards to the Inactive or Archived dashboards.
- Options to specify GitHub fetch behavior.
- Checkboxes for whether to show the Reviewing or Assignee columns.

## Right-click to Navigate to PR Details

PR Focus provides an accessibility setting to override the default navigate to PR details behavior. By default, when you click a PR summary card, you go into a new view that shows you the details for that PR. For people who prefer an alternate behavior, there is a setting to use the right click menu to navigate to PR details.

![Screenshot showing the accessibility settings tab with a checkbox to override the default navigation behavior](/images/accessibility-settings.png)

When you select this setting, clicking a PR summary card no longer opens the PR details. Instead, you must right-click to open the context menu, and select the **View PR Details** menu open to open the detail view. This option only displays in the context menu when you have this setting enabled.

![Screenshot of the right-click context menu with the "View PR Details" option highlighted](/images/view-pr-details-navigation-menu.png)

## Days Until Inactive/Archive

You can customize how long PR Focus should wait for a PR to be inactive or closed before moving it into the [Inactive PRs]({{< ref "docs/pull-requests/inactive-prs.md" >}}) or [Archived PRs]({{< ref "docs/pull-requests/archived-prs.md" >}}) dashboards.

The settings default to 30 days until inactive and 10 days until archive.

To customize these settings, select the **Archive and Inactive** option in the **Settings** menu.

![Screenshot showing the Archive and Inactive Settings option with the values set to the Inactive: 30 day and Archive: 10 day defaults](/images/archive-and-inactive-settings.png)

You can override these global settings on a per-repository basis. For example, if you watch many repositories in which you want to archive PRs right away, but one repository in which you want to leave closed or merged PRs in your dashboard view for a period of time, you can set the global *days until archive* setting to a low value, and customize the repo where you want it to have a longer value.

For more information about customizing settings for a repository, refer to [Repository Settings]({{< ref "docs/repositories/manage-repository.md" >}}).

### Archive Strategies

If you're a downstream team and your work *starts* when a PR is closed, you might want closed PRs to remain in your dashboard longer.  If you're an engineer responsible for the work and you want PRs to disappear right away when they're closed, you can shorten this setting.

The **All Pull Requests** and **Repository** dashboards provide the option to customize sort order in your lists. If you're a downstream team whose work *starts* when a PR is closed, you can sort your PR lists by closed date or merged date to find the PRs that are relevant to your work.

For more details about sort options, refer to [Sort PRs in Lists]({{< ref "docs/pull-requests/all-prs/#sort-prs-in-lists" >}})

### Inactive Strategies

PR Focus considers PRs that don't get updates for a period of time to be "inactive." It moves these pull requests to a special dashboard. This gets them out of your main views where they might become "clutter", and gives you a place where you can easily view pull requests that haven't been updated in a while to find things that might need your attention.

You might want to set a lower default for when a PR becomes "inactive" if you are someone who is responsible for keeping PRs moving, such as a team lead, a project manager, or someone who works at an agency or consultency. This highlights pull requests that might need help to get moving again.

If you are someone who works in a repository where pull requests commonly go weeks between updates, you might want a higher value for this setting. The work may still be valid and "active" for longer in a slower-moving repository.

For more details about inactive pull requests, refer to [Inactive PRs]({{< ref "docs/pull-requests/inactive-prs/" >}}).

## Specify the GitHub Fetch Behavior

When PR Focus is running, it uses scheduled jobs to periodically fetch updates from GitHub in the background. You can customize how often to fetch updates app-wide, or on a per repository basis.

![Screenshot showing the GitHub Fetching Settings option with the default "Hourly" interval displayed in the picker](/images/github-fetch-settings.png)

If you use the app frequently and want to find out right away when a pull request is updated, you can choose the "several times per hour" option. If you're only checking PR Focus a few times per day while you're context switching or between tasks, you might choose a less frequent fetch interval.

You can manually fetch all PRs, or fetch the PRs for a specific repository, at any time using the **Fetch PRs** buttons in the toolbar.

For more details about GitHub fetching, API rate limits, and repository-specific setting strategies, refer to [GitHub Fetch Frequency]({{< ref "docs/repositories/manage-repository/#github-fetch-frequency" >}}).

### Temporarily Disable Fetching (Coming Soon!)

In some cases, you may want to temporarily disable GitHub fetching. You might not want PR Focus to try fetching if you're traveling and may be offline, for example, or if you want to minimize app activity to prolong battery life when you're not connected to power.

PR Focus will soon have an option to temporarily disable fetching. You will still be able to manually fetch PRs using the **Fetch PRs** buttons in the toolbar, but the automated fetch jobs won't run in the background.

## Customize Lists in Dashboard Views

You can customize whether to show the "Reviewing PRs" and "Assignee PRs" columns in your **All Pull Requests** dashboard and your **Repository** dashboards.

![Screenshot showing the Show Columns Settings option with the "Show Reviewing PRs" checkbox checked and the "Show Assigned PRs" option unchecked](/images/show-columns-settings.png)

Check or uncheck the `Show Assigned PRs` or `Show Reviewing PRs` checkboxes to show or hide those lists in your dashboards. 

This is a global setting that defaults to showing the **Reviewing PRs** list and hiding the **Assigned PRs** list.

If you choose the options to not display these columns, but you become an assignee or reviewer on a PR, these columns display in the dashboards anyway. This ensures you don't miss important PRs where you may be an assignee or reviewer.

You can override these global settings on a per-repository basis. For example, if you watch many repositories in which you are a reviewer, but only one in which you may be an assignee, you may want to leave the global **Assigned PRs** setting unchecked, and specify it only for the repository where you need this information.

Note that if you specify to show Reviewing PRs or Assigned PRs on a repository basis, but leave the global setting unchecked, the column will display in your **All Pull Requests** dashboard because it is an aggregate of every dashboard's settings.

For more information about customizing settings for a repository, refer to [Repository Settings]({{< ref "docs/repositories/manage-repository.md" >}}).
