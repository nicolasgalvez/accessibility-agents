# Triage Labels

The skills speak in terms of five canonical triage roles. This file maps those roles to the actual label strings used in this repo's issue tracker.

| Canonical role    | Label in our tracker | Meaning                                  |
| ----------------- | -------------------- | ---------------------------------------- |
| `needs-triage`    | `needs-triage`       | Maintainer needs to evaluate this issue  |
| `needs-info`      | `needs-info`         | Waiting on reporter for more information |
| `ready-for-agent` | `ready-for-agent`    | Fully specified, ready for an AFK agent  |
| `ready-for-human` | `ready-for-human`    | Requires human implementation            |
| `wontfix`         | `wontfix`            | Will not be actioned                     |

When a skill mentions a role (e.g. "apply the AFK-ready triage label"), use the corresponding label string from this table.

Edit the right-hand column to match whatever vocabulary you actually use.

## Repository status: do not create these yet

`Community-Access/accessibility-agents` does not track triage state today. Measured usage across all issues:

| Label | Times applied |
| ----- | ------------- |
| `urgent` | 9 |
| `roadmap` | 8 |
| `copilot` | 1 |
| `wontfix`, `question`, `help wanted`, `automated` | 0 |

The live vocabulary is `urgent` and `roadmap`. The rest is GitHub's stock label set, largely never applied, including `wontfix`, which exists but has never been used.

The repo's labels are also a different kind from these: type (`bug`, `enhancement`), topic (`security`, `code-quality`, `source-broken`), and priority (`urgent`). The five canonical roles encode a state machine: unevaluated, waiting on the reporter, specified, routed to agent or human. That workflow has never run here.

**So create nothing up front.** Create a label at the moment `triage` first needs it, not before. Unused labels on a public repo are noise contributors have to interpret.

If you would rather map onto what exists than create: `question` ("Further information is requested") is a near-exact fit for `needs-info`. Edit the right-hand column of the table above and `triage` will apply your existing labels instead.

When you do want them, these are the commands:

```bash
gh label create needs-triage --description "Maintainer needs to evaluate this issue"
gh label create needs-info --description "Waiting on reporter for more information"
gh label create ready-for-agent --description "Fully specified, ready for an AFK agent"
gh label create ready-for-human --description "Requires human implementation"
```
