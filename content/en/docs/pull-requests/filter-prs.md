---
title: "Filter PRs"
date: 2024-08-15
weight: 3
description: >
  You can create custom filters to automatically perform an action when an incoming pull request meets some criteria you define.
---

You can define custom filters to automatically perform one of these actions when an incoming pull request meets your criteria:

- Watch
- Ignore
- Apply a Tag
- Mark important [^1]

You can define criteria that determines when PR Focus should apply your filter, similar to email filtering.

If you want to find out about incoming pull requests, but automatically ignore certain PRs, such as Snyk dependency update PRs, you can define a filter to **Ignore** pull requests made by the Snyk PR user - in our case, *admin-token-bot*.

If your organization uses naming conventions in pull requests, you might want to automatically **Watch** a PR, or apply a specific tag to it, when the title includes "Feature:" or "Bug:" naming patterns.

{{% alert title="Tip" %}} PR Focus *always* displays a pull request where you are the PR author, the reviewer, or the assignee, even if you have **Ignored** it. If you set a filter to automatically ignore a pull request, PR Focus overrides the **Ignored** status for these pull requests. This is an intentional design feature to ensure you never miss an important pull request. {{% /alert %}}

[^1]: Mark important is a feature whose supporting functionality is coming in a future release.

## Create a Filter

To create a new filter:

1. Go to the **Filters** menu.
2. Select **Create a Filter**
3. Provide a name for the filter.
4. Add at least one condition for PR Focus to determine when to apply the filter. You can optionally add multiple conditions.
5. Specify the action PR Focus should take when an incoming PR meets the filter criteria.
6. Press the **Create Filter** button.

### Add Filter Criteria

You can define the criteria that PR Focus uses to determine whether or not to apply the filter. Filter criteria consists of:

- A supported field to filter
- A condition to determine whether or not to apply the filter
- A user-defined string to check for in the filter field

You cannot create a filter unless you provide a user-defined string.

You can optionally provide more than one condition. If you supply more than one condition, you must specify the filter logic that PR Focus should use when determining whether to apply the filter.

#### Supported Fields

You can select one of these fields for PR Focus to evaluate whether or not to apply the filter:

- Username: The GitHub username of the pull request author
- Title: The pull request title
- Description: The content contained in the initial comment by the pull request author, which may include a pull request template and typically contains the PR author's description of the pull request.
- Repository: The repository default name (for example, `prfocus-website` in `https://github.com/dacharyc/prfocus-website`), or the custom name for a repository you have defined in PR Focus.

#### Conditions

PR Focus evaluates these conditions when determining whether or not to apply the filter:

- `exactly matches`: the text in the selected field is an exact match (`==`) for the user-defined string. For example, `username` `exactly matches` `admin-token-bot` evalutes to true - and the filter is applied - when the PR author's username is "admin-token-bot."
- `includes`: the text in the selected field contains the user-defined string. PR Focus does not attempt to do any stemming or tokenization. This implementation uses the `.contains()` operator. For example, `username` `includes` `admin-token-b` evaluates to true - and the filter is applied - when the PR author's username is "admin-token-bot."
- `does not match exactly`: the text in the selected field does not match (`!=`) the exact user-defined string. For example, `username` `does not match exactly` `bot` evaluates to true - and the filter is applied - when the PR author's username is "admin-token-bot." The text contains the user-defined string, but it's not an exact match.
- `does not include`: the text in the selected field does *not* contain the user-defined string. PR Focus does not attempt to do any stemming or tokenization. This implementation uses the `!.contains()` operator. For example, `username` `does not include` `dacharyc` evaluates to true - and the filter is applied - when the PR author's username is "admin-token-bot." If the user-defined text was `bot`, this would evaluate to false, because the "admin-token-bot" username *does* contain `bot`, and the filter would not be applied.

When evaluating these conditions, PR Focus uses case-insensitive comparison with the user-defined string.

#### User-Defined Strings

PR Focus requires a user-defined string to evaluate the condition. It does not accept an empty string, and does not support regex or wildcard matching.

PR Focus converts both the text and the user-defined string to lowercase for comparison, making it a case-insensitive comparison.

#### Apply Filter Logic

When you create a filter, you must supply at least one condition. You can optionally supply multiple conditions for a filter. When you provide more than one condition, you can specify the logic that PR Focus uses to apply the conditions. PR Focus supports the following logical operators:

- `any of`: if any of the conditions evaluate to true, PR Focus applies the filter. For example, if you define a username condition and a title condition, and the title meets your condition but the username does not, PR Focus applies the filter. "Any of" means at least one condition must apply. As long as at least one condition applies, the filter applies - even if the other conditions don't apply.
- `none of`: if all of the conditions evaluate to false, PR Focus applies the filter. For example, if you define a username condition and a title doesn't meet your condition, but the username does, PR Focus *does not* apply the filter. "None of" means that if any of your conditions *do* apply, the filter overall *does not* apply.
- `all of`: if all of the conditions evaluate to true, PR Focus applies the filter. For example, if you define a username condition and a title condition, and the username meets your condition but the title does not, PR Focus *does not* apply the filter. "All of" means that if any of your conditions *do not* apply, the filter overall *does not* apply. In other words, all of your conditions must evaluate to true.

### Specify the Filter Action

When you create a filter, you specify what action PR Focus should take when a filter applies to a pull request. Available filter actions include:

- Watch: PR Focus automatically watches the PR on your behalf. It bypasses your **Inbox** and appears in your **Watched PRs** list as if you had manually selected to **Watch** the pull request.
- Ignore: PR Focus automatically ignores the PR on your behalf. It bypasses your **Inbox** and appears in your **Ignored PRs** dashboard as if you had manually selected to **Ignore** the pull request. Ignored PRs still appear in your main dashboards if you're the PR author, or if you become a reviewer or assignee. For more details, refer to [Ignored PRs: Unexpected Ignore Behavior]({{< ref "docs/pull-requests/dashboards/ignored-prs.md#unexpected-ignore-behavior" >}}).
- Apply a Tag: PR Focus automatically applies the tag you select. The PR appears in your **Inbox** or relevant lists already tagged, and is available in the **Tagged PRs** dashboard with your tag applied.
- Mark important: Mark important is a feature whose supporting functionality is coming in a future release. For the moment, "Mark important" has no visible effect.

## Update a Filter

To update a filter:

1. Go to the **Filters** menu.
2. Select **Manage Filters**.
3. Press the **Edit Filter** button next to the filter you want to change.

From the Edit Filter window, you can:

- Rename the filter
- Add, remove, or change filter criteria
- Change the filter logic if your filter has multiple criteria (any, all, none)
- Change the filter action

When you have finished the filter edits, press the **Update Filter** button.

## Delete a Filter

To delete a filter:

1. Go to the **Filters** menu.
2. Select **Manage Filters**.
4. Press the **Delete Filter** button next to the filter you want to remove from PR Focus.
