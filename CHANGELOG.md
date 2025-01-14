# Changelog

All notable changes to the Schematron Rules and this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/)
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## UNRELEASED

This release is compatible with XRechnung ?.?.?

## v1.7.2 on 2022-05-31

This version is compatible with XRechnung 2.2.0

### Added
* Schematron Rules
  * BR-DE-26 to UBL CreditNote to allow for "Corrected CreditNotes"

### Changed

* Schematron Rules
  * BR-DE-20, that testing is more robust, because type conversion is now explicitly to decimal and thus more compatible with xpath 1.0

## v1.7.1 on 2022-02-07

This version is compatible with XRechnung 2.2.0

### Fixed

* Schematron Rules
  * BR-DE-28, that - (minus), \_ (underscore), and other special characters are allowed in emails 

## v1.7.0 on 2022-01-31

This version is compatible with XRechnung 2.2.0

### Added

* Schematron Rules
  * BR-DE-27, that a telephone number must have at least three digits
  * BR-DE-28, that an email address must have exactly one @ sign, does not start or end with a dot, the @ sign must not be flanked by a whitespace or a dot and must be preceded and followed by at least two characters.
  * BR-DE-18-a, CII cardinality for BT-20 

* Schematron Rules for XRechnung Extension to include DIGA Codes (XR01, XR02, XR03)
  * BR-DEX-04 replaces CEN rule BR-CL-10 (ISO 6523 ICD Codelist)
  * BR-DEX-05 replaces CEN rule BR-CL-11 (ISO 6523 ICD Codelist)
  * BR-DEX-06 replaces CEN rule BR-CL-21 (ISO 6523 ICD Codelist)
  * BR-DEX-07 replaces CEN rule BR-CL-25 (EAS Codelist)
  * BR-DEX-08 replaces CEN rule BR-CL-26 (ISO 6523 ICD Codelist)

* numerous tests for BR-DEX-04 to BR-DEX-08 rules 

### Changed

* BR-DE-18 more robust checking of Skonto rules

### Fixed

* Corrected UBL invoice test for IBAN, checking for BR-DE-19 instead of BR-DE-21

## v1.6.1 on 2021-11-15

This version is compatible with XRechnung 2.1.1

### Fixed

* Schematron Rules
  * BR-DE-18 fixed bug, that no newline was not allowed at last not skonto note
* Tests
  * fixed wrong CII syntax in cii-br-de-23-test-bg-17-with-bg-18.xml

## v1.6.0 on 2021-07-31

This version is compatible with XRechnung 2.1.1

### Added

* Schematron Rules
  * BR-DE-23 replaces BR-DE-13
  * BR-DE-24 replaces BR-DE-13
  * BR-DE-25 replaces BR-DE-13
  * BR-DE-26 (for UBL Invoice and CII only)

### Changed

* Schematron Rules
  * BR-DE-13 removed
* Now only one Schematron file per Syntax
* All test source instances valid to EN16931 and XRechnung 2.1 

## v1.5.0 on 2020-12-31

This version is compatible with XRechnung 2.0.1

### Added

* Schematron Rules
  * BR-DEX-03 to check existence of BG-DEX-06 in a BG-DEX-01

### Changed

* This version is compatible with XRechnung 2.0.1
* Bump version to 1.5.0 for next release
* Schematron Rules
  * BR-DE-16 is now only relevant, if bt-95, bt-102 or bt-151 exist

### Fixed

* Schematron Rules
  * BR-DEX-02 rewrote rule to not give false negative
  * BR-DE-18 now checks last newline and allows negative Basisbetrag
  * BR-DE-19 flag is set to warning for CII

## v1.4.0 on 2020-07-31

### Added

* Schematron Rules
  * BR-DE-22 to check for unique file names
  * BR-DEX-01 to allow mime type 'application/xml' in XRechnung Extension
  * BR-DEX-02 on checking the sum of prices for UBL sub invoice lines in XRechnung extension

### Changed

* Schematron Rules
  * BR-DE-19 and BR-DE-20 refactoring IBAN rules
  * BR-DE-21 to check specification identifier for extension

### Fixed

* Schematron Rules
  * BR-DE-19 and BR-DE-20 fixed CII IBAN rules

## v1.3.0 on 2019-12-30

### Added

* Schematron Rules
  * BR-DE-19 und BR-DE-20 on IBAN test
  * BR-DE-21 on correct CustomizationID independent of validation scenarios
* Unit tests on Contact rules and on IBAN using xmute instructions  

### Changed

* Removed superflous files 
* Build.xml
  * Version string in Schematron files is configured by build script
  * Overwrite of Schematron compilation files is configurable

## v1.2.1 on 2019-06-24

### Added

- License.md
- Apache 2.0 License to this work
- CEN License statement
- OpenPeppol BIS 3.0 material incl.
  - [specific test instances](test/instances/bis)
  - [BIS Version of Schematron rules](src/bis)

### Changed

- README.md includes List of XRechnung business rules covered by schematron rules


## v1.2.0 on 2018-12-19

This release is compatible to XRechnung 1.2.0.

This version is only by chance the same version as XRechnung!

Because of #19 and #12 it might break your validation and business workflow. Please evaluate impact!

### Added

- Semantic Versioning (see [README](README.md)) #9
- Codelist term 389 (Self-billed invoice) for BT-3 #19

### Changed

- Made descriptions of rules `BR-DE-10` (#18), `BR-DE-11` (#18), `BR-DE-13` (#17), `BR-DE-16` (#16), and `BR-DE-18` (#22)  more precise

### Fixed

- Workaround to inconsistency in CEN Norm and Rules concerning syntax binding as described in [CEN issue #57](https://github.com/CenPC434/validation/issues/57)
- For now we allow for both 'VA' and 'VAT' (see #12)
