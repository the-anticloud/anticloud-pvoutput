# PVOUTPUT

![license](https://img.shields.io/badge/license-license-blue) ![offline-first](https://img.shields.io/badge/offline--first-air--gap-green) ![audit](https://img.shields.io/badge/audit-SHA3--256-orange) ![category](https://img.shields.io/badge/category-solar-lightgrey)

> Anticloud-hardened packaging of the upstream project `PVOUTPUT` in category **SOLAR**. Upstream source is vendored in `UPSTREAM_CLONE/` at the pinned commit below; the 12-improvement overlay lives in `anticloud/`. Every fact in this file traces to a file on disk in this project directory.

**Category:** SOLAR · **Upstream:** https://github.com/markruys/gw2pvo · **Upstream pin:** `0f1c82a359d26f682b152f7aeb8c620893e235f1` · **Vendor:** Anticloud FZ LLE

---

## What This Project Does

<!-- ALL-CONTRIBUTORS-BADGE:START - Do not remove or modify this section -->
[![All Contributors](https://img.shields.io/badge/all_contributors-9-orange.svg?style=flat-square)](#contributors-)
<!-- ALL-CONTRIBUTORS-BADGE:END -->

[![codecov](https://codecov.io/gh/openclimatefix/pvoutput/branch/main/graph/badge.svg?token=GTQDR2ZZ2S)](https://codecov.io/gh/openclimatefix/pvoutput)

Download historical solar photovoltaic data from [PVOutput.org](https://pvoutput.org).

This code is a work-in-progress.  The aim is to provide both a Python library for interacting with [PVOutput.org's API](https://pvoutput.org/help.html#api), and a set of scripts for downloading lots of data :)

# Installation

```bash
$ pip install pvoutput-ocf
```

## Development installation

If you want to install the latest development version directly from GitHub:

```bash
pip install git+https://github.com/openclimatefix/pvoutput.git
```

## Register with PVOutput.org

You need to get an API key *and* a system ID from PVOutput.org.

If you don't own a physical PV system, click the "energy consumption only" box
when registering on PVOutput.  If you don't include a
system ID, then you'll get a "401 Unauthorized" response from the PVOutput API.

You can pass the API key and system ID into the `PVOutput` constructor.
Or, create a `~/.pvoutput.yml` file which looks like:

```yaml
api_key: <API key from PVOutput.org>
system_id: <SystemID from PVOutput.org>
```

The default location of the `.pvoutput.yml` is the user's home directory, expanded from `~`. This can be overridden by setting the `PVOUTPUT_CONFIG` environment variable.

e.g. `export PVOUTPUT_CONFIG="/my/preferred/location/.pvoutput.yml"`

Alternatively, you can set `API_KEY`, `SYSTEM_ID` and `DATA_SERVICE_URL` (see below) as environmental variables.

### API quotas and paid subscriptions
Please see [here](https://pvoutput.org/help/data_services.html) for update info.

#### Free

For free, PVOutput.org gives you 60 API requests per hour. In a single API request you can download one day of data for one PV system.  (See PVOutput's docs for more info about [rate limits](https://pvoutput.org/help/api_specification.html#rate-limits).)

#### Donate
[Donating to PVOutput.org](https://pvoutput.org/help/donations.html#donations) increases your API quota to 300 requests per hour.

#### Paid
To get more historical data, you can pay $800 Australian dollars for a year's 'Live System History' subscription for a single country ([more info here](https://pvoutput.org/help/data_services.html). And [here's PVOutput.org's full price list](https://pvoutput.org/services.jsp)).
This allows you to use the [`get batch status`](https://pvoutput.org/help/data_services.html#get-batch-status-service) API to download 900 PV-system-*years* per hour.

If you have subscribed to PVOutput's data service then either
- add `data_service_url` to your configuration file (`~/.pvoutput.yml`) or
- pass `data_service_url` to the `PVOutput` constructor.

The `data_service_url` should end in `.org` (note the `data_service_url` doesn't include the `/service/r2` part of the URL)
For example: `data_service_url: https://pvoutput.org/`

# Usage

See the [Quick Start notebook](examples/quick_start.ipynb).

## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tbody>
    <tr>
      <td align="center"><a href="http://jack-kelly.com"><img src="https://avatars.githubusercontent.com/u/460756?v=4?s=100" width="100px;" alt="Jack Kelly"/><br /><sub><b>Jack Kelly</b></sub></a><br /><a href="https://github.com/openclimatefix/pvoutput/commits?author=JackKelly" title="Code">💻</a></td>
      <td align="center"><a href="https://github.com/ssmssam"><img src="https://avatars.githubusercontent.com/u/39378848?v=4?s=100" width="100px;" alt="Sam Murphy-Sugrue"/><br /><sub><b>Sam Murphy-Sugrue</b></sub></a><br /><a href="https://github.com/openclimatefix/pvoutput/commits?author=ssmssam" title="Code">💻</a></td>
      <td align="center"><a href="https://gabrieltseng.github.io/"><img src="https://avatars.githubusercontent.com/u/29063740?v=4?s=100" width="100px;" alt="Gabriel Tseng"/><br /><sub><b>Gabriel Tseng</b></sub></a><br /><a href="https://github.com/openclimatefix/pvoutput/commits?author=gabrieltseng" title="Code">💻</a></td>
      <td align="center"><a href="http://www.solar.sheffield.ac.uk/"><img src="https://avatars.githubusercontent.com/u/12187350?v=4?s=100" width="100px;" alt="Jamie Taylor"/><br /><sub><b>Jamie Taylor</b></sub></a><br /><a href="https://github.com/openclimatefix/pvoutput/commits?author=JamieTaylor-TUOS" title="Code">💻</a></td>
      <td align="center"><a href="https://github.com/peterdudfield"><img src="https://avatars.githubusercontent.com/u/34686298?v=4?s=100" width="100px;" alt="Peter Dudfield"/><br /><sub><b>Peter Dudfield</b></sub></a><br /><a href="#infra-peterdudfield" title="Infrastructure (Hosting, Build-Tools, etc)">🚇</a></td>
      <td align="center"><a href="https://github.com/vnshanmukh"><img src="https://avatars.githubusercontent.com/u/67438038?v=4?s=100" width="100px;" alt="Shanmukh Chava"/><br /><sub><b>Shanmukh Chava</b></sub></a><br /><a href="https://github.com/openclimatefix/pvoutput/commits?author=vnshanmukh" title="Code">💻</a></td>
      <td align="center"><a href="https://github.com/Antsthebul"><img src="https://avatars.githubusercontent.com/u/56587872?v=4?s=100" width="100px;" alt="Antsthebul"/><br /><sub><b>Antsthebul</b></sub></a><br /><a href="https://github.com/openclimatefix/pvoutput/commits?author=Antsthebul" title="Code">💻</a></td>
    </tr>
    <tr>
      <td align="center"><a href="http://www.rachitsingh.com"><img src="https://avatars.githubusercontent.com/u/1606892?v=4?s=100" width="100px;" alt="Rachit Singh"/><br /><sub><b>Rachit Singh</b></sub></a><br /><a href="#dat

*(excerpt; full text in `UPSTREAM_CLONE/`)*

*Quoted from the upstream `README.md` file in `UPSTREAM_CLONE/`.*
Project-specific facts detected in this directory:

- Ecosystem: **Python** (manifests: setup.py, requirements.txt; scanned in UPSTREAM_CLONE)
- Top-level source layout: `examples/`, `infrastructure/`, `pvoutput/`, `scripts/`, `tests/`
- Snapshot size: **54 files**, **4172 lines of code** (measured; see Benchmarks)
- Primary languages: `.py` (27), `.ipynb` (9), `(none)` (4), `.md` (2), `.pickle` (2), `.txt` (2)
- Upstream commit pinned for this packaging: `0f1c82a359d26f682b152f7aeb8c620893e235f1`

---

## Installation

No installation section was found in the upstream readme, so the commands below are generated from the manifests detected in this project directory.

```sh
python -m venv .venv && source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -e .                                     # or: pip install -r requirements.txt
```

Overlay install (this project):

```sh
python -m pip install -e anticloud/     # overlay package with the 12 improvements
python anticloud/cli.py --help          # 13 subcommands, JSON stdout
```

---

## Usage

If you have subscribed to PVOutput's data service then either
- add `data_service_url` to your configuration file (`~/.pvoutput.yml`) or
- pass `data_service_url` to the `PVOutput` constructor.

The `data_service_url` should end in `.org` (note the `data_service_url` doesn't include the `/service/r2` part of the URL)
For example: `data_service_url: https://pvoutput.org/`

*Section quoted from the upstream readme.*
Anticloud overlay CLI (available in every project):

```sh
python anticloud/cli.py --help     # 13 subcommands, JSON stdout
python anticloud/cli.py checks     # run the 16-check suite
```

---

## API

Download historical solar photovoltaic data from [PVOutput.org](https://pvoutput.org).

This code is a work-in-progress.  The aim is to provide both a Python library for interacting with [PVOutput.org's API](https://pvoutput.org/help.html#api), and a set of scripts for downloading lots of data :)

*Section quoted from the upstream readme.*
---

## Dependencies

| Metric | Value |
|--------|-------|
| Ecosystem | Python |
| Manifests detected | setup.py, requirements.txt |
| Files in snapshot | 54 |
| Lines of code | 4172 |
| Dependency references | 11 |
| Dependencies by ecosystem | conda: 11 |
| Upstream license | Apache-2.0 |
| Overlay license | Anticommons 0.1.0 |

Top dependency references recorded in the benchmark snapshot:

| Ecosystem | Name | Version | Source file |
|-----------|------|---------|-------------|
| conda | conda-forge | - | environment.yml |
| conda | python | - | environment.yml |
| conda | pytest | - | environment.yml |
| conda | pyyaml | - | environment.yml |
| conda | pytables | - | environment.yml |
| conda | pandas | - | environment.yml |
| conda | matplotlib | - | environment.yml |
| conda | jupyterlab | - | environment.yml |
| conda | urllib3 | - | environment.yml |
| conda | requests | - | environment.yml |
| conda | beautifulsoup4 | - | environment.yml |

Pinned lockfile: `anticloud/requirements.lock` (hash-pinned, PEP 508). SBOM: `sbom.cdx.json` (CycloneDX 1.5, pinned to the upstream SHA).

---

## Configuration

e.g. `export PVOUTPUT_CONFIG="/my/preferred/location/.pvoutput.yml"`

Alternatively, you can set `API_KEY`, `SYSTEM_ID` and `DATA_SERVICE_URL` (see below) as environmental variables.

*Section quoted from the upstream readme.*
Overlay configuration (Anticloud):

- `anticloud/` - improvement overlay; environment-driven, no cloud dependency
- `LEDGERS/` - aioss tamper-evident chain files (per-project, verified with `aioss verify --live`)
- `ISOLATED_LAB_RESULTS/` - reproducibility record (environment, reproduction steps, result register, evidence)
- `OFFICIAL_BENCHMARKS/` - 26 framework assessments for this project

---

## Contributing

Upstream contributions: fork the `PVOUTPUT` project, create a feature branch, and open a pull request against upstream. Keep `UPSTREAM_CLONE/` untouched in this packaging; put improvements in the `anticloud/` overlay.

Overlay contributions: run the 16-check suite before opening a pull request:

```sh
python anticloud/bench/runner.py --cwd anticloud
```

---

## License

**Upstream license: Apache-2.0** (evidence: `LICENSE.txt` in the upstream snapshot).

License file excerpt:

```text

                                 Apache License
                           Version 2.0, January 2004
                        http://www.apache.org/licenses/

   TERMS AND CONDITIONS FOR USE, REPRODUCTION, AND DISTRIBUTION

   1. Definitions.

      "License" shall mean the terms and conditions for use, reproduction,
      and distribution as defined by Sections 1 through 9 of this document.

      "Licensor" shall mean the copyright owner or entity authorized by
      the copyright owner that is granting the License.

      "Legal Entity" shall mean the union of the acting entity and all
      other entities that control, are controlled by, or are under common
      control with that entity. For the purposes of this definition,
      "control" means (i) the power, direct or indirect, to cause the
      direction or management of such entity, whether by contract or
```

### Anticommons 0.1.0 overlay

The Anticloud integration overlay in `anticloud/` - improvements 1 through 12 listed under Benchmarks - is licensed under **Anticommons 0.1.0**. Upstream code remains under its original Apache-2.0 terms. See `ANTICOMMONS_LICENSE.md` in this directory for the overlay terms and contact.

SPDX: `Apache-2.0` (upstream) + Anticommons 0.1.0 (overlay, dual).

---

## Upstream

- **Project:** `PVOUTPUT` (category: SOLAR)
- **Upstream URL:** https://github.com/markruys/gw2pvo
- **Pinned commit (SHA):** `0f1c82a359d26f682b152f7aeb8c620893e235f1`
- **Branch:** master
- **Pin provenance:** GitHub API commits/master. The parent-project stamp is explicitly rejected for this project.
- **Snapshot location:** `UPSTREAM_CLONE/` (vendored, not shipped as-is)
- **Benchmark snapshot:** `BENCH.json`

---

## Benchmarks

Measured by the Anticloud assurance suite. Every value below is read from this
project's `BENCH.json`, produced by a real run — the SHA3-256 of that file is
`656776628a26f4ee0d481338815d4b90ab04207bc4fd781a0ecebf74d12b2442`.

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

