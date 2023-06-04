---
title: "Settings"
linkTitle: "Settings"
weight: 5
date: 2023-06-04
description: >
  Configure PR Focus Settings
---

PR Focus has a handful of global settings you can configure from the **User Profile**.

A future version of PR Focus will move these settings into **Preferences**, and make some changes to how they work.

![Screenshot showing configurable settings in the User Profile](/images/user-profile.png)

## API Key

You can change the API Key that PR Focus uses to make API calls to GitHub.

Press the **Edit API Key** button to provide a new API access token.

The access token must have **repo** and **user** permissions.

## Profile URL

You can change the GitHub profile that PR Focus uses to determine whether you are the assignee/reviewer/person making the pull request. Provide a new GitHub profile URL in the format `https://github.com/YOUR-USERNAME-HERE` and replace `YOUR-USERNAME-HERE` with the new GitHub username you'd like to use.

PR Focus does not currently support having multiple GitHub user profiles. If this is something you need, please file a feature request.

## Dashboard Views

You can customize the lists displayed in your Repository Dashboard and All Repositories Dashboard. Check or uncheck the `Show Assigned PRs` or `Show Reviewing PRs` checkboxes to show or hide those lists in your dashboards. 

Currently, this is a global setting that defaults to showing the **Reviewing PRs** list and hiding the **Assigned PRs** list.

A future version of PR Focus will make this a customizable setting on a per-repository basis.

## Days until inactive/archive

The `Days until inactive` and `Days until archive` settings are used to determine the time interval for when PR Focus should move PRs into the [Inactive PRs]({{< ref "docs/pull-requests/inactive-prs.md" >}}) or [Archived PRs]({{< ref "docs/pull-requests/archived-prs.md" >}}) dashboards.

When you change these values, PR Focus automatically recalculates whether any PRs should be changed to or from inactive or archived, and moves them into or out of the appropriate dashboards.

Currently, these are global settings that default to 30 days until inactive and 3 days until archive.

A future version of PR Focus will make these customizable settings on a per-repository basis.
