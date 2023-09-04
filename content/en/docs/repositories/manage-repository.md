---
title: "Repository Settings"
date: 2023-06-04
weight: 4
description: >
  Update repository metadata in PR Focus, or stop watching the repository.
---

While you're viewing a Repository Dashboard, you'll see a **Repo Settings** button in the toolbar.

![Screenshot showing the "Repo Settings" button](/images/repo-settings-button.png)

Press this button to customize the name or label color, or customize repository settings. This takes you to the Repository Details view.

![Screenshot showing the "Repository Details" view with metadata and customization options](/images/repo-details-view.png)

## Repository Metadata

Above the divider, you see Repository Details. These pieces of metadata are derived from the URL you provide when you [Add a Repository]({{< ref "docs/repositories/add-repository.md" >}}).

The GitHub URL contains the owner and repository name, which PR Focus extracts to the relevant pieces of metadata. If you ever forget what a repository is, or need a quick way to get to the repository, you can click the **Repository URL** to go to the repository in a web browser.

The repository name from this URL is displayed as the Repo Name in the PR Focus sidebar, and on the repository label in the [PR Summary]({{< ref "docs/repositories/view-repository.md#pr-summary" >}}).

## Customize Repository Appearance

You can customize these repository details:

- Provide a custom, human-friendly name for the repository, which replaces the default Repo Name in the PR Focus sidebar and on the repository label in the PR Summary
- Select a repository label color to make it easier to distinguish the repository that a PR belongs to when viewing the **All Repositories** dashboard

In this example, the `docs-realm` repository name has been replaced by the custom `Realm SDK docs` name, and a specific color has been chosen for the repository label.

![Screenshot showing a PR Summary](/images/pr-summary.png)

You can customize the repository appearance independent of customizing repository settings. Pressing the **Update Apperance** button *only* changes the repository's custom name and label color; it does not affect the repository settings below the divider.

## Customize Repository Settings

In this view, you can also customize the settings for a repository. Settings you customize here override the **Global Default** settings for these options. The settings you can customize include:

- Which columns to show in the repo dashboard.
  - If you'll never be a reviewer, assignee, or contributor to the repository, you can select the "Watch-only view" setting. This removes the **My PRs**, **Reviewing PRs**, and **Assigned PRs** columns when viewing that repository. When you toggle this setting, the rest of the options disappear.
  - If you may be a reviewer, assignee, or contributor to the repository, you can check which columns apply to your role in that repository. PR Focus shows the corresponding columns in the **Repository Dashboard**, and in the **All Repositories** dashboard.
- How many days to wait before setting a PR to "inactive." When a PR becomes inactive, it moves out of the repository dashboards to the **Inactive PRs** dashboard. This helps avoid cluttering your repository dashboards with pull requests that may be blocked.
- How many days to wait after a PR has been closed before setting it to "archived." When a PR has been closed or merged for the designated number of days, it moves to the **Archived PRs** dashboard.
- How often to fetch PRs for the repository. For some repositories, you may only need to see updates daily, and more frequent updates would be a distraction. For other repositories, you may want to see updates whenever you look at PR Focus, so you may want it to update as often as several times per hour. The default fetch interval is one hour.

When you press the **Save Repo Settings** button, PR Focus saves all of the values in the "Customize Repository Settings" section of the view as custom repository settings. These settings apply only to this repository, and override the global default settings for this repo.

If you would instead like to customize the global default settings, refer to [Settings]({{< ref "docs/settings/_index.md" >}})
