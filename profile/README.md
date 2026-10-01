# Itinera

**Workflows that keep business rules separate from flow control.**

Every system mixes two kinds of decision. Business rules decide what the business does. Flow control decides what happens around that work: retry a failed piece, try another strategy, take a different path. When flow decisions live inside business code, nobody can see a flow in one place, and nobody can change it without touching the business.

Itinera makes the separation structural:

- **Steps know nothing.** A step is a business unit. It asks for data without knowing where it comes from, contributes data without knowing where it goes, and reports an outcome. It never sees the workflow running it.
- **The flow is written in one place.** A workflow is an ordered list of steps plus the policies that decide what happens after each outcome. The list you read is the order that runs.
- **Policies decide, executors carry out.** After each outcome, a hook returns what should happen next, or nothing to accept the default. Moving to a different path means moving the journey to another workflow, explicitly.
- **Everything is observable.** Every executor reports a standard stream of events, so a journey can be followed from start to end in production.

## Status

Early. Itinera is being specified before it is built, and the first implementation is in Rust. Nothing is released yet.

## Repositories

- [spec](https://github.com/itinera-dev/spec): the language-neutral specification, the proposal process and the roadmap. **Start here.**
- [itinera-rs](https://github.com/itinera-dev/itinera-rs): the Rust implementation, the first one.
- [conformance](https://github.com/itinera-dev/conformance): test cases, written as data, that every implementation must pass.

Implementations for TypeScript and the JVM (Kotlin, with support for Java) are planned after Rust.

## Roadmap

Itinera grows in cumulative tiers. A language claims a tier when it passes every conformance case up to that tier.

1. **Tier 1, a single workflow:** steps, the data bag, a local executor, retries, step hooks and the event stream.
2. **Tier 2, transfers and switches:** moving a journey to another workflow, with or without its data and progress.
3. **Tier 3, sub workflows:** running a workflow from within another.
4. **Tier 4, rescue steps:** fixing the cause of a failure, then running the failed step again.
5. **Later:** durable runs that survive crashes, and more.

The details are in [ROADMAP.md](https://github.com/itinera-dev/spec/blob/main/ROADMAP.md).

## How Itinera is built

AI is an integral part of how Itinera is made: agents write code and specification text, review pull requests and help manage issues. A human maintainer reviews everything before it is merged, and work that is right is used whoever, or whatever, wrote it. The terms are those of [A manifesto for software engineering with AI](https://marlon-sousa.com/blog/manifesto/), and contributors accept them as described in the [contributing guide](https://github.com/itinera-dev/.github/blob/main/CONTRIBUTING.md#how-itinera-is-built).

## Contributing

To propose a feature, open a Proposal issue in [spec](https://github.com/itinera-dev/spec/issues/new/choose). Proposals are triaged, evaluated in the issue thread, and turned into specification text once agreed. Please share implementation ideas in the issue, and open a pull request only after the spec is merged; then implementation is open to everyone. Opening the issue is all that is asked of you; the rest is done when the proposal is planned. [It is not bureaucracy](https://github.com/itinera-dev/.github/blob/main/CONTRIBUTING.md#this-is-not-bureaucracy). The whole process is in [PROCESS.md](https://github.com/itinera-dev/spec/blob/main/PROCESS.md).

Itinera is dual-licensed under MIT and Apache-2.0.
