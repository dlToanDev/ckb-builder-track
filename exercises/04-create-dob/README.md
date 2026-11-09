# 04 — Create a DOB

**Status:** Not Started. No digital object has been created or verified.

## Objective

Explore Spore Protocol by creating and inspecting a digital object on devnet or
testnet. Understand the relationship between content, ownership, protocol rules,
and the capacity occupied by the object.

## Prerequisites

- Understand [Cell data](../02-store-data-on-cell/README.md) and
  [token Type Scripts](../03-create-token/README.md).
- Review the [environment plan](../../notes/development-environment.md).
- Prepare CCC, a development signer, and network-specific Spore dependencies.
- Choose a small public asset you own or have permission to use, with its source
  and license recorded. No generated screenshot or asset is supplied as evidence.

## Official Documentation

- [Create a DOB](https://docs.nervos.org/docs/dapp/create-dob)
- [Spore Protocol](https://docs.spore.pro/)
- [CCC SDK](https://docs.nervos.org/docs/sdk-and-devtool/ccc)

## Implementation Checklist

- [ ] Record versions, network, and selected Spore protocol/SDK compatibility.
- [ ] Identify the public content bytes, content type, size, and usage rights.
- [ ] Read Spore content rules and distinguish a basic Spore from optional DOB extensions.
- [ ] Verify the Spore Type Script and dependencies on the selected network.
- [ ] Estimate occupied capacity from the complete serialized output.
- [ ] Build and inspect the creation transaction with CCC's current Spore support.
- [ ] Submit the transaction and verify commitment and the actual object ID.
- [ ] Query the object Cell and compare its stored content with the original bytes.
- [ ] Transfer the object between development accounts and inspect ownership, if performed.

## Development Instructions

Inspect the official tutorial's current example under `examples/dApp/create-dob`
in the Nervos documentation repository and record the source revision used.
Confirm the installed CCC package's Spore APIs and dependencies before adapting it.

Use the environment plan for local installation and manual devnet startup. Keep
the eventual source in this directory. No SDK integration or creation command is
present or locally tested yet; add commands after verifying your implementation.
Do not substitute an arbitrary data Cell for a protocol-valid digital object.

## Expected Results — Not Yet Observed

A committed transaction creates a protocol-valid Spore with a real object ID,
the intended content type and bytes, the intended ownership lock, and sufficient
capacity. A query retrieves the same content. A transfer changes the ownership
state while respecting the protocol's content rules.

## Evidence Checklist

- [ ] Asset source, usage rights, content type, and actual byte length.
- [ ] Actual versions, network, and Spore deployment references.
- [ ] Real creation hash, object ID, OutPoint, and committed-status query.
- [ ] Read-back comparison with original bytes and observed ownership.
- [ ] Actual transfer evidence if that optional step was performed.
- [ ] Sanitized screenshots, real source links, and weekly report entry.

Use the [reporting guide](../../weekly-reports/README.md). A reference picture or
planned object description is not proof of an on-chain creation.

## Troubleshooting Notes

| Symptom | Investigation |
| --- | --- |
| Creation rejected | Check protocol version, output serialization, and dependencies |
| Capacity estimate too small | Include content, protocol metadata, and script overhead |
| Object cannot be decoded | Verify content type, stored bytes, and SDK compatibility |
| Object absent in public explorer | Check whether the selected chain is local devnet |
| Transfer invalid | Confirm live input, current ownership, and Spore constraints |

Observed errors and resolutions: {{fill only after an actual attempt}}
