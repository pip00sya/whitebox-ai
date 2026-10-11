# Source publication record

Published 12 October 2026 by Nurkhan Aimukatov (`pip00sya`) for QwertyS.

- Prior public `main`: `aa54c7b7feef2675bcd9212241c64dc0209aff2f`.
- Studio source: `Eye172/whitebox-ai-1`, branch `p0-p1-build`, commit `409bda5d5177d9a828621f3b10d782302b733498`.
- Joint project engineers: Nurkhan Aimukatov and Shakhnazar Akhmer, equal engineering roles.
- The studio source files were added over the existing public snapshot. No original
  commits, tags or gallery files were removed. Existing public README content is
  retained in `docs/archive/README-early-snapshot.md`.
- Documentation now separates the later studio from the original competition pitch.
- Publication uses a new commit on the existing history; it does not reconstruct
  individual engineering contributions from commit authorship.

Full Git bundles, original refs and repository-setting snapshots were retained
locally before publication. Rollback can use a new revert commit without rewriting history.

## Publication maintenance

The imported studio remains on Next.js 15. Production dependency fixes were
applied within that version line: Next.js 15.5.27 and a PostCSS 8.5.29 override.
The lockfile records the exact installed versions. The dependency audit used
`npm audit --omit=dev --audit-level=high` and reported no runtime vulnerabilities.
The upstream fixes are documented in [the Next.js advisory](https://github.com/advisories/GHSA-p293-qw3h-jr36)
and [the PostCSS advisory](https://github.com/advisories/GHSA-r28c-9q8g-f849).

The existing browser journey now expects the current canonical-state recovery
message after its intentionally injected initial 503 response. Its assertions
that recording remains disabled before a question, the server turn state stays
unchanged, and retry recovers the interview are preserved. Application behavior
was not changed for this test adjustment.

The browser test also selects the visible current question (the history pane
contains another copy) and plays each synthetic protected clip before recording
human transcript verification, as required by the existing server policy.

The scorecard navigation assertion now uses the visible pseudonymous candidate
link from the visible application row, instead of expecting a raw
application UUID in a ranking summary that intentionally strips that identifier.
It still checks the evaluated application identity and its transition to human adjudication.
