# 02 — Store Data on Cell

**Status:** Not Started. No data Cell has been created or verified.

## Objective

Store a small public message in a CKB Cell, retrieve its bytes, and understand
encoding, occupied capacity, and immutable state transitions.

## Prerequisites

- Understand the [transfer exercise](../01-transfer-ckb/README.md) transaction flow.
- Review [Cell data and capacity](../../notes/ckb-fundamentals.md).
- Prepare the [local development environment](../../notes/development-environment.md).
- Use a development signer with sufficient devnet or testnet capacity.
- Choose harmless public text; never store secrets on-chain.

## Official Documentation

- [Store Data on Cell](https://docs.nervos.org/docs/dapp/store-data-on-cell)
- [Capacity](https://docs.nervos.org/docs/tech-explanation/capacity)
- [Cell Model](https://docs.nervos.org/docs/ckb-fundamentals/cell-model)

## Implementation Checklist

- [ ] Record package versions, network, and RPC endpoint.
- [ ] Choose a short message and explicitly encode it as UTF-8 bytes.
- [ ] Calculate occupied capacity including script fields and the payload.
- [ ] Build a CCC transaction with matching `outputs` and `outputs_data` entries.
- [ ] Inspect outputs, change, fees, and data before signing.
- [ ] Submit on devnet or testnet and verify commitment.
- [ ] Retrieve the output by its actual OutPoint and decode the stored bytes.
- [ ] Compare the retrieved bytes and decoded text with the original message.
- [ ] Consume the Cell and create a replacement to demonstrate a data update.

## Development Instructions

Follow the official tutorial and inspect its example at
`examples/dApp/store-data-on-cell` in the Nervos documentation repository.
Record the source revision and dependency versions used. Develop your own source
in this exercise directory; no runnable application is present yet.

Use the environment plan for project-local packages and manual devnet startup.
The official guide documents encoding text to bytes and reading it back; no
transaction commands or application scripts have been executed for this exercise.
Add installation, run, and query commands here only after checking them against
your actual implementation. Keep any private configuration in ignored local files.

## Expected Results — Not Yet Observed

A committed output contains exactly the chosen bytes and enough capacity for its
fields. Decoding reproduces the message. An update consumes the original Cell
and creates a new one; it does not mutate the original output in place.

## Evidence Checklist

- [ ] Original public text, encoding, hex payload, and byte length.
- [ ] Actual capacity calculation and output fields.
- [ ] Real transaction hash, output index, network, and committed-status query.
- [ ] Retrieved bytes and a recorded equality check.
- [ ] Actual update transaction and before/after live Cell state, if performed.
- [ ] Sanitized screenshots, real published source links, and weekly report entry.

Follow the [evidence guide](../../weekly-reports/README.md). Keep all result fields
unfilled until execution.

## Troubleshooting Notes

| Symptom | Investigation |
| --- | --- |
| Capacity validation fails | Count payload bytes and script overhead for each output |
| Decoding differs | Check UTF-8 encoding, hex conversion, and selected output index |
| Retrieved data empty | Confirm the corresponding `outputs_data` entry was included |
| Cell no longer live | Check whether a later transaction consumed it |
| Cannot find old devnet output | Check whether the local chain was reset |

Observed errors and resolutions: {{fill only after an actual attempt}}
