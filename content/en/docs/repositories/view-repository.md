---
title: "View a Repository"
date: 2017-01-05
weight: 3
description: >
  View the Repository Dashboard to drill down into PRs in the repository, manage repo details, or stop watching the repo.
---

When you select a repository in the sidebar, this opens the Repository Dashboard. From here, you can:

- Manage incoming PRs
- View the details of a specific PR
- Manage details about the repository, or stop watching it.

Or if you want to view a rollup of all the PRs you're watching in one view, you can select the **All Repositories** view, which aggregates the individual repository dashboards into an aggregate view.

## The Repository Dashboard

The Repository Dashboard breaks down into different lists of pull requests. By default, you see:

- Inbox: a list of [Incoming PRs]({{< ref "docs/repositories/view-repository.md" >}})
- Watched PRs: a list of PRs you've chosen to watch
- My PRs: a list of your PRs in the repository
- Reviewing PRs: a list of PRs where you're a reviewer

Optionally, if your workflow involves assigning PRs, you can check the setting in the **User Profile** to *Show Assigned PRs*. This adds a fifth list of PRs that are assigned to you.

![Screenshot showing the Repository Dashboard](/images/repository-dashboard.png)

### PR Summary

A summary view gives you information about each PR in the repository, including:

- The PR's title
- The PR number
- The repository where the PR exists
- Whether a PR is Mergeable
- The PR's status
- Whether there are any checks for the PR, and if those checks have passed or failed
- The number of commits in the PR
- The number of comments on the PR
- The number of reviews the PR has gotten

You can click into a PR row to see the full details of the pull request.

The background color of the PR summary changes when the PR has new updates since you last viewed the details. *Note: in the alpha TestFlight of PR Focus, this color change feature may behave inconsistently.*

![Screenshot showing a PR Summary](/images/pr-summary.png)

#### Mergeable

