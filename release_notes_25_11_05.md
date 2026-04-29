# OPEN FIFTH RELEASE NOTES FOR KOHA 25.11.04
29 Apr 2026

**Internal Release Notes - Open Fifth Backport Tracking**

These release notes document additional patches and features backported by Open Fifth
to our production Koha installation, beyond what is included in the community release
of Koha 25.11.04. These changes represent work either sponsored by Open Fifth
or backported from future versions to meet our library partners' needs.

For complete community release notes for Koha 25.11.04, please see:
- [Koha Community Release Notes](https://koha-community.org/download/release-notes/)

---

## Summary

This release includes 1 new features, 30 enhancements, 4 bugfixes.


## Bugfixes

### Acquisitions

#### Critical bugs fixed

- [42010](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=42010) Include escaping when using PO numbers in EDI acquisitions
  - **Backported from version(s):** 26.05.00

### Circulation

#### Other bugs fixed

- [41977](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=41977) Hold fee not charged for title-level holds when all items have negative notforloan status
  - **Backported from version(s):** 26.05.00

  **Sponsored by** *OpenFifth*

### ILL

#### Other bugs fixed

- [41861](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=41861) ILL request cost and price paid don't show if 0
  - **Backported from version(s):** 26.05.00
  >This updates how an ILL request cost and price paid are shown - if the amount is $0, then it is now shown. Previously, the fields were not shown if the amount was $0.
  >
  >(Note: 'Cost' is not editable in the user interface, but the backend used may set the value. 'Price paid' is editable through the 'Edit request' action)

### SIP2

#### Other bugs fixed

- [41369](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=41369) SIP payments have no branchcode
  - **Backported from version(s):** 26.05.00
  >This fixes SIP2 based payments, so that a branchcode (institution id) is now recorded for the payment.

## Enhancements 

### Acquisitions

#### Enhancements

- [40383](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40383) Modernise the EDIFACT Message display modal
  - **Backported from version(s):** 26.05.00
  >The EDIFACT message viewer has been significantly improved with a new interactive modal interface replacing the previous basic display.
  >
  >New features:
  >
  >  - Tree view — Collapsible, hierarchical display of EDIFACT interchange structure with segment tagging
  >  - Raw view — Plain-text fallback for direct inspection of message content
  >  - Search — Real-time search with regex support, result count, and previous/next navigation
  >  - Focus mode — Highlights segments relevant to the current context (basket or invoice) when opened from those pages
  >  - JSON download — New ?format=json endpoint on edimsg.pl and download button for programmatic access and debugging; backed by a new to_json() method on Koha::Edifact
- [40391](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40391) EDI: Add support for GIR:LSL field
  - **Backported from version(s):** 26.05.00
  >Add support for the Library Sub-location field in EDIfact messages, to allow both Collection Code and Location Code mappings from EDI messages.
- [41020](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=41020) Add ability to use file transports for MARC ordering accounts
- [41297](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=41297) Add duplicate invoice number detection on EDI invoice import

  **Sponsored by** *Royal Borough of Kensington and Chelsea* and *Westminster City Council*
- [41709](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=41709) GIR segment data should be encoded in EDI ORDERs
- [41996](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=41996) Further improvements to EDIFACT error recording
- [42001](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=42001) Update duplicate purchase order number detection on EDI quote import to optionally send notifications to staff and vendors

  **Sponsored by** *Royal Borough of Kensington and Chelsea* and *Westminster City Council*
- [42110](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=42110) Migrate marc_order_accounts.download_directory to use local file transport option

### Architecture, internals, and plumbing

#### Enhancements

- [35761](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=35761) Add an administration editor for FTP and SFTP servers
  - **Backported from version(s):** 25.11.00
  >Koha now includes a unified administration interface for managing FTP and SFTP server connections, eliminating the need to duplicate connection details across different parts of the system.
  >
  >This new centralised configuration system allows you to define FTP and SFTP server credentials once and then reference them from multiple features (such as EDI). If a password changes or a vendor upgrades from FTP to SFTP, only a single configuration record needs updating.
  >
  >**Key features:**
  >
  >- **Unified server management**: Configure FTP and SFTP servers under Administration → File transports
  >- **Secure credential storage**: Passwords and SSH keys are encrypted in the database
  >- **Connection testing**: Test connections directly from the Koha interface to verify credentials and connectivity
  >- **Granular permissions**: New `manage_file_transports` permission controls access to the configuration interface
  >- **Reusable configurations**: Server configurations can be referenced by multiple features, reducing duplication
  >
  >**Configuration options:**
  >
  >- Transport type (FTP or SFTP)
  >- Server hostname and port
  >- Username and password
  >- Upload and download directories
  >- Connection settings (passive mode, debug mode)
  >- SSH private key (for SFTP)
  >
  >**For administrators:**
  >
  >Access the new file transport management under Administration → File transports. The interface includes a connection testing feature that validates your credentials and checks read/write permissions on the configured directories.
  >
  >**Future extensibility:**
  >
  >This architecture provides a foundation for adding file transport capabilities to other Koha features such as `runreport.pl`, `export_records.pl`, and `export_borrowers.pl`, allowing them to upload outputs directly to remote servers.
- [39971](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39971) Patron attribute types form logic should be reusable
  - **Backported from version(s):** 26.05.00
  >Internal refactoring of code for reusability. No end-user functionality changes.

### Authentication

#### New features

- [40824](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40824) Add option to prevent re-use of passwords

### Circulation

#### Enhancements

- [37966](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=37966) When overriding a hold to renew a book the due date becomes "now" if not specified
- [38924](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=38924) Introduce an organization level loan 'Quota' system for Koha
- [39802](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39802) Add CircControl equivalent system preference for lost item fees and actions
  - **Backported from version(s):** 26.05.00
  >This enhancement adds a new system preference: LostChargesControl which is used to determine the branch that is used to look up the circulation rule for charging lost fees when an item is marked lost.
  >
  >Choices are:
  >library the item is from (follows HomeOrHolding)
  >library the patron is from
  >library you are logged in at
  >
  >Currently this is only used by the longoverdue cronjob. Selecting "library you are logged in at" will cause the cronjob to cancel as there is no branch - this mimics current behavior, but is more verbose.

  **Sponsored by** *MAIN Library Alliance*

### Hold requests

#### Enhancements

- [3492](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=3492) Move hold fee setting into circulation rules
  - **Backported from version(s):** 26.05.00
  >Hold fees can now be configured through the circulation rules matrix, providing much more granular control over hold charges based on patron category, item type, and library combinations.
  >
  >Previously, hold fees (reservefee) could only be set at the patron category level in the patron category administration. This enhancement integrates hold fees into the main circulation rules system, where they follow the standard rule hierarchy with automatic fallback handling.
  >
  >**Key changes:**
  >
  >- Hold fees can now be set for specific combinations of patron category, item type, and library
  >- The deprecated `reservefee` field has been removed from patron categories
  >- Hold fee configuration appears as a new column in the circulation rules matrix
  >- Hold fees follow the same rule precedence as other circulation rules (most specific rule wins, with fallback to broader rules)
  >
  >**For administrators:**
  >
  >After upgrading, you may want to review your circulation rules and update hold fees where appropriate. Any existing hold fees previously set at the patron category level will have been migrated to the circulation rules.

  **Sponsored by** *OpenFifth*
- [40817](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40817) Holds charges should be accessible from Holds

### ILL

#### Enhancements

- [39941](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39941) Adding a patron to an unauthenticated request should change the request's status to 'NEW'
- [39944](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39944) Metadata should be trimmed before creating an ILL request

  **Sponsored by** *NHS England (National Health Service England)*
- [41111](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=41111) AutoILLBackendPriority should consider a 'yellow' stage
- [41536](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=41536) ILL "Confirm Request" button fails to stand out as a primary action
  - **Backported from version(s):** 26.05.00

### MARC Bibliographic data support

#### Enhancements

- [38096](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=38096) Field 857 is not considered for display on XSLT files
  - **Backported from version(s):** 26.05.00

### Notices

#### Enhancements

- [4858](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=4858) Ability to Charge for Print Notices

### OPAC

#### Enhancements

- [39698](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39698) Add option to expand responsive datatable rows by default
  - **Backported from version(s):** 26.05.00
  >This enhancement lets you control the default responsiveness of OPAC tables, such as OPAC search history. New system preference 'OPACTableColExpandedByDefault' controls the default behavor. Tables are collapsed by default with a '+' to expand, and when expanded a '-' is visible to collapse. (This enhancement is a result of recommendations from a recent accessibility audit.)
  >
  >** Sponsored by: Open Fifth **

### Patrons

#### Enhancements

- [26355](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=26355) Allow patron account renewals through the OPAC
- [41749](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=41749) Add patron consent status display to staff patron detail page
  - **Backported from version(s):** 26.05.00
  >Adds a "Consents" section to the staff patron detail page. It shows the patron's privacy consent status (when PrivacyPolicyConsent
  >is enabled) and any plugin-defined consent types.
  >
  >Each consent displays with visual status indicators:
  >- Green checkmark with timestamp when consent was given
  >- Red X with timestamp when consent was refused
  >- Gray "Not specified" when no consent recorded

