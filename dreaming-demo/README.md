# dreaming-loop-demo

Throwaway repo for **Loop Engineering Project 12 — Build a Dreaming Loop (Capstone 2)**
(from [The AI Agent Factory / Loop Engineering, Routines Appendix](https://agentfactory.panaversity.org)).

A "base" loop has supposedly been running for weeks and leaving dated entries in `progress.md`.
On top of it sits a **dreaming loop** (a weekly cloud routine) that:

1. reads `progress.md` entries dated after `dreaming-state.md`'s `last_reviewed_date`,
2. finds any failure/correction pattern that appears **more than once**,
3. drafts the **smallest** `CLAUDE.md` / skill change that would prevent it — as a **PR** on a
   `claude/dreaming-<date>` branch, never a direct commit,
4. the PR description cites: which runs showed the pattern, how often, why the line stops it,
5. also proposes **one deletion**: a rule no recent run needed,
6. finishes by updating `dreaming-state.md` with today's date.

### Planted evidence (so the loop has something real to find)

- **Pattern A — lint skipped before commit** — appears in the entries for 2026-08-10, 2026-08-16, 2026-08-23 (3x)
- **Pattern B — reviewer subagent pointed at the wrong branch** — 2026-08-13, 2026-08-21 (2x)
- Deletion candidate: a `CLAUDE.md` rule about updating `CHANGELOG.md` that no run has ever touched.

### Done jab (self-check)

- [ ] PR ka proposed change real hai, cited log entries tak trace hota hai (guess nahi)
- [ ] Jaan-boojh kar planted repeated failure pakri gayi + proposal ban gayi
- [ ] Koi change `CLAUDE.md` mein bina merge kiye nahi hua (sirf PR branch par)
- [ ] `dreaming-state.md` aaj ki date se update hui
