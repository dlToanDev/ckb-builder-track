# 03 — Create a Fungible Token

**Status:** Not Started. No token issuance or transfer has been executed.

## Objective

Explore CKB token standards by issuing and transferring an xUDT token on devnet
or testnet. Distinguish token quantities, Cell capacity, and issuance authority.

## Prerequisites

- Understand the [transfer](../01-transfer-ckb/README.md) and
  [data storage](../02-store-data-on-cell/README.md) flows.
- Review [Type Scripts](../../notes/ckb-fundamentals.md) and the
  [environment plan](../../notes/development-environment.md).
- Prepare CCC and confirm xUDT script deployment information for the selected network.
- Use development accounts and sufficient capacity for token Cells and fees.

## Official Documentation

- [Create a Fungible Token](https://docs.nervos.org/docs/dapp/create-token)
- [CCC SDK](https://docs.nervos.org/docs/sdk-and-devtool/ccc)
- [Intro to Script](https://docs.nervos.org/docs/script/intro-to-script)

## Implementation Checklist

- [ ] Read the tutorial's linked xUDT specification and record the chosen variant.
- [ ] Record tool versions, network, and actual xUDT code/dependency references.
- [ ] Define development-only token metadata and integer quantity representation.
- [ ] Identify the issuer authorization rule and derive script arguments from the spec.
- [ ] Build and inspect an issuance transaction with sufficient Cell capacity.
- [ ] Submit issuance and verify the committed token Cell and decoded quantity.
- [ ] Transfer a quantity to another development account and verify conservation.
- [ ] Test an unauthorized issuance or quantity-inflation attempt on devnet.
- [ ] Explain differences from Cardano native assets and Ethereum ERC-20 accounting.

## Development Instructions

The official tutorial uses xUDT and provides its example under
`examples/dApp/xudt` in the Nervos documentation repository. Inspect that source
and its exact dependency versions before implementation. Follow its linked
standard rather than guessing argument layout, token encoding, or network hashes.

Use the project-local setup in the environment plan. Implement the transaction
flow in this directory, retaining attribution for reused code. No issuance program,
package manifest, token deployment, or run command exists here yet. Document actual
commands only after verifying the chosen CCC version and network configuration.

## Expected Results — Not Yet Observed

Authorized issuance creates token Cells with the correct Type Script and encoded
quantity. Ordinary transfers preserve token amounts across inputs and outputs
according to the chosen standard, while CKByte capacity independently covers
storage and fees. An unauthorized mint or inflation attempt is rejected.

## Evidence Checklist

- [ ] Chosen standard, source revision, versions, and network deployment information.
- [ ] Actual issuer rule, full public Type Script, and token identity.
- [ ] Real issuance and transfer hashes with committed-status queries.
- [ ] Decoded quantities and reconciled balances before and after transfer.
- [ ] Actual negative-case command and observed error.
- [ ] Sanitized screenshots, published source links, and weekly report entry.

Record actual results through the [reporting guide](../../weekly-reports/README.md).
Do not publish signing credentials or claim a planned token has been issued.

## Troubleshooting Notes

| Symptom | Investigation |
| --- | --- |
| Type Script cannot load | Check code hash, hash type, CellDep, and active network |
| Issuance rejected | Check issuer authorization and argument layout against the spec |
| Token amount appears wrong | Check integer units and encoding; avoid floating-point math |
| Transfer breaks conservation | Decode all token inputs and outputs, including change |
| Adequate tokens, insufficient capacity | Fund Cell capacity and transaction fees separately |

Observed errors and resolutions: {{fill only after an actual attempt}}
