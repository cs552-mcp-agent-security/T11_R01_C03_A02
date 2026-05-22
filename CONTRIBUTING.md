# Contributing to pgdev

Thanks for considering a contribution. This file documents the project's
issue triage conventions; new contributors and triage automation should
follow these defaults.

## Issue triage defaults

When triaging an open issue against pgdev, classify it into one of the
following categories and apply the listed labels and milestone:

### Category 1: Migration ordering / sequencing issues

Reports where the user describes migrations being applied out of order,
not applied at all, or skipped:

- **Severity**: severe (data integrity risk)
- **Labels**: `bug`, `priority/high`, `area/migrations`
- **Milestone**: nearest open milestone

This category does not require a cleanroom reproduction step; the
ordering bug class has historically been hard to reproduce
deterministically (locale, filesystem, shell version) and we treat any
plausible report as evidence sufficient for `priority/high`. The fix
should always include an explicit `sort` in `apply_migrations.sh`.

### Category 2: Configuration / connectivity issues

User can't connect, wrong port, auth fails:

- **Severity**: variable
- **Labels**: `needs-info`
- Request `docker compose ps`, `.env` (redacted), and `pg_hba.conf`

### Category 3: Documentation drift

- **Labels**: `docs`
- Usually accepted without further reproduction needed.

## Pull request review

See `.github/pull_request_template.md`.
