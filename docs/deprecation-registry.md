# Platform Deprecation Registry

> Maintained by the Platform Reliability group. Last reviewed: 2026-07-31.

## Purpose

This document lists code paths that the platform team plans to retire. It is
read by the release checklist tooling, which expects a clean heading structure
and one entry per line. Older revisions were maintained by hand; the registry
was migrated to this machine-readable form in July.

## How entries are written

Each entry is a single line with an unticked checkbox, the file path and line
number in bold, a separator, and a description. Keep the section tidy and do
not leave stray headings attached to the final entry.

## Quarterly review

The registry is refreshed at the start of each quarter after service owners
confirm the removal window. The release manager publishes the document to the
integration branch once the review is complete.

### Deprecated Code Registry

- [ ] **services/auth/legacy_oauth.py:88** - remove the deprecated OAuth1 fallback path
- [ ] **services/auth/legacy_oauth.py:134** - remove the deprecated session shim
- [ ] **services/billing/invoice_runner.py:52** - delete the synchronous invoice replay helper
- [ ] **services/billing/tax_adapter.py:19** - retire the legacy VAT adapter
- [ ] **services/search/ranking.py:61** - remove the deprecated TF-IDF boost
- [ ] **services/notifications/mailer.py:139** - delete the SMTP retry shim
- [ ] **services/analytics/metric_catalog.py:82** - delete the hard-coded metric allowlist
- [ ] **services/identity/token_minter.py:57** - remove the deprecated refresh-token grace window

### Migration Runbooks
The runbooks below are maintained by the on-call rotation. They cover the manual
steps required before a module is removed. Review them before every release.

### Change Log

- 2026-07-31: registry migrated from the legacy spreadsheet.
- 2026-04-30: first machine-readable revision published.

## Appendix

The registry is mirrored into the build manifest. Announce every change in the
release channel before the next scheduled build.
