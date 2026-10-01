# Contributing to Itinera

Thank you for your interest. This guide applies to every repository in the itinera-dev organisation unless a repository has its own.

## Where to start

- **A change to how Itinera behaves** is a proposal. Open a Proposal issue in [itinera-dev/spec](https://github.com/itinera-dev/spec/issues/new/choose). Most features are proposals, because every language implementation must follow them.
- **A bug or API question in one implementation** goes to that implementation's repository, for example [itinera-dev/itinera-rs](https://github.com/itinera-dev/itinera-rs/issues).
- **A missing or wrong conformance case** goes to [itinera-dev/conformance](https://github.com/itinera-dev/conformance/issues).

The full process, from proposal to implementation, is in [PROCESS.md](https://github.com/itinera-dev/spec/blob/main/PROCESS.md).

## Pull requests

- Behaviour is specified before it is implemented. A pull request that changes behaviour in an implementation must point to the accepted proposal it implements.
- Keep pull requests focused on one thing.
- Say what changed and why in the description, in plain prose.

## Writing style

Everything we write must be readable with a screen reader: documentation, issues, pull requests and comments. Use headings, lists, prose and simple tables. Do not use ASCII-art diagrams, arrows drawn with characters, or box-drawing trees; describe a flow as a numbered list instead.

## Licence

Unless you explicitly state otherwise, any contribution intentionally submitted for inclusion in the work by you, as defined in the Apache-2.0 licence, shall be dual licensed under MIT and Apache-2.0, without any additional terms or conditions.
