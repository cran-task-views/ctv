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


### Available task views

* [Econometrics](https://github.com/cran-task-views/Econometrics/)

**FIXME:** Maintain this list manually? Or generate it automatically? If so, how?


### How to contribute?

For contributing to an existing task view please go to the respective repository
(see links above) and follow the guidelines in `CONTRIBUTING.md`.

For proposing a new task view please follow the guidelines in `PROPOSAL.md`.

Technical documentation about the task view format is in `DOCUMENTATION.md`.

All contributions must be made under the following `CODEOFCONDUCT.md`.

**FIXME:** Better file names? How to make the file names active links?

