# Kraków alcohol-permit source spreadsheets

This repository is a public, file-level archive of spreadsheets listing
establishments in Kraków that hold permits to sell alcoholic beverages. It is
intended to make the source inputs for reproducible processing available in a
machine-readable form.

## Contents

`data/xlsx/` contains **360 XLS/XLSX files**: six files for each of **60
report dates** from 1 November 2010 to 7 September 2026.

Each date has lists for:

- retail sales (`detal`) and on-premises sales (`gastronomia`); and
- permit categories A, B and C.

File names encode the activity type, permit category and report date, for
example `detal_A_2026_09_07.xlsx`.

## Provenance and relation to the official publication

The spreadsheets were obtained from the City of Kraków through a request for
access to public information (*dostęp do informacji publicznej*). They are the
source files used by the reproducible import of the accompanying research
dataset and processing code:

- processing repository: <https://github.com/ciembor/alcohol_permits_map>
- published, derived dataset: <https://doi.org/10.5281/zenodo.23601757>

The City of Kraków also publishes permit lists in its Public Information
Bulletin (BIP), primarily as PDF attachments:

- official BIP page: <https://www.bip.krakow.pl/?dok_id=30394>
- BIP register entry and access information:
  <https://www.bip.krakow.pl/rejestry/457/11065/574249>

The BIP PDFs are the official public presentation. This repository does not
replace them or assert that it is the authoritative current register. It keeps
the XLS/XLSX files supplied by the office because they provide denser historical
coverage, include later snapshots, and are substantially more suitable for
reproducible automated extraction than PDF layout parsing.

## Reproducible processing

The files here are deliberately **raw inputs**. They have not been renamed to
standardize values, corrected, geocoded, deduplicated or grouped into sales
points. Use the processing repository for those derived steps.

To reproduce the import from a clean clone of the processing repository:

1. Clone this repository and the processing repository at their documented
   release commits.
2. Copy or symlink `data/xlsx/` to `vendor/data/xlsx/` in the processing
   repository.
3. Follow the import and release instructions in that repository's README and
   run its validation task.
4. Compare the generated release with the Zenodo package by its documented
   file counts, checksums and validation report.

The `v1.1.0` Zenodo release was generated from these 360 spreadsheets. Its
published control totals are 60 reports, 426,360 permit records and 3,098
derived sales points in the latest report dated 2026-09-07.

## Interpretation and reuse

These are administrative lists, not a direct measurement of operating
premises. They can contain source errors, abbreviations, historical addresses
and business-operator information. A permit record is not automatically a
distinct sales location.

The original material comes from the City of Kraków. Users should cite the
official BIP source above, preserve provenance when redistributing derivatives,
and check the current BIP reuse notice and any applicable Polish public-
information, privacy and data-protection requirements for their intended use.
The derived Zenodo dataset is released under CC BY 4.0; that licence applies to
the derived package, not as a claim to alter the legal status of the municipal
source records preserved here.

## Scope and maintenance

This is a frozen source archive for the documented research release, not a
live feed. New official reports should be added as new files with their source
date and provenance recorded; existing files should not be silently replaced.
