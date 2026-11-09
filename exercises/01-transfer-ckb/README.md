# 01 — Transfer CKB

**Status:** Not Started. This guide contains preparation only; no transfer has been
executed or verified.

## Objective

Understand how a transaction consumes input Cells and creates recipient and change
outputs. Transfer CKBytes on a local development network or testnet using CCC.

## Prerequisites

- Read the [fundamentals](../../notes/ckb-fundamentals.md), especially capacity and transactions.
- Review the [environment plan](../../notes/development-environment.md).
- Prepare project-local OffCKB and the appropriate CCC package when implementing.
- Use development-only accounts and devnet funds or testnet faucet funds.
- Confirm the wallet, client, dependencies, and network agree before signing.

## Official Documentation

- [Transfer CKB](https://docs.nervos.org/docs/dapp/transfer-ckb)
- [CCC installation](https://docs.ckbccc.com/en/docs/getting-started/installation)
- [Transaction structure](https://docs.nervos.org/docs/tech-explanation/transaction)

## Implementation Checklist

- [ ] Record the actual Node.js, package manager, OffCKB, and CCC versions.
- [ ] Configure devnet or testnet explicitly and inspect sender/recipient addresses.
- [ ] Inspect available live Cells and calculate recipient and change capacity.
- [ ] Construct the transfer with CCC, including inputs, dependencies, and fees.
- [ ] Inspect the unsigned transaction before signing with a development account.
- [ ] Submit the transaction and wait for the observed committed status.
- [ ] Query the resulting Cells and reconcile input capacity, outputs, and fee.
- [ ] Try an invalid-capacity case on devnet and record the actual error.

## Development Instructions

No implementation files or dependencies exist yet. Follow the environment plan
before using these commands. From the repository root, after local installation:

```bash
./node_modules/.bin/offckb --version
./node_modules/.bin/offckb --help
```

The command interface is documented in the official OffCKB guide; these invocations
have not been run locally. Starting the node is a separate manual step described
in the environment plan. The official transfer tutorial's example is under
`examples/dApp/simple-transfer` in the Nervos documentation repository. Inspect
its current manifest and record its source revision before using it as a reference.
Keep your own implementation in this directory and preserve upstream attribution
if copying code. Add only commands verified for that implementation afterward.

## Expected Results — Not Yet Observed

A successful ordinary transfer creates the intended recipient Cell and any change
Cell, consumes the selected inputs, and pays the recorded fee from the difference
between total input and output capacity. A returned hash alone does not prove
commitment; query transaction status and inspect outputs.

## Evidence Checklist

- [ ] Actual command, tool versions, date, and selected network/RPC.
- [ ] Real transaction hash and observed status, plus before/after Cell queries.
- [ ] Sanitized screenshot or transcript saved under `screenshots/`.
- [ ] Real source commit link after approved publication, where applicable.
- [ ] Outcome and actual study time linked from the relevant weekly report.

Use local query evidence for devnet; public explorers cannot verify a local chain.
Never publish signing credentials. Follow the [evidence guide](../../weekly-reports/README.md).

## Troubleshooting Notes

| Symptom | Investigation |
| --- | --- |
| Cannot reach RPC | Confirm the manually started node and actual RPC endpoint |
| Insufficient capacity | Check recipient and change occupied capacity plus fees |
| Input already spent | Refresh live Cell selection and rebuild the transaction |
| Signing or dependency error | Confirm signer Lock Script, network, and CellDeps |
| Hash returned, outputs missing | Query status and inspect rejection or pending state |

Observed errors and resolutions: {{fill only after an actual attempt}}
