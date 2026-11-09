# 05 — Simple Lock

**Status:** Not Started. No Script has been implemented, built, tested, or deployed.

## Objective

Understand Lock Script validation by implementing a basic authorization condition
and verifying both acceptance and rejection cases. Use devnet or offline tests
before considering testnet.

## Prerequisites

- Understand [transactions and Script roles](../../notes/ckb-fundamentals.md).
- Review the [environment inspection](../../notes/development-environment.md).
- For the Rust path, prepare Rust/Cargo, the appropriate RISC-V target, Clang,
  Make, cargo-generate, ckb-std, ckb-testtool, and ckb-debugger as required by the guide.
- Prepare OffCKB and CCC only when testing an actual on-chain spending flow.
- Read the template's build instructions before installing additional system tools.

## Official Documentation

- [Build a Simple Lock](https://docs.nervos.org/docs/dapp/simple-lock)
- [Intro to Script](https://docs.nervos.org/docs/script/intro-to-script)
- [Rust Quick Start](https://docs.nervos.org/docs/script/rust/rust-quick-start)
- [Script Testing Guide](https://docs.nervos.org/docs/script/script-testing-guide)

The simple-lock dApp tutorial uses JavaScript/TypeScript on ckb-js-vm. This exercise
plans a Rust implementation using the separate official Rust workflow; the dApp
tutorial is a behavioral reference. Do not assume their scaffolds or build commands
are interchangeable.

## Implementation Checklist

- [ ] Choose and document a precise authorization rule, argument format, and witness format.
- [ ] Record toolchain versions and the maintained template revision.
- [ ] Create a Rust project from ckb-script-templates using the official guide.
- [ ] Implement argument/witness parsing and reject malformed or missing values.
- [ ] Implement the intended condition with explicit success and failure codes.
- [ ] Build for the supported CKB RISC-V target and record the actual artifact.
- [ ] Use ckb-testtool to verify a valid spend, invalid proof, missing witness,
  malformed arguments, and multiple inputs sharing the same Lock Script group.
- [ ] Record actual errors and cycles; confirm a failure occurs for the intended reason.
- [ ] Deploy only to devnet initially and record the actual code Cell OutPoint and CellDep.
- [ ] Fund a development-only locked Cell, then verify accepted and rejected spending flows.

## Development Instructions

After the Rust prerequisites are available, the following commands follow the
official Rust Quick Start. They are **source-checked, not locally executed**.
Run them from this exercise directory; they create a new `simple-lock` workspace.

```bash
cargo generate gh:cryptape/ckb-script-templates workspace --name simple-lock
cd simple-lock
make generate CRATE=simple-lock
```

Implement the rule and meaningful tests before running the generated project's
build and test commands from inside that workspace:

```bash
make build
make test
```

Record the resolved template commit and lockfile; inspect the generated Makefile
and confirm these commands still apply before running. Template compilation alone
does not prove authorization logic is correct. Add devnet deployment and spending
commands only after verifying the actual binary, dependencies, and network setup.

If using the tutorial's educational hash-preimage rule, use a disposable public
test value. Revealing a preimage makes it public and proves knowledge rather than
identity; this example must never protect real funds. Do not use real passwords,
wallet secrets, or a personal authentication secret.

## Expected Results — Not Yet Observed

A correctly authorized transaction passes validation; unauthorized and malformed
cases fail with the expected reason. On devnet, a valid spend consumes the locked
Cell and creates intended outputs; rejection leaves that Cell unspent. Deployment
alone is insufficient because output Lock Scripts do not execute at Cell creation.

## Evidence Checklist

- [ ] Source, chosen rule, actual template revision, and toolchain versions.
- [ ] Real build command, artifact path, and observed output.
- [ ] Actual positive and negative test output, commands, date, and cycle results.
- [ ] If deployed: actual network, code OutPoint, CellDep, and transaction hashes.
- [ ] Actual accepted spend and rejected attempt, with queried Cell states.
- [ ] Sanitized screenshots, real published source links, and weekly report entry.

Follow the [evidence guide](../../weekly-reports/README.md). Test results remain
unfilled until execution; a generated test is not evidence that a test passed.

## Troubleshooting Notes

| Symptom | Investigation |
| --- | --- |
| Rust or target unavailable | Recheck toolchain prerequisites; do not install unrelated global tools |
| Contract binary missing | Inspect generated build rules and target configuration |
| Script cannot be loaded | Confirm code OutPoint, CellDep, hash type, and network |
| Valid proof rejected | Check serialization, witness indexing, and Script group context |
| Invalid proof accepted | Review the rule and tests before any further deployment |
| Test fails unexpectedly | Check the error reason; avoid mistaking missing dependencies for authorization rejection |

Observed errors and resolutions: {{fill only after an actual attempt}}
