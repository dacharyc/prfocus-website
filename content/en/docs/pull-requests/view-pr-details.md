---
title: "View PR Details"
date: 2023-06-04
weight: 3
description: >
  View all the important details about any PR you're watching, in one place.
---

When you're viewing a Repository Dashboard or the **All Repositories** Dashboard, you can click into a [PR Summary]({{< ref "docs/repositories/view-repository.md#pr-summary" >}}) to get a detailed view of the pull request.

![Screenshot showing a PR Summary](/images/viewed-pr-summary.png)

The PR Details view contains:

- The PR title, number, description, and date last updated
- A link to view the PR on the GitHub website
- A label telling you which repository a PR belongs to, which is useful if you've clicked into it from the All Repositories view
- Buttons to Watch or Ignore the PR
- A list of commits in the PR, with links to view each commit on GitHub
- A list of status checks for the PR, with links to view each status check on GitHub
- A list of reviews on the PR, with links to view each review on GitHub
- A list of comments on the PR, with links to view each comment on GitHub
- A "New" label for any item that has been added to PR Focus since you last viewed the PR details

![Screenshot showing the PR Details view](/images/pr-detail-view.png)

## Commits

Each commit in the list of commits contains:

- The GitHub user who made the commit (if the commit contains this information)
- The date and time of the commit
- A link to view the commit on GitHub
- The commit message
- A "New" label if you have not viewed PR details since this commit was added to PR Focus

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
- A "New" label if you have not viewed PR details since this status check was added to PR Focus

PR Focus displays the status checks for the branch head commit sha at the time of the last [fetch job]({{< ref "docs/repositories/view-repository.md#fetch-new-and-updated-prs-in-the-repository" >}}). This information may not match the current state of status checks if:

- A more recent status check or workflow run has occurred since PR Focus last fetched the status checks
- The status check or workflow run was still running in GitHub when PR Focus checked for updates, and PR Focus does not have the status of the completed job

### Missing Status Checks

Status checks or workflow runs come from GitHub in many different structures. PR Focus is still fine-tuning the best way to get the relevant status checks for the branch head. If you are missing status checks that you expect to see, please let me know these details (if the repo is public and you are able to share):

- The repo owner and name
- The PR number
- What checks you see in PR Focus
- The checks you *expect* to see that are missing from PR Focus

Feel free to file an issue, send me an email, or contact me directly with these details. Thank you!

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
- A "New" label if you have not viewed PR details since this review was added to PR Focus

The list of reviews displays in chronological reverse order, with the most recent review at the top of the list.

## Comments

Each comment in the list of comments contains:

- The GitHub user who left the comment
- The date and time of the comment
- A link to view the comment on GitHub
- The comment text
- A "New" label if you have not viewed PR details since this comment was added to PR Focus

The list of comments displays in chronological reverse order, with the most recent comment at the top of the list.

*Note: In PR Focus v0.2.0, I added a module to parse GitHub-flavored Markdown to nicely formatted text in the PR Detail view. I have seen some impact to performance when scrolling comment lists since adding this module. If you have performance issues when scrolling, the UI should un-freeze again after a short delay. Please let me know if you run into this issue so I can troubleshoot and potentially re-evaluate using this module.*
