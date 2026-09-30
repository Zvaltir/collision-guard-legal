# Security — Collision Guard for Jira Cloud

## Security posture

| Property | Collision Guard 1.0.0 |
|---|---|
| Hosting | Atlassian Forge only ("Runs on Atlassian"). There is no publisher-operated infrastructure |
| Forge modules | One `jira:issueViewBackgroundScript` (Custom UI, invisible) |
| Backend / Forge functions / resolvers | None |
| Jira permissions (scopes) | None (`permissions.scopes: []`) |
| Jira REST API calls | None |
| External egress | None. No `permissions.external` entries, so Forge's content security policy blocks outbound requests |
| Storage | None (no Forge storage, no browser storage) |
| Secrets, API keys, credentials | None in the app or repository |
| Third-party services | None (no analytics, telemetry, error reporting or CDN) |
| Runtime dependency | `@forge/bridge` (Atlassian), bundled at build time |

**What a compromise could reach.** The script runs in a sandboxed iframe with
no scopes. It can only:

- receive Jira's change notifications for the displayed work item;
- read the Forge view context;
- show a flag;
- reload the Jira page.

It cannot read or modify Jira content.

**Fail-open design.** Every error is caught inside the script, so a failure
in the app is designed not to block reading, editing, transitions, comments or
navigation in Jira.
The page reloads only when the user clicks **Reload now**.

## Build and supply chain

- Dependencies are pinned to exact versions, with a committed `package-lock.json`.
- `npm audit` is run before every release; a release with a known critical or
  high vulnerability is not shipped.
- The deployed bundle is built from source with `npm run build` (esbuild).
  Automated tests run that bundle in a sandbox without network, storage or DOM
  APIs.
- `forge lint` and `forge eligibility` are run before every production deployment.

## Reporting a vulnerability

Please report suspected vulnerabilities **privately** through the support
contact on the app's Atlassian Marketplace listing. Put "SECURITY" in the
subject, and do not open a public issue.

We aim to:

- acknowledge a report within **3 business days**;
- give a first assessment within **10 business days**;
- fix confirmed critical or high issues as a priority, then publish a release
  and credit the reporter if they wish.

Atlassian platform vulnerabilities (Forge, Jira) should be reported to
Atlassian: <https://www.atlassian.com/trust/security/report-a-vulnerability>.

## Supported versions

Only the latest version published on the Atlassian Marketplace is supported.
Forge upgrades installations automatically for minor versions. A version that
needs new permissions requires administrator approval.
