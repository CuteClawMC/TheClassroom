# Classroom

Public-facing submission repository for the proposed Classroom subnet on Bittensor.

Classroom is a network-native research engine for empirical market discovery. The goal is not to publish a trading bot. The goal is to show the protocol shape, the evidence model, and the public submission materials behind the subnet proposal.

## What Is In This Repo

- [Landing page source](index.html)
- [White paper PDF](docs/classroom-whitepaper.pdf)
- [Bitstarter narrative PDF](docs/classroom-bitstarter-narrative.pdf)
- [Technical appendix](docs/technical-appendix.md)
- [Raise and economics draft](docs/raise-economics.md)
- [Visual architecture](docs/visual-architecture.md)
- [Public repo scope](docs/public-repo-scope.md)
- [Metric buckets](docs/metric-buckets.md)
- [Probation protocol](docs/probation-protocol.md)
- [Example miner payload](examples/miner-payload.example.json)

## What Classroom Is

Classroom is a proposed Bittensor subnet built around controlled market experimentation.

Miners do not submit abstract predictions. They submit protocol-valid experiments: structured trade outcomes with lineage, context, and parameter state. Validators score whether those experiments are complete, coherent, and honest. Over time, the accepted output becomes a compounding empirical database of parameter-response behavior.

## Current Prototype Evidence

As of 2026-03-21, the internal prototype already includes:

- `7` active prototype lanes
- `1,633` settled prototype trades across the active lanes that currently produce structured trade history
- approximately `75,118` metric-events at the current `46 metrics per trade` standard
- a live control plane for proposals, probation, state persistence, and reporting

## Why This Repo Is Public-Safe

This repository is intentionally scoped.

It includes:
- the narrative submission materials
- technical framing for miners, validators, and protocol behavior
- representative examples that make the project legible

It does **not** include the private trading engine, live parameters, production state, credentials, or the full proprietary internal data model.

## Submission Note

This repo is intended to accompany the Classroom whitepaper / narrative packet for external review. It is a public proof surface, not a full open-source release of the Money Squad production environment.
