# MomentBackup support

The public support home for MomentBackup on GitHub: `README.md`, `SECURITY.md`, issue
templates in `.github/`, and Discussions. Part of the MomentBackup org;
`MomentBackup/MomentBackup` is the desktop repo.

`AGENTS.md` is the only instructions file. `CLAUDE.md` is a symlink to it, so Codex and Claude
read the same text. Edit `AGENTS.md`, and keep `CLAUDE.md` as the link, never a copy.

## MomentBackup-wide rules

Michael's standing decisions. The full text is in the desktop repo's `AGENTS.md`
(`~/Development/MomentBackup/AGENTS.md`).

- **No new tests or proofs.** Do not propose, request, plan, write, generate, record, or
  automate a test, proof, gate, receipt, screenshot, workflow, or CI job. If work seems to need
  one, stop: do not make one, and do not ask Michael for one.
- **Tests, CI, release automation, packaging, and code signing are paused (2026-10-01).**
  GitHub Actions is disabled. Do not add or enable a workflow until Michael decides a new plan.
- **One banned word.** Never write "h‑o‑u‑s‑e‑h‑o‑l‑d" in pages, templates, docs, commit messages, or
  mockups. Say **your computers**, **this hub**, or **the owner**, and do not swap in a synonym
  (2026-08-09).
- **AI slop ban (2026-10-26).** MetaTana's slop ban applies here in full: no hype, filler,
  structure tells, internal words, essays, or visual slop. The full list is "AI slop ban" in
  the desktop `AGENTS.md`.
- Secrets never appear in the repo, chat, commits, logs, or CLI arguments.
- Record finished work in the desktop repo: a dated `PROGRESS.md` entry and a reconciled
  `TODO.md`.

## Support rules

- This repo is public. It holds no product code and no private customer reports.
- Keep the private path first: the support page on momentbackup.com. Public GitHub reports are
  for technical users whose details are all safe to share.
- Security problems go to private vulnerability reporting, never to a public issue or
  Discussion.
- Links to momentbackup.com help and support pages must point at pages that exist.

## Branch hygiene

Delete branches whose work has already landed, and check by content, not by commit count:

```sh
git fetch -q origin
git diff --quiet origin/main origin/<branch> && echo "identical to main, safe to delete"
```

Archive the tip first (`git update-ref refs/archive/<branch> <sha>`). A branch carrying unique
work is landed or explicitly superseded, never silently dropped.
