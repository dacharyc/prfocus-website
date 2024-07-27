---
title: "Release Notes"
linkTitle: "Release Notes"
weight: 9
date: 2024-07-05
description: >
  Find out about updates to PR Focus.
---

## v0.11 Build 1

Release Date: July 29, 2024

This is the final release candidate for the v1.0 launch. I appreciate any bug reports and feedback before launch!

### Enhancements

The theme for this final release candidate is onboarding improvements!

**UI Updates**

- Add onboarding flow with carousel of images describing key features.
- Add styling and additional information to the paywall.
- Add a little Easter Egg for people who buy the full version of the app.
- Request review at a few key moments.
- Add a release notes flow to display info about app updates on first launch after release.
- Style the About pane with custom layout and more info.
- Change the "File an issue" Help menu option to "File a bug" to be clearer about the destination.
- Redesign UI for first time setup view.

Most of this will be invisible for folks who have been using the beta builds, but should be some nice improvements for new folks who are onboarding for the first time.

## v0.10 Build 1

Release Date: July 23, 2024

This release fixes a few minor bugs and adds a few small quality-of-life improvements. This is the first release candidate for the v1.0 launch.

The only further changes planned before v1.0 are some onboarding improvements, and any bug fixes that come up in the next week or two. I appreciate any bug reports and feedback!

### Enhancements

**New Features**

- When in the PR Detail view, added Next and Previous buttons to view the next and prior PR details without having to go back to the dashboard.
- Are you an eager clicker? This version adds an accessibility setting to only view PR details through the right-click context menu. No more accidentally clicking into PR details!

**UI Updates**

- Monolithic App Settings and Repo Settings are monolithic no more! Break up settings into discrete chunks to set the stage for the settings options to grow.
- "Add a single repo" and "Update repo settings" options now display the label color in the color picker, so you have some idea what color you're choosing.
- You can now specify a custom name when you add a single repo, instead of requiring you to do it later through the update settings screen.
- Other small navigation name and UI fixes for improved consistency throughout the app.

### Bugfixes

- Fix bug where updated comments show as new comments.
- Fix bug where Inactive PRs badge count did not accurately reflect the number of PRs in the dashboard.
- Fix bug where edited reviews weren't updating.
- Fix bug where daily GitHub fetch job was running too often.
- Fix bug in Perform Bulk Operations view where the background of the checkbox area did not match the background of the PR summary card if the PR was in a "viewed" state.

## v0.9 Build 1

Release Date: July 15, 2024

This release adds a free trial and paywall to PR Focus. People who want to take the app for a spin get 30 days to try it out for free before deciding it they'd like to buy it.

### Enhancements

- Add a free 30-day trial and the ability to unlock the unlimited access version of PR Focus
- Add a "Buy or Restore Purchases" menu option to the PR Focus menu

## v0.8 Build 1

Release date: July 8, 2024

This release represents the final feature set for the public beta and eventual v1.0 release. Any releases between now and v1.0 are intended to be bugfixes or minor UX improvements only - no feature changes.

### Enhancements

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

### Bugfixes

- Fix a bug where adding a new repo may never fetch PRs for that repo (since v0.6)
- Override global or custom settings to show the "assigned" or "reviewing" columns if you are an assignee or reviewer for a PR
