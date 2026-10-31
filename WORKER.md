# Worker brief

The conductor fills this into the assignment; do not send the entire coordination
history to every worker. Workers read host rules and relevant topic docs themselves.

```text
Issue/repository and acceptance:
Scope, likely files, boundaries:
Checkout/base revision, isolated ports/server config and evidence directory:
Shared expensive verification (queue/turn) if any:
Owner/session label and other workers' file responsibilities:
Resolved Issueflow revision/content (reuse conductor's session snapshot):
Capability/effort choice (or selection limit), reason and stop/reassessment condition:
Short plan and independent helper output (if any):
2–3 risk-based checks and mandatory release gates:
Applicable project hooks: names/phases, triggers/timing, procedure links, owner and required/optional evidence:
Integration/publishing owner:
Follow-up owner, evidence format, destination and timing:
Heartbeat, question channel and required result evidence:
```

Follow the [isolation rules](ORCHESTRA.md#isolate-concurrent-agents): only your
assigned checkout, ports, servers and temporary/build directories; confirm a server
serves your checkout before collecting evidence. Start background servers as
`cmd & pid=$!` and stop them with `kill "$pid"`. Commit (and push when the host allows)
at each meaningful milestone, so progress survives the loss of the worker. Work only the
assigned scope and preserve others' changes. When you start the first active sub-issue
of a parent, also add the parent's missing work label; its removal and closure belong
to the conductor. Use existing helpers/harnesses; verify the agreed risks, then stop
expanding. Tell the conductor promptly when evidence changes the plan, a check fails or
access is denied; to escalate, send a concise diagnosis and the preserved patch/evidence
rather than retrying blindly or raising effort for an ordinary command failure. Never
bypass a denial. A helper returns revision/patch, checks and limitations to the
integration owner; it does not publish or close the issue.

Before returning, stop every background process you started and release shared locks;
the conductor stops a reported worker that still has background work instead of waiting.
Return outcome, commit, checks/evidence, remaining acceptance and rough phase times.
Then wait for a new assignment; never continue a queue chain yourself. Resume an
interrupted checkout rather than duplicate finished work.
