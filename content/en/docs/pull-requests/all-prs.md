---
title: "All Pull Requests"
date: 2024-07-03
weight: 1
description: >
  View the roundup of all the important pull requests you're tracking.
---

PR Focus provides an **All Pull Requests** dashboard where you can see an aggregate view of all of the important pull requests across all of the repositories you're watching. This is the main dashboard in the app, and it's the view that loads when you open the app.

Not *every* PR in PR Focus appears in the **All Pull Requests** dashboard. Pull requests that you don't need to actively pay attention to move to secondary dashboards to get them out of the way. PR Focus moves these pull requests automatically:

- **Inactive PRs**: When a PR hasn't had activity for a while, PR Focus marks it as "inactive" and moves it to the **Inactive PRs** dashboard. If it gets an update, PR Focus moves it back to the active dashboards. You can configure the interval to wait to set a PR as inactive on a global basis, or on a per-repository basis. For more information, refer to [Settings]({{< ref "docs/settings" >}}) or [Repository Settings]({{< ref "docs/repositories/manage-repository.md" >}}).
- **Ignored PRs**: When you ignore a pull request, it moves to the **Ignored PRs** dashboard. You can un-ignore it at any time, or change your mind and start watching it. PRs where you are an assignee or a reviewer automatically appear in your active dashboards, even if you ignore them.
- **Archived PRs**: When a pull request is closed, it eventually moves to the **Archived PRs** dashboard. Once a PR becomes archived, you can delete it from PR Focus. You can configure the interval to wait to set a PR as archived on a global basis, or on a per-repository basis. For more information, refer to [Settings]({{< ref "docs/settings" >}}) or [Repository Settings]({{< ref "docs/repositories/manage-repository.md" >}}).

Any pull request that isn't inactive, ignored, or archived appears in the **All Pull Requests** view.

![Screenshot showing the All Pull Requests dashboard](/images/repository-dashboard.png)

## Anatomy of the PR Focus Dashboard

The **All Pull Requests** and **Repository** dashboards break down into different lists of pull requests. By default, you see:

- Inbox: a list of [Incoming PRs]({{< ref "docs/repositories/view-repository.md" >}})
- Watched PRs: a list of PRs you've chosen to watch
- My PRs: a list of your PRs
- Reviewing PRs: a list of PRs where you're a reviewer

Optionally, if your workflow involves assigning PRs, you can check the setting in the **Settings** or the **Repository Settings** to *Show Assigned PRs*. This adds a fifth list of PRs that are assigned to you.

![Screenshot showing the Repository Dashboard](/images/dashboard-with-show-assigned.png)

### PR Summary

A summary view gives you information about each PR in the dashboard, including:

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

The background color of the PR summary changes when the PR has new updates since you last viewed the details. Additionally, when there are updates since you've last viewed the details, PR Focus bolds the relevant column that has updates - **Checks**, **Commits**, **Comments**, or **Reviews**. PR Focus uses your macOS settings for Light or Dark mode.

In Light mode, a PR summary with a bright white background has updates you haven't seen. One that is gray does not have any new updates since you last viewed it.

![Screenshot of a PR Summary with new updates in Light mode - the background is bright white](/images/pr-summary.png)

In Dark mode, a PR summary with a dark black background has updates you haven't seen. One that is grey does not have any new updates since you last viewed it.

![Screenshot of a PR Summary with new updates in Dark mode - the background is dark black](/images/pr-summary-dark-mode.png)

If you're viewing a repository where you are showing all three columns - "My PRs", "Assigned PRs", and "Reviewing PRs", you see a condensed PR Summary designed to prevent the column names from overflowing.

![Screenshot of a condensed PR Summary - it has no "Conflicts" column name, and the columns are closer together to avoid overflowing titles](/images/pr-summary-condensed.png)

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

- **Open**: Indicated by a green pull request icon: ![A green git PR open icon](/images/pull-request-status-open.png)
- **Draft**: Indicated by a grey pull request draft icon: ![A green git PR open icon](/images/pull-request-status-draft.png)
- **Merged**: Indicated by a purple merged icon: ![A purple git merged icon](/images/pull-request-status-merged.png)
- **Closed without merging**: Indicated by a red pull request closed icon: ![A red git PR closed without merging icon](/images/pull-request-status-closed.png) 

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

If none of those things applies, the pull request appears in the **Inbox**. From here, you can view the PR's details and decide whether to Watch or Ignore a PR. If the PR is closed, you can Archive it. If you later become a reviewer or an assignee, the PR moves to one of those columns whether or not you Watch or Ignore it.

