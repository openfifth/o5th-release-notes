# OPEN FIFTH RELEASE NOTES FOR KOHA 24.11.12
12 Feb 2026

**Internal Release Notes - Open Fifth Backport Tracking**

These release notes document additional patches and features backported by Open Fifth
to our production Koha installation, beyond what is included in the community release
of Koha 24.11.12. These changes represent work either sponsored by Open Fifth
or backported from future versions to meet our library partners' needs.

For complete community release notes for Koha 24.11.12, please see:
- [Koha Community Release Notes](https://koha-community.org/download/release-notes/)

---

## Summary

This release includes 20 enhancements, 22 bugfixes.


## Bugfixes

### Accessibility

#### Other bugs fixed

- [39489](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39489) 'Refine your search' should have an aria-expanded attribute
  - **Backported from version(s):** 25.11.00,25.05.03
  >This fixes the "Refine your search" section in the OPAC. For screen reader users on smaller screens, it now correctly announces that it is an expandable section, instead of a link (by adding an aria-expanded attribute).
  >
  >Explanation: The 'Refine your search' expandable section in the Koha OPAC was not clearly announced by screen readers for smaller screen sizes. This is because the expandable section was identified and announced as a link. This resulted in screen reader users incorrectly expecting a link to another page, and not being informed that it was an expandable section.
- [39490](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39490) Table columns missing headings
  - **Backported from version(s):** 25.05.00
- [39492](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39492) Add missing aria label on the OPAC holdings table browse shelf link
  - **Backported from version(s):** 25.05.00
  >This enhancement adds an aria label to the browse shelf link in the OPAC holdings table. This provides more information about what the link does for those using assistive technology, such as screen readers.
- [39494](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39494) Announce status messaging on login page
  - **Backported from version(s):** 25.05.00
- [39497](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39497) 'Lists' page tabs should be marked as such
  - **Backported from version(s):** 25.05.00
- [39547](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39547) Required fields not conveyed programmatically in patron details in the OPAC
  - **Backported from version(s):** 25.05.00

### Acquisitions

#### Critical bugs fixed

- [33430](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=33430) Use REST API for suggestions tables
  - **Backported from version(s):** 25.05.00
  >This development reworks the purchase suggestion tables to use the API, which results in much faster load times when there are many suggestions.

#### Other bugs fixed

- [39787](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39787) Sending EDI order from basket fails if only one Library EAN exists
  - **Backported from version(s):** 25.05.00,24.11.10
- [40036](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40036) Purchase suggestion status column no longer displays reason
  - **Backported from version(s):** 25.11.00,25.05.01
  >This restores the display of suggestion accept or reject reasons (from the SUGGEST authorized values category) in the status column for the list of purchase suggestions. (This is related to Bug 33430 - Use REST API for suggestions tables, added in Koha 25.05.)
  >
  >It also adds classes for the SUGGEST authorized values, so that these can be styled.
- [40593](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40593) Can't search all columns in Acquisitions Suggestions table
  - **Backported from version(s):** 25.11.00,25.05.05

### Architecture, internals, and plumbing

#### Other bugs fixed

- [41523](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=41523) Bug 41409 update statement is not accurate
  - **Backported from version(s):** 26.05.00,25.11.02

### ERM

#### Other bugs fixed

- [40737](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40737) Usage statistics data provider "Import logs" table does not render if "Imported by": "Cronjob"

### Hold requests

#### Other bugs fixed

- [40331](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40331) Extra transfer generated when transfer for hold cancelled due to checkin at incorrect library
  - **Backported from version(s):** 25.11.00,25.05.04,24.11.10

### ILL

#### Other bugs fixed

- [41237](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=41237) OPAC created requests ignore library selection, always default to patron's library
  - **Backported from version(s):** 26.05.00
  >This fixes a bug on the OPAC create ILL request form which was always setting the library to the patron's library, ignoring the library selection made on the form.

### OPAC

#### Other bugs fixed

- [33012](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=33012) Accessibility: Some navigation items in OPAC cannot be accessed by keyboard (search history, log out)
  - **Backported from version(s):** 25.05.00,24.11.10
  >This fixes the OPAC navigation menus when logged in so that keyboard users can use the tab key to navigation menus. Some menu items (such as some list options, search history, and log out) were not selectable when just using the tab key.
- [40780](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40780) Removing rows on advanced search should not lose focus
  - **Backported from version(s):** 25.11.00,25.05.04

### Plugin architecture

#### Other bugs fixed

- [40653](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40653) plugins/run.pl controller drops authentication if logging in to that route
  - **Backported from version(s):** 25.11.00,25.05.04

### Point of Sale

#### Other bugs fixed

- [40625](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40625) Prevent cashup re-submissions on page reload
  - **Backported from version(s):** 25.11.00,25.05.06,24.11.11

### SIP2

#### Other bugs fixed

- [32934](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=32934) SIP checkouts using "no block" flag have a calculated due rather than the specified due date
  - **Backported from version(s):** 25.11.00,25.05.02,24.11.08
- [41369](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=41369) SIP payments have no branchcode
  - **Backported from version(s):** 26.05.00
  >This fixes SIP2 based payments, so that a branchcode (institution id) is now recorded for the payment.

### Searching - Elasticsearch

#### Other bugs fixed

- [40980](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40980) Clicking a search facet without logging in may trigger a cud-login error
  - **Backported from version(s):** 26.05.00,25.11.01
  >This fixes using facets in the OPAC for searching when not logged in, where Elasticsearch or OpenSearch is used as the search engine. In some circumstances, a 403 Forbidden Error was incorrectly generated (this is related to changes made in previous versions of Koha to improve form security).

### Staff interface

#### Other bugs fixed

- [40734](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40734) Libraries additional fields don't appear when creating a new library
  - **Backported from version(s):** 25.11.00,25.05.04
  >This fixes adding a new library when additional fields are configured in Administration > Additional fields > Libraries (branches). The additional fields were not shown when creating a new library (they were shown when editing an existing library).

## Enhancements 

### Acquisitions

#### Enhancements

- [38689](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=38689) EDIFACT errors should log to a staff accessible location
  - **Backported from version(s):** 25.05.00
  >**Summary:**  
  >Previously, EDIFACT import errors were only visible in server logs, making troubleshooting difficult for staff.
  >
  >**Fix:**  
  >Errors are now logged in a location accessible via the staff interface, allowing easier review and follow-up.
  >
  >**Impact:**  
  >Helps acquisitions staff and sysadmins quickly identify and resolve issues with vendor data.
  >

  **Sponsored by** *Open Fifth*

### Circulation

#### Enhancements

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

### Database

#### Enhancements

- [41409](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=41409) Streetnumber has a different data type in borrower_modifications
  - **Backported from version(s):** 26.05.00,25.11.02
  >The database data types for these fields are tinytext in the borrowers table and varchar(10) in the borrower_modifications table:
  >
  >- streetnumber (a patron's main address street number field)
  >- B_streetnumber (a patron's alternate address street number field)
  >
  >This enhancement updates the borrower_modifications table so that the fields are now tinytext, consistent with the borrowers table.

  **Sponsored by** *Cheshire Libraries Shared Services*

### Fines and fees

#### Enhancements

- [38457](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=38457) Add additional fields support to debit types
  - **Backported from version(s):** 25.05.00
  >**Summary:**  
  >Debit types were previously limited in customization, restricting the ability to store extra metadata.
  >
  >**Enhancement:**  
  >Additional fields can now be configured for debit types, allowing storage of custom financial codes or reporting data.
  >
  >**Impact:**  
  >Improves flexibility for libraries with advanced accounting or reporting requirements.

  **Sponsored by** *OpenFifth*

### Hold requests

#### Enhancements

- [40769](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40769) Highlight hold fees when placing a hold from the staff interface
  - **Backported from version(s):** 26.05.00
  >This enhancement adds hold fee information display in the staff interface's hold
  >request interface, bringing it to feature parity with the OPAC.
  > 
  >The OPAC already shows patrons the fee that will be charged for placing
  >a hold, but the staff interface did not display this information when staff
  >place holds on behalf of patrons. This creates a transparency gap where
  >staff cannot inform patrons about potential charges.

### ILL

#### Enhancements

- [38685](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=38685) ILL pages have incomplete breadcrumbs
  - **Backported from version(s):** 25.05.00
- [39917](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39917) Display a prompt for status alias when completing a request if ILL_STATUS_ALIAS in use
  - **Backported from version(s):** 25.11.00,25.05.03
  >This enhancement to ILL requests lets you select a 'status alias' when marking requests as complete. This is only shown when values are defined for the ILL_STATUS_ALIAS authorized values category. The alias is then shown in the status field on the request details page, and in the status column for the list of ILL requests. If there are no values defined, then you are not prompted to select a status alias.

  **Sponsored by** *NHS England (National Health Service England)*
- [40012](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40012) Standard form missing publisher for journal articles
  - **Backported from version(s):** 25.11.00
- [40262](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40262) ILL - Save the fact that copyright clearance has been confirmed by the patron
  - **Backported from version(s):** 25.11.00
  >This enhancement to copyright clearance for interlibrary loan requests:
  >- records the copyright clearance in the database (it previously wasn't)
  >- shows the message "Patron has confirmed copyright clearance for this request" on the request page
  >
  >(This requires text in the ILLModuleCopyrightClearance HTML customization.)

### MARC Bibliographic data support

#### Enhancements

- [38096](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=38096) Field 857 is not considered for display on XSLT files
  - **Backported from version(s):** 26.05.00

### OPAC

#### Enhancements

- [39698](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39698) Add option to expand responsive datatable rows by default
  >This enhancement lets you control the default responsiveness of OPAC tables, such as OPAC search history. New system preference 'OPACTableColExpandedByDefault' controls the default behavor. Tables are collapsed by default with a '+' to expand, and when expanded a '-' is visible to collapse. (This enhancement is a result of recommendations from a recent accessibility audit.)
  >
  >** Sponsored by: Open Fifth **

### Patrons

#### Enhancements

- [39579](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39579) Add ability to restrict patron date of birth on self registration
  - **Backported from version(s):** 25.05.00
  >This new feature adds a new system preference `PatronSelfRegistrationAgeRestriction` to restrict the maximum age of patrons self registering.

  **Sponsored by** *Cheshire Libraries Shared Services*
- [41411](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=41411) Streetnumber field is limited to 10 characters despite being tinytext
  - **Backported from version(s):** 26.05.00,25.11.02
  >The input form for a patron's main and alternative address street number fields are limited to 10 characters, even though the underlying database field can have up to 255 characters.
  >
  >This enhancement removes this 10-character limit, which makes it more useful where house names are used instead of house numbers.

### Plugin architecture

#### Enhancements

- [39522](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39522) Add hooks to allow 'Valuebuilder' plugins to be installable
  - **Backported from version(s):** 26.05.00

### SIP2

#### Enhancements

- [40800](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40800) TransferArrived needlessly triggers alerts in SIP

### Searching - Elasticsearch

#### Enhancements

- [40890](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40890) Make batch_size configurable for koha-es-indexer
  - **Backported from version(s):** 25.11.00
  >A new configuration entry has been introduced in `koha-conf.xml` to control how many Elasticsearch update tasks the indexer processes per iteration.
  >
  >Previously, the indexer defaulted to a batch size of 10. While the `koha-es-indexer` command supported overriding this with the `--batch_size` parameter, there was no way to set a different default value.
  >
  >This change is particularly beneficial for large sites, where the indexer may otherwise struggle to keep pace with the update queue during peak activity.

### Staff interface

#### Enhancements

- [15461](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=15461) Add shelving location to holdings table as a separate column
  - **Backported from version(s):** 25.05.00
  >This enhancement adds a separate column for the display of shelving location in the staff interface's holdings table.
- [38663](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=38663) Add additional fields to libraries
  - **Backported from version(s):** 25.05.00
  >This enhancement lets you add additional fields to libraries (Koha administration > Additional parameters > Additional fields ).

### Templates

#### Enhancements

- [38720](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=38720) HTML1 no longer valid? TT tags can be present in HTML without breaking the translator tool
  - **Backported from version(s):** 25.05.00

### Test Suite

#### Enhancements

- [39007](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39007) Add last_audit to the sushi_service API spec
  - **Backported from version(s):** 25.05.00,24.11.03,24.05.07,23.11.12

## New system preferences

- LostChargesControl
- OPACTableColExpandedByDefault
- PatronSelfRegistrationAgeRestriction

## Credits

We thank the following libraries, companies, and other institutions who sponsored
new features in this release:
<div style="column-count: 2;">

- Cheshire Libraries Shared Services
- MAIN Library Alliance
- NHS England (National Health Service England)
- [OpenFifth](https://openfifth.co.uk)
</div>

Contributors to this release:
<div style="column-count: 2;">

- Pedro Amorim (31)
- Tomás Cohen Arazi (2)
- Alexander Blanchard (5)
- Matt Blenkinsop (14)
- Nick Clemens (7)
- Jake Deery (7)
- Jonathan Druart (3)
- Katrin Fischer (1)
- Lucas Gass (3)
- Kyle M Hall (3)
- David Nind (1)
- Jacob O'Mara (2)
- Martin Renvoize (31)
- Lisette Scheer (1)
- Slava Shishkin (1)
- Lari Strand (1)
- Chloe Zermatten (3)
</div>

Contributing organizations:
<div style="column-count: 2;">

- [Bibliotheksservice-Zentrum Baden-Württemberg (BSZ)](https://bsz-bw.de) (1)
- [ByWater Solutions](https://bywatersolutions.com) (14)
- David Nind (1)
- Independant Individuals (1)
- Koha Community Developers (3)
- [Koha-Suomi Oy](https://koha-suomi.fi) (1)
- [OpenFifth](https://openfifth.co.uk) (93)
- [Theke Solutions](https://theke.io) (2)
</div>

Testers and sign-offs:
<div style="column-count: 2;">

- Pedro Amorim (1)
- Emmanuel Bétemps (2)
- Trevor Diamond (4)
- Jonathan Druart (1)
- Laura Escamilla (3)
- Katrin Fischer (11)
- Brendan Gallagher (4)
- Lucas Gass (5)
- Stephen Graham (2)
- Kyle M Hall (10)
- Tomas Jiglind (1)
- Brendan Lawlor (1)
- Christine Lee (1)
- Owen Leonard (6)
- David Nind (19)
- Martin Renvoize (26)
- Marcel de Rooy (4)
- Lisette Scheer (8)
- Fridolin Somers (7)
- Baptiste Wojtkowski (9)
</div>

---

*Generated by Open Fifth release tools on 12 Feb 2026 10:12:38*

*These are internal tracking notes and may include patches not yet available in community releases.*
