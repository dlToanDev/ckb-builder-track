# CKB Fundamentals

**Learning status:** Not Started. The reference explanations below are preparatory
summaries of official documentation, not personal study results. Personal notes and
practical observations remain unfilled.

## Reference Explanations from Official Documentation

### What is Nervos CKB?

Nervos Common Knowledge Base (CKB) is the Nervos Layer 1 blockchain for storing and
verifying shared state. CKByte (CKB) is its native asset. Applications construct
proposed state transitions off-chain, and nodes verify their validity on-chain.

Source: [How CKB Works](https://docs.nervos.org/docs/getting-started/how-ckb-works).

### Proof of Work Consensus

CKB uses Proof of Work with NC-Max consensus and the Eaglesong hash function.
NC-Max separates transaction proposal from commitment to improve propagation.
Inclusion in a block and confidence after subsequent confirmations are distinct;
applications must account for possible reorganizations.

Source: [Consensus](https://docs.nervos.org/docs/ckb-fundamentals/consensus).

### Cell Model

A Cell is an immutable unit of state in CKB's generalized UTXO model. An unspent
Cell is live. A transaction consumes live Cells and creates new Cells. Consumed
Cells become dead and cannot be consumed again. Updating application data means
creating a replacement Cell through a valid transaction.

Source: [Cell Model](https://docs.nervos.org/docs/ckb-fundamentals/cell-model).

### Capacity

Capacity is both a Cell's CKByte amount and its storage allowance. One CKByte
corresponds to one byte of occupied state; one CKB equals 100,000,000 shannons.
Capacity must cover the Cell's capacity field, Lock Script, optional Type Script,
and data. Calculate occupied capacity for each output rather than assuming a
single minimum applies to all Cells.

Source: [Capacity](https://docs.nervos.org/docs/tech-explanation/capacity).

### Cell Data

Cell data consists of arbitrary bytes. In a transaction, `outputs_data` supplies
the data for the corresponding entries in `outputs`. Application protocols define
serialization and meaning; scripts can enforce those rules. A human-readable
string still needs an explicit byte encoding.

Sources: [Transaction structure](https://docs.nervos.org/docs/tech-explanation/transaction)
and [Store Data on Cell](https://docs.nervos.org/docs/dapp/store-data-on-cell).

### Lock Scripts

A Lock Script controls the conditions for consuming a Cell. Input Lock Scripts
execute during validation; output Lock Scripts do not execute simply because a
Cell is created. A signature check is one possible authorization rule.

Source: [Intro to Script](https://docs.nervos.org/docs/script/intro-to-script).

### Type Scripts

A Cell may also have a Type Script to constrain valid state transitions, such as
token issuance or conservation. Type Scripts on both inputs and outputs participate
in validation. A Script is described by `code_hash`, `hash_type`, and `args`;
transaction dependencies provide access to the referenced executable code.

Source: [Intro to Script](https://docs.nervos.org/docs/script/intro-to-script).

### CKB-VM

CKB-VM executes validation programs compiled for its supported RISC-V environment.
Execution is deterministic and bounded by cycle limits. Scripts inspect transaction
context through syscalls. A successful program returns zero; a failing required
Script makes the transaction invalid.

Sources: [CKB-VM](https://docs.nervos.org/docs/ckb-fundamentals/ckb-vm)
and [Intro to Script](https://docs.nervos.org/docs/script/intro-to-script).

### RISC-V

RISC-V is an instruction set architecture, not a smart contract language. Rust can
compile to the supported target; CKB-VM executes that resulting machine code.
The target, VM version, runtime support, and syscalls must match the network.

Sources: [CKB-VM](https://docs.nervos.org/docs/ckb-fundamentals/ckb-vm)
and [Rust Quick Start](https://docs.nervos.org/docs/script/rust/rust-quick-start).

### Transaction Inputs and Outputs

Inputs refer to previous outputs through OutPoints: a transaction hash plus output
index. Outputs describe replacement Cells, with matching `outputs_data` entries.
Dependencies make code or other referenced data available without consuming those
Cells. Witnesses carry supporting validation data, such as signatures. For an
ordinary transfer, the difference between input and output capacity pays the fee.

Source: [Transaction](https://docs.nervos.org/docs/tech-explanation/transaction).

### CKB, Cardano eUTXO, and Ethereum Accounts

This comparison summarizes the linked primary documentation; the models are not
interchangeable, even when they support similar applications.

| Aspect | CKB Cell Model | Cardano eUTXO | Ethereum accounts |
| --- | --- | --- | --- |
| State unit | Live Cells with capacity, data, Lock Script, and optional Type Script | Unspent outputs with value and optional datum associated with validation | Accounts with balance and nonce; contracts also have code and storage |
| State transition | Consume Cells and create replacements | Consume outputs and create replacements | Execute a transaction that updates account state |
| Validation model | Input Lock Scripts and input/output Type Scripts | Spending validators and minting policies | Contract execution in the EVM |
| Asset representation | CKBytes plus protocol-defined token Cells | ADA and native multi-assets in outputs | ETH balances and contract-defined token state |
| Storage consideration | Occupied capacity must fit each Cell | Minimum ADA requirements apply to outputs | Storage operations incur gas costs |

Sources: [CKB Cell Model](https://docs.nervos.org/docs/ckb-fundamentals/cell-model),
[Cardano Extended UTXO model](https://docs.cardano.org/about-cardano/learn/eutxo-explainer),
and [Ethereum accounts](https://ethereum.org/developers/docs/accounts/).

## Personal Learning Notes — To Be Completed by the Author

- Date and source actually studied: {{to be filled}}
- My explanation of the Cell lifecycle: {{to be filled}}
- What transfers from my Cardano development experience: {{to be filled}}
- Assumptions from Ethereum that I need to revisit: {{to be filled}}
- My understanding of Lock versus Type Scripts: {{to be filled}}
- Links to my genuine exercises and weekly reports: {{to be filled}}

## Practical Examples — Reference Only, Not Executed

### Capacity calculation on paper

Consider a Cell with an 8-byte capacity field, a Lock Script containing a 32-byte
code hash, a 1-byte hash type, and 20 bytes of arguments, no Type Script, and empty
data. Its occupied capacity is `8 + 32 + 1 + 20 = 61` bytes, requiring 61 CKB.
Adding a five-byte UTF-8 payload makes the occupied capacity 66 bytes. Other script
layouts produce different requirements. This calculation is not a transaction or
an instruction to transfer that amount; the transaction must also cover fees and
any change output's occupied capacity.

Source: [Capacity](https://docs.nervos.org/docs/tech-explanation/capacity).

### State transition on paper

An application can propose consuming a live Cell holding text version A and
creating one with version B. It must satisfy the input's Lock Script and applicable
Type Script rules. The original Cell becomes dead only when the transaction is
committed. No actual Cell or transaction hash exists for this illustration.

Source: [Cell Model](https://docs.nervos.org/docs/ckb-fundamentals/cell-model).

### Hands-on work to perform later

- [ ] Inspect a real transfer's inputs, outputs, data, witnesses, and dependencies.
- [ ] Calculate occupied capacity and compare it with a CCC-generated output.
- [ ] Store and retrieve a public UTF-8 message on devnet.
- [ ] Record an actual failed validation and explain the cause.

Record commands, tool versions, network, and observed results only after execution.
Start with [Transfer CKB](../exercises/01-transfer-ckb/README.md).

## Questions Requiring Further Study

- How does NC-Max's proposal window affect an application's confirmation handling?
- How do Script groups determine which validation programs execute?
- How do `hash_type` and VM versions affect code resolution and execution?
- How should an application handle a dead input or a chain reorganization?
- How do xUDT rules distinguish issuance from ordinary transfers?
- How do Cell capacity requirements compare with Cardano minimum ADA and EVM gas?
- Which wallet integration patterns fit identity applications on CKB?

For each question, add an answer, primary source, and reproducible example after
investigation. See [useful links](../resources/useful-links.md).
