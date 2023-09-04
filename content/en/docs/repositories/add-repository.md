---
title: "Add a Repository"
date: 2023-06-04
weight: 2
description: >
  Add repositories to watch for new and updated PRs.
---

You can add a repository to PR Focus using the **Add or Remove Repos** button in the sidebar.

![Screenshot showing the "Add or Remove Repos" button](/images/add-remove-repos-button.png)

This opens the pane where you can manage the list of repositories you're watching.

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

## What's Next

- [View a Repository]({{< ref "docs/repositories/view-repository.md" >}})
- [Incoming PRs]({{< ref "docs/pull-requests/incoming-pr.md" >}})
- [Customize Repository Settings]({{< ref "docs/repositories/manage-repository.md" >}})
