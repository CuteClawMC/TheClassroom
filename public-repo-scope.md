# Public Repo Scope

This repository is designed to prove that Classroom is real and technically legible without exposing the private trading core.

## Safe To Publish

- narrative submission materials
- technical appendix
- raise and economics draft
- visual architecture
- representative miner payload examples
- representative metric buckets
- high-level protocol mechanics such as proposal and probation flow

## Keep Private

- live trading code
- production runtime parameters
- full 46-metric internal schema if it is considered proprietary
- live agent state and trade logs
- broker integrations and production execution code
- dashboards, credentials, launch agents, and environment files
- any infrastructure that exposes security posture or operational weaknesses

## Why This Boundary Exists

The public repo should help a reviewer answer:

- is the project real?
- is there technical substance here?
- does the founder understand the protocol and validator problem?

It does not need to answer:

- what exact private logic is running in production today?
- what exact parameter values are currently live?
- how is the proprietary engine implemented end-to-end?
