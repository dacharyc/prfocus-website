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

GitHub provides two types of access tokens:

- A fine-grained access token (currently in beta) which provides more precise control over what the bearer can access
- A classic access token with less precise control over what the bearer can access

The required permissions for PR Focus to fetch pull request data vary depending on which type of access token you create. If you are not seeing pull requests after adding a repository to PR Focus, verify that your API access token has the appropriate permissions for the repository.

### Fine-Grained Access Token Permissions

GitHub's fine-grained access token provides the most precise control over what a user can access. As a result, PR Focus needs a number of permissions to get all the data it needs. PR Focus requires:

Repository permissions
- Actions: Read-only
- Commit statuses: Read-only
- Contents: Read-only
- Deployments: Read-only
- Issues: Read-only
- Metadata: Read-only
- Pull-Requests: Read-only
- Workflows: Read and write (PR Focus does not need write permission, but GitHub does not provide read-only access for Workflows, so Read and write is the only option)

Account permissions
- Profile: Read and write (PR Focus does not need write permission, but GitHub does not provide read-only access for the user Profile, so Read and write is the only option)

### Classic Access Token Permissions

If you're using a Classic access token, it must have the following permissions:

- `repo` read permissions for any repository you want to watch in PR Focus. 
- `user` read permissions to get your username and avatar for use in the app.

If your organization uses SAML single sign-on (SSO), and you use a classic personal access token, you must configure SSO for your personal access token after you create it. For more details, refer to the GitHub Authentication documentation page [Authorizing a personal access token for use with SAML single sign-on](https://docs.github.com/en/enterprise-cloud@latest/authentication/authenticating-with-saml-single-sign-on/authorizing-a-personal-access-token-for-use-with-saml-single-sign-on).

#### How does PR Focus store and transmit the access token?

When you enter the access token, PR Focus saves it securely to your [macOS Apple Keychain](https://support.apple.com/guide/mac-help/use-keychains-to-store-passwords-mchlf375f392/mac). PR Focus does not store your access token directly in the app code or otherwise transmit it except to make API calls to GitHub. If you ever want to remove your access token from Keychain, you can find it in the Keychain Access app. 

Note that if you remove your access token from Keychain, PR Focus can no longer make API calls to GitHub. This means PR Focus will no longer be able to fetch PR updates or new PRs.

#### Why does PR Focus need user read permissions?

When you provide an access token during setup, if your access token has the appropriate permissions, PR Focus uses it to create a User Profile in the app for you. It reads your GitHub username and avatar and displays it in the **Global Settings** in the app. PR Focus uses this information to determine whether a PR was made by you, and whether you are a reviewer or assigned to a PR.

If your access token doesn't have the appropriate permissions, PR Focus can't fetch your user profile and can't proceed with the initial user setup.

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
