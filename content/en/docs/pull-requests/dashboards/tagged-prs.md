---
title: "Tagged PRs"
date: 2024-08-13
weight: 4.5
description: >
  You can apply custom tags to pull requests to track important work. View and filter tagged PRs in the Tagged PRs dashboard.
---

You can use tags to create your own categories to track important pull requests. You might create a tag to easily categorize pull requests:

- Going into a specific release
- Related to a new feature, even across repositories
- For a specific client
- Conforming to a certain naming protocol that has significance in your workplace, like "Feature" or "Bug"

You can apply tags to pull requests manually, or create filters to automatically tag incoming pull requests that meet criteria you define.

Once you have tagged pull requests, you can view and filter your tagged PRs in the Tagged PRs dashboard.

## Tagged PRs Dashboard

In the Tagged PRs dashboard, each pull request summary displays a list of tags that have been applied to it.

![Screenshot showing the Tagged PRs Dashboard with a list of PR Summary rows that display the various tags that have been applied to the PRs](/images/tagged-prs-dashboard.jpg)

You can filter PRs by tag, and optionally within a date range by one of the available date fields.

### Filter PRs by Tag

You can filter PRs by tag using the **Tag** filter in the upper left-hand corner of the Tagged PRs dashboard. Select a specific tag to view only the PRs related to that tag. Or select the placeholder "Filter by Tag" to clear the tag filter.

![Screenshot showing the Tagged PRs Dashboard with the Filter by Tag drop-down menu expanded to show the available tags for filtering](/images/tagged-prs-filter-by-tag.jpg)

### Filter PRs within a date range

You can filter PRs within a date range in the Tagged PRs dashboard. Press the **Filter by date** button in the upper-right corner of the Tagged PRs dashboard. This opens the date picker.

![Screenshot showing the Tagged PRs Dashboard with the Filter by Date options expanded to show the Start Date and End Date date pickers, and the option to select the date field to filter on](/images/tagged-prs-filter-by-date.jpg)

Select a start date, and an optional end date. You can specify the type of pull request activity to use in the date filter:

- Created at date
- Updated at date
- Closed at date
- Merged at date

If a pull request has not yet been closed or merged, the closed and merged dates are nil, so the PR will not show up in either of those filters.

Press the **Apply** button to view only pull requests where the specified pull request activity falls within the date range. When you're done, press the **Clear** button to remove the date filter.

## Apply Tags to PRs

You can apply tags to a PR from two places:

- The right-click context menu available when you're viewing pull request summaries in a list view. Right-click a PR summary, and select **Apply Tags**.

  ![Screenshot showing a PR summary with the right-click context menu option, the "Apply Tags" menu expanded, and a tag called "Consolidation" selected](/images/apply-tags-in-pr-summary-menu.jpg)
- The pull request detail view. Select a tag from the **Apply Tags** menu in the upper right-hand corner of the detail view, above the repository label.

  ![Screenshot showing the PR detail view with a tag called "Consolidation" and an arrow pointing to the "Apply Tags" drop-down menu](/images/apply-tags-option-in-pr-detail-view.jpg)

Any tags that you've created appear in this menu, sorted by most recently updated.

When you apply a tag, the pull request summary gets a "Tag" icon.

![Screenshot showing a PR summary with an arrow pointing to the "Tag" icon that indicates that a PR has been tagged](/images/pr-summary-with-tag-icon.jpg)

The tag appears in the pull request detail view. And the tag is displayed in the pull request summary when you're viewing the **Tagged PRs** dashboard.

## Remove Tags from PRs

You can remove tags from a PR from two places:

- The right-click context menu available when you're viewing pull request summaries in a list view. Right-click a PR summary, and select **Remove Tags**. Choose the tag you want to remove.

  ![Screenshot showing a PR summary with the right-click context menu option, the "Remove Tags" menu expanded, and a tag called "Consolidation" selected](/images/pr-summary-remove-tags.jpg)
- The pull request detail view. Right click on a tag in this view, and select the **Remove Tag** option. 

  ![Screenshot showing a PR detail view with an arrow pointing to a "Consolidation" tag circled, where the right-click menu has been opened and the option to "Remove Tag" is selected](/images/pr-detail-remove-tag.jpg)

The tag is removed from the PR. If no other tags apply, the PR no longer appears in the Tagged PRs dashboard.

## Create and Manage Tags

You can create and manage tags from the **Tags** menu.

### Create a Tag

To create a new tag:

1. Go to the **Tags** menu.
2. Select **Create a Tag**

   ![Screenshot showing the "Create a Tag" menu option](/images/create-a-tag-menu-option.jpg)

3. Provide a name for the tag.

   ![Screenshot showing the "Create a Tag" window with a tag name "Bugfix" entered into the text field](/images/create-a-tag-window.jpg)
4. Press the **Create Tag** button.

### Rename or Delete a Tag

To rename or delete a tag:

1. Go to the **Tags** menu.
2. Select **Manage Tags**.

   ![Screenshot showing the "Manage Tags" menu option](/images/manage-tags-menu-option.jpg)
3. Click a tag name to bring up a sheet where you can edit the tag name. This automatically renames the tag in the menus, and on all PRs that have had the tag applied.

   ![Screenshot showing the "Edit tag text" sheet where the tag name is "Add Tagging". There are buttons to "Edit tag text" or "Cancel".](/images/edit-tag-name-sheet.jpg)
4. Press the **Delete tag** button to remove a tag from PR Focus. This automatically untags all PRs that have the tag applied.

   ![Screenshot showing the "Manage Tags" window with an arrow pointing to the "Delete tag" button.](/images/manage-tags-window-with-delete-tag-arrow.jpg)
