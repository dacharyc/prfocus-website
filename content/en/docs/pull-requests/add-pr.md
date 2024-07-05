---
title: "Solo PRs"
date: 2024-07-02
weight: 4
description: >
  Watch individual pull requests for updates.
---

In addition to watching a repository for every pull request that comes through it, you can watch individual pull requests - without watching the repository. You might want to watch an individual pull request:

- When the repository is too busy to watch the entire repo
- When you're watching your own pull request in a repo you don't normally visit, and want to know when it has activity
- When someone is proposing an important patch or update in a repo you don't normally watch, and you want to know when it's merged

You can watch these "one-off" pull requests in PR Focus. The app refers to pull requests that don't come through watching a repository as a "Solo PR."

## How to Watch a Solo PR

To watch a solo PR:

1. Go to the **Pull Requests** menu in the menu bar
2. Select **Watch a PR**

   ![Screenshot showing the "Watch a PR" menu option](/images/add-a-pr.png)

3. Enter a GitHub URL for the pull request you want to watch, similar to `https://github.com/swiftlang/swift/pull/74908`.

   ![Screenshot showing the "Watch a PR" window, with a URL added and the button to watch a PR](/images/add-pr-window.png)

4. Press the **Watch PR** button

This validates the PR URL, checks the GitHub permissions to confirm you can access the relevant repository, and enqueues a job to fetch the solo PR details. Once any running jobs are complete, PR Focus gets the PR details from GitHub.

## View Updates to Solo PRs

Once PR Focus fetches the solo PR details, it appears in the "Watched" list in two dashboards:

- In the **All Pull Requests** dashboard (unless it falls under the rules to become inactive or archived)
- In the **Solo PRs** dashboard

PR Focus provides individual repository dashboards to let you focus on a subset of pull requests. If you're watching a lot of repositories, or highly active repositories, the **All Pull Requests** dashboard may make it easier to miss updates. The **Solo PRs** dashboard serves this same purpose for pull requests that don't fall into a repository dashboard.

PRs in the **Solo PRs** dashboard are sorted by updated date.

![Screenshot showing the "Solo PRs" dashboard, with a single PR Summary for an archived PR in the dashboard](/images/solo-prs.png)

Unlike the repository dashboards and the **All Pull Requests** dashboard, pull requests never move out of the **Solo PRs** dashboard when they become inactive or archived. PR Focus assumes that pull requests you felt were important enough to add manually should not "get out of the way" until you manually stop watching them.

## Stop Watching a Solo PR

You can stop watching a solo PR the same way you can stop watching PRs that come in through watched repositories:

- Right click a PR Summary to open the context menu, and select `Stop Watching`
- View the [PR Details]({{< ref "docs/pull-requests/view-pr-details.md" >}}) and press the `Stop Watching` button

However, unlike PRs that come in through watched repositories, when you stop watching a solo PR, PR Focus deletes it from the app. It does not go to your **Inbox** for you to re-process at a future time.

This is the only way to remove a pull request from the **Solo PRs** dashboard.

## Solo PR Fetch Interval

Unlike watched repositories, you cannot customize the interval to fetch solo PRs. PR Focuses uses the "several times per day" interval to automatically fetch updates to solo PRs. You can manually fetch updates to solo PRs at any time by pressing the **Fetch PRs** button.

## Watch a Repository Where You've Added a Solo PR

In some cases, you might watch a solo PR in a repository, and then later decide to watch the repository for all activity. When you [Watch a Repository]({{< ref "docs/repositories/add-repository.md" >}}), PR Focus starts treating solo PRs the same as any other pull request that comes in through watching a repository. The solo PR no longer appears in the **Solo PRs** dashboard, and instead appears in the Repository Dashboard for the repository. If you stop watching a solo PR after you have started watching its repository, it moves to the **Inbox** for you to re-process at your convenience.

## Customize Solo PR Repository Details

When you watch a solo PR, PR Focus creates a "hidden" repository that behaves differently than repositories you watch. It uses the repository name as the repo label on the PR Summary, and selects a random color for the repo label. Unlike a repository you're watching, PR Focus does not provide the option to customize the repo name or label color for a "hidden" repository.
