## CRAN Task View Initiative

### About

CRAN task views aim to provide some guidance which packages on the Comprehensive
R Archive Network (CRAN) at <https://CRAN.R-project.org/> are relevant for tasks
related to a certain topic. They give a brief overview of the included packages
and can be automatically installed using the
[ctv](https://CRAN.R-project.org/package=ctv) package. The views are intended to
have a sharp focus so that it is sufficiently clear which packages should be
included (or excluded) - and they are not meant to endorse the "best" packages
for a given task.

To automatically install the views, the [ctv](https://CRAN.R-project.org/package=ctv)
package needs to be installed, e.g., via

```
install.packages("ctv")
```

and then the views can be installed via `install.views()` or `update.views()`
(where the latter only installs those packages are not installed and up-to-date),
e.g.,

```
ctv::install.views("Econometrics")
ctv::update.views("Econometrics")
```

The task views as a whole are overseen and coordinated by the _CRAN Task View
Editors_ and each individual task view is maintained by a group of volunteers.
See below for details on how to contribute to an existing task view or propose
a new one.


### CRAN Task View Editors

* [Henrik Bengtsson](https://github.com/HenrikBengtsson)
* [Roger Bivand](https://github.com/rsbivand)
* [Dirk Eddelbuettel](https://github.com/eddelbuettel)
* [Heather Turner](https://github.com/hturner)
* [Achim Zeileis](https://github.com/zeileis)

**FIXME:** Which additional information to add here? Just GitHub handle?
With text or icon? Affiliation? Personal web page?

* RSB: Do we want contact with the group as such - that would suggest issues in this repo for this group?
  Or is it OK for contact to go randomly to an editor? If the former, no handles here at all, or maybe just
  `*@R-project.org`?  
  Z: Typically, contact will be with the group as such, i.e., through issues in this repo, especially for
  proposing new task views which should be described in [Proposal](Proposal.md). However, as we think about
  this like an editorial board we would typically also list the affiliation for a scientific journal along
  with potentially further information (see e.g., [JSS Editorial Team](https://www.jstatsoft.org/about/editorialTeam)).
  And although we start now with a team of editors that are all R Foundation members, this will change as
  we will try to involve some younger and more diverse CTV Editors as well.
  
* RSB: In any case, contact about the contents of individual TVs should be by issue/PR for that specific TV.  
  Z: Yes, completely agree. Would you mind outlining a potential workflow with in [Contributing](Contributing.md)?

### Available task views

* [Econometrics](https://github.com/cran-task-views/Econometrics/)

**FIXME:** Maintain this list manually? Or generate it automatically? If so, how?

* RSB: Do we expect all TVs to be hosted by this organisation (no?)?  
  Z: Yes. All official task views should be hosted by this organization.

* RSB: I feel that as TVs convert, this group may need to offer help to get the TV maintainers
  feeling confident, but the more they take responsibility the better.  
  Z: Yes, we should help them getting started. Also we will push for teams of maintainers
  (rather than a single person) so that ideally at least one person in the maintainer team
  would be more confident with the technical/GitHub aspects.


### How to contribute?

For contributing to an existing task view please go to the respective repository
(see links above) and follow the guidelines in [Contributing](Contributing.md).

For proposing a new task view please follow the guidelines in [Proposal](Proposal.md).

Technical documentation about the task view format is in [Documentation](Documentation.md).

All contributions must be made under the following [Code of conduct](CodeOfConduct.md).