### Point of Sale

#### Enhancements

- [37671](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=37671) Can't print receipt for refund from cash register transaction history
  >This enhancements adds a new PAYOUT notice template to be use for receipt printing of refund transactions.
  >
  >We then use that template from both the cash management registers page and the patron account pages.

  **Sponsored by** *OpenFifth*
- [40445](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40445) Point of Sale reconciliation input during daily summaries

  **Sponsored by** *OpenFifth*
- [41751](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=41751) Cash register transaction history returns 403 for users with only anonymous_refund permission

  **Sponsored by** *OpenFifth*
- [41819](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=41819) Refunds via the Cash registers page should not result in PAYOUTS if the transaction type is 'Account Credit'

### SIP2

#### Enhancements

- [40800](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40800) TransferArrived needlessly triggers alerts in SIP
- [41649](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=41649) Add support for setting the magnetic media flag for SIP in Koha

## Other changes

Commits in this range that don't reference a Bugzilla bug number:

- LOCAL: Replaced package crontab files with empties _(Jake Deery)_
- [LOCAL] Remove check-atomic-updates test file _(Pedro Amorim)_
- LOCAL: Add POD stubs for BorrowerPasswordHistory koha_*_class subs _(Martin Renvoize)_
- LOCAL: Tail-end xt fixes from Phase 4 verification _(Martin Renvoize)_
- LOCAL: chmod +x on 5 atomicupdate scripts _(Martin Renvoize)_
- LOCAL: Fix Jenkins test failures from backports _(Martin Renvoize)_
- LOCAL: Automated Schema Update (dbic --force regen) _(Martin Renvoize)_
- LOCAL: Sync sysprefs.sql with YAML and db_revs renames _(Martin Renvoize)_
- LOCAL: Bump Hold.t and holds.t plan counts for Test::NoWarnings _(Martin Renvoize)_
- LOCAL: Repair EDI.t subtest corruption and Order.t plan count _(Martin Renvoize)_
- LOCAL: Misc tidy for Jenkins _(Jake Deery)_
- LOCAL: Update DBIC Schema's _(Martin Renvoize)_
- Fix: Add print_notice_charge column to categories schema and atomicupdate _(Martin Renvoize)_
- Fix: Resolve leftover conflict markers in Circulation.pm and opac-memberentry.pl _(Martin Renvoize)_
- LOCAL: SFTP/FTP fixes - add path parameter to list_files() _(Martin Renvoize)_
- BUG 38924 (BACKPORT FIX): restore includes to circulation_quota.tt _(Jacob O'Mara)_
- Fix: Prevent duplicate holds from duplicate biblionumber parameters _(Martin Renvoize)_
- LOCAL: Fix permissions _(Martin Renvoize)_
- LOCAL: Fix for encode_json missing in SFTP _(Martin Renvoize)_
- LOCAL: Fixed orderline identification algorithm _(Martin Renvoize)_
- Bug fix: Handle missing orders in EDI service charge processing _(Martin Renvoize)_
- fix: prevent creation of £0 EDI service charge adjustments _(Martin Renvoize)_
- LOCAL: Add more detail to EDI Adjustment Notes _(Martin Renvoize)_
- fix: use exact EDI tax values for tax_value_on_receiving _(Martin Renvoize)_
- fix: recalculate tax_value_on_receiving after service charge adjustment _(Martin Renvoize)_
- fix: use EDI TAX segment for accurate tax rate _(Martin Renvoize)_
- LOCAL: Correctly handle service charge tax in EDI processing _(Martin Renvoize)_
- LOCAL: Fix EDI service charge adjustment creation to handle split orders _(Martin Renvoize)_
- LOCAL: Fix EDI service charge processing for multiple messages per transmission _(Martin Renvoize)_
- LOCAL: Fix edi_process_service_charges to account for multiple messages _(Martin Renvoize)_
- Skip allowances (ALC+A) in EDI service charge processing _(Martin Renvoize)_
- Correct split order lookup logic for service charge adjustments _(Martin Renvoize)_
- Fix service charge adjustment for split orders _(Martin Renvoize)_
- Optimize EDI service charge processing _(Martin Renvoize)_
- Fix double-counting in EDI service charge processing _(Martin Renvoize)_
- Fix allowance sign in EDI service charge processing _(Martin Renvoize)_
- Add vendor-to-budget mapping for EDI service charges _(Martin Renvoize)_
- Add EDI service charge processing script _(Martin Renvoize)_
- LOCAL 41297: Fix failing EDI.t tests _(Martin Renvoize)_
- fix: ensure LSL field is copied to item_hash in EDI quote processing _(Martin Renvoize)_
- LOCAL: Bug 40445 - Add print notice charge installation data _(Martin Renvoize)_
- LOCAL: Add placehold op in cashup modal _(Martin Renvoize)_
- LOCAL: Fix display for older classes in cashup _(Martin Renvoize)_
- O5TH Branch Start _(Jake Deery)_

## New system preferences

- AllowQuotaOverride
- EdifactInvoiceImportBlockDuplicates
- EdifactInvoiceImportBlockDuplicatesEmailAddresses
- EdifactInvoiceImportBlockDuplicatesEmailNotice
- EdifactLSL
- EdifactOrderSendBlockDuplicatesEmailAddresses
- EdifactOrderSendBlockDuplicatesEmailNotice
- EnableCirculationQuotas
- LostChargesControl
- OPACTableColExpandedByDefault
- PasswordHistoryCount
- TitleHoldFeeStrategy
- UseGuarantorQuota

## Credits

We thank the following libraries, companies, and other institutions who sponsored
new features in this release:
<div style="column-count: 2;">

- MAIN Library Alliance
- NHS England (National Health Service England)
- [OpenFifth](https://openfifth.co.uk)
- [Royal Borough of Kensington and Chelsea](https://www.rbkc.gov.uk)
- [Westminster City Council](https://www.westminster.gov.uk)
</div>

Contributors to this release:
<div style="column-count: 2;">

- Pedro Amorim (19)
- Matt Blenkinsop (10)
- Colin Campbell (1)
- Nick Clemens (4)
- Jake Deery (3)
- Lucas Gass (1)
- Michael Hafen (2)
- Kyle M Hall (6)
- Jacob O'Mara (29)
- Martin Renvoize (148)
</div>

Contributing organizations:
<div style="column-count: 2;">

- [ByWater Solutions](https://bywatersolutions.com) (11)
- Independant Individuals (14)
- [OpenFifth](https://openfifth.co.uk) (198)
</div>

Testers and sign-offs:
<div style="column-count: 2;">

- Tomás Cohen Arazi (6)
- Christopher Brannon (1)
- Trevor Diamond (4)
- Marion Durand (1)
- Roger fredricks (1)
- Lucas Gass (1)
- David Nind (3)
- Martin Renvoize (7)
- Marcel de Rooy (1)
- Jackie Usher (7)
- Anneli Österman (1)
</div>

---

*Generated by Open Fifth release tools on 29 Apr 2026 11:24:26*

*These are internal tracking notes and may include patches not yet available in community releases.*
