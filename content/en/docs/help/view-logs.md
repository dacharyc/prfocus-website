---
title: "View Logs"
date: 2023-09-04
weight: 2
description: >
  View PR Focus logs for helpful details.
---

PR Focus keeps logs of events in the app while the app is running. These logs disappear when you close the app.

The logs contain information about activity in the app, and can be a helpful resource for debugging unexpected behaviors while the app is in beta.

To view the logs, go to the `File` menu, select `New >`, and select `New PR Focus Logs Window`.

![Screenshot showing File -> New -> New PR Focus Logs Window](/images/new-log-window.png)

This opens the log view, which is a chronological list of activities in PR Focus:

![Screenshot showing the PR Focus logs view with a list of log activities and timestamps](/images/pr-focus-logs.png)

The logs can help you identify when the automated fetch isn't running at the time you expect, what PRs PR Focus is seeing in a repository, and other helpful debugging information.

You can sort the log by ascending or descending view.

When you encounter something unexpected while beta testing PR Focus, please check the logs for any relevant error messages.

I'm doing ongoing work to add more log messages and make them clear. Please let me know if you think something should have appeared in the logs but wasn't there, or if something appeared in an unexpected or unhelpful way in the logs.