A PR's "Mergeable" status is determined by GitHub's the [`MergeableState` enum](https://docs.github.com/en/graphql/reference/enums#mergeablestate) and the [`MergeStateStatus` enum](https://docs.github.com/en/graphql/reference/enums#mergestatestatus). `MergeStateStatus` is a partially-documented enum in GitHub's GraphQL API, but undocumented in the REST API. The values returned for these fields may be unstable.

For the purposes of PR Focus, a PR gets these values for the "Mergeable" field:

- A green check if it has a `MergeableState` of `Mergeable` and a `MergeStateStatus` of `clean`. 
- A yellow check if it has a `MergeableState` of `Mergeable` but the `MergeStateStatus` is anything other than `clean`.
- A gray check if the `MergeableState` is anything other than `Mergeable`.

#### Status

A PR's "Status" can be one of three states:

- Open: Indicated by a green pull request icon: ![A green git PR open icon](/images/pull-request-status-open.png)
- Merged: Indicated by a purple merged icon: ![A purple git merged icon](/images/pull-request-status-merged.png)
- Closed without merging: Indicated by a red pull request closed icon: ![A red git PR closed without merging icon](/images/pull-request-status-closed.png) 

#### Checks

A PR's "Checks" include jobs that run on a PR before merging, such as linters, test suites, or other CI jobs. The status of these jobs is indicated as one of three states in the PR summary:

- A green check: A PR has at least one check, and it has passed all checks.
- A red `X`: A PR has at least one check, and it has failed at least one check.
- An "N/A": A PR has no checks, or the status of checks is unknown. 

When you click into a PR's details, you can see the status of individual checks.

### Inbox

When a new PR is opened in a repository you're watching, it appears in the Inbox. From here, you can view the PR's details and decide whether to Watch or Ignore a PR. If you later become a reviewer or an assigned contributor, the PR moves to one of those columns whether or not you Watch or Ignore it.

If you open a PR in the repository, it bypasses the Inbox and automatically goes to **My PRs**.

For more information about processing incoming PRs, refer to [Incoming PRs]({{< ref "docs/pull-requests/incoming-pr.md" >}}).

#### PRs Opened and Closed Between Fetches

It is possible for a PR to be opened and never appear in PR Focus. At the time of the writing of this documentation, PR Focus does not automatically fetch PRs. You must manually press the **Fetch PRs** button to pull down new PRs.

PR Focus only pulls down new PRs if they are open. If a new PR is opened and closed again in between the times you manually fetch PRs, it does not appear in PR Focus.

A future update for PR Focus will include the ability to automatically fetch PRs, with a plan to make fetch frequency a user-configurable setting. However, it may still be possible for a PR to be opened and closed again between fetch jobs, in which case it will not appear in PR Focus.

### Watched PRs

When you choose to **Watch** an incoming PR, it moves into the **Watched PRs** list for the repository and in the **All Repositories** rollup view.

You can stop watching a PR at any time by clicking into the [PR Details]({{< ref "docs/pull-requests/view-pr-details.md" >}}) and pressing the **Stop Watching** button. If the PR is still open, it goes back to your Inbox unless you **Ignore** it. If the PR is no longer open, it disappears from all dashboards.

### My PRs

When the GitHub user who created the PR is the same as the GitHub user in the PR Focus **User Profile**, the app considers you the PR author and automatically moves the PR into **My PRs**. PR Focus does not provide a way to manually designate a PR as "mine."

### Reviewing PRs

When the GitHub user in the PR Focus **User Profile** is the same as a GitHub user in the `requestedReviewers` array in the GitHub Pull Request API, PR Focus moves the PR into the **Reviewing PRs** list. 

When you review a PR, GitHub automatically adds you to the `requestedReviewers` array. Someone else, such as the PR author, can also add you as a `requestedReviewer` by requesting a review from you.

*Note: PR Focus does not have support for `requestedTeams` because it does not have information about teams. If your organization uses requested teams, PR Focus will not add the PR to your **Reviewing PRs** list until you actually review the PR.*

### Assigned PRs

When the GitHub user in the PR Focus **User Profile** is the same as a GitHub user in the `assignee` field or the `assignees` array in the GitHub Pull Request API, PR Focus moves the PR into the **Assigned PRs** list. 

If you do not use this workflow, you can hide the **Assigned PRs** list from your dashboards by un-checking the **Show Assigned PRs** checkbox in the **User Profile**.

## PR Movement Between Lists and Dashboards

When you **Watch** or **Ignore** an incoming PR, the PR moves to the **Watched PRs** list or the **Ignored PRs** dashboard.

You can manually change the status of a watched or ignored PR at any point by clicking into the [PR Details]({{< ref "docs/pull-requests/view-pr-details.md" >}}) and pressing the appropriate button.

PRs may also move between lists automatically in the Repository Dashboard and Inactive/Archived dashboards when:

- You become a reviewer or an assigned contributor. When this occurs, the PR moves into one of those respective columns.
- A PR has been inactive for longer than the **Days until inactive** setting. When this occurs, the PR moves into the **Inactive PRs** dashboard.
- A PR has been closed or merged for longer than the **Days until archive** setting. When this occurs, the PR moves into the **Archived PRs** dashboard.

## View PR Details

At any time, you can click into a PR Summary in a list or dashboard to view the PR details. When you are viewing the PR details, you can press the buttons to **Watch** or **Ignore** a PR. For more information, refer to [View PR Details]({{< ref "docs/pull-requests/view-pr-details.md" >}}).

## Fetch New and Updated PRs in the Repository

At its current state of alpha development, PR Focus does not automatically fetch and update PRs in the repositories you watch. You must manually press the **Fetch PRs** button to fetch new PRs and PR updates. A future version will have a configurable user setting to automatically fetch and update PRs at an interval you specify while the app is open.

When you press the **Fetch PRs** button, this kicks off a few jobs:

- It fetches a list of open pull requests in the repositories you're watching
- It fetches updates from the remote repository for "open" PRs that PR Focus knows about:
  - If the PR has previously been added and is still open in PR Focus but closed in the remote repository, PR Focus fetches updates from the remote repository, and updates the status. 
  - If the PR is merged or closed in PR Focus and not listed as "open" on the remote repository, PR Focus does not fetch updates for it.
  - While fetching updates, PR Focus looks for any new commits, comments, reviews, or status checks, and adds them to the PR details and increments the PR summary counts.
  - If PR updates include adding you as an `assignee` or `requestedReviewer`, PR Focus moves the PR to the appropriate list in your dashboard.
- It sets PRs that have not had updates on the remote repository for longer than the **Days until inactive** setting as inactive, and moves them to the **Inactive PRs** dashboard.
- It sets PRs that have been merged or closed for longer than the **Days until archive** setting as archived, and moves them to the **Archived PRs** dashboard.

### GitHub API Calls

The GitHub API rate-limits API access tokens to 5,000 calls per hour. PR Focus makes many API calls when you fetch PR updates.

Each time you run the fetch job, PR Focus makes the following API calls for each repository:

- A call to fetch the list of open pull requests in the repository
- If any pull requests are open in the repository, it makes these additional calls:
  - A call to fetch the most recent repository workflow runs for a given repository
  - Calls to get details for each PR, including:
    - A call to fetch all the commits for a given pull request in the repository
    - A call to fetch all the comments for a given pull request in the repository
    - A call to fetch all the reviews for a given pull request in the repository
    - A call to fetch all the pull request statuses for a given pull request in the repository

This is a minimum of one call for each repository to check for open PRs. If there are open PRs, it's a minimum of one additional call to get workflow runs, and then four more calls for each open PR in the repository to update the details that PR Focus displays.

If you are watching many repositories, or if the repositories you watch have many open PRs, the fetch job can be quite lengthy and can consume hundreds of API calls per run. For this reason, we recommend not fetching PR updates too often. 

When we add the ability to set automated fetch intervals, we will experiment with how many API calls the fetch job makes, and may limit the interval at which the fetch job can run. In future versions of PR Focus, we may experiment with optimizing the API calls. 

## Manage Repository Details

While you're viewing a Repository Dashboard, you'll see a **Manage Repo** button in the toolbar.

![Screenshot showing the "Manage Repo" button](/images/manage-repo-button.png)

Press this button to manage details about the repository, or stop watching it. For more information, refer to [Manage a Repository]({{< ref "docs/repositories/manage-repository.md" >}})
