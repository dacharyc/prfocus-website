---
title: "View a Repository"
date: 2023-06-04
weight: 3
description: >
  View the Repository Dashboard to see only PRs for that repository or change repo settings.
---

When you select a repository in the sidebar, this opens the Repository Dashboard. From here, you can:

- Manage incoming PRs
- View any PR in GitHub
- View the details of a specific PR in PR Focus
- Manage details about the repository, or stop watching it

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
- Whether a PR has merge conflicts
- Whether a PR is open, closed, or merged
- Whether there are any checks for the PR, and if those checks have passed or failed
- The number of commits in the PR
- The number of comments on the PR
- The number of reviews the PR has gotten

You can click into a PR summary to see the full details of the pull request.

The background color of the PR summary changes when the PR has new updates since you last viewed the details. PR Focus uses your macOS settings for Light or Dark mode. 

In Light mode, a PR summary with a bright white background has updates you haven't seen. One that is gray does not have any new updates since you last viewed it.

![Screenshot of a PR Summary with new updates in Light mode - the background is bright white](/images/pr-summary.png)

In Dark mode, a PR summary with a gray background has updates you haven't seen. One that is dark black does not have any new updaets since you last viewed it.

![Screenshot of a PR Summary with new updates in Dark mode - the background is gray instead of dark black](/images/pr-summary-dark-mode.png)

#### PR Summary Context Menu

You can right-click on a PR summary to open a context menu. This menu lets you quickly perform common actions without clicking into the pull request details.

The available options change depending on the context in which you open the menu. For example, if a PR is closed or merged, one of the options in the context menu is "Archive PR." If the pull request is open, this option is not available.

You can always select "Open in GitHub" to immediately interact with the PR on GitHub. Or you can click into the pull request details to view the details without leaving PR Focus.

![Screenshot showing the PR Summary context menu, with options to watch or ignore a PR, or open it in GitHub](/images/pr-summary-context-menu.png)

#### Conflicts

A PR's "Conflicts" icon can indicate one of three states:

- A green check: A PR has no merge conflicts. 
- A gray check: GitHub hasn't finished calculating whether a PR has merge conflicts.
- A red `X`: A PR has merge conflicts.

#### Status

A PR's "Status" can be one of four states:

- Open: Indicated by a green pull request icon: ![A green git PR open icon](/images/pull-request-status-open.png)
- Draft: Indicated by a grey pull request draft icon: ![A green git PR open icon](/images/pull-request-status-draft.png)
- Merged: Indicated by a purple merged icon: ![A purple git merged icon](/images/pull-request-status-merged.png)
- Closed without merging: Indicated by a red pull request closed icon: ![A red git PR closed without merging icon](/images/pull-request-status-closed.png) 

#### Checks

A PR's "Checks" include jobs that run on a PR before merging, such as linters, test suites, or other CI jobs. The status of these jobs is indicated as one of three states in the PR summary:

- A green check: A PR has at least one check, and it has passed all checks.
- A red `X`: A PR has at least one check, and it has failed at least one check.
- An "N/A": A PR has no checks, or the status of checks is unknown. 

When you click into a PR's details, you can see the status of individual checks.

### Inbox

When a new PR is opened in a repository you're watching, PR Focus checks for a few things:

- Are you the PR author? If so, the PR goes to **My PRs**.
- Are you an assignee? If so, the PR goes to **Assigned PRs**
- Are you a reviewer or requested reiewer? If so, the PR goes to **Reviewing PRs**

If none of those things applies, the pull request appears in the **Inbox**. From here, you can view the PR's details and decide whether to Watch or Ignore a PR. If you later become a reviewer or an assigned contributor, the PR moves to one of those columns whether or not you Watch or Ignore it.

For more information about processing incoming PRs, refer to [Incoming PRs]({{< ref "docs/pull-requests/incoming-pr.md" >}}).

#### PRs Opened and Closed Between Fetches

It is possible for a PR to be opened and never appear in PR Focus. In PR Focus v0.2.x, the app only pulls down new PRs if they are open. If a new PR is opened and closed again in between the times PR Focus fetches the pull requests from the repository - for example, while you are on vacation - PR Focus does not ever see the PR.

A future update for PR Focus will fetch PRs that are opened and then closed again between fetches.

### Watched PRs

When you choose to **Watch** an incoming PR, it moves into the **Watched PRs** list for the repository and in the **All Repositories** rollup view.

You can stop watching a PR at any time by either: 

- Clicking into the [PR Details]({{< ref "docs/pull-requests/view-pr-details.md" >}}) and pressing the **Stop Watching** button.
- Right-clicking on the PR Summary and selecting **Stop Watching** from the context menu.

