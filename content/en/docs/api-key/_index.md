---
title: "GitHub API Key"
linkTitle: "GitHub API Key"
weight: 6
date: 2024-03-17
description: >
  Configure the GitHub API Key
---

PR Focus uses a GitHub API key to make calls to GitHub. You can view and update the GitHub API key from the **Manage API Key** menu option in the **PR Focus** menu.

![Screenshot showing the "Settings" menu option in the **PR Focus** menu](/images/manage-api-key-menu-option.png)

Selecting this option opens a window where you can view details about your GitHub API Key, or update it.

![Screenshot showing the Manage API Key window](/images/manage-api-key.png)

When your API key expires, PR Focus can no longer fetch updates. PR Focus warns you when the API key is close to expiring or if it has expired. You can view the expiration date of the current API key anytime from this window.

## API Key

You can change the API key that PR Focus uses to make API calls to GitHub.

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

### Authorize for SSO

If your organization uses SAML single sign-on (SSO), you must configure SSO for your personal access token after you create it. For more details, refer to the GitHub Authentication documentation page [Authorizing a personal access token for use with SAML single sign-on](https://docs.github.com/en/enterprise-cloud@latest/authentication/authenticating-with-saml-single-sign-on/authorizing-a-personal-access-token-for-use-with-saml-single-sign-on).

## How does PR Focus store and transmit the access token?

When you enter the access token, PR Focus saves it securely to your [macOS Apple Keychain](https://support.apple.com/guide/mac-help/use-keychains-to-store-passwords-mchlf375f392/mac). PR Focus does not store your access token directly in the app code or otherwise transmit it except to make API calls to GitHub. If you ever want to remove your access token from Keychain, you can find it in the Keychain Access app. 

Note that if you remove your access token from Keychain, PR Focus can no longer make API calls to GitHub. This means PR Focus will no longer be able to fetch PR updates or new PRs.

## Why does PR Focus need user read permissions?

When you provide an access token during setup, if your access token has the appropriate permissions, PR Focus uses it to create a User Profile in the app for you. It reads your GitHub username and avatar and displays it in this window. PR Focus uses this information to determine whether a PR was made by you, and whether you are a reviewer or assigned to a PR.

If your access token doesn't have the appropriate permissions, PR Focus can't fetch your user profile and can't proceed with the initial user setup.

PR Focus does not currently support having multiple GitHub user profiles. If this is something you need, please file a feature request.
