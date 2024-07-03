---
title: "Watch Repositories"
date: 2023-06-04
weight: 2
description: >
  Watch repositories for new and updated PRs.
---

When you watch a repository, PR Focus checks GitHub for all of the open pull requests that are currently in that repository. While the app is open, PR Focus automatically checks the repository for:

- Updates to existing PRs
- New PRs opened in the repository

New PRs go into your **Inbox**. From there, you can decide whether to **Watch** or **Ignore** the PR. For more information, refer to [Incoming PRs]({{< ref "docs/pull-requests/incoming-pr.md" >}}).

If you are an assignee, a reviewer, or if the PR was made by you, the incoming PR goes directly into the relevant list of PRs, bypassing your **Inbox**. For more details about how PR Focus determines these states, refer to [View a Repository]({{< ref "docs/repositories/view-repository.md#the-repository-dashboard" >}}).

When a pull request gets updates, the pull request moves to the top of its respective list. The background color of the PR Summary changes to indicate there are updates. If the updates are to status checks, commits, comments, or reviews, the relevant column in the PR Summary is bolded. Clicking into the PR details tells you what information is new. For more information about PR Summaries, refer to [PR Summary]({{< ref "docs/repositories/view-repository.md#pr-summary" >}}). For more information about the information available when viewing PR details, refer to [View PR Details]({{< ref "docs/pull-requests/view-pr-details.md" >}}).

If you don't need to know about *every* new pull request in a repository, you can watch individual pull requests instead of watching the repo. For details, refer to [Watch an Individual PR]({{< ref "docs/pull-requests/add-pr.md" >}}).

## How to Watch a Repository

To watch repositories in PR Focus:

1. Go to the **Repositories** menu in the menu bar
2. Select **Watch Repositories**

![Screenshot showing the "Watch Repositories" menu option](/images/add-repositories.png)

### Add One Repository

By default, when you open the **Watch Repositories** window, you see the option to add a single repository.

Enter a GitHub URL for the repository you want to add, similar to `https://github.com/dacharyc/prfocus-website`.

You can also select a color for the repository pill to help visually distinguish the repository in a list.

![Screenshot showing the "Add one" option in the "Watch Repository" pane, with a text field to enter a URL, a picker to select a color and a save buttons](/images/add-repo-info.png)

Press the **Add Repository** button to add the repo to the list of repositories you're watching.

The repository appears in the sidebar. PR Focus enqueues a job to automatically fetch the open pull requests in the repository from GitHub. Once any running jobs are complete, PR Focus gets the open PRs for the new repository.

If you go to the **Manage Repositories** option in the **Repositories** menu, you'll see the repository in your list of watched repositories. From here, you can click a link to view the repository in GitHub.

![Screenshot showing the Manage Repositories window with links to view repositories on GitHub, and buttons to update settings or delete the repositories](/images/manage-repositories-trimmed.png)

### Add Many Repositories

If you want to quickly onboard a team to PR Focus, you can create a list of repository URLs to add to the app. 

When you open the **Watch Repositories** window, you'll see the option to **Add many**. 

![Screenshot showing the Watch Repository pane, with `Add Many` selected and a text box to enter many repository URLs](/images/add-many-repositories.png)

When you select this option, you can enter a list of repository URLs separated by newlines. PR Focus parses this list and adds all of the repositories to the app. 

When adding many repositories, you cannot customize the color of the labels. PR Focus assigns a color at random to each repository in the list.

You can manually customize these labels later if you [customize repository settings]({{< ref "docs/repositories/manage-repository.md" >}}).

## What's Next

- [View a Repository]({{< ref "docs/repositories/view-repository.md" >}})
- [Incoming PRs]({{< ref "docs/pull-requests/incoming-pr.md" >}})
- [Customize Repository Settings]({{< ref "docs/repositories/manage-repository.md" >}})
