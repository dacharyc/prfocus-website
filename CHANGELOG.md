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