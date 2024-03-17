---
title: "Add Repositories"
date: 2023-06-04
weight: 2
description: >
  Add repositories to watch for new and updated PRs.
---

You can add a repository to PR Focus using the **Add Repositories** option in the **Repositories** menu.

![Screenshot showing the "Add Repositories" menu option](/images/add-repositories.png)

This opens a window where you can add one or many repositories.

## Add One Repository

By default, when you open the **Add Repositories** window, you see the option to add a single repository.

Enter a GitHub URL for the repository you want to add, similar to `https://github.com/dacharyc/prfocus-website`.

You can also select a color for the repository pill to help visually distinguish the repository in a list.

![Screenshot showing the "Add one" option in the "Add Repository" pane, with a text field to enter a URL, a picker to select a color and a save buttons](/images/add-repo-info.png)

Press the **Add Repository** button to add the repo to the list of repositories you're watching.

The repository appears in the sidebar. PR Focus enqueues a job to automatically fetch the open pull requests in the repository from GitHub. Once any running jobs are complete, PR Focus gets the open PRs for the new repository.

If you view **Manage Repositories** option in the **Repositories** menu, you'll see the repository in your list of watched repositories. From here, you can click a link to view the repository in GitHub.

![Screenshot showing the Manage Repositories window with links to view repositories on GitHub, and buttons to update settings or delete the repositories](/images/manage-repositories.png)

## Add Many Repositories

If you want to quickly onboard a team to PR Focus, you can create a list of repository URLs to add to the app. 

 When you open the **Add Repositories** window, you'll see the option to **Add many**. 

![Screenshot showing the Add Repo sheet, with `Add Many` selected and a text box to enter many repository URLs](/images/add-many-repositories.png)

When you select this option, you can enter a list of repository URLs separated by newlines. PR Focus parses this list and adds all of the repositories to the app. 

When adding many repositories, you cannot customize the color of the labels. PR Focus starts at the top of the color list and assigns a different color to each repository in the list. If you enter more repositories than colors, PR Focus starts assigning label colors again at the beginning of the list.

You can manually customize these labels later if you [configure repository settings]({{< ref "docs/repositories/manage-repository.md" >}}).

## What's Next

- [View a Repository]({{< ref "docs/repositories/view-repository.md" >}})
- [Incoming PRs]({{< ref "docs/pull-requests/incoming-pr.md" >}})
- [Customize Repository Settings]({{< ref "docs/repositories/manage-repository.md" >}})
