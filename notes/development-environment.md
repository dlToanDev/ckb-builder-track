# Development Environment

## Inspection Results

Inspected on **2026-11-06**, on Linux x86_64 with glibc 2.39. Availability means the
command was found on `PATH` and its version was queried, not that a working chain
or complete application environment was verified.

| Tool | Observed status |
| --- | --- |
| Git | 2.43.0 |
| Node.js | v22.23.2 |
| npm | 10.9.8 |
| pnpm | 11.5.1 |
| Docker CLI | 29.1.3; daemon access and operation not checked |
| Rust / rustc | Not installed or not on PATH |
| Cargo / rustup / cargo-generate | Not installed or not on PATH |
| CKB / ckb-cli / OffCKB | Not installed or not on PATH |
| moleculec / ckb-debugger / ckb-script-verify | Not installed or not on PATH |
| GNU Make | 4.3 |
| Clang / protoc | Not installed or not on PATH |
| Python 3 / markdown-it-py | Available for documentation checks |
| markdownlint / markdownlint-cli2 | Not installed or not on PATH |
| CCC SDK | No project manifest or local dependency installation exists |

No packages were installed, no system configuration was changed, and no services
were started. There is no application or Script implementation to test yet.

## Current Official Tooling

Use [OffCKB](https://docs.nervos.org/docs/sdk-and-devtool/offckb) for a local
chain and [CCC](https://docs.ckbccc.com/en/docs/getting-started/installation) for
TypeScript development. The official OffCKB guide requires Node.js 20 or later;
the installed Node.js satisfies that documented minimum. CCC's current package
guide recommends `@ckb-ccc/shell` for Node.js scripts and backends and
`@ckb-ccc/connector-react` for a React wallet UI.

For Rust Scripts, use the
[Rust Quick Start](https://docs.nervos.org/docs/script/rust/rust-quick-start),
`ckb-std`, maintained `ckb-script-templates`, and `ckb-testtool`. The guide lists
Rust, a RISC-V target, Clang, Make, cargo-generate, and ckb-debugger as prerequisites.
Inspect their current requirements when starting the Rust exercise. Rust setup
changes the user toolchain and is a later manual step; Docker is not required for
the documentation setup.

## Project-Local Installation Plan — Not Executed

Dependency installation is deferred until implementation begins. It is unnecessary
for reading notes or filling reports. The following commands are proposed local
adaptations of official npm instructions; registry resolution, installation, and
CLI execution have **not** been tested in this workspace.

`@offckb/cli` supplies local chain tooling. `@ckb-ccc/shell` supplies Node.js
transaction APIs. `--save-exact` pins the resolved direct versions; commit the
resulting `package-lock.json` after review, and use `npm ci` to reproduce them.
Use one package manager per project. Do not ignore lockfiles or add global packages.

When ready, run from the repository root, only while no `package.json` exists:

```bash
npm init -y
npm pkg set private=true --json
npm pkg set license=MIT
npm pkg set author="HOANG ANH TOAN"
npm view @offckb/cli version engines --json
npm view @ckb-ccc/shell version engines --json
```

Review registry versions and engine requirements against Node.js before installing:

```bash
npm install --save-dev --save-exact @offckb/cli
npm install --save-exact @ckb-ccc/shell
./node_modules/.bin/offckb --version
./node_modules/.bin/offckb --help
```

These steps would create a root tooling manifest and lockfile. Later frontend or
Rust projects may keep their own manifests under their exercise directories.
Keep the generated package private and remove unused generated npm scripts when
adding meaningful ones. Add TypeScript and a runner only when source files need them.

## Start Devnet Manually — Not Executed

After installation, the following is the documented OffCKB node command using the
local executable. It may download binaries and create chain data. It is a future
manual action because starting services requires permission for this setup.

```bash
./node_modules/.bin/offckb node
```

Run it in a foreground terminal and stop it with `Ctrl+C`. Current documentation
uses `http://127.0.0.1:28114` as the debugging proxy and
`http://127.0.0.1:8114` as the direct RPC endpoint. Confirm the actual startup output
before configuring an application. A local chain has no public explorer record.
Use plain account inspection commands; do not print or capture private keys.

For testnet, use development funds and verify the network in both wallet and SDK.
Mainnet use and real spending require explicit owner approval.

## Network and Verification Limits

- Shell command `curl -I -L --max-time 15 https://docs.nervos.org/` failed with
  exit code 6: host DNS resolution was unavailable in the shell sandbox.
- The separate web browsing tool could read official CKB, CCC, Spore, and other
  sources. Link status is recorded in [useful-links.md](../resources/useful-links.md).
- Two exploratory GitHub page reads (the remote learning repository and a possible
  Handbook mirror) returned cache misses. The official Handbook was subsequently
  located through the programme organizer's Nervos Talk report.
- Google Docs exposed only the Handbook title; text export and mobile rendering
  attempts were unavailable. Full Handbook compliance remains manually unverified.
- npm registry connectivity and installability were not tested. Documentation
  availability does not prove package installation will succeed here.
- No blockchain transactions, builds, deployments, or Script tests were executed.
- A dedicated Markdown linter is unavailable; local structural checks can use
  the existing Markdown parser, filesystem checks, and `git diff --check`.
