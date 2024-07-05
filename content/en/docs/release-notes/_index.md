---
title: "Release Notes"
linkTitle: "Release Notes"
weight: 9
date: 2024-07-05
description: >
  Find out about updates to PR Focus.
---

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
