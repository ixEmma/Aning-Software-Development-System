# Approval states

## PLANNING ONLY

Allowed: inspect, research, analyze, compare, propose, plan, identify risk.

Not allowed: repository writes, configuration changes, database writes, deployment, production mutation, or billing/pricing changes.

## READY FOR GO

The scope and intended change are approved. Execution has not happened.

## EXECUTED LIVE

Use only after the approved write succeeded and the requested behavior was verified at the relevant layer.

## Keep these states separate

A change may be:
- proposed;
- implemented locally;
- committed;
- pushed;
- CI-verified;
- deployed;
- verified in production.

Report the actual state. Never compress these into "done."
