---
title: "Manage a Repository"
date: 2017-01-05
weight: 4
description: >
  Update repository metadata in PR Focus, or stop watching the repository.
---

While you're viewing a Repository Dashboard, you'll see a **Manage Repo** button in the toolbar.

![Screenshot showing the "Manage Repo" button](/images/manage-repo-button.png)

Press this button to manage details about the repository, or stop watching it. This takes you to the Manage Repository view.

![Screenshot showing the "Manage Repository" view with metadata and customization options](/images/manage-repo-view.png)

## Repository Metadata

Above the divider, you see Repository Details. These pieces of metadata are derived from the URL you provide when you [Add a Repository]({{< ref "docs/repositories/add-repository.md" >}}).

The GitHub URL contains the owner and repository name, which PR Focus extracts to the relevant pieces of metadata. If you ever forget what a repository is, or need a quick way to get to the repository, you can click the **Repository URL** to go to the repository in a web browser.

The repository name from this URL is displayed as the Repo Name in the PR Focus sidebar, and on the repository pill in the [PR Summary]({{< ref "docs/repositories/view-repository.md#pr-summary" >}}).

## Customize Repository Details

You can customize these repository details:

-  Provide a custom, human-friendly name for the repository, which replaces the default Repo Name in the PR Focus sidebar and on the repository pill in the PR Summary
- Select a repository pill color to make it easier to distinguish the repository that a PR belongs to when viewing the All Repositories Dashboard

In this example, the `docs-realm` repository name has been replaced by the custom `Realm SDK docs` name, and a specific color has been chosen for the repository pill.

![Screenshot showing a PR Summary](/images/pr-summary.png)

## Delete Repository

Press the **Delete repository** button to stop watching a repository. This removes the repository and all of its pull requests from all the dashboards in PR Focus.

*Note: In the current state of the alpha PR Focus TestFlight build, there is a known issue where the app crashes when you delete a repository. However, the repository should be removed when you restart the app. This will be fixed before the PR Focus TestFlight beta.*
