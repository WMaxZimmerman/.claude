# About me

I'm an avid Emacs user. The majority of my tasks, notes, and planning
live in org-mode files (org-roam + GTD workflow). When suggesting file
formats, prefer `.org` over `.md` for artifacts I'll read, except when
tooling strictly requires markdown (e.g., Claude Code subagent
definitions) — in those cases suggest an org → markdown export workflow
rather than authoring in markdown directly. I'm comfortable with
Emacs-native solutions (hooks, elisp, capture templates).

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

`gtd-assistant` is central (lives in `~/.claude/agents/`). A future sync
agent for `~/gtd` would be repo-specific.

I sync `~/.claude/` itself across machines as a separate git repo — so
new central agents, settings, and hooks travel via that repo. Don't
suggest symlinks, hardlinks, or copying agents into workspace repos to
solve cross-machine sync — that's already handled.
