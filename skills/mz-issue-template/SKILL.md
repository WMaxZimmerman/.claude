---
name: mz-issue-template
description: "Reference text, not a task: the six-heading layout for GitHub issue bodies — the headings and the question each answers, how they are written as markdown `## <Name>` lines, that all six always appear, a heading with nothing to say carrying the line `Not applicable — <reason>.`, where acceptance criteria go in the body and how they are recognised on an existing issue, when an existing issue counts as in the layout, how the one kind of issue that keeps its own shape is recognised on an existing issue, which headings of an existing issue are unanswered, and the two lines in which a rewrite or a fill-in is offered. Personal fallback. Listed under `skills:` by `mz-gh-issue-writer`, which writes issues in this layout, and `mz-gh-scout`, which checks an issue against it. The one copy of the layout; neither agent restates it."
user-invocable: false
---

# The issue body layout

This is the one copy of the layout. `mz-gh-issue-writer` writes GitHub issues in it; `mz-gh-scout` checks an issue against it. What each agent does with it — when the writer applies it, where its content comes from, when each agent makes the offer, how a readiness check is reported — is in that agent's own definition, not here.

An issue's body sits under six headings, in this order. One kind of issue is the exception and keeps its own shape: the follow-up issue that `mz-suite.org` § Tracking defines, as `mz-gh-issue-writer` writes it. The heading on the issue is the short name; the question beside it is the rule for what goes under it.

| Heading | The question its content answers |
| --- | --- |
| Problem | What is the problem? |
| Why it matters | Why is this a problem? |
| Approach | How do we plan to solve it, and what are we deliberately leaving out? |
| Where it lives | What repos, systems, and modules are involved? |
| Verifying locally | How can I run and verify this locally? |
| Open questions and decisions | What is still undecided, and what has been decided? |

- **Written as `## <Name>`.** Each heading is a markdown line in the issue body: `## ` followed by the short name spelled as in the table, and nothing else — no question, no number. A stored heading reads `## Problem`. The content follows it as ordinary markdown, up to the next of the six headings or the end of the body.
- **All six, always.** All six headings appear on every issue the layout covers, the `tech-debt` issues included. A heading that truly has nothing to say carries one line saying it is not applicable and why: `Not applicable — <reason>.` There is no seventh heading: what is deliberately left out goes under Approach.
- **Acceptance criteria.** They go in the issue body, at the end of the Approach section: a line reading `**Acceptance criteria**`, then a markdown task list, one item per condition (`- [ ] <criterion>`). That line is bold text, not a heading. When an issue has no acceptance criteria, the line and the list are left out. On an existing issue, in the layout or not, acceptance criteria are present when the body holds a line reading `**Acceptance criteria**` with one or more task-list items after it, ticked or not, wherever in the body that line sits; otherwise they are absent.
- **Whether an existing issue is in the layout.** An existing issue is in the six-heading layout when its body holds all six headings as `## ` lines spelled as in the table. Anything else — no headings, other headings, a heading at another level, one of the six absent — is not in the layout.
- **The exception, recognised on an existing issue.** The follow-up issue: its title begins `mz follow-ups from` and it carries the `mz-follow-up` label. An issue with that title and without the label, or the label and without that title, is not the exception, and a report on it says that it may have been meant as one.
- **Which headings are unanswered.** On an existing issue, a heading of the six is unanswered when the issue's present content does not answer its question from the table. The present content, for this rule, is the issue body and nothing else: the title, the labels, and the comments do not make a heading answered. The acceptance-criteria line and its list answer no heading's question. On an issue in the layout, a heading — any of the six — is unanswered when nothing sits under it, or nothing but the acceptance-criteria line and its list. On an issue not in the layout, it is any of the six whose question no part of the present content answers, whether or not the heading itself is there. A heading that carries a not-applicable line (a line opening `Not applicable`) is answered. This is the one statement of the rule: the writer's offer to rewrite and the scout's readiness check both name headings by it.
- **The offer.** Being in the layout and having every heading answered are two different conditions, each decided by the rule of that name above, and an offer is made on either failing. Each condition has its own line, worded so the main agent can put it to the user as it stands; at most one applies to an issue, and none when it is in the layout with every heading answered:

  ```
  Offer for the user: #<number> is not in the six-heading layout. Its present content leaves these headings unanswered: <headings, or none>. Rewrite it to match?
  Offer for the user: #<number> is in the six-heading layout with these headings unanswered: <headings>. Fill them in?
  ```

  The first line is for an issue that is not in the layout; the second for an issue that is in the layout with one or more headings unanswered. No offer is made on the follow-up issue. When each agent makes the offer — the writer after an edit, the scout on a readiness check — and what follows the user's yes are in that agent's own definition. This is the one copy of the two lines.
