---
title: "View PR Details"
date: 2023-06-04
weight: 3
description: >
  View all the important details about any PR you're watching, in one place.
---

When you're viewing a Repository Dashboard or the **All Repositories** Dashboard, you can click into a [PR Summary]({{< ref "docs/repositories/view-repository.md#pr-summary" >}}) to get a detailed view of the pull request.

![Screenshot showing a PR Summary](/images/pr-summary.png)

The PR Details view contains:

- The PR title, number, description, and date last updated
- A link to view the PR on the GitHub website
- A pill telling you which repository a PR belongs to, which is useful if you've clicked into it from the All Repositories view
- Buttons to Watch or Ignore the PR
- A list of commits in the PR, with links to view each commit on GitHub
- A list of status checks for the PR, with links to view each status check on GitHub
- A list of reviews on the PR, with links to view each review on GitHub
- A list of comments on the PR, with links to view each comment on GitHub

![Screenshot showing the PR Details view](/images/pr-detail-view.png)

## Commits

Each commit in the list of commits contains:

- The GitHub user who made the commit
- The date and time of the commit
- A link to view the commit on GitHub
- The commit message

The list of commits displays in chronological reverse order, with the most recent commit at the top of the list.

## Status Checks

Status Checks in PR Focus refer to a list of jobs or statuses associated with a PR. These may be GitHub workflow runs, CI jobs, or other required checks that repository rules enforce on a PR.

Each status check in the list of status checks contains:

- Information about whether the status check passed or failed
  - A green checkmark for passing checks
  - A red `X` mark for failing checks 
- The name of the status check
- An icon, if one is associated with the status check
- A link to view it on GitHub

PR Focus displays the most recent status for each check at the time of the last [fetch job]({{< ref "docs/repositories/view-repository.md#fetch-new-and-updated-prs-in-the-repository" >}}). This information may not match the current state of status checks if a more recent run has occurred since the last fetch job.

### Missing Status Checks

Status checks or workflow runs involve making a separate API call to GitHub and are not directly accessible on a PR. This API provides a paginated list of all status checks in the repository, which can be multiple calls for each page of results per fetch job if there are many status checks in the repository. To minimize API calls, PR Focus only fetches the most recent pages of status checks. In highly active repositories, or if a pull request has been open for a longer period of time, the relevant status checks for a PR may "fall off" the list of fetched status checks. In this case, PR Focus may show no status checks are available even if they're present on the PR in GitHub.

This is a known limitation of the GitHub API, and PR Focus has no plans to address this limitation at this time.

If status checks appear to be missing from a PR, but the PR is relatively new and the status checks are "recent" in the repository, please file an issue as that may be a bug.

## Reviews

Each review in the list of reviews contains:

- The review status, which is one of:
  - Approved: The reviewer has approved the PR. Indicated by a green review approved icon ![A green review approved icon](/images/review-approved.png)
  - Changes Requested: The reviewer has requested changes on the PR. Indicated by a red request changes icon ![A red request changes icon](/images/review-request-changes.png)
  - Commented: The reviewer has commented without approving or requesting changes. Indicated by a yellow commented icon ![A yellow commented icon](/images/review-commented.png)
- The GitHub user who left the review
- The date and time of the review
- A link to view the review on GitHub
- A review message, if one was left with the review.

The list of reviews displays in chronological reverse order, with the most recent review at the top of the list.

## Comments

Each comment in the list of comments contains:

- The GitHub user who left the comment
- The date and time of the comment
- A link to view the comment on GitHub
- The comment text

The list of comments displays in chronological reverse order, with the most recent comment at the top of the list.