If the PR is still open, it goes back to your **Inbox**. If the PR is no longer open, it disappears from all dashboards.

You can also choose to **Ignore** a pull request that you're currently watching. If you select this option, PR Focus stops watching the PR and moves it to the **Ignored PRs** dashboard.

Choosing to **Watch** or **Ignore** a PR does not move a pull request out of the **My PRs**, **Assigned PRs** or **Reviewing PRs** columns.

### My PRs

When the GitHub user who created the PR is the same as the GitHub user in the PR Focus **Global Settings**, the app considers you the PR author and automatically moves the PR into **My PRs**. PR Focus does not provide a way to manually designate a PR as "mine."

Choosing to **Watch** or **Ignore** a PR does not move the pull request out of the **My PRs** column. The only way to move a pull request you've made is waiting for it to become inactive and move to the **Inactive PRs** dashboard, or waiting for it to close and move to the **Archived PRs** dashboard. 

### Reviewing PRs

When the GitHub user in the PR Focus **Global Settings** is the same as a GitHub user in the `requestedReviewers` array in the GitHub Pull Request API, PR Focus moves the PR into the **Reviewing PRs** list. 

When you review a PR, GitHub automatically adds you to the `requestedReviewers` array. Someone else, such as the PR author, can also add you as a `requestedReviewer` by requesting a review from you.

If you do not use this workflow, you can hide the **Reviewing PRs** list from your dashboards by un-checking the **Show Reviewing PRs** checkbox in the **Global Settings** or **Repository Settings**. 

**Reviewing PRs** is enabled by default.

