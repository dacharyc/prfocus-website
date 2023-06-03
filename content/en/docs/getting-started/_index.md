---
title: "Get Started"
linkTitle: "Get Started"
weight: 2
description: >
  What do you need to know to get started with PR Focus?
---

## Prerequisites

PR Focus is an English-language macOS app. The minimum macOS version required to use PR Focus is 13.3.

PR Focus is currently available as a private alpha through TestFlight. You must install [TestFlight](https://apps.apple.com/us/app/testflight/id899247664) from the App Store to use it.

PR Focus currently only supports repositories hosted on GitHub. You cannot use PR Focus to watch repositories hosted on GitLab, Bitbucket, or any other git repository hosting provider. PR Focus is not compatible with self-hosted enterprise GitHub installations.

PR Focus requires a GitHub access token to make API calls. The access token must have the appropriate permissions for the repositories you want to watch.

## Installation

PR Focus is currently available as a private alpha through TestFlight. 

If you have been invited to the private TestFlight group, you should get an email from Apple. Follow the instructions in the email to accept the invite and begin testing PR Focus.

## Setup

The first time you start PR Focus, you'll be asked to provide some setup details. This includes:

- Creating an account for PR Focus
- Providing a GitHub Access Token

### PR Focus Account

PR Focus requires an account to sync data with the cloud and your other devices. This enables PR Focus to share watched PRs across your devices - for example, a work laptop and a personal laptop - and to backup and easily restore your watched PRs in the event you need to change computers.

There are no plans to make a non-syncing version of PR Focus at this time.

PR Focus will likely be a subscription app to cover the costs of sync and cloud storage.

### Generate a GitHub Access Token

For details about generating a GitHub access token, refer to the GitHub Authentication documentation page [Manage Personal Access Tokens](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens).

The access token you generate should have `repo` and `user` read permissions. These are the minimum required permissions for PR Focus.

When you enter the access token, PR Focus saves it securely to your [macOS Apple Keychain](https://support.apple.com/guide/mac-help/use-keychains-to-store-passwords-mchlf375f392/mac). PR Focus does not store your access token directly or otherwise transmit it except to make API calls to GitHub. If you ever want to remove your access token from Keychain, you can find it in the Keychain Access app. 

Note that if you remove your access token from Keychain, PR Focus can no longer make API calls to GitHub. This means PR Focus will no longer be able to fetch PR updates or new PRs.

You can update your access token from the PR Focus **User Profile**.

When you provide an access token during setup, if your access token has the appropriate permissions, PR Focus uses it to create a User Profile in the app for you. It reads your GitHub username and avatar and displays it in the **User Profile** in the app. PR Focus uses this information to determine whether a PR was made by you, and whether you are a reviewer or assigned to a PR.

If your access token doesn't have the appropriate permissions, PR Focus can't fetch your user profile and can't proceed with the initial user setup.

### Add a Repository

After your initial setup is complete, use the **Add a Repository** button to start watching repositories. For more information about adding repositories, refer to [Add a Repository]({{< ref "docs/repositories/add-repository.md" >}}).

### Fetch PRs

After you add a repository, press the **Fetch PRs** button to fetch open PRs in the repository you just added! When the fetch job is complete, you'll see PRs in your Inbox. Click into each PR to **Watch** or **Ignore** the PR. For more information, refer to [Incoming PRs]({{< ref "docs/pull-requests/incoming-pr.md" >}}).
