---
title: "Add Repositories"
date: 2023-06-04
weight: 2
description: >
  Add repositories to watch for new and updated PRs.
---

You can add a repository to PR Focus using the **Add or Remove Repos** button in the sidebar.

![Screenshot showing the "Add or Remove Repos" button](/images/add-remove-repos-button.png)

This opens the pane where you can manage the list of repositories you're watching.

## Add One Repository

Press the **Add Repo** button to add a new repository to PR Focus.

This opens a pane asking for details about the repository you want to add. 

Enter a GitHub URL for the repository you want to add, similar to `https://github.com/dacharyc/prfocus-website`.

You can also select a color for the repository pill to help visually distinguish the repository in a list.

![Screenshot showing the "Add Repository" pane, with a text field to enter a URL, a picker to select a color and a buttons to save or cancel](/images/add-repo-info.png)

Press the **Add Repository** button to add the repo to the list of repositories you're watching.

The repository appears in the sidebar. PR Focus automatically fetches the open pull requests in the repository from GitHub.

If you view **Global Settings**, you'll see the repository in your list of **Watched Repositories**. From here, you can click a link to view the repository in GitHub.

![Screenshot showing the User Profile for 'dacharyc' with a 'prfocus-website' repo in a list of Watched Repos](/images/see-repo-in-watched-repos.png)

If you view **Add or Remove Repos** again, you'll see the new repository in your list.

![Screenshot showing the Add or Remove Repositories pane with a 'prfocus-website' repo, and a button to delete the repo.](/images/add-remove-repos-with-one-repo.png)

## Add Many Repositories

If you want to quickly onboard a team to PR Focus, you can create a list of repository URLs to add to the app. 

After you press the **Add Repo** button, you'll see the option to **Add many**. 

![Screenshot showing the Add Repo sheet, with `Add Many` selected and a text box to enter many repository URLs](/images/add-many-repositories.png)

When you select this option, you can enter a list of repository URLs separated by newlines. PR Focus parses this list and adds all of the repositories to the app. 

When adding many repositories, you cannot customize the color of the labels. PR Focus starts at the top of the color list and assigns a different color to each repository in the list. If you enter more repositories than colors, PR Focus starts assigning label colors again at the beginning of the list.

You can manually customize these labels later if you [configure repository settings]({{< ref "docs/repositories/manage-repository.md" >}}).

## What's Next

- [View a Repository]({{< ref "docs/repositories/view-repository.md" >}})
- [Incoming PRs]({{< ref "docs/pull-requests/incoming-pr.md" >}})
- [Customize Repository Settings]({{< ref "docs/repositories/manage-repository.md" >}})