*Note: PR Focus does not have support for `requestedTeams` because it does not have information about teams. If your organization uses requested teams, PR Focus will not add the PR to your **Reviewing PRs** list until you actually review the PR. If this is a feature that is important to you, please [file a feature request](https://github.com/dacharyc/prfocus-website/issues/new?assignees=&labels=enhancement%2C+PR+Focus+App&projects=&template=feature_request.md&title=%5BFeature%5D+%28App+or+Website+-+pick+one%21%29%3A+) or leave a comment or an emoji reaction if this feature request already exists.*

### Assigned PRs

When the GitHub user in the PR Focus **Global Settings** is the same as a GitHub user in the `assignee` field or the `assignees` array in the GitHub Pull Request API, PR Focus moves the PR into the **Assigned PRs** list. 

If you do not use this workflow, you can hide the **Assigned PRs** list from your dashboards by un-checking the **Show Assigned PRs** checkbox in the **Global Settings** or **Repository Settings**. 

**Assigned PRs** is disabled by default.

### Sort PRs in the Repository Dashboard

You can sort pull request lists in the repository dashboard by a number of options. By default, all lists in the repository dashboards are sorted by updated date. Recently updated PRs always appear at the top of the lists.

You can change the sort order of **Watched PRs**, **Assigned PRs**, **Reviewing PRs**, or **My PRs** with one of these sort options:

- Review count: Sort in descending order by the number of reviews
- Comment count: Sort in descending order by the number of comments
- Commit count: Sort in descending order by the number of commits
- State: Group PRs together by state; Closed, Open, or Merged
- Broken: Show PRs with failing status checks and/or merge conflicts at the top of the list
- Updated date: Sort in descending order by updated date
- Closed date: Sort in descending order by closed date. Only closed PRs have a closed date.
- Merged date: Sort in descending order by merged date. Only merged PRs have a merged date.

You can individually change the sort order for each column. PR Focus does not preserve the sort order you select and always defaults to showing PRs in descending order by updated date.

![Screenshot showing the opened "Sort by" menu with the available sort options](/images/sort-pr-lists.png)

## PR Movement Between Lists and Dashboards

Pull requests may move automatically between lists and dashboards depending on things like whether you are a reviewer or assignee, or whether the PR has been inactive or closed for a period of time. You can manually change the status of PRs by watching or ignoring them, or by archiving a PR that is closed or merged.

### Manually Move PRs Between Lists and Dashboards

When you **Watch** or **Ignore** a PR in your **Inbox**, the PR moves to the **Watched PRs** list or the **Ignored PRs** dashboard.

You can manually change the status of a watched or ignored PR at any point by either:

- Clicking into the [PR Details]({{< ref "docs/pull-requests/view-pr-details.md" >}}) and pressing the appropriate button.
- Right-clicking on a PR Summary and selecting the appropriate option from the context menu.

You can also right click on the PR Summary of a closed or merged PR and select the `Archive PR` option to immediately move it to the **Archived PRs** dashboard.

### Automatic Movement Between Lists and Dashboards

PRs may also move between lists automatically in the Repository Dashboard and Inactive/Archived dashboards when:

- You become a reviewer or an assignee on a pull request. When this occurs, the PR moves into one of those respective columns.
- A PR has been inactive for longer than the **Days until inactive** setting. When this occurs, the PR moves into the [**Inactive PRs** dashboard]({{< ref "docs/pull-requests/inactive-prs.md" >}}).
- A PR has been closed or merged for longer than the **Days until archive** setting. When this occurs, the PR moves into the [**Archived PRs** dashboard]({{< ref "docs/pull-requests/archived-prs.md" >}}).

You can customize these settings on a per-repository basis, or by changing the **Global Settings** from their default values. For more information, refer to:

- [Customize Repository Settings]({{< ref "docs/repositories/manage-repository.md" >}})
- [Customize Global Settings]({{< ref "docs/settings/_index.md" >}})

## View PR Details

At any time, you can click into a PR Summary in a list or dashboard to view the PR details. When you are viewing the PR details, you can press the buttons to **Watch** or **Ignore** a PR. For more information, refer to [View PR Details]({{< ref "docs/pull-requests/view-pr-details.md" >}}).

## Fetch New and Updated PRs in the Repository

While PR Focus is open, it automatically fetches and updates PRs in the repositories. You can configure the interval at which PR Focus fetches and updates PRs in two ways:

- Customize the global default fetch interval from the [Global Settings]({{< ref "docs/settings/_index.md" >}}).
- Customize the fetch interval for a specific repository from the [Repository Settings]({{< ref "docs/repositories/manage-repository.md" >}}).

The default interval for fetching and updating PRs is every hour.

If you configure repositories to fetch different intervals, you may see some repos not included in a "fetch PRs" job run in the logs. For example, you may have a few repositories fetching updates several times per hour, but the rest on an hourly cadence. When each of these jobs run, you'll only see the repositories with that fetches interval appear in the logs for that job.

### Manually Fetch PRs

Optionally, you can manually press the **Fetch PRs** button at the upper right hand of the PR Focus window. This lets you get updates from GitHub for all of the repositories you watch any time when there isn't already a job running. 

![Screenshot showing "Fetch PRs" button in the toolbar](/images/fetch-prs-button.png)

When a job is running, an animation appears in the PR Focus toolbar and replaces the **Fetch PRs** button. The button returns when the job is complete.

![Screenshot showing the animation in the toolbar that replaces the "Fetch PRs" button](/images/fetch-job-running-animation.png)

### What Does Fetching PRs Do?

When you press the **Fetch PRs** button, this kicks off a few jobs:

- It fetches a list of open pull requests in all of the repositories you're watching
- It fetches updates from the repository for "open" PRs that PR Focus knows about:
  - If the PR has previously been added and is still open in PR Focus but closed in the remote repository, PR Focus fetches updates from the remote repository, and updates the status. 
  - If the PR is merged or closed in PR Focus and not listed as "open" on the remote repository, PR Focus does not fetch updates for it.
  - While fetching updates, PR Focus looks for any new commits, comments, reviews, or status checks, adds them to the PR details, and increments the PR summary counts.
  - If PR updates include adding you as an `assignee` or `requestedReviewer`, PR Focus moves the PR to the appropriate list in your dashboard.

### GitHub API Calls

The GitHub API rate-limits API access tokens to 5,000 calls per hour. 

PR Focus makes a call to fetch the list of open PRs in a repository, and then makes indvidiual calls to get the details or each pull request it needs to update.

If you are watching many repositories, or if the repositories you watch have many open PRs, the fetch job can be quite lengthy and can consume hundreds of API calls per run. For this reason, we recommend not fetching PR updates too often. The default fetch interval is hourly. The most frequent fetch interval that PR Focus provides for its automated jobs is "several times per hour." You can manually fetch updates at any time by pressing the **Fetch PRs** button, but if the rate limit has been exceeded, you won't see any updates to your pull requests in PR Focus.

*Note: As of v0.2.x, PR Focus does not handle exceeding the rate limit with any sort of timeout or backoff. It also does not currently surface this failure to users. A future version of PR Focus will gracefully handle exceeding the rate limit, and will provide information to users about these possible errors.*

## Manage Repository Details

While you're viewing a Repository Dashboard, you'll see a **Repo Settings** button in the toolbar.

![Screenshot showing the "Repo Settings" button](/images/repo-settings-button.png)

Press this button to customize the name or label color, or customize repository settings. For more information, refer to [Repository Settings]({{< ref "docs/repositories/manage-repository.md" >}})
