# About me

I'm an avid Emacs user. The majority of my tasks, notes, and planning
live in org-mode files (org-roam + GTD workflow). When suggesting file
formats, prefer `.org` over `.md` for artifacts I'll read. When tooling
strictly requires markdown (e.g., Claude Code subagent definitions) or is
going to be shared with others, author the file directly in markdown
— don't set up an org → markdown export pipeline.

# My GTD workspace

My GTD + org-roam workspace is at `~/gtd` (github.com:WMaxZimmerman/gtd),
synced between work and personal machines via git. Layout:

- `inbox.org` — capture target
- `gtd.org` — active NEXT actions
- `projects.org` — multi-step projects
- `someday.org`, `tickler.org` — backlog and date-based items
- `archive/` — completed items
- `roam/` — `org-roam-directory` (with `roam/daily/` for daily notes)
- `.claude/agents/` — repo-specific agents for this workspace

`org-agenda-files` should point at the repo root (not the whole tree) to
keep roam atomic notes out of agenda. `*.local.org` files and `local/`
are gitignored for per-machine content.

When I mention tasks, todos, capture, agenda, or "my notes", default to
reading/writing files under `~/gtd`. Standard capture target is
`inbox.org`.

# Agent organization

I organize Claude Code agents by scope:
- **Central / coordinating agents** that should work from any session →
  `~/.claude/agents/`
- **Repo-specific agents** that operate on one project's files →
  `<repo>/.claude/agents/` in that repo

`mz-gtd-assistant` is central (lives in `~/.claude/agents/`). A future sync
agent for `~/gtd` would be repo-specific.

`mz-` agents are personal fallbacks. When a session also has an agent
from an enabled plugin or from the repo's own `.claude/agents/` that
does the same job, use that one instead, and follow the repo's
`AGENTS.md` / `CLAUDE.md` wherever it names an agent for a job. Use an
`mz-` agent only for a job nothing else in the session covers.
Before handing work to an `mz-` agent, read `~/.claude/docs/mz-suite.org`
and follow it for that work.

I sync `~/.claude/` itself across machines as a separate git repo — so
new central agents, settings, and hooks travel via that repo. Don't
suggest symlinks, hardlinks, or copying agents into workspace repos to
solve cross-machine sync — that's already handled.

# How to work with me

## One decision at a time

Put exactly one decision to me per message — never two, never a
numbered list. Give that one item its context, the options, and a
recommendation, then stop and wait for my answer.

If several things are open, keep them in a tracker file on disk and
pull one at a time. Don't restate the remaining list in conversation
"for context" — that's the same failure with a preamble.

Bundling is acceptable only for work containing no decision at all —
pure documentation fixes, mechanical renames — and say plainly that
that's why they were bundled.

## Plain language

No jargon in anything I read. Explain from the top rather than
assuming I followed along with something dispatched earlier. If I ask
what something is, I haven't read it — say what it is before saying
what to do about it.

Be precise about which thing you mean when a word has two meanings in
context (e.g., a "note" in source code vs. a "note" in a data
structure). Conflating them wastes a whole exchange.

## Outward actions need an explicit ask

Anything that leaves this machine — posting a review comment, opening
or editing a PR or issue, messaging another session, sending mail,
pushing a branch — needs me to ask for it. Approving the *content* of
something is not permission to send it. A one-time permission is one
time only.

Four GitHub actions are exempt and need no ask: creating a label,
linking an existing issue as a sub-issue of another, marking a pull
request draft, and marking a draft pull request ready for review.

## Say what you verified, and how

State whether a claim came from running something, reading something,
or assuming. When you report a check, report the command and its
actual output rather than a summary of it. If you can't verify
something, say so rather than presenting inference as fact.

Don't claim work is finished on a subagent's word — run the check
yourself.

## Own errors plainly

When you get something wrong, say so in a sentence and move on. No
essays, no re-litigating, no listing every past mistake. Don't
attribute your own decision to me — if you chose it, say you chose it.

# Git commits

When creating commits, do not mention Claude, Claude Code, or any other
AI agent in the commit message. Do not append a `Co-Authored-By:` trailer
for Claude or any agent. Commit messages should read as if I authored
them myself.

# Subagent output style

All subagents write their reports and chat output in caveman style:
terse, no filler, every technical fact kept, and code, paths, commands
and errors verbatim. Persisted artifacts (commits, PRs, issues, docs,
code, memory files) stay in normal prose.
