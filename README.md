# Pavu

**Understand what your apps are doing—and what deserves your attention.**

Pavu is a local-first, open-source application security project for personal devices. It is being built to make application behavior visible, explain potential risks with evidence, and help people respond without first becoming security experts.

AI agents, browsers, developer tools, and everyday applications can have broad access to files, terminals, and networks. Pavu aims to provide a clearer picture of that activity while keeping collection, analysis, and storage on the device by default.

> **This is the future public home of Pavu.** The source code and full technical documentation have not landed here yet. **Stay tuned.**

**Website:** [pavu.org](https://pavu.org)

## What we are building

- **Observe:** Follow application activity and network connections through clearly defined platform capabilities.
- **Understand:** Turn structured evidence into readable findings instead of presenting raw logs without context.
- **Respond:** Provide practical recommendations and, where platform support permits, user-controlled mitigation paths.
- **Stay private:** Keep core analysis local, minimize collected metadata, and make missing permissions or unavailable evidence visible.

Pavu is designed around deterministic evidence first. Optional AI-assisted explanation must not hide uncertainty, invent missing evidence, or independently enforce security actions.

## Architecture preview

Pavu separates thin platform integrations from a shared analysis core and native user interfaces:

```text
Operating system events
        ↓
Platform collectors
        ↓
Authenticated adapters and transports
        ↓
Shared Rust Core
(normalization, correlation, rules, and local storage)
        ↓
Local API / FFI with Protobuf contracts
        ↓
Native applications and command-line interfaces
```

The intended boundaries are straightforward:

- **Platform collectors** use official operating-system APIs to gather only the facts and health signals the system can actually provide.
- **Pavu Core** owns cross-platform behavior: normalization, application identity, flow aggregation, correlation, baselines, deterministic rules, retention, and local storage.
- **Protobuf contracts** provide a shared language across process and language boundaries.
- **Native UI and CLI layers** communicate with Core through local APIs or FFI rather than duplicating detection logic or directly accessing privileged collectors.
- **Capability and evidence states** distinguish unavailable data from zero activity, so limited coverage is not presented as a clean bill of health.

The architecture is intended to support macOS, Windows, Linux, and Android without pretending that every platform has identical capabilities. Platform availability and release readiness will be documented explicitly as the public implementation lands.

## What will land here

Over time, this repository is intended to contain the shared Core, platform implementations, protocol definitions, native applications, tests, development documentation, and the automation used to validate and release them.

The initial material in this repository prepares that public home: project metadata, contribution automation, and continuous-integration workflows. It is not yet a source release or an installable product.

## Privacy by design

Pavu is being designed not to collect network payloads, TLS plaintext, passwords, cookies, authentication tokens, or file contents, and not to perform TLS interception. Correlation between file and network activity can provide context, but it does not by itself prove that a file's contents were transmitted.

## Stay tuned

Pavu is under active development. Watch this repository and visit **[pavu.org](https://pavu.org)** for future source releases, documentation, and platform announcements.

## License

The project is available under the [Apache License 2.0](LICENSE). Pavu and PavuLabs names and brand assets are not licensed as part of the software license.
