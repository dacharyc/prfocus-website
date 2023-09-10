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