---
title: "View Logs"
date: 2023-09-04
weight: 2
description: >
  View PR Focus logs for helpful details.
---

PR Focus keeps logs of events in the app while the app is running. These logs disappear when you close the app.

The logs contain information about activity in the app, and can be a helpful resource for debugging unexpected behaviors. When you encounter something unexpected, please check the logs for any relevant error messages.

I'm doing ongoing work to add more log messages and make them clearer. Please let me know if you think something should have appeared in the logs but wasn't there, or if something appeared in an unexpected or unhelpful way in the logs.

## Open the Log View

To view the logs, go to the `Logs` menu, and select `View Logs`.

![Screenshot showing Logs -> View Logs menu option](/images/view-logs-menu-option.png)

This opens the log view, which is a chronological list of activities in PR Focus:

![Screenshot showing the PR Focus logs view with a list of log activities and timestamps](/images/pr-focus-logs.png)

The logs can help you identify when the automated fetch isn't running at the time you expect, what PRs PR Focus is seeing in a repository, and other helpful debugging information.

## Sort and Clear Logs

You can sort the log by ascending or descending view. Press the up arrow or down arrow to sort the logs by ascending or descending order.

To clear log entries, press the `Clear Log` button. This removes all log entries.

If you leave PR Focus running overnight, PR Focus automatically trims logs more than a day old.
