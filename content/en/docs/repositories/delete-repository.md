---
title: "Delete a Repository"
date: 2023-09-04
weight: 5
description: >
  Delete a repository and all of its PRs from PR Focus.
---

You can delete repositories that you're watching from PR Focus. When you delete a repository, PR Focus:

- Deletes all pull requests and their associated data from PR Focus
- Removes the repository from your "Watched Repositories" list
- Stops fetching new and updated pull requests from GitHub

You might want to delete a repository if you stop working on a project, or if the repository is too active and you find you are exceeding the GitHub rate limit. 

If you delete a repository because it's too active, you can still watch individual pull requests in the repository. For more information, refer to [Watch a Pull Request]({{< ref "docs/pull-requests/add-pr.md" >}}). Or you could fetch updates from the repository less often. For more information about how to set the fetch interval for a repository, refer to [Repository Settings]({{< ref "docs/repositories/manage-repository.md#github-fetch-frequency" >}}).

You can delete closed pull requests without deleting a repository. If you only want to delete closed pull requests in a repository, refer to [Archived PRs]({{< ref "docs/pull-requests/archived-prs.md#deleting-archived-prs" >}})

## How to Delete a Repository

1. Go to the **Repositories** menu.
2. Select the **Manage Repositories** option.

   ![Screenshot showing the Manage Repositories menu option](/images/manage-repositories-menu-option.png)


3. Find the row for the repository you want to delete, and press the **Delete repo** button. This deletes the repository and all of its pull requests from PR Focus.

   ![Screenshot showing the Manage Repositories window with an arrow pointing to the circled "Delete Repo" button for the 'dacharyc/GitHubGraphQLAPITester' repo.](/images/delete-repo-button.png)