The aggregate Inbox gives you the option to perform bulk operations. You can select multiple PRs and Watch or Ignore them. If you select multiple closed PRs, you can Archive them.

For more information about processing incoming PRs, refer to [Incoming PRs]({{< ref "docs/pull-requests/incoming-pr.md" >}}).

### Watched PRs

When you choose to **Watch** an incoming PR, it moves into the **Watched PRs** list for the repository and in the **All Pull Requests** rollup view. If you watch an individual pull request without watching the repository, it automatically moves into your **Watched PRs** list.

Choosing to **Watch** a PR does not move the pull request out of the **My PRs**, **Assigned PRs** or **Reviewing PRs** columns.

#### Stop Watching

You can stop watching a PR at any time by either: 

- Clicking into the [PR Details]({{< ref "docs/pull-requests/view-pr-details.md" >}}) and pressing the **Stop Watching** button.
- Right-clicking on the PR Summary and selecting **Stop Watching** from the context menu.

You can also choose to **Ignore** a pull request that you're currently watching. If you select this option, PR Focus stops watching the PR and moves it to the **Ignored PRs** dashboard.

##### In a Watched Repository

If the PR is still open, it goes back to your **Inbox**. If the PR is no longer open, it disappears until it eventually becomes *archived* at the interval you've configured. Once it is archived, it appears in the **Archived PRs** dashboard.

You might stop watching a PR if you're undecided if you need to pay attention to it. You might choose this option instead of going directly to **Ignore** if you want to see upcoming changes to a PR before deciding how to react to it.

##### When it's a solo PR

If you have added a pull request that isn't part of a repository you're watching, it automatically goes into your **Watched PRs** list. PR Focus assumes that when you **Stop Watching** one of these pull requests, you no longer care about it, and PR Focus deletes it. This is the only scenario where PR Focus makes it possible to delete a pull request that isn't closed.

### My PRs

When the GitHub user who created the PR is the same as the GitHub user whose API token is used in PR Focus, the app considers you the PR author and automatically moves the PR into **My PRs**. PR Focus does not provide a way to manually designate a PR as "mine."

Choosing to **Watch** or **Ignore** a PR does not move the pull request out of the **My PRs** column. The only way to move a pull request you've made is waiting for it to become inactive and automatically move to the **Inactive PRs** dashboard, or waiting for it to close and automatically or manually move to the **Archived PRs** dashboard.

### Reviewing PRs

When the GitHub user whose API token is used in PR Focus is the same as a GitHub user in the `requestedReviewers` array in the GitHub Pull Request API, PR Focus moves the PR into the **Reviewing PRs** list. 

When you review a PR, GitHub automatically adds you to the `requestedReviewers` array. Someone else, such as the PR author, can also add you as a `requestedReviewer` by requesting a review from you.

If you do not use this workflow, you can hide the **Reviewing PRs** list from your dashboards by un-checking the **Show Reviewing PRs** checkbox in the global app **Settings** or **Repository Settings**. 

**Reviewing PRs** is enabled by default.

