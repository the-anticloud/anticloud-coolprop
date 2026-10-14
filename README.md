# COOLPROP

![license](https://img.shields.io/badge/license-MIT-blue) ![offline-first](https://img.shields.io/badge/offline--first-air--gap-green) ![audit](https://img.shields.io/badge/audit-SHA3--256-orange) ![category](https://img.shields.io/badge/category-chemical_production-lightgrey)

> Anticloud-hardened packaging of the upstream project `COOLPROP` in category **CHEMICAL PRODUCTION**. Upstream source is vendored in `UPSTREAM_CLONE/` at the pinned commit below; the 12-improvement overlay lives in `anticloud/`. Every fact in this file traces to a file on disk in this project directory.

**Category:** CHEMICAL PRODUCTION · **Upstream:** https://github.com/CoolProp/CoolProp · **Upstream pin:** `bb8f87931ec62b59a4e4dd6e38c1f5925ea5e7c0` · **Vendor:** Anticloud FZ LLE

---

## What This Project Does

# Welcome to CoolProp

CoolProp is a thermophysical property database and wrappers for a selection of programming environments.
It offers similar functionality to REFPROP, but CoolProp is open-source and free.
It was originally developed by Ian Bell, at the time a post-doc at the University of Liege, in Liege, Belgium.

* CoolProp has flexible licensing terms: Commercial - ok! Academic? - ok! [![license](https://img.shields.io/github/license/CoolProp/CoolProp.svg)](https://github.com/CoolProp/CoolProp/blob/master/LICENSE)

* For Python, get the latest release via `pip install coolprop` [![PyPI downloads](https://img.shields.io/pypi/dm/CoolProp.svg?label=PyPI-downloads)](https://pypi.org/project/CoolProp/) [![PyPI version](https://img.shields.io/pypi/v/coolprop.svg?label=PyPI-binaries)](https://pypi.org/project/CoolProp/)

* ... other binaries are available from [SourceForge](https://sourceforge.net/projects/coolprop/files) [![sourceforge downloads](https://img.shields.io/sourceforge/dm/CoolProp.svg?label=SF-downloads)](https://sourceforge.net/projects/coolprop/files) ![CoolProp version tag](https://img.shields.io/github/release/CoolProp/CoolProp.svg?label=SF-binaries)

* There is also a bleeding edge nightly build of the [development version](https://sourceforge.net/projects/coolprop/files/CoolProp/nightly).

* The documentation is available for the [latest release](https://www.coolprop.org) and the [development version](https://coolprop.github.io/devdocs/)

* For any kind of question regarding CoolProp and its usage, you can ask the [CoolProp Discussions](https://github.com/CoolProp/CoolProp/discussions)

* ... you might also find answers in our [FAQ](https://github.com/CoolProp/CoolProp/blob/master/FAQ.md)

* If you found a bug or have an issue that requires the developers to become active, please file an issue in our [issue tracker](https://github.com/CoolProp/CoolProp/issues)

* [Contributions](https://github.com/CoolProp/CoolProp/blob/master/.github/CONTRIBUTING.md) to this project are welcomed and encouraged! If you wish to [contribute](https://github.com/CoolProp/CoolProp/blob/master/.github/CONTRIBUTING.md) bug fixes, patches, or new features, wrappers, or material properties, please submit a Pull Request with your code.

* If you are new to Git and Github, please see the [CoolProp Wiki](https://github.com/CoolProp/CoolProp/wiki) for guidance on becoming a contributor to the project.

## CMake package

CoolProp can build and install static and shared libraries independently or in
the same build:

```sh
cmake -S . -B build \
  -DCOOLPROP_STATIC_LIBRARY=ON \
  -DCOOLPROP_SHARED_LIBRARY=ON
cmake --build build --config Release
cmake --install build --config Release --prefix /path/to/prefix
```

An installed package is consumed through imported targets, without manually
adding include directories or platform libraries:

```cmake
find_package(CoolProp 8 CONFIG REQUIRED)
target_link_libraries(my_app PRIVATE CoolProp::CoolProp)
```

When CoolProp is configured with both variants, the producer-side
`COOLPROP_DEFAULT_LIBRARY` cache setting chooses which variant is exported
through `CoolProp::CoolProp` (`SHARED` by default). This choice is recorded in
the installed package and cannot be changed by a package consumer. Consumers
that require explicit linkage should use `CoolProp::Static` or
`CoolProp::Shared`. Separate consumer targets may select different variants,
but one final binary must not link both variants.
On Windows, the portable shared-library interface is the C API from
`CoolProp/CoolPropLib.h`; use the static target for the complete C++ API.

Source-tree consumers can use the same canonical target:

```cmake
set(COOLPROP_STATIC_LIBRARY ON CACHE BOOL "" FORCE)
add_subdirectory(externals/CoolProp)
target_link_libraries(my_app PRIVATE CoolProp::CoolProp)
```

Nested builds add no CoolProp install rules by default. A parent project that
intentionally packages CoolProp can enable `COOLPROP_INSTALL_CMAKE_PACKAGE`
and/or `COOLPROP_INSTALL_LEGACY_LAYOUT` before calling `add_subdirectory`.

By default, `COOLPROP_VENDOR_THIRD_PARTY=ON` bundles the pinned Eigen and fmt
headers and licenses into the relocatable package. Their sources are fetched
even with `CPM_USE_LOCAL_PACKAGES=ON`, because installed packages may not supply
the source files required for vendoring. Explicit `CPM_Eigen_SOURCE` and
`CPM_fmt_SOURCE` source-directory overrides remain supported; they must point at
complete source trees, including the upstream license files. Distributors can set
`COOLPROP_VENDOR_THIRD_PARTY=OFF` to use installed `Eigen3` and `fmt` CMake
packages instead (Eigen 3.4 or newer); downstream consumers must then provide
those packages too.
This option concerns Eigen/fmt only, not CoolProp's other build dependencies.

Use `CMAKE_INSTALL_PREFIX` (or `cmake --install --prefix`) to choose the install
location. The legacy `COOLPROP_INSTALL_PREFIX` override must not be empty and
is ignored in nested builds, which retain their parent's install prefix.

## Sponsors

Free code signing on Windows provided by [SignPath.io](https://about.signpath.io/), certificate by [SignPath Foundation](https://signpath.org/).

*Quoted from the upstream `README.md` file in `UPSTREAM_CLONE/`.*
Project-specific facts detected in this directory:

- Ecosystem: **Python** (manifests: pyproject.toml; scanned in UPSTREAM_CLONE)
- Top-level source layout: `Web/`, `cmake/`, `dev/`, `doc/`, `externals/`, `include/`, `src/`, `wrappers/`
- Snapshot size: **1808 files**, **207176 lines of code** (measured; see Benchmarks)
- Primary languages: `.txt` (300), `.json` (290), `.py` (221), `.h` (165), `.cpp` (142), `.sdf` (115)
- Upstream commit pinned for this packaging: `bb8f87931ec62b59a4e4dd6e38c1f5925ea5e7c0`

---

## Installation

* ... other binaries are available from [SourceForge](https://sourceforge.net/projects/coolprop/files) [![sourceforge downloads](https://img.shields.io/sourceforge/dm/CoolProp.svg?label=SF-downloads)](https://sourceforge.net/projects/coolprop/files) ![CoolProp version tag](https://img.shields.io/github/release/CoolProp/CoolProp.svg?label=SF-binaries)

* There is also a bleeding edge nightly build of the [development version](https://sourceforge.net/projects/coolprop/files/CoolProp/nightly).

* The documentation is available for the [latest release](https://www.coolprop.org) and the [development version](https://coolprop.github.io/devdocs/)

* For any kind of question regarding CoolProp and its usage, you can ask the [CoolProp Discussions](https://github.com/CoolProp/CoolProp/discussions)

* ... you might also find answers in our [FAQ](https://github.com/CoolProp/CoolProp/blob/master/FAQ.md)

* If you found a bug or have an issue that requires the developers to become active, please file an issue in our [issue tracker](https://github.com/CoolProp/CoolProp/issues)

* [Contributions](https://github.com/CoolProp/CoolProp/blob/master/.github/CONTRIBUTING.md) to this project are welcomed and encouraged! If you wish to [contribute](https://github.com/CoolProp/CoolProp/blob/master/.github/CONTRIBUTING.md) bug fixes, patches, or new features, wrappers, or material properties, please submit a Pull Request with your code.

* If you are new to Git and Github, please see the [CoolProp Wiki](https://github.com/CoolProp/CoolProp/wiki) for guidance on becoming a contributor to the project.

*Section quoted from the upstream readme.*
Overlay install (this project):

```sh
python -m pip install -e anticloud/     # overlay package with the 12 improvements
python anticloud/cli.py --help          # 13 subcommands, JSON stdout
```

---

## Usage

* ... you might also find answers in our [FAQ](https://github.com/CoolProp/CoolProp/blob/master/FAQ.md)

* If you found a bug or have an issue that requires the developers to become active, please file an issue in our [issue tracker](https://github.com/CoolProp/CoolProp/issues)

* [Contributions](https://github.com/CoolProp/CoolProp/blob/master/.github/CONTRIBUTING.md) to this project are welcomed and encouraged! If you wish to [contribute](https://github.com/CoolProp/CoolProp/blob/master/.github/CONTRIBUTING.md) bug fixes, patches, or new features, wrappers, or material properties, please submit a Pull Request with your code.

* If you are new to Git and Github, please see the [CoolProp Wiki](https://github.com/CoolProp/CoolProp/wiki) for guidance on becoming a contributor to the project.

*Section quoted from the upstream readme.*
Anticloud overlay CLI (available in every project):

```sh
python anticloud/cli.py --help     # 13 subcommands, JSON stdout
python anticloud/cli.py checks     # run the 16-check suite
```

---

## API

* For any kind of question regarding CoolProp and its usage, you can ask the [CoolProp Discussions](https://github.com/CoolProp/CoolProp/discussions)

* ... you might also find answers in our [FAQ](https://github.com/CoolProp/CoolProp/blob/master/FAQ.md)

* If you found a bug or have an issue that requires the developers to become active, please file an issue in our [issue tracker](https://github.com/CoolProp/CoolProp/issues)

* [Contributions](https://github.com/CoolProp/CoolProp/blob/master/.github/CONTRIBUTING.md) to this project are welcomed and encouraged! If you wish to [contribute](https://github.com/CoolProp/CoolProp/blob/master/.github/CONTRIBUTING.md) bug fixes, patches, or new features, wrappers, or material properties, please submit a Pull Request with your code.

* If you are new to Git and Github, please see the [CoolProp Wiki](https://github.com/CoolProp/CoolProp/wiki) for guidance on becoming a contributor to the project.

*Section quoted from the upstream readme.*
---

## Dependencies

| Metric | Value |
|--------|-------|
| Ecosystem | Python |
| Manifests detected | pyproject.toml |
| Files in snapshot | 1808 |
| Lines of code | 207176 |
| Dependency references | 67 |
| Dependencies by ecosystem | cargo: 22, native: 23, npm: 21, pypi: 1 |
| Upstream license | MIT |
| Overlay license | Anticommons 0.1.0 |

Top dependency references recorded in the benchmark snapshot:

| Ecosystem | Name | Version | Source file |
|-----------|------|---------|-------------|
| native | Python | - | CMakeLists.txt |
| native | SWIG | - | CMakeLists.txt |
| native | Octave | - | CMakeLists.txt |
| native | SWIG | - | CMakeLists.txt |
| native | Csharp | - | CMakeLists.txt |
| native | SWIG | - | CMakeLists.txt |
| native | Csharp | - | CMakeLists.txt |
| native | SWIG | - | CMakeLists.txt |
| native | R | - | CMakeLists.txt |
| native | SWIG | - | CMakeLists.txt |
| native | Java | - | CMakeLists.txt |
| native | JNI | - | CMakeLists.txt |
| native | SWIG | - | CMakeLists.txt |
| native | SWIG | - | CMakeLists.txt |
| native | Mathematica | - | CMakeLists.txt |
| ... | (52 more) | | |

Pinned lockfile: `anticloud/requirements.lock` (hash-pinned, PEP 508). SBOM: `sbom.cdx.json` (CycloneDX 1.5, pinned to the upstream SHA).

---

## Configuration

It offers similar functionality to REFPROP, but CoolProp is open-source and free.
It was originally developed by Ian Bell, at the time a post-doc at the University of Liege, in Liege, Belgium.

* CoolProp has flexible licensing terms: Commercial - ok! Academic? - ok! [![license](https://img.shields.io/github/license/CoolProp/CoolProp.svg)](https://github.com/CoolProp/CoolProp/blob/master/LICENSE)

* For Python, get the latest release via `pip install coolprop` [![PyPI downloads](https://img.shields.io/pypi/dm/CoolProp.svg?label=PyPI-downloads)](https://pypi.org/project/CoolProp/) [![PyPI version](https://img.shields.io/pypi/v/coolprop.svg?label=PyPI-binaries)](https://pypi.org/project/CoolProp/)

* ... other binaries are available from [SourceForge](https://sourceforge.net/projects/coolprop/files) [![sourceforge downloads](https://img.shields.io/sourceforge/dm/CoolProp.svg?label=SF-downloads)](https://sourceforge.net/projects/coolprop/files) ![CoolProp version tag](https://img.shields.io/github/release/CoolProp/CoolProp.svg?label=SF-binaries)

* There is also a bleeding edge nightly build of the [development version](https://sourceforge.net/projects/coolprop/files/CoolProp/nightly).

* The documentation is available for the [latest release](https://www.coolprop.org) and the [development version](https://coolprop.github.io/devdocs/)

* For any kind of question regarding CoolProp and its usage, you can ask the [CoolProp Discussions](https://github.com/CoolProp/CoolProp/discussions)

* ... you might also find answers in our [FAQ](https://github.com/CoolProp/CoolProp/blob/master/FAQ.md)

* If you found a bug or have an issue that requires the developers to become active, please file an issue in our [issue tracker](https://github.com/CoolProp/CoolProp/issues)

* [Contributions](https://github.com/CoolProp/CoolProp/blob/master/.github/CONTRIBUTING.md) to this project are welcomed and encouraged! If you wish to [contribute](https://github.com/CoolProp/CoolProp/blob/master/.github/CONTRIBUTING.md) bug fixes, patches, or new features, wrappers, or material properties, please submit a Pull Request with your code.

* If you are new to Git and Github, please see the [CoolProp Wiki](https://github.com/CoolProp/CoolProp/wiki) for guidance on becoming a contributor to the project.

*Section quoted from the upstream readme.*
Overlay configuration (Anticloud):

- `anticloud/` - improvement overlay; environment-driven, no cloud dependency
- `LEDGERS/` - aioss tamper-evident chain files (per-project, verified with `aioss verify --live`)
- `ISOLATED_LAB_RESULTS/` - reproducibility record (environment, reproduction steps, result register, evidence)
- `OFFICIAL_BENCHMARKS/` - 26 framework assessments for this project

---

## Contributing

*Excerpt from upstream `.github/CONTRIBUTING.md`:*

# Contributing to CoolProp

Thank you for taking the time to contribute!

The following is a set of guidelines for contributing to CoolProp, which is hosted at [CoolProp](https://github.com/CoolProp) on GitHub. These are mostly guidelines, not rules. Use your best judgment, and feel free to propose changes to this document in a pull request.

#### Table Of Contents

[I don't want to read this whole thing, I just have a question!!!](#i-dont-want-to-read-this-whole-thing-i-just-have-a-question)

[How Can I Contribute?](#how-can-i-contribute)
  * [Reporting Bugs](#reporting-bugs)
  * [Suggesting Enhancements](#suggesting-enhancements)
  * [Your First Code Contribution](#your-first-code-contribution)
  * [Pull Requests](#pull-requests-prs)
  * [AI-Assisted Contributions](#ai-assisted-contributions)

[Styleguides](#styleguides)
  * [Git Commit Messages](#git-commit-messages)
  * [C++ Code](https://github.com/CoolProp/CoolProp/wiki/Coding-Guidelines)

## I don't want to read this whole thing I just have a question!!!

> **Note:** Please don't file an issue to ask a question. You'll get faster results by using the resources below.

We have an official Google Group, where the community chimes in with helpful advice if you have questions, and a fairly detailed set of on-line documentation.

* [Discuss, the official CoolProp User Group](https://goo.gl/Pa7FBT)
* CoolProp documentation: [Release Version](https://www.coolprop.org) and [Development Version](https://www.coolprop.org/dev)

## How Can I Contribute?

### Reporting Bugs

This section guides you through submitting a bug report for CoolProp. Following these guidelines helps maintainers and the community understand your report, reproduce the behavior, and find related reports.

Before creating bug reports, please check [this list](#before-submitting-a-bug-report) as you might find out that you don't need to create one. When you are creating a bug report, please [include as many details as possible](#how-do-i-submit-a-good-issue-report). Fill out [the required template](ISSUE_TEMPLATE.md), the information it asks for helps us resolve issues faster.

> **Note:** If you find a **Closed** issue that seems like it is the same thing that you're experiencing, and you are using the latest CoolProp version that includes that issue resolution, open a new issue and include a link to the original issue in the body of your new one.

#### Before Submitting A Bug Report

* **Check the [FAQs file](https://github.com/CoolProp/C

Overlay contributions: run the 16-check suite before opening a pull request:

```sh
python anticloud/bench/runner.py --cwd anticloud
```

---

## License

**Upstream license: MIT** (evidence: `LICENSE` in the upstream snapshot).

License file excerpt:

```text
MIT License

Copyright (c) 2012-2018 Ian H. Bell and other CoolProp developers

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
```

### Anticommons 0.1.0 overlay

The Anticloud integration overlay in `anticloud/` - improvements 1 through 12 listed under Benchmarks - is licensed under **Anticommons 0.1.0**. Upstream code remains under its original MIT terms. See `ANTICOMMONS_LICENSE.md` in this directory for the overlay terms and contact.

SPDX: `MIT` (upstream) + Anticommons 0.1.0 (overlay, dual).

---

## Upstream

- **Project:** `COOLPROP` (category: CHEMICAL PRODUCTION)
- **Upstream URL:** https://github.com/CoolProp/CoolProp
- **Pinned commit (SHA):** `bb8f87931ec62b59a4e4dd6e38c1f5925ea5e7c0`
- **Branch:** master
- **Pin provenance:** GitHub API commits/master. The parent-project stamp is explicitly rejected for this project.
- **Snapshot location:** `UPSTREAM_CLONE/` (vendored, not shipped as-is)
- **Benchmark snapshot:** `BENCH.json`

---

## Benchmarks

Measured by the Anticloud assurance suite. Every value below is read from this
project's `BENCH.json`, produced by a real run — the SHA3-256 of that file is
`fd65196cc328cfc61806a64cc942b7ecb0d8b66a7f6c4394681067619f28e243`.

| Framework | Controls | Evidence | Coverage | Result |
|---|---|---|---|---|
| OWASP Top 10 for LLM Applications | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| OWASP Top 10 (2021) | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| SOC 2 Type II readiness | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| NIST AI Risk Management Framework | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| NIST SP 800-53 Rev. 5 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| NIST Cybersecurity Framework 2.0 | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| FedRAMP Rev. 5 | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| PCI DSS v4.0.1 | 11 controls mapped | 11 with evidence | 100.0% | PASS |
| ISO/IEC 27001:2022 | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| MITRE ATT&CK v16 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| ML Technology Readiness Level | TRL 8 | 8/8 criteria | | PASS |

**Overall: 16/16 checks passing.**

See `ISOLATED_LAB_RESULTS/03_Result_Register.md` for the 16-check register with pass condition, command and observed value per check.

Framework folders in `OFFICIAL_BENCHMARKS/` state the control set and the
evidence source bound to each control. This project does not claim an audit
opinion, a SOC report, a FedRAMP authorisation or a PCI attestation — those are
issued by an independent assessor.



## Archives and Permanent Records

| Platform | Identifier | Volume |
|---|---|---|
| Harvard Dataverse | DOI 10.7910/DVN/YMJKOG | 145 citable datasets |
| AIOSS verification kit | DOI 10.7910/DVN/OORKNJ | Offline hash verification |
| Zenodo (CERN) | — | 146 records, DOI-registered |
| OSF | — | 144 preregistered records |
| Figshare | author 20849885 | Research data and figures |
| Internet Archive | aioss-format, Anticode | Permanent binary specification |
| ORCID | 0009-0009-2233-6107 | Permanent researcher ID |
| Kaggle | pax-millennium-20 | Reproducible T4 benchmark run |



## Press and Independent Publication

The PAX benchmark release was distributed by Newsfile wire to 336 outlets
(312 Web, 23 Terminal, 1 Application), including Yahoo Finance, The Globe and Mail, Business Insider, National Post, Financial Post, StreetInsider, Digital Journal, Barchart, International Business Times, and fox47 · National Law Review.
Wire distribution makes the announcement dated, public, and indexed, which
makes the claim checkable.

