# Contributing to Itinera

Thank you for your interest. This guide applies to every repository in the itinera-dev organisation unless a repository has its own.

## How Itinera is built

AI is an integral part of how Itinera is made. Agents write code, documentation and specification text, review pull requests, and evaluate and manage issues. This is by design, not an exception.

A human maintainer reviews everything before it is merged. The review asks whether the work is right: whether it does what the specification says, whether it is safe to change, and whether the next person can read it. It reviews the work, not its author, and it does not mark work down for being written differently from how the reviewer would have written it. Work that is right is used, whether a person or a machine produced it. Work that is not right is not merged, whoever produced it.

The maintainer who merges answers for what is merged, whatever wrote it.

These are the terms of [A manifesto for software engineering with AI](https://marlon-sousa.com/blog/manifesto/), written by Itinera's maintainer, in particular its commitments 1 (what is live is mine, whatever wrote it), 11 (stay able to judge what the machine produces), 12 (judge code by whether it works, not by whether it is mine) and 13 (the machine does not lower the bar on who can use the result).

### What this means for contributors

By opening an issue or a pull request in any itinera-dev repository, you accept these terms:

- You may write your contribution with AI, without it, or both. Every contribution is reviewed the same way.
- You have read what you submit and you answer for it, whatever wrote it.
- Your contribution will be judged by whether it is right, not by who or what produced it.
- Agents working in these repositories may read, evaluate and comment on your issues and pull requests, always on a maintainer's request and always marked as an agent's comment.

## Where to start

- **A change to how Itinera behaves** is a proposal. Open a Proposal issue in [itinera-dev/spec](https://github.com/itinera-dev/spec/issues/new/choose). Most features are proposals, because every language implementation must follow them.
- **A bug or API question in one implementation** goes to that implementation's repository, for example [itinera-dev/itinera-rs](https://github.com/itinera-dev/itinera-rs/issues).
- **A missing or wrong conformance case** goes to [itinera-dev/conformance](https://github.com/itinera-dev/conformance/issues).

The full process, from proposal to implementation, is in [PROCESS.md](https://github.com/itinera-dev/spec/blob/main/PROCESS.md).

## The three kinds of document

Every feature is described by three documents:

1. **The proposal, a PRD:** why the feature exists and what is wanted. Discussed in an issue in [itinera-dev/spec](https://github.com/itinera-dev/spec) and kept there once accepted. Never specific to a language.
2. **The behaviour specification:** exactly what every implementation must do, in terms the conformance suite can observe. Kept in [itinera-dev/spec](https://github.com/itinera-dev/spec). Never specific to a language.
3. **The tech spec:** how one language implements a proposal. Agreed in that language's implementation issue and kept next to the code, under `docs/specs/` in that language's repository.

If the conformance suite could observe something, it belongs in the behaviour specification. If it is about how code is written in one language, it belongs in that language's tech spec. When we say "the spec" on its own, we mean the behaviour specification.

## Please do not open a pull request before the spec exists

If you have an idea for a feature, and even an idea of how to implement it, please start with a Proposal issue and wait. Do not open an implementation pull request until the proposal has been accepted and its spec has been merged.

- **Put your implementation ideas in the issue.** Describe how you would do it, sketch the code if that helps. Those ideas are welcome and will be weighed during the evaluation.
- **The spec comes first because the architecture is global.** Every feature has to fit the specification, every tier, every language and every executor. The maintainers, working with agents across all of it, are best placed to see how a feature fits the whole, and the agreed spec may end up different from what any single implementation idea assumed.
- **After the spec is merged, implementation is open to everyone,** including you. Each accepted proposal gets an implementation issue in every language repository. Say in that issue that you would like to take it, and follow the spec and the existing architecture.

A pull request opened before its proposal is accepted may be closed, with a pointer to the issue, however good the code is. Nothing is lost: the ideas move to the issue, and the code can come back once the spec exists.

## Pull requests

- Behaviour is specified before it is implemented. A pull request that changes behaviour in an implementation must point to the accepted proposal it implements and to its implementation issue.
- Keep pull requests focused on one thing.
- Say what changed and why in the description, in plain prose.

## Writing style

Everything we write must be readable with a screen reader: documentation, issues, pull requests and comments. Use headings, lists, prose and simple tables.

Diagrams are Mermaid diagrams, in fenced code blocks marked `mermaid`, which GitHub renders. Every diagram declares `accTitle` and `accDescr`, which are exposed to screen readers, and is accompanied by text that says everything the diagram shows. Do not use ASCII-art diagrams, arrows drawn with characters, or box-drawing trees.

## Licence

Unless you explicitly state otherwise, any contribution intentionally submitted for inclusion in the work by you, as defined in the Apache-2.0 licence, shall be dual licensed under MIT and Apache-2.0, without any additional terms or conditions.
