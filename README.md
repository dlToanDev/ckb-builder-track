# 🛠️ CKBuilders Learning Journey

A practical learning repository by **HOANG ANH TOAN** for exploring Nervos CKB,
recording weekly progress, and building applications through reproducible exercises.
This repository documents a personal learning plan; it does not assert official
acceptance into the CKBuilders programme.

**Current status:** Repository prepared. All learning weeks and exercises are
**Not Started**. Templates and reference material are preparation, not evidence of
completed study.

## 👋 About Me

I am **HOANG ANH TOAN** ([dlToanDev](https://github.com/dlToanDev)), a blockchain
developer with over two years of experience developing smart contracts and dApps
across Cardano and Ethereum, including wallet integration and decentralized identity.
I also have one year of experience building AI-powered applications using LLM APIs,
AI automation, and backend AI integration.

This journey extends that experience to CKB's Cell Model, transaction construction,
Script development, and application ecosystem.

## 🎯 Learning Objectives

- Understand CKB's Proof of Work consensus, Cells, capacity, and transaction lifecycle.
- Compare CKB's model with Cardano eUTXO and Ethereum accounts.
- Build transactions and integrate wallets using the CCC TypeScript SDK.
- Explore fungible tokens and Spore digital objects on devnet or testnet.
- Develop and test basic Scripts using maintained tools and Rust resources.
- Keep an honest, evidence-based record of learning and development.

## 🗺️ Learning Roadmap

This ten-week plan is a personal roadmap, not an official programme syllabus.
Plan for at least **4–5 hours each week**, recording actual time even when it falls
short. Dates begin when study actually starts. Update statuses only after doing
the work; completion requires supporting evidence.

| Week | Focus | Planned output | Status |
| --- | --- | --- | --- |
| 01 | CKB fundamentals and environment review | [Fundamentals notes](notes/ckb-fundamentals.md) and [Week 1 report](weekly-reports/week-01.md) | Not Started |
| 02 | Cells, capacity, inputs, outputs, and fees | Annotated transaction and capacity calculations | Not Started |
| 03 | CCC and CKByte transfers | [Transfer exercise](exercises/01-transfer-ckb/README.md) | Not Started |
| 04 | Cell data and state transitions | [Store data exercise](exercises/02-store-data-on-cell/README.md) | Not Started |
| 05 | Token standards and issuance rules | [Fungible token exercise](exercises/03-create-token/README.md) | Not Started |
| 06 | Spore Protocol and digital objects | [DOB exercise](exercises/04-create-dob/README.md) | Not Started |
| 07 | Lock Scripts, Type Scripts, CKB-VM, and Rust | Toolchain setup and Script design notes | Not Started |
| 08 | Script implementation and testing | [Simple Lock exercise](exercises/05-simple-lock/README.md) with positive and negative cases | Not Started |
| 09 | Wallet integration and application design | Small CCC application prototype | Not Started |
| 10 | Application validation and documentation | Reproducible demo, evidence, and next development plan | Not Started |

## 📝 Weekly Learning Reports

Follow the [reporting guide](weekly-reports/README.md) and complete the
[unfilled Week 1 template](weekly-reports/week-01.md) using real activities,
actual hours, and verifiable evidence. Publish one report each week; do not generate
personal experiences or batch reports after several weeks.

| Report | Reporting period | Study hours | Status |
| --- | --- | --- | --- |
| [Week 01](weekly-reports/week-01.md) | To be filled | To be filled | Not Started |

Add future report files and links when each reporting week begins. AI may help
edit wording after the author provides the underlying facts.

## ⚙️ Technical Focus

| Area | Focus |
| --- | --- |
| CKB architecture | Cell Model, capacity, Proof of Work, transaction validation |
| TypeScript | CCC clients, signers, transaction composition, wallet integration |
| On-chain Scripts | Lock and Type Scripts, Rust, CKB-VM, RISC-V, validation tests |
| Assets | xUDT token issuance and Spore digital objects |
| Development workflow | OffCKB devnet, testnet, reproducible dependencies, evidence |
| Future exploration | Decentralized identity, AI-assisted tooling, Fiber payments |

Use CCC and maintained Script templates for new work. Some older learning material
references Lumos or Capsule; do not adopt those tools for these exercises.

### Development environment

See [environment status and setup instructions](notes/development-environment.md).
No dependencies have been installed and no services have been started for this
repository. Installation commands are future steps, not verified local executions.

Use local devnet or testnet with development funds. Keep credentials out of source,
logs, screenshots, and reports. Mainnet use or spending real funds requires explicit
approval. Commits and pushes also require the repository owner's explicit approval.

## 📂 Repository Structure

```text
ckb-builder-track/
├── README.md
├── LICENSE
├── .gitignore
├── weekly-reports/
│   ├── README.md
│   └── week-01.md
├── exercises/
│   ├── 01-transfer-ckb/
│   │   ├── README.md
│   │   └── .gitkeep
│   ├── 02-store-data-on-cell/
│   │   ├── README.md
│   │   └── .gitkeep
│   ├── 03-create-token/
│   │   ├── README.md
│   │   └── .gitkeep
│   ├── 04-create-dob/
│   │   ├── README.md
│   │   └── .gitkeep
│   └── 05-simple-lock/
│       ├── README.md
│       └── .gitkeep
├── screenshots/
│   └── .gitkeep
├── notes/
│   ├── ckb-fundamentals.md
│   └── development-environment.md
└── resources/
    └── useful-links.md
```

The existing exercise `.gitkeep` files are preserved. Store real evidence in
`screenshots/` and link it from the relevant exercise and report.

## 📚 Learning Resources

- [Nervos CKB Documentation](https://docs.nervos.org/) — official concepts and tutorials.
- [CKB Academy](https://academy.ckb.dev/) — interactive fundamentals; check tooling references against current docs.
- [CCC SDK](https://docs.ckbccc.com/en/docs/getting-started/introduction) — current TypeScript SDK documentation.
- [OffCKB](https://docs.nervos.org/docs/sdk-and-devtool/offckb) — local development environment.
- [CKBuilder Handbook](https://docs.google.com/document/d/1aFHXU1ZL1MyIbBAIVRjG6stqdWwPUPyHV90O1QNwY-M/edit?usp=sharing) — official programme reference; reporting details require manual confirmation because its body was not readable during setup.

See the [resource directory](resources/useful-links.md) for Script development,
Spore, Fiber, community links, and verification details.

## 🌱 Long-Term Goals

- Build a useful CKB application with documented design and tested transaction flows.
- Apply existing wallet and identity experience to CKB integrations.
- Explore where AI tooling can improve developer workflows while keeping on-chain
  validation deterministic and personal progress reports factual.
- Contribute reproducible examples, documentation improvements, and fixes upstream.

## 📄 License

Licensed under the [MIT License](LICENSE).
Copyright (c) 2026 HOANG ANH TOAN.
