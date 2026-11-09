# Useful Learning Links

Checked on **2026-11-06** using the web browsing tool. “Verified” means the page
returned readable content at inspection time; it does not certify every downstream
link, code example, current package version, or service. The shell's direct DNS
request failed, so these are browser checks rather than local HTTP checks.

## Core Resources

| Resource | Purpose | Verification |
| --- | --- | --- |
| [Nervos CKB Documentation](https://docs.nervos.org/) | Official concepts, tutorials, and development tools | Verified |
| [CKB Academy](https://academy.ckb.dev/) | Interactive fundamentals | Search-index content verified; direct page body unreadable, interactive availability unverified |
| [CCC SDK](https://docs.ckbccc.com/en/docs/getting-started/introduction) | TypeScript SDK and wallet integration | Verified |
| [CCC installation](https://docs.ckbccc.com/en/docs/getting-started/installation) | Select the appropriate project-local SDK package | Verified |
| [OffCKB](https://docs.nervos.org/docs/sdk-and-devtool/offckb) | Local development chain and tools | Verified |
| [CKB Developer Resources](https://github.com/ckb-devrel) | Official DevRel projects and examples | Verified |
| [Nervos Talk](https://talk.nervos.org/) | Community discussions and technical questions | Verified |
| [CKB Script Development](https://docs.nervos.org/docs/script/intro-to-script) | Lock Scripts, Type Scripts, and execution | Verified |
| [Rust Development on CKB](https://docs.nervos.org/docs/script/rust/rust-quick-start) | Maintained Rust Script workflow | Verified |
| [Script Testing Guide](https://docs.nervos.org/docs/script/script-testing-guide) | Validation strategy and failure cases | Verified |
| [Fiber Network](https://github.com/nervosnetwork/fiber) | Payment channel network and implementation | Verified |
| [Spore Protocol](https://docs.spore.pro/) | Digital objects and protocol documentation | Verified |

Some Academy material still advertises Lumos and Capsule. Use it for concepts and
compare all installation steps with current Nervos and CCC documentation. New
exercises in this repository use CCC and maintained Script tooling.

## CKBuilders Programme and Reporting

| Resource | Purpose | Verification |
| --- | --- | --- |
| [CKBuilders](https://ckbuilders.dev/) | Programme entry point | Landing page retrieved; dynamic details unverified |
| [Community Keeps Building](https://nervoscatalyst.org/community-keeps-building) | Official programme overview | Verified |
| [Catalyst quarterly reports](https://talk.nervos.org/t/nervos-community-catalyst-quarterly-reports/8822) | Organizer's source linking the Handbook and confirming weekly reports | Verified |
| [CKBuilder Handbook](https://docs.google.com/document/d/1aFHXU1ZL1MyIbBAIVRjG6stqdWwPUPyHV90O1QNwY-M/edit?usp=sharing) | Programme expectations and reporting requirements | Official link and document title verified; body and exact reporting requirements unverified |

The [weekly reporting guide](../weekly-reports/README.md) implements the owner's
supplied requirements, including the 4–5 hour weekly planning expectation. Confirm
the Handbook body manually before asserting exact programme compliance. This
repository does not establish CKBuilders admission or funding eligibility.

## Official Exercise Guides

| Exercise | Official guide | Verification |
| --- | --- | --- |
| Transfer CKBytes | [Transfer CKB](https://docs.nervos.org/docs/dapp/transfer-ckb) | Verified |
| Store data | [Store Data on Cell](https://docs.nervos.org/docs/dapp/store-data-on-cell) | Verified |
| Issue fungible tokens | [Create a Fungible Token](https://docs.nervos.org/docs/dapp/create-token) | Verified |
| Create digital objects | [Create a DOB](https://docs.nervos.org/docs/dapp/create-dob) | Verified |
| Implement authorization logic | [Build a Simple Lock](https://docs.nervos.org/docs/dapp/simple-lock) | Verified |

## Fundamentals and Model Comparison

| Resource | Verification |
| --- | --- |
| [How CKB Works](https://docs.nervos.org/docs/getting-started/how-ckb-works) | Verified |
| [Cell Model](https://docs.nervos.org/docs/ckb-fundamentals/cell-model) | Verified |
| [Consensus](https://docs.nervos.org/docs/ckb-fundamentals/consensus) | Verified |
| [Capacity](https://docs.nervos.org/docs/tech-explanation/capacity) | Verified |
| [Transaction structure](https://docs.nervos.org/docs/tech-explanation/transaction) | Verified |
| [CKB-VM](https://docs.nervos.org/docs/ckb-fundamentals/ckb-vm) | Verified |
| [Cardano eUTXO](https://docs.cardano.org/about-cardano/learn/eutxo-explainer) | Verified |
| [Ethereum accounts](https://ethereum.org/developers/docs/accounts/) | Verified |

Recheck the relevant guide before implementation and record the package or tool
versions actually used. Add new links with an inspection date; label inaccessible
pages as unverified rather than assuming they work.
