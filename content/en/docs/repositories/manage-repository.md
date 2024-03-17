---
title: "Repository Settings"
date: 2023-06-04
weight: 4
description: >
  Update repository metadata in PR Focus, or stop watching the repository.
---

To update the settings for repositories you're watching, or to delete repositories from PR Focus, select the **Manage Repositories** option in the **Repositories** menu.

![Screenshot showing the Manage Repositories menu option](/images/manage-repositories-menu-option.png)

When you select this option, you open the **Manage Repositories** window. This window provides:

- A list of all the repositories you're watching
- Links to navigate directly to the repositories in GitHub
- Buttons to update the settings for each repository
- Buttons to delete repositories from PR Focus

![Screenshot showing the Manage Repositories window with links to view repositories on GitHub, and buttons to update settings or delete the repositories](/images/manage-repositories.png)

When you press the **Update Settings** option, you open the repository settings window for that repository.

![Screenshot showing the "Repository Details" view with metadata and customization options](/images/repo-details-view.png)

## Repository Metadata

Above the divider, you see Repository Details. These pieces of metadata are derived from the URL you provide when you [Add a Repository]({{< ref "docs/repositories/add-repository.md" >}}).

The GitHub URL contains the owner and repository name, which PR Focus extracts to the relevant pieces of metadata. If you ever forget what a repository is, or need a quick way to get to the repository, you can click the **Repository URL** to go to the repository in a web browser.

The repository name from this URL is displayed as the Repo Name in the PR Focus sidebar, and on the repository label in the [PR Summary]({{< ref "docs/repositories/view-repository.md#pr-summary" >}}).

## Customize Repository Appearance

You can customize these repository details:

- Provide a custom, human-friendly name for the repository, which replaces the default Repo Name in the PR Focus sidebar and on the repository label in the PR Summary
- Select a repository label color to make it easier to distinguish the repository that a PR belongs to when viewing the **All Repositories** dashboard

In the example below, the `realm-kotlin` repository name has been replaced by the custom `Realm Kotlin` name, and a specific color has been chosen for the repository label.

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

### GitHub Fetch Frequency

The GitHub API rate-limits API access tokens to 5,000 calls per hour. 

PR Focus makes a call to fetch the list of open PRs in a repository, and then makes indvidiual calls to get the details of each pull request it needs to update.

If you are watching many repositories, or if the repositories you watch have many open PRs, the fetch job can be quite lengthy and can consume hundreds of API calls per run. For this reason, we recommend not fetching PR updates too often. The default fetch interval is hourly. The most frequent fetch interval that PR Focus provides for its automated jobs is "several times per hour." You can manually fetch updates at any time by pressing the **Fetch PRs** button, but if the rate limit has been exceeded, you won't see any updates to your pull requests in PR Focus.

*Note: Currently, PR Focus has minimal handling for exceeding the rate limit. If you don't see updates to PRs you expect, check the PR Focus Logs to see if there are any error messages related to exceeding the rate limit. You may want to stagger the fetch interval across repositories if you encounter issues with the GitHub rate limit.*
