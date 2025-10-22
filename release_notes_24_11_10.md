# RELEASE NOTES FOR KOHA 24.11.09
22 Oct 2025

Koha is the first free and open source software library automation
package (ILS). Development is sponsored by libraries of varying types
and sizes, volunteers, and support companies from around the world. The
website for the Koha project is:

- [Koha Community](https://koha-community.org)

Koha 24.11.09 can be downloaded from:

- [Download](https://download.koha-community.org/koha-24.11.09.tar.gz)

Installation instructions can be found at:

- [Koha Wiki](https://wiki.koha-community.org/wiki/Installation_Documentation)
- OR in the INSTALL files that come in the tarball

Koha 24.11.09 is a bugfix/maintenance release.

It includes 16 enhancements, 26 bugfixes.

**System requirements**

You can learn about the system components (like OS and database) needed for running Koha on the [community wiki](https://wiki.koha-community.org/wiki/System_requirements_and_recommendations).


## Bugfixes

### Accessibility

#### Other bugs fixed

- [39274](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39274) HTML bg-* elements are low contrast

  **Sponsored by** *Athens County Public Libraries*
- [39489](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39489) 'Refine your search' should have an aria-expanded attribute
  >This fixes the "Refine your search" section in the OPAC. For screen reader users on smaller screens, it now correctly announces that it is an expandable section, instead of a link (by adding an aria-expanded attribute).
  >
  >Explanation: The 'Refine your search' expandable section in the Koha OPAC was not clearly announced by screen readers for smaller screen sizes. This is because the expandable section was identified and announced as a link. This resulted in screen reader users incorrectly expecting a link to another page, and not being informed that it was an expandable section.
- [39490](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39490) Table columns missing headings
- [39492](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39492) Add missing aria label on the OPAC holdings table browse shelf link
  >This enhancement adds an aria label to the browse shelf link in the OPAC holdings table. This provides more information about what the link does for those using assistive technology, such as screen readers.
- [39494](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39494) Announce status messaging on login page
- [39497](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39497) 'Lists' page tabs should be marked as such
- [39502](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39502) Web Usability Accessibility Audit - Decorative Images Don't Need alt Text
- [39547](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39547) Required fields not conveyed programmatically in patron details in the OPAC

### Acquisitions

#### Critical bugs fixed

- [33430](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=33430) Use REST API for suggestions tables
  >This development reworks the purchase suggestion tables to use the API, which results in much faster load times when there are many suggestions.

#### Other bugs fixed

- [39787](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39787) Sending EDI order from basket fails if only one Library EAN exists
- [40593](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40593) Can't search all columns in Acquisitions Suggestions table

### Architecture, internals, and plumbing

#### Other bugs fixed

- [40725](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40725) DBRev 23.12.00.053 should be made more resilient

### Circulation

#### Other bugs fixed

- [38861](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=38861) Error loading the table in the bookings to collect report
  >This patch fixes a bug where the bookings to collect table was not loading correctly.
- [39212](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39212) Error when attempting to edit a booking
- [39389](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39389) Cannot use dataTables export function on checkout table in members/moremember.pl

### ERM

#### Other bugs fixed

- [40737](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40737) Usage statistics data provider "Import logs" table does not render if "Imported by": "Cronjob"

### Hold requests

#### Other bugs fixed

- [40331](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40331) Extra transfer generated when transfer for hold cancelled due to checkin at incorrect library

### OPAC

#### Other bugs fixed

- [33012](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=33012) Accessibility: Some navigation items in OPAC cannot be accessed by keyboard (search history, log out)
  >This fixes the OPAC navigation menus when logged in so that keyboard users can use the tab key to navigation menus. Some menu items (such as some list options, search history, and log out) were not selectable when just using the tab key.
- [40780](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40780) Removing rows on advanced search should not lose focus

### Patrons

#### Other bugs fixed

- [40807](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40807) Quick add form does not include 'username' when it is included in BorrowerMandatoryFields

### SIP2

#### Other bugs fixed

- [32934](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=32934) SIP checkouts using "no block" flag have a calculated due rather than the specified due date
- [40675](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40675) Carriage return in patron note message breaks SIP

### Searching - Elasticsearch

#### Other bugs fixed

- [40980](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40980) Clicking a search facet without logging in may trigger a cud-login error

### Staff interface

#### Other bugs fixed

- [39080](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39080) Table headers of holds to pull table are incorrect size on scroll
- [40734](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40734) Libraries additional fields don't appear when creating a new library

### Tools

#### Other bugs fixed

- [32950](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=32950) MARC modification template moving subfield can lose values for repeatable fields
  >MARC modification templates now correctly preserve existing values when moving subfields within repeatable fields. Previously, moving subfields could cause data loss or duplication when the source subfield didn't exist in all instances of the repeatable field.
  >
  >**The problem:**
  >
  >When using a MARC modification template to move a subfield within a repeatable field (for example, moving 020$z to 020$a), if some 020 fields had existing $a values but no $z values, those existing $a values would be overwritten or lost.
  >
  >**Example scenario:**
  >
  >Given multiple 020 fields:
  >- 020$a with existing ISBN
  >- 020$a with another existing ISBN  
  >- 020$z with cancelled ISBN (to be moved to $a)
  >- 020$z with another cancelled ISBN (to be moved to $a)
  >
  >Previously, when moving 020$z to 020$a, the first two existing 020$a values would be replaced with values from the 020$z fields, causing data loss.
  >
  >**What's fixed:**
  >
  >- Existing subfield values in fields that don't contain the source subfield are now preserved
  >- Source subfield values are only moved to the corresponding target positions in fields that actually contain the source subfield
  >- The move operation correctly removes the source subfields after copying their values
  >- Field order and other subfields are maintained correctly
  >
  >**For cataloguers:**
  >
  >MARC modification template "move" operations now work reliably with repeatable fields. When moving subfields, only the fields that contain the source subfield will be affected, and all other existing values in the repeatable fields will be preserved.

## Enhancements 

### Acquisitions

#### Enhancements

- [38689](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=38689) EDIFACT errors should log to a staff accessible location
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

### ERM

#### Enhancements

- [39345](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39345) Koha must support COUNTER 5.1
  >This enhancement adds support to the ERM module for Release 5.1 of the Code of Practice for COUNTER Metrics that came into force in January 2025, with a requirement for reports to be delivered by the 28th of February 2025.

### Fines and fees

#### Enhancements

- [38457](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=38457) Add additional fields support to debit types
  >**Summary:**  
  >Debit types were previously limited in customization, restricting the ability to store extra metadata.
  >
  >**Enhancement:**  
  >Additional fields can now be configured for debit types, allowing storage of custom financial codes or reporting data.
  >
  >**Impact:**  
  >Improves flexibility for libraries with advanced accounting or reporting requirements.

  **Sponsored by** *Open Fifth*

### Hold requests

#### Enhancements

- [40769](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40769) Highlight hold fees when placing a hold from the staff client

### ILL

#### Enhancements

- [40012](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40012) Standard form missing publisher for journal articles
- [40262](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40262) ILL - Save the fact that copyright clearance has been confirmed by the patron
  >This enhancement to copyright clearance for interlibrary loan requests:
  >- records the copyright clearance in the database (it previously wasn't)
  >- shows the message "Patron has confirmed copyright clearance for this request" on the request page
  >
  >(This requires text in the ILLModuleCopyrightClearance HTML customization.)

### OPAC

#### Enhancements

- [39698](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39698) Add option to expand responsive datatable rows by default
  >This enhancement lets you control the default responsiveness of OPAC tables, such as OPAC search history. New system preference 'OPACTableColExpandedByDefault' controls the default behavor. Tables are collapsed by default with a '+' to expand, and when expanded a '-' is visible to collapse. (This enhancement is a result of recommendations from a recent accessibility audit.)
  >
  >** Sponsored by: Open Fifth **

### Patrons

#### Enhancements

- [39579](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39579) Add ability to restrict patron date of birth on self registration
  >This new feature adds a new system preference `PatronSelfRegistrationAgeRestriction` to restrict the maximum age of patrons self registering.

  **Sponsored by** *Cheshire Libraries Shared Services*

### Plugin architecture

#### Enhancements

- [39522](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39522) Add hooks to allow 'Valuebuilder' plugins to be installable
- [40653](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40653) plugins/run.pl controller drops authentication if logging in to that route

### Point of Sale

#### Enhancements

- [40625](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40625) Prevent cashup re-submissions on page reload

### SIP2

#### Enhancements

- [40800](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40800) TransferArrived needlessly triggers alerts in SIP

### Staff interface

#### Enhancements

- [15461](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=15461) Add shelving location to holdings table as a separate column
  >This enhancement adds a separate column for the display of shelving location in the staff interface's holdings table.
- [38663](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=38663) Add additional fields to libraries
  >This enhancement lets you add additional fields to libraries (Koha administration > Additional parameters > Additional fields ).

### Templates

#### Enhancements

- [38720](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=38720) HTML1 no longer valid? TT tags can be present in HTML without breaking the translator tool

### Test Suite

#### Enhancements

- [39007](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39007) Add last_audit to the sushi_service API spec

## New system preferences

- OPACTableColExpandedByDefault
- PatronSelfRegistrationAgeRestriction

## Documentation

The Koha manual is maintained in Sphinx. The home page for Koha
documentation is

- [Koha Documentation](https://koha-community.org/documentation/)
As of the date of these release notes, the Koha manual is available in the following languages:

- [English (USA)](https://koha-community.org/manual/24.11/en/html/)
- [French](https://koha-community.org/manual/24.11/fr/html/) (75%)
- [German](https://koha-community.org/manual/24.11/de/html/) (95%)
- [Greek](https://koha-community.org/manual/24.11/el/html/) (99%)
- [Hindi](https://koha-community.org/manual/24.11/hi/html/) (67%)

The Git repository for the Koha manual can be found at

- [Koha Git Repository](https://gitlab.com/koha-community/koha-manual)

## Translations

Complete or near-complete translations of the OPAC and staff
interface are available in this release for the following languages:
<div style="column-count: 2;">

- Arabic (ar_ARAB) (95%)
- Armenian (hy_ARMN) (100%)
- Bulgarian (bg_CYRL) (100%)
- Chinese (Simplified Han script) (86%)
- Chinese (Traditional Han script) (99%)
- Czech (68%)
- Dutch (88%)
- English (100%)
- English (New Zealand) (63%)
- English (USA)
- Finnish (99%)
- French (99%)
- French (Canada) (99%)
- German (100%)
- Greek (68%)
- Hindi (97%)
- Italian (82%)
- Norwegian Bokmål (74%)
- Persian (fa_ARAB) (96%)
- Polish (99%)
- Portuguese (Brazil) (99%)
- Portuguese (Portugal) (87%)
- Russian (94%)
- Slovak (60%)
- Spanish (99%)
- Swedish (87%)
- Telugu (67%)
- Tetum (52%)
- Turkish (83%)
- Ukrainian (73%)
- Western Armenian (hyw_ARMN) (62%)
</div>

Partial translations are available for various other languages.

The Koha team welcomes additional translations; please see

- [Koha Translation Info](https://wiki.koha-community.org/wiki/Translating_Koha)

For information about translating Koha, and join the koha-translate 
list to volunteer:

- [Koha Translate List](https://lists.koha-community.org/cgi-bin/mailman/listinfo/koha-translate)

The most up-to-date translations can be found at:

- [Koha Translation](https://translate.koha-community.org/)

## Release Team

The release team for Koha 24.11.09 is


- Release Manager: Lucas Gass

- QA Manager: Martin Renvoize

- QA Team:
  - Andrew Fuerste-Henry
  - Andrii Nugged
  - Baptiste Wojtkowski
  - Brendan Lawlor
  - David Cook
  - Emily Lamancusa
  - Jonathan Druart
  - Julian Maurice
  - Kyle Hall
  - Laura Escamilla
  - Lisette Scheer
  - Marcel de Rooy
  - Nick Clemens
  - Paul Derscheid
  - Petro V
  - Tomás Cohen Arazi
  - Victor Grousset

- Documentation Manager: David Nind

- Documentation Team:
  - Aude Charillon
  - Caroline Cyr La Rose
  - Donna Bachowski
  - Heather Hernandez
  - Kristi Krueger
  - Philip Orr

- Translation Manager: Jonathan Druart


- Wiki curators: 
  - George Williams
  - Thomas Dukleth

- Release Maintainers:
  - 25.05 -- Paul Derscheid
  - 24.11 -- Fridolin Somers
  - 24.05 -- Jesse Maseto
  - 22.11 -- Catalyst IT (Wainui, Alex, Aleisha)

- Release Maintainer assistants:
  - 25.05 -- Martin Renvoize
  - 24.11 -- Baptiste Wojtkowski
  - 24.05 -- Laura Escamilla

## Credits

We thank the following libraries, companies, and other institutions who are known to have sponsored
new features in Koha 24.11.09
<div style="column-count: 2;">

- Athens County Public Libraries
- Cheshire Libraries Shared Services
- [Open Fifth](https://openfifth.co.uk/)
</div>

We thank the following individuals who contributed patches to Koha 24.11.09
<div style="column-count: 2;">

- Pedro Amorim (14)
- Alexander Blanchard (6)
- Matt Blenkinsop (10)
- Nick Clemens (4)
- Jake Deery (7)
- Jonathan Druart (5)
- Katrin Fischer (1)
- Lucas Gass (5)
- Kyle M Hall (1)
- Owen Leonard (1)
- David Nind (1)
- Jacob O'Mara (2)
- Martin Renvoize (31)
- Bernard Scaife (1)
- Lisette Scheer (1)
- Slava Shishkin (1)
- Lari Strand (1)
- Chloe Zermatten (4)
</div>

We thank the following libraries, companies, and other institutions who contributed
patches to Koha 24.11.09
<div style="column-count: 2;">

- Athens County Public Libraries (1)
- [Bibliotheksservice-Zentrum Baden-Württemberg (BSZ)](https://bsz-bw.de) (1)
- [ByWater Solutions](https://bywatersolutions.com) (11)
- David Nind (1)
- Independant Individuals (1)
- Koha Community Developers (5)
- [Koha-Suomi Oy](https://koha-suomi.fi) (1)
- [Open Fifth](https://openfifth.co.uk/) (75)
</div>

We also especially thank the following individuals who tested patches
for Koha
<div style="column-count: 2;">

- Tomás Cohen Arazi (1)
- Emmanuel Bétemps (2)
- Nick Clemens (1)
- Jonathan Druart (1)
- Magnus Enger (1)
- Laura Escamilla (2)
- Katrin Fischer (11)
- Brendan Gallagher (4)
- Lucas Gass (3)
- Kyle M Hall (9)
- Andrew Fuerste Henry (1)
- Janne (1)
- Tomas Jiglind (1)
- Kristi Krueger (2)
- Brendan Lawlor (2)
- Christine Lee (1)
- David Nind (15)
- Eric Phetteplace (1)
- Martin Renvoize (18)
- Marcel de Rooy (4)
- Bernard Scaife (2)
- Lisette Scheer (8)
- Fridolin Somers (7)
- Baptiste Wojtkowski (9)
</div>





We regret any omissions.  If a contributor has been inadvertently missed,
please send a patch against these release notes to koha-devel@lists.koha-community.org.

## Revision control notes

The Koha project uses Git for version control.  The current development
version of Koha can be retrieved by checking out the main branch of:

- [Koha Git Repository](https://git.koha-community.org/koha-community/koha)

The branch for this version of Koha and future bugfixes in this release
line is 24.11.o5th.

## Bugs and feature requests

Bug reports and feature requests can be filed at the Koha bug
tracker at:

- [Koha Bugzilla](https://bugs.koha-community.org)

He rau ringa e oti ai.
(Many hands finish the work)

Autogenerated release notes updated last on 22 Oct 2025 14:27:56.
