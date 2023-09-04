---
title: "Ignored PRs"
date: 2023-06-04
weight: 4
description: >
  Ignoring a PR gets it out of your way. You can get it back at any time.
---

When you [view PR Details]({{< ref "docs/pull-requests/view-pr-details.md" >}}), you see a button that lets you ignore the PR.

![Screenshot showing the Watch and Ignore buttons at the top of a PR Detail view](/images/watch-or-ignore-buttons.png)

When you press the **Ignore** button, the pull request goes into the **Ignored PRs** Dashboard.

This dashboard is a list of PRs that you've ignored.

![Screenshot showing the Ignored PRs Dashboard with a list of full-width PR Summary rows](/images/ignored-prs.png)

You can access the **Ignored PRs** Dashboard by pressing the **Ignored PRs** button in the PR Focus sidebar.

## Stop Ignoring a PR

At any time, you can stop ignoring a PR.

To stop ignoring a PR:

1. Go into your **Ignored PRs** Dashboard.
2. Find the PR you want to stop ignoring.
3. Click into the PR Summary to open the PR Details view.
4. Press the **Stop Ignoring** button.

This moves the PR out of your **Ignored PRs** Dashboard and into the **Inbox**.

If you want an ignored PR to move directly to your **Watched PRs** list, press the **Watch** button instead of the **Stop Ignoring** button. This automatically stops ignoring the PR and moves it directly to your **Watched PRs** list.

## PR Not Moving to Ignored PRs

If you try to ignore a PR where you are an assignee, a reviewer, or where the PR is yours, it does not move into the **Ignored PRs** Dashboard. It stays in the relevant column in the Repository Dashboard and All Repositories Dashboard.

This is an intentional design decision to prevent you from missing important work that requires your attention.

## PR Comes Back from Ignored PRs

If you have previously ignored a PR, but you later become an assignee or reviewer, the PR moves out of the **Ignored PRs** Dashboard and into the relevant column in the Repository Dashboard and All Repositories Dashboard.

This is an intentional design decision to prevent you from missing important work that requires your attention.
