# v0.9 Build 1

Release Date: July 15, 2024

This release adds a free trial and paywall to PR Focus. People who want to take the app for a spin get 30 days to try it out for free before deciding it they'd like to buy it.

## Enhancements

- Add a free 30-day trial and the ability to unlock the unlimited access version of PR Focus
- Add a "Buy or Restore Purchases" menu option to the PR Focus menu

# v0.8 Build 2

Release date: July 8, 2024

This release represents the final feature set for the public beta and eventual v1.0 release. Any releases between now and v1.0 are intended to be bugfixes or minor UX improvements only - no feature changes.

## Enhancements

- Sort the PRs in the Ignored/Archived/Inactive dashboards by repository
- Add the ability to watch PRs without watching the entire repository
  - New "Solo PRs" dashboard where you can view all the PRs you're watching that aren't affiliated with a repo you're watching
  - New "Pull Requests" menu where you can access the option to watch a single PR
   - Rename main "All Repositories" view to "All PRs" to include the solo PRs you may be watching, and move it out of Repositories section of sidebar
- Add a menu option to the Help menu that takes you to the form to email support
- Add a menu option to the Help menu that goes to the PR Focus social media account
- Other UI Improvements
  - Use repo custom name (if you've provided one) in the Manage Repos view
  - Provide a less-detailed PR row view when performing bulk operations
  - Add to "success" banners that watching a PR or repo enqueues a fetch job which will begin shortly
  - In a PR Row view, bold the Checks, Commits, Comments, or Reviews if a PR has any of those new items
  - Minor adjustments to the condensed PR Row view used when displaying "My PRs", "Assignee", and "Reviewing" columns side-by-side to avoid overflowing text labels

## Bugfixes

- Fix a bug where adding a new repo may never fetch PRs for that repo (since v0.6)
- Override global or custom settings to show the "assigned" or "reviewing" columns if you are an assignee or reviewer for a PR
- Fix a bug where the provided GitHub API key could not be saved to the keychain during onboarding.

# 0.7 Build 1

This release brings some nice improvements:

## Enhancements

- Perform bulk operations from the aggregate Inbox view. [Feature: Bulk operations on PRs](https://github.com/dacharyc/prfocus-website/issues/25)
- Archive and unarchive a PR while in the detail view.
- New button to fetch the PRs for a specific repo. This is useful if you're watching a lot of repositories, and don't want to wait for all of the fetch jobs to run - you can quickly fetch only the updates for a single repository.

## Fixes

- Surface better error handling for disallowing an API access token with no expiration date.  [Bug: Errors if API token has no expiration date](https://github.com/dacharyc/prfocus-website/issues/24)
- Fix a serialization error for some types of GitHub checks.
- Check whether or not a repository has already been added to PR Focus, and don't add it again.

# 0.6 Build 1

This release adds support for fetching all PRs that have been opened from the date you add a repository to PR Focus. This is a change in behavior from prior versions. In prior versions, if a PR was opened and closed in between PR Focus fetches, PR Focus would never see the PR. Now, PR Focus sees *all* PRs that are open in a repo from the date that you add the repository to PR Focus. It does not fetch PRs that have already been closed before you add the repository to PR Focus.

## Example

I add the prfocus-website repository to PR Focus on June 19, 2024. PR Focus does not see PRs #23 and older, since those were closed prior to adding this repository to PR Focus. But it sees PR #27, which was opened after adding the repository to PR Focus - even if the PR is already closed before the next time I fetch this repository with PR Focus.

# 0.5 Build 1

This release features a ton of changes and improvements, including:

PR Focus has a shiny new icon! This replaces the placeholder icon as I prepare for release.

PR Focus has been freed from its window!

Moved lots of functionality from the dashboard to new app menu options in the menu bar. Find familiar functionality in the following new menu items:
- PR Focus Menu
  - Settings: formerly `Global Settings` in the dashboard sidebar
  - Manage API Key: formerly part of the `Global Settings` in the dashboard sidebar
- Repositories
  - Add Repositories: formerly part of Add or Remove Repos in the dashboard sidebar
  - Manage Repositories: formerly part of Add or Remove Repos in the dashboard sidebar, and Repo Settings when viewing a specific repository dashboard
- Logs
  - View Logs: formerly under New -> New LogView Window menu item

Lots of UI improvements!

PR Detail View
- Switch the "View on GitHub" links in inconsistent places for a consistently-styled GitHub link in consistent placement throughout the detail view. [Feature: big-ol-button for view on github](https://github.com/dacharyc/prfocus-website/issues/20)
- Populate a placeholder title for PR Status Checks that don't have a title
- Populate a placeholder icon for PR Status Checks that don't have a status
- Show the PR's status in the detail view
- Replace the custom icons in the column headers with SF Symbols that scale and display better

Outside of the PR Detail View, there have been a few other UI improvements:
- Add a badge count for Inactive PRs
- Remove the comma from PR numbers with four or more digits
- Views that have been moved to their own menu items from the dashboard have been refactored for a nicer appearance in their more atomic windows.
- Added a button to delete PRs in the Archived PRs dashboard. This button is only available when no other jobs are running.

There have also been some behind-the-scenes changes to the background job processes:
- When you add a new repository to PR Focus, a background job gets enqueued to fetch the PRs for that repository when any running jobs are complete. Previously, if you added a repository while a job was running, the automated task to fetch PRs for the new repository simply wouldn't run.
- Minor refactors to try to more accurately show the "background job running" spinner animation when PR Focus is running a background task. This appears to resolve a few cases where the spinner didn't show while a job was running, but any feedback around this is appreciated!

Bugfixes:
- PR Focus would display a message in the logs when a PR had more than 250 commits suggesting you should contact support. It turns out, GitHub just doesn't provide a way to access more than the last 250 commits on a PR, even for their own internal API, so this message has been refactored into a note in the UI when viewing a PR with more than 250 commits.
- Fix an issue where the view would update and pop you out of the PR Detail View when viewing a PR with new commits, comments, reviews, or status checks.

# 0.4 Build 1

- Handles fetching data when a PR has more than 100 commits.
- Improves the clarity of error messages and troubleshooting recommendations related to data fetching and deserialization errors.

# 0.3 Build 2

## Bugfixes

- Fix crash when adding multiple repos.
- Fix crash related to changing the repository label color.

# 0.3 Build 1

## New Features

- Better handling of API access token expiration.
  - Warns if the API access token expires within the next 24 hours.
  - Doesn't try to fetch PRs if the API access token is expired.
- UI updates.
  - Update pull request status icons and colors. Add an icon for pull requests that are in Draft state.
  - Display a "New" label on new commits, status checks, reviews, and comments when viewing PR details.
  - Update the "Review" status icons to use SF Symbols. Add a drop-shadow for the icons in light mode to increase contrast. Increase the size of the status icons to improve legibility.

## Bugfixes

- Fix crash when adding multiple repos.
- Fix change to divider styling in lists introduced by macOS Sonoma.

## Breaking Changes

- Revert changes to dark mode PR Summary colors. [Feature: dark mode related UI changes](https://github.com/dacharyc/prfocus-website/issues/17)
  - This build of PR Focus reverts the changes to "secondary" and "tertiary" colors for the PR Summary row cards. After the prior change, the grey color was "brighter" per the related issue feedback, and represented PRs with updates. This build reverts that, so the dark black color indicates new updates, as Apple's counterpoint to the bright white color in light mode.
- Changes to the data model to support new functionality. While PR Focus is in beta, I'm not performing migrations for breaking changes, so you'll need to delete and re-install PR Focus. This means adding your API access token and repositories again, and re-triaging pull requests to watch/ignore.

# 0.2 Build 10

[Milestone: PR Focus App 0.2 Build 10](https://github.com/dacharyc/prfocus-website/milestone/2)
Released: September 17, 2023

## Breaking Changes

- Change dark mode colors to increase contrast and make the "bright" card represent one that has updates. [Feature: dark mode related UI changes](https://github.com/dacharyc/prfocus-website/issues/17)
  - This build of PR Focus reverses the "secondary" and "tertiary" colors for the PR Summary row cards. In prior builds, the dark black color indicated new updates, as Apple's counterpoint to the bright white color in light mode. The more grey color was the "viewed" color in both color schemes. Based on feedback that the "brighter" color should be the one that indicates updates, I've made the grey-ish card in dark mode the color that indicates updates
  - This build also makes the "has updates" color in dark mode a lighter color to increase contrast.
  - If you have feedback on this change, please leave a comment on the issue linked above! I am willing to consider further changes if people have strong opinions.

## New Features

### From GitHub Issues
- Add the ability to sort PR columns in the repository dashboards. [Feature: Filter and/or Sort PRs by attribute](https://github.com/dacharyc/prfocus-website/issues/11)
- Add the ability to add multiple repositories in one operation. Select "Add many" from the "Add repo" sheet and you can add a list of repository URLs, separated by newlines. [Feature: Import/Export a configuration file that contains repository addresses](https://github.com/dacharyc/prfocus-website/issues/12)

## Bugfixes

### From GitHub Issues
- Rewrite the PR fetch logic to determine which PRs to fetch. [Bug: Too many PRs showing up in "PRs to create or update"](https://github.com/dacharyc/prfocus-website/issues/16)

### From Internal Backlog
- Fix missing PR status checks. Rewrite the way PR status checks are being fetched, created and updated.
- Fix an issue where network requests could trigger a secondary GitHub API rate limit. Network requests now run serially, which has slowed the fetch process but avoids violating GitHub's secondary rate limit.
- Validate that the API key in PR Focus has the correct permissions to access a repository before adding the repository to PR Focus.
- Add better error reporting around network requests. Additional details should now appear in the app logs for a variety of network request issues.
- Fix the animation that runs when automated jobs are running. The PR Focus title bar now hides the manual "Fetch" button when automated jobs are running, and instead shows an animated spinner and provides details about which job is running until the job is complete.

# 0.2 Build 5

[Milestone: PR Focus App 0.2 Build 5](https://github.com/dacharyc/prfocus-website/milestone/1)
Released: September 10, 2023

## New Features

### From GitHub Issues
- Add the ability to open a PR in GitHub from the PR Summary context menu [Feature ability to go directly to GitHub without clicking into details.](https://github.com/dacharyc/prfocus-website/issues/15)
- Add the ability to clear log entries, and automatically clear log entries more than a day old [Feature app - log trimming features](https://github.com/dacharyc/prfocus-website/issues/13)

### From Internal Backlog:
- Add the ability to immediately archive a PR from the PR Summary context menu (right-click on a closed or merged PR to see this option)

## Bugfixes
### From GitHub Issues:
- Fix overly picky URL validation [Bug App - overly picky url validation](https://github.com/dacharyc/prfocus-website/issues/3)
- Add a success banner when updating the API key [Bug app - no success banner when updating API key](https://github.com/dacharyc/prfocus-website/issues/4)
- Remove unused User Profile URL field in Global Settings [Feature app - confusing User Profile URL things](https://github.com/dacharyc/prfocus-website/issues/5)
- Update initial onboarding link to generate an API access token to PR Focus documentation w/detailed permissions [Feature app - onboarding screen & docs don't specify that it must be a classic API token](https://github.com/dacharyc/prfocus-website/issues/7)
- Rename "Mergeable" to "Conflicts" [BugApp or Website - pick one!:](https://github.com/dacharyc/prfocus-website/issues/14)

### From Internal Backlog
- Fix an incorrect UI label when you add the first repository (User Profile to Global Settings)
- Fix PRs that you are ignoring should not appear in the Inactive PRs dashboard
- Updating a repo custom name or label color does not immediately dismiss the Repo Settings view
- Fix Repo Settings not dismissing when you select a different repository
- Switch to a more compact PR Summary when a row displays three columns
- Fix a case where the status check icon on the PR Summary may not correctly reflect the status checks on a PR

Note: There is currently a known issue where PR Focus is not ingesting some status checks from check suites/workflow runs. I'm currently alpha testing a private build that fixes this issue to ensure stability. If it's stable, that should be in the beta build for next week.