---
title: "Ignored PRs"
date: 2023-06-04
weight: 4
description: >
  Ignoring a PR gets it out of your way. You can get it back at any time.
---

From the PR Summary context menu, or when viewing PR details, you can access a button to **Ignore** a pull request.

You might want to **Ignore** a pull request if its status and details don't matter to you. For example, if you're watching a repository for user-facing changes, and a team puts up a pull request for internal refactoring, you may want to ignore the PR. When you press the **Ignore** button, the pull request goes into the **Ignored PRs** dashboard, which gets it out of your main dashboard views.

While a PR is ignored, but its status is still open, PR Focus continues to fetch updates to the pull request.

## Ignored PRs Dashboard

This dashboard is a list of PRs that you've ignored, sorted by the repository where the PR originated.

![Screenshot showing the Ignored PRs Dashboard with a list of full-width PR Summary rows](/images/ignored-prs.png)

You can access the **Ignored PRs** Dashboard by pressing the **Ignored PRs** button in the PR Focus sidebar.

The **Ignored PRs** dashboard does not have a counter. The PR Focus design assumes you do not need to pay attention to ignored PRs.

## Stop Ignoring a PR

At any time, you can stop ignoring a PR. You might want to stop ignoring a PR if you have a reason to think you might need to pay attention to it, but you're not necessarily ready to watch it. When you stop ignoring a PR, it moves out of your **Ignored PRs** Dashboard and into the **Inbox**.

To stop ignoring a PR:

1. Go into your **Ignored PRs** Dashboard.
2. Find the PR you want to stop ignoring.
3. Use the PR Summary context menu or click into the PR Summary to open the PR Details view.
4. Press the **Stop Ignoring** button.

If you want an ignored PR to move directly to your **Watched PRs** list, press the **Watch** button instead of the **Stop Ignoring** button. This automatically stops ignoring the PR and moves it directly to your **Watched PRs** list.

## Unexpected Ignore Behavior

PR Focus is an opinionated app designed to prevent you from missing important pull requests that require your attention. It includes some important design decisions that may result in behavior that seems unexpected unless you understand the design rationale:

- Some PRs may not move to the **Ignored PRs** dashboard
- PRs may come back from the **Ignored PRs** dashboard without you doing anything
- You cannot delete an open PR - you can only ignore it

### PR Not Moving to Ignored PRs

If you try to ignore a PR where you are an assignee, a reviewer, or where the PR is yours, it does not move into the **Ignored PRs** Dashboard. It stays in the relevant column in the Repository Dashboard and **All Pull Requests** Dashboard.

This is an intentional design decision to prevent you from missing important work that requires your attention.

### PR Comes Back from Ignored PRs

If you have previously ignored a PR, but you later become an assignee or reviewer, the PR moves out of the **Ignored PRs** Dashboard and into the relevant column in the Repository Dashboard and **All Pull Requests** Dashboard.

This is an intentional design decision to prevent you from missing important work that requires your attention.

### You Can Only Ignore - Can't Delete - an Open PR

In some cases, you may want to delete a pull request instead of ignoring it. You might want to delete a pull request when you're absolutely certain you don't need to pay attention to it.

PR Focus does not allow deleting open pull requests. This is an intentional design decision, as PR Focus assumes you may eventually become a reviewer or assignee on an open pull request. Ignoring a pull request is intended to remove it from the pull requests you need to pay attention to, while preserving the ability to let you know if it moves into a state where you need to pay attention to it.
