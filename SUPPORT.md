# Support — Collision Guard for Jira Cloud

## How to get help

Contact the publisher through the support contact on the app's Atlassian
Marketplace listing. Please include:

- your Jira site URL (`your-site.atlassian.net`);
- what you did, what you expected and what happened;
- the approximate time, the browser and its version;
- optionally, lines from the browser's developer console that start with
  `[collision-guard]` (DevTools → Console, with **Verbose** enabled). These
  lines contain no personal data or Jira content.

Please do not send Jira content, screenshots with confidential data,
passwords or API tokens.

## What we support

- Collision Guard on Jira Cloud, in the web browsers that Jira Cloud supports.
- The latest version published on the Atlassian Marketplace.

Out of scope:

- Jira Data Center and Server;
- Jira mobile apps;
- Jira's own behaviour, such as the timing of Jira's change notifications;
- requests for features that the product intentionally excludes, such as
  locking, presence and "who is viewing".

## Response targets

- **First response:** within **2 business days** (Monday–Friday, excluding
  public holidays in the publisher's country). This is best effort, with no contractual SLA.
- **Security reports:** see [`SECURITY.md`](SECURITY.md).

## Self-help

| Symptom | Explanation |
|---|---|
| No warning after my own change | Expected: your own changes are never reported (by design, also from another tab) |
| No warning after a comment | Expected: comment-only activity is not reported |
| Warning came a few seconds after the change | Expected: timing depends on Jira's change notifications |
| Several changes, only one warning | Expected: one warning per work item until you reload the page |
| The warning has no close button | Expected: reload the page (Reload now or the browser) to clear it |
| Jira already shows the new value | Jira refreshes some fields itself. The warning still tells you someone else changed the work item, so reload to see everything |
| Warning after an automation rule ran | Can happen: automation changes are made by another account |

## Uninstalling

A Jira administrator can uninstall the app at any time from **Apps → Manage
apps**. The app stores no data, so nothing remains afterwards.
