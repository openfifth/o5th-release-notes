# RELEASE NOTES FOR KOHA 24.11.05
18 Jun 2025

Koha is the first free and open source software library automation
package (ILS). Development is sponsored by libraries of varying types
and sizes, volunteers, and support companies from around the world. The
website for the Koha project is:

- [Koha Community](https://koha-community.org)

Koha 24.11.05 can be downloaded from:

- [Download](https://download.koha-community.org/koha-24.11.05.tar.gz)

Installation instructions can be found at:

- [Koha Wiki](https://wiki.koha-community.org/wiki/Installation_Documentation)
- OR in the INSTALL files that come in the tarball

Koha 24.11.05 is a bugfix/maintenance release.

It includes 5 enhancements, 4 bugfixes.

**System requirements**

You can learn about the system components (like OS and database) needed for running Koha on the [community wiki](https://wiki.koha-community.org/wiki/System_requirements_and_recommendations).


## Bugfixes

### Acquisitions

#### Critical bugs fixed

- [33430](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=33430) Use REST API for suggestions tables
  >This development reworks the purchase suggestion tables to use the API, which results in much faster load times when there are many suggestions.

### Circulation

#### Other bugs fixed

- [38861](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=38861) Error loading the table in the bookings to collect report
  >This patch fixes a bug where the bookings to collect table was not loading correctly.
- [39212](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39212) Error when attempting to edit a booking

### Staff interface

#### Other bugs fixed

- [39080](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39080) Table headers of holds to pull table are incorrect size on scroll

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

### ILL

#### Enhancements

- [40012](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=40012) Standard form missing publisher for journal articles

### Patrons

#### Enhancements

- [39579](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39579) Add ability to restrict patron date of birth on self registration
  >This new feature adds a new system preference `PatronSelfRegistrationAgeRestriction` to restrict the maximum age of patrons self registering.

  **Sponsored by** *Cheshire Libraries Shared Services*

### Test Suite

#### Enhancements

- [38818](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=38818) Add diag option to t::lib::Mocks::Logger

  **Sponsored by** *Open Fifth*
- [39007](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=39007) Add last_audit to the sushi_service API spec

## New system preferences

- PatronSelfRegistrationAgeRestriction

## Documentation

The Koha manual is maintained in Sphinx. The home page for Koha
documentation is

- [Koha Documentation](https://koha-community.org/documentation/)
As of the date of these release notes, the Koha manual is available in the following languages:

- [English (USA)](https://koha-community.org/manual/24.11/en/html/)
- [French](https://koha-community.org/manual/24.11/fr/html/) (73%)
- [German](https://koha-community.org/manual/24.11/de/html/) (98%)
- [Greek](https://koha-community.org/manual/24.11/el/html/) (99%)
- [Hindi](https://koha-community.org/manual/24.11/hi/html/) (70%)

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
- Czech (67%)
- Dutch (88%)
- English (100%)
- English (New Zealand) (63%)
- English (USA)
- Finnish (100%)
- French (100%)
- French (Canada) (98%)
- German (99%)
- Greek (67%)
- Hindi (97%)
- Italian (81%)
- Norwegian Bokmål (74%)
- Persian (fa_ARAB) (97%)
- Polish (100%)
- Portuguese (Brazil) (98%)
- Portuguese (Portugal) (88%)
- Russian (94%)
- Slovak (61%)
- Spanish (99%)
- Swedish (87%)
- Telugu (68%)
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

The release team for Koha 24.11.05 is


- Release Manager: 

## Credits

We thank the following libraries, companies, and other institutions who are known to have sponsored
new features in Koha 24.11.05
<div style="column-count: 2;">

- Cheshire Libraries Shared Services
- [Open Fifth](https://openfifth.co.uk/)
</div>

We thank the following individuals who contributed patches to Koha 24.11.05
<div style="column-count: 2;">

- Pedro Amorim (2)
- Alexander Blanchard (1)
- Matt Blenkinsop (9)
- Jake Deery (4)
- Jonathan Druart (2)
- Katrin Fischer (1)
- Lucas Gass (2)
- Martin Renvoize (12)
- Lisette Scheer (1)
</div>

We thank the following libraries, companies, and other institutions who contributed
patches to Koha 24.11.05
<div style="column-count: 2;">

- [Bibliotheksservice-Zentrum Baden-Württemberg (BSZ)](https://bsz-bw.de) (1)
- [ByWater Solutions](https://bywatersolutions.com) (3)
- Koha Community Developers (2)
- [Open Fifth](https://openfifth.co.uk/) (28)
</div>

We also especially thank the following individuals who tested patches
for Koha
<div style="column-count: 2;">

- Emmanuel Bétemps (1)
- Katrin Fischer (13)
- Kyle M Hall (10)
- Kristi Krueger (2)
- David Nind (1)
- Martin Renvoize (2)
- Marcel de Rooy (1)
- Lisette Scheer (8)
- Fridolin Somers (7)
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

Autogenerated release notes updated last on 18 Jun 2025 09:26:44.
