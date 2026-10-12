# DICOM Study Migration & Reconciliation Toolkit

A hands-on learning project that simulates migrating medical imaging studies between two PACS nodes and verifying that nothing was lost along the way. Built with Python (pydicom), PostgreSQL, DCMTK, Orthanc, and Bash.

> **Status:** Early work in progress. See the [roadmap](#roadmap) for what exists today.

## Why I'm building this

I work in radiology scheduling and want to move into data migration engineering, so I'm building this project to learn how imaging studies move between PACS systems and how to verify nothing is lost along the way.

I'm using Claude as a tutor: it explains concepts, gives me tasks and hints, and quizzes me. I write and debug the code myself, and I can explain every part of it.

## Data policy

This project uses **only public or synthetic data**: pydicom's bundled test files and datasets from [The Cancer Imaging Archive (TCIA)](https://www.cancerimagingarchive.net/). It contains no real patient data and nothing from any employer or internal system.

## What it will do

- Parse DICOM files and walk the Study / Series / Instance hierarchy
- Load the metadata into PostgreSQL so it can be investigated with SQL
- Migrate studies between two Orthanc nodes using DCMTK (`storescu` / `storescp`) with configured AE Titles and ports
- Reconcile source against destination and report missing studies, series, and instances
- Wrap the workflow in Bash scripts with logging, log rotation, a failed-study log, and basic disk/permission checks
- Document setup and troubleshooting in a runbook

## Roadmap

- [ ] **Phase 1:** Environment and DICOM basics (DCMTK, Orthanc via Docker, sample data)
- [ ] **Phase 2:** pydicom parser that loads study/series/instance metadata into PostgreSQL
- [ ] **Phase 3:** Two Orthanc nodes (source and destination) and study migration
- [ ] **Phase 4:** Reconciliation script and report, tested against deliberately broken transfers
- [ ] **Phase 5:** Operations: Bash wrappers, cron, logging with rotation, disk/permission checks
- [ ] **Phase 6:** README polish, troubleshooting runbook, project write-up

## Tech stack

Python, pydicom, PostgreSQL, DCMTK, Orthanc, Docker, Bash, Linux (WSL on Windows).

<!-- ## Setup -->

<!-- TODO (end of Phase 1): add prerequisites (WSL, Python, Docker, DCMTK) and the exact commands to start Orthanc and run the first script. -->

<!-- ## Repository layout -->

<!-- TODO (after Phase 2): add a short tree of the folders (scripts/, sql/, docs/, ...) with one line each on what they hold. -->

## Author
### Jesse Brumley

**Website:** [hirejesse.dev](https://hirejesse.dev) | **LinkedIn:** [linkedin.com/in/jessebrumley](https://linkedin.com/in/jessebrumley) | **Email:** [jessebrumley86@gmail.com](mailto:jessebrumley86@gmail.com)