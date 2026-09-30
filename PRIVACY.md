# Privacy Policy — Collision Guard for Jira Cloud

Effective date: the date of publication of version 1.0.0 on the Atlassian Marketplace.

In this policy, **we** means the publisher of Collision Guard, the Atlassian
Marketplace partner named on the app's listing. **You** means the Jira Cloud
customer and its users.

## Summary

Collision Guard does **not collect, store, sell or share** any personal data or
Jira content. It has no servers of its own and sends no data anywhere. All of
its work happens inside the user's web browser, within Atlassian's Forge
platform.

## What the app processes, and where

When a user opens a Jira work item, Atlassian's Forge platform loads the app as
an invisible script in that user's browser. The script works with this
information:

| Data | Source | Purpose | Kept |
|---|---|---|---|
| The user's Atlassian **account id** | Forge view context | Tell the user's own changes apart from other people's | Not kept; read again for each notification |
| The displayed **work item id** | Forge view context | Ignore notifications about other work items | Only the ids of work items already warned about, in browser memory, until the page is reloaded or closed |
| Jira's change notification: work item id, project id, change type (`updated` / `commented`) and the **account id** of whoever made the change | Jira, via Forge (`JIRA_ISSUE_CHANGED`) | Decide whether to show the warning | Not kept; used only while handling the notification |
| The Forge licence status (paid version only) | Forge view context | Disable warnings on unlicensed installations | Not kept |

Forge delivers the standard view context to every app, including the site
URL, locale, time zone, and the work item's key and type. Collision Guard
receives it but uses only the fields in the table above, and keeps none of it.

The app never reads or receives:

- summaries, descriptions, comments, attachments or field values;
- names, email addresses or avatars.

## What the app stores

Nothing. The app does not use:

- Forge storage (KVS, SQL, Object Store);
- browser storage (cookies, `localStorage`, `sessionStorage`, IndexedDB);
- any other database.

## What the app transmits

Nothing to us or to any third party. The app:

- has no backend and no Forge functions;
- declares no external network permissions;
- makes no Jira REST API calls;
- includes no analytics, telemetry or error-reporting service.

Automated tests check that the shipped script does not use network,
page-storage or DOM APIs.

The app does exchange data with the Jira page itself, through Atlassian's Forge
bridge inside the browser:

- it receives the context and notifications described above;
- it asks Jira to display the warning and, on request, to reload the page.

## Logs

The script writes short technical lines to the browser's developer console,
such as `[collision-guard] JIRA_ISSUE_CHANGED -> WARN`. These lines contain no
identifiers or Jira content, stay on the user's device and are never collected
by us.

## Atlassian

The app runs on Atlassian's Forge platform. Atlassian processes data as
described in its own privacy policy: <https://www.atlassian.com/legal/privacy-policy>.
This app adds no data processing beyond what is described above.

## Data subject requests

We hold no personal data, so there is nothing for us to access, export,
correct or delete. Uninstalling the app removes it completely.

## Children

The app is intended for business use in Jira Cloud and is not directed at
children.

## Changes to this policy

If a future version changes how data is handled, this policy will be updated
before that version is released, and the change will be listed in the release
notes. Any new Jira permission requires an administrator's approval in Jira
before it takes effect.

## Contact

For privacy questions, use the support contact on the app's Atlassian
Marketplace listing.
