---
title: "Get Started"
linkTitle: "Get Started"
weight: 2
description: >
  What do you need to know to get started with PR Focus?
---

## Prerequisites

- PR Focus is an English-language macOS app. The minimum macOS version required to use PR Focus is 13.3.
- PR Focus is currently available as a private alpha through TestFlight. You must install [TestFlight](https://apps.apple.com/us/app/testflight/id899247664) from the App Store to use it.
- PR Focus currently only supports repositories hosted on GitHub. You cannot use PR Focus to watch repositories hosted on GitLab, Bitbucket, or any other git repository hosting - provider. PR Focus is not compatible with self-hosted enterprise GitHub installations.
- PR Focus requires a GitHub access token to make API calls. The access token must have the appropriate permissions for the repositories you want to watch. Details below.

## Installation

PR Focus is currently available as a private alpha through TestFlight. 

If you have been invited to the private TestFlight group, you should get an email from Apple. Follow the instructions in the email to accept the invite and begin testing PR Focus.

## Setup

The first time you start PR Focus, you'll be asked to provide some setup details. You must:

- Provide a GitHub Access Token
- Add your first repository

### Generate a GitHub Access Token

PR Focus requires a GitHub access token with permissions to access the repositories you want to watch.

For details about how to generate a GitHub access token, refer to the GitHub Authentication documentation page [Manage Personal Access Tokens](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens).

GitHub provides two types of access tokens:

- A fine-grained access token (currently in beta) which provides more precise control over what the bearer can access
- A classic access token with less precise control over what the bearer can access

The required permissions for PR Focus to fetch pull request data vary depending on which type of access token you create. 

For more details about the required permissions for each type of access token, refer to [GitHub API Key]({{< ref "docs/api-key/_index.md" >}})

You can update your access token later from the **PR Focus** menu with the **Manage API Key** option.

### Add a Repository

After you provide a valid API access token, PR Focus guides you to add your first repository. Provide the GitHub URL for a repository you want to watch, similar to `https://github.com/dacharyc/prfocus-website`

When you are adding your first repository, you can optionally configure settings for that repository. For more information, refer to *Customize Repository Settings* below. If you just want to get started, you can skip this step.

After you add the initial repository, PR Focus automatically fetches open pull requests for that repository. You'll go to the main dashboard, and should start seeing PRs appear in your **Inbox**, **My PRs**, and **Assigned PRs** or **Reviewing PRs** respectively. You can specify whether to **Watch** or **Ignore** the PRs that come in. For more information, refer to [Incoming PRs]({{< ref "docs/pull-requests/incoming-pr.md" >}}).

#### Customize Repository Settings (Optional)

You can optionally configure repository-specific settings for this repository. These settings include:

- How you interact with the repository. This affects the view of that repository's dashboard, *and* your main dashboard.
  - You can specify that you'll never be a reviewer, assignee, or contributor to the repository. PR Focus considers this a "watch-only" view. When you check this checkbox, PR Focus does *not* show the **My PRs**, **Assigned PRs**, or **Reviewing PRs** columns for that repository. You'll only see an **Inbox** and your **Watched PRs** for that repository.
  - If you may be a contributor, assignee, or reviewer in that repository, check the appropriate checkbox(es). These checkboxes toggle the visibility of the **My PRs**, **Assigned PRs** and **Reviewing PRs** columns respectively.
  - When you check that you may be an assignee or a reviewer in a repository, the **Assigned PRs** or **Reviewing PRs** column *also* appears in your main dashboard.
  - The global default is that you may be a contributor and a reviewer.
- How often to fetch pull requests for the repository.
  - The global default is hourly.
- The number of days to wait until archiving a pull request after it has been closed or merged. 
  - The global default is 10 days.
  - If your work *starts* after an upstream repository has merged a PR, you may want it to remain in your repository dashboard for several days or weeks before it moves to archived.
  - If your work is *done* when a PR is closed or merged, you may want it to be archived right away. 
- The number of days to wait before moving a pull request without updates to "inactive".
  - The global default is 30 days.
  - You may want a PR in a specific repository to move to inactive sooner.
  - If a repository has a longer review cycle, you may want to delay the time until inactive.

You can always update these settings later in **Repo Settings**. For more information about customizing repository setings, refer to [Repository Settings]({{< ref "docs/repositories/manage-repository.md" >}}).

You can update your global default settings later in **Global Settings**. For more information, refer to [Global Settings]({{< ref "docs/settings/_index.md" >}}).

## What's Next

After you add your first repository, you may want to add more repositories for PR Focus to watch. For more information about adding repositories, refer to [Add a Repository]({{< ref "docs/repositories/add-repository.md" >}}).

You may also want to change the label color or provide a custom name for a repository. For more information about customizing the way the repository appears in PR Focus, refer to [Repository Settings]({{< ref "docs/repositories/manage-repository.md" >}}).

You may want to customize your global default settings. If you do not customize the settings for a repository, PR Focus uses the global default settings to determine:

- What columns to display
- How often to fetch pull requests
- How long to wait before archiving a PR or setting it to "Inactive"

For more information about global default settings, refer to [Settings]({{< ref "docs/settings/_index.md" >}}).