*Note: PR Focus does not have support for `requestedTeams` because it does not have information about teams. If your organization uses requested teams, PR Focus will not add the PR to your **Reviewing PRs** list until you actually review the PR. If this is a feature that is important to you, please [file a feature request](https://github.com/dacharyc/prfocus-website/issues/new?assignees=&labels=enhancement%2C+PR+Focus+App&projects=&template=feature_request.md&title=%5BFeature%5D+%28App+or+Website+-+pick+one%21%29%3A+) or leave a comment or an emoji reaction if this feature request already exists.*

### Assigned PRs

When the GitHub user whose API token is used in PR Focus is the same as a GitHub user in the `assignee` field or the `assignees` array in the GitHub Pull Request API, PR Focus moves the PR into the **Assigned PRs** list. 

If you do not use this workflow, you can hide the **Assigned PRs** list from your dashboards by un-checking the **Show Assigned PRs** checkbox in the global app **Settings** or **Repository Settings**. 

**Assigned PRs** is disabled by default.

*Note: PR Focus does not have support for `requestedTeams` because it does not have information about teams. If your organization uses requested teams, PR Focus will not add the PR to your **Assigned PRs** list. If this is a feature that is important to you, please [file a feature request](https://github.com/dacharyc/prfocus-website/issues/new?assignees=&labels=enhancement%2C+PR+Focus+App&projects=&template=feature_request.md&title=%5BFeature%5D+%28App+or+Website+-+pick+one%21%29%3A+) or leave a comment or an emoji reaction if this feature request already exists.*

### Sort PRs in Lists

You can sort pull request lists in the **All Pull Requests** or repository dashboards by a number of options. By default, all lists in these dashboards are sorted by updated date. Recently updated PRs always appear at the top of the lists.

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

You can also manually select the `Archive PR` option on a closed or merged PR to immediately move it to the **Archived PRs** dashboard.

### Automatic Movement Between Lists and Dashboards

PRs may also move between lists automatically in the Repository Dashboard and Inactive/Archived dashboards when:

- You become a reviewer or an assignee on a pull request. When this occurs, the PR moves into one of those respective columns.
- A PR has been inactive for longer than the **Days until inactive** setting. When this occurs, the PR moves into the [**Inactive PRs** dashboard]({{< ref "docs/pull-requests/inactive-prs.md" >}}).
- A PR has been closed or merged for longer than the **Days until archive** setting. When this occurs, the PR moves into the [**Archived PRs** dashboard]({{< ref "docs/pull-requests/archived-prs.md" >}}).

You can customize these settings on a per-repository basis, or by changing the app **Settings** from their default values. For more information, refer to:

- [Customize Repository Settings]({{< ref "docs/repositories/manage-repository.md" >}})
- [Customize App Settings]({{< ref "docs/settings/_index.md" >}})

## View PR Details

At any time, you can click into a PR Summary in a list or dashboard to view the PR details. When you are viewing the PR details, you can press the buttons to **Watch**, **Ignore**, or **Archive** a PR. For more information, refer to [View PR Details]({{< ref "docs/pull-requests/view-pr-details.md" >}}).

## Fetch New and Updated PRs in the Repository

While PR Focus is open, it automatically fetches and updates PRs in the repositories. You can configure the interval at which PR Focus fetches and updates PRs in two ways:

- Customize the global default fetch interval from the app [Settings]({{< ref "docs/settings/_index.md" >}}).
- Customize the fetch interval for a specific repository from the [Repository Settings]({{< ref "docs/repositories/manage-repository.md" >}}).

The default interval for fetching and updating PRs is every hour.

If you configure repositories to fetch different intervals, you may see some repos not included in a "fetch PRs" job run in the logs. For example, you may have a few repositories fetching updates several times per hour, but the rest on an hourly cadence. When each of these jobs run, you'll only see the repositories with that fetches interval appear in the logs for that job.

### Manually Fetch PRs

When a job is running, you cannot manually fetch PRs. An animation appears in the PR Focus toolbar and replaces the **Fetch PRs** buttons. The buttons return when the job is complete.

![Screenshot showing the animation in the toolbar that replaces the "Fetch PRs" button](/images/fetch-job-running-animation.png)

#### Fetch all PRs

You can manually press the **Fetch all PRs** button at the upper right hand of the PR Focus window. This gets updates from GitHub for all of the solo pull requests and repositories you watch. 

![Screenshot showing "Fetch PRs" button in the toolbar](/images/fetch-prs-button.png)

#### Fetch PRs for a Specific Repository

You can manually press the **Fetch specific repo** button at the upper right hand of the PR Focus window. This opens a dropdown of all of the repositories you're watching. You can select a specific repository, and PR Focus fetches *only* the updates for that repository. This is useful if you're watching a lot of repositories, and don't want to wait for all of the fetch jobs to run - you can quickly fetch only the updates for a single repository.

![Screenshot showing "Fetch specific repo" button in the toolbar, with the SDK Docs repository highlighted](/images/fetch-specific-repo.png)

### What Does Fetching PRs Do?

When you press the **Fetch PRs** button, this kicks off a few jobs:

- It fetches updates for the solo PRs you're watching
- It fetches a list of open pull requests in all of the repositories you're watching
- During a fetch job:
  - If the PR has previously been added and is still open in PR Focus but closed in the remote repository, PR Focus fetches updates from the remote repository, and updates the status. 
  - If the PR is merged or closed in PR Focus and not listed as "open" on the remote repository, PR Focus does not fetch updates for it.
  - While fetching updates, PR Focus looks for any new commits, comments, reviews, or status checks, adds them to the PR details, and increments the PR summary counts.
  - If PR updates include adding you as an `assignee` or `requestedReviewer`, PR Focus moves the PR to the appropriate list in your dashboard.
