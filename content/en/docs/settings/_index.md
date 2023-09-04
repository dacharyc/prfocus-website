---
title: "Settings"
linkTitle: "Settings"
weight: 5
date: 2023-06-04
description: >
  Configure PR Focus Settings
---

PR Focus has a handful of global settings you can configure from the **Global Settings**.

A future version of PR Focus will move these settings into **Preferences**.

![Screenshot showing configurable settings in Global Settings](/images/global-settings.png)

## API Key

You can change the API Key that PR Focus uses to make API calls to GitHub.

Press the **Edit API Key** button to provide a new API access token.

For details about generating a GitHub access token, refer to the GitHub Authentication documentation page [Manage Personal Access Tokens](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens).

The access token you generate should have `repo` read permissions for any repository you want to watch in PR Focus. PR Focus also needs `user` read permissions to get your username and avatar for use in the app.

If your organization uses SAML single sign-on (SSO), and you use a classic personal access token, you must configure SSO for your personal access token after you create it. For more details, refer to the GitHub Authentication documentation page [Authorizing a personal access token for use with SAML single sign-on](https://docs.github.com/en/enterprise-cloud@latest/authentication/authenticating-with-saml-single-sign-on/authorizing-a-personal-access-token-for-use-with-saml-single-sign-on).

When you enter the access token, PR Focus saves it securely to your [macOS Apple Keychain](https://support.apple.com/guide/mac-help/use-keychains-to-store-passwords-mchlf375f392/mac). PR Focus does not store your access token directly or otherwise transmit it except to make API calls to GitHub. If you ever want to remove your access token from Keychain, you can find it in the Keychain Access app. 

## Profile URL

You can change the GitHub profile that PR Focus uses to determine whether you are the assignee/reviewer/person making the pull request. Provide a new GitHub profile URL in the format `https://github.com/YOUR-USERNAME-HERE` and replace `YOUR-USERNAME-HERE` with the new GitHub username you'd like to use.

PR Focus does not currently support having multiple GitHub user profiles. If this is something you need, please file a feature request.

## Dashboard Views

You can customize the lists displayed in your Repository Dashboard and All Repositories Dashboard. Check or uncheck the `Show Assigned PRs` or `Show Reviewing PRs` checkboxes to show or hide those lists in your dashboards. 

Currently, this is a global setting that defaults to showing the **Reviewing PRs** list and hiding the **Assigned PRs** list.

You can override these global settings on a per-repository basis. For example, if you watch many repositories in which you are a reviewer, but only one in which you may be an assignee, you may want to leave the global **Assigned PRs** setting unchecked, and specify it only for the repository where you need this information.

For more information about customizing settings for a repository, refer to [Repository Settings]({{< ref "docs/repositories/manage-repository.md" >}}).

## Days until inactive/archive

The `Days until inactive` and `Days until archive` settings are used to determine the time interval for when PR Focus should move PRs into the [Inactive PRs]({{< ref "docs/pull-requests/inactive-prs.md" >}}) or [Archived PRs]({{< ref "docs/pull-requests/archived-prs.md" >}}) dashboards.

The global settings default to 30 days until inactive and 10 days until archive.

You can override these global settings on a per-repository basis. For example, if you watch many repositories in which you want to archive PRs right away, but one repository in which you want to leave closed or merged PRs in your dashboard view for a period of time, you can set the global *days until archive* setting to a low value, and customize the repo where you want it to have a longer value.

For more information about customizing settings for a repository, refer to [Repository Settings]({{< ref "docs/repositories/manage-repository.md" >}}).
