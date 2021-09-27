---
title: Writing CRAN Task Views
author: Achim Zeileis, CRAN Task View Editors
date: 2021-09-27
---


## Overview

CRAN task views aim to provide some guidance which packages on the Comprehensive
R Archive Network (CRAN) at <https://CRAN.R-project.org/> are relevant for tasks
related to a certain topic. They give a brief overview of the included packages
and can be automatically installed using the
[ctv](https://CRAN.R-project.org/package=ctv) package. The views are intended to
have a sharp focus so that it is sufficiently clear which packages should be
included (or excluded) - and they are not meant to endorse the "best" packages
for a given task.

For more details on how task views are maintained and how to contribute to
task views, see <https://github.com/cran-task-views/ctv/>. In the following
the details of the R/Markdown format for CRAN task views is presented.


## Format

The file format for CRAN task views leverages the R/Markdown format
(Xie, Allaire, Grolemund 2019, see <https://bookdown.org/yihui/rmarkdown/>)
so that standard Markdown can be used for formatting and structuring the
text and a handful of special R functions are provided to link to CRAN
packages, other task views, GitHub projects, etc.

> In `ctv` versions prior to 0.9-0 (released in late 2021), task views used
> an XML-based format (introduced in Zeileis 2005, _R News_, **5**(1), 39-40).
> See below for converting task views from the old XML-based format to the
> new R/Markdown format.

The format is mostly self-explanatory and is illustrated below using an
excerpt from the `Econometrics` task view which is hosted on CRAN at
<https://CRAN.R-project.org/view=Econometrics> and maintained on GitHub at
<https://github.com/cran-task-views/Econometrics/>.

```
---
name: Econometrics
topic: Econometrics
maintainer: Achim Zeileis, Laurent Berge, Grant McDermott, Kevin Tappe
email: Achim.Zeileis@R-project.org
version: 2021-09-27
---

Base R ships with a lot of functionality useful for computational econometrics,
in particular in the stats package. This functionality is complemented by many
packages on CRAN, a brief overview is given below. There is also a considerable
overlap between the tools for econometrics in this view and those in the task
views on `r view("Finance")`, `r view("SocialSciences")`, and
`r view("TimeSeries")`.

Further information can be formatted with standard Markdown syntax, e.g., for
_emphasizing text_ or showing something really important in **bold face**.
R/Markdown syntax with special functions can be used to link to a standard
package like `r pkg("ivreg")` or an important "core" package like
`r pkg("AER", priority = "core")`.

### Links
- [Journal of Statistical SoftwareL Econometrics in R](https://www.jstatsoft.org/v27/)
- [The Title of a Relevant Homepage](http://path/to/homepage/)
```

The document structure consists of three main blocks: (1) Some metainformation
is given in the YAML header at the beginning (separated by lines with `---`),
followed by (2) the information in the main text, and (3) a concluding special
section called `Links`.


## Details

The metainformation needs to provide the following elements:

* `name` gives the name of the task view in _CamelCase_. This is used as the
identifier for installing the view and as the name for the R/Markdown file, e.g.,
`Econometrics.md`, and the auto-generated HTML file, e.g., `Econometrics.html`.
Hence, it should be not too long (typically 1-3 words) and contain no special
characters like.

* `topic` is a plain text specification of the topic of the task view. In the
example above it is identical to the `name` but is often a somewhat longer and
more detailed title (in title case).

* `maintainer` gives the name(s) of the maintainer(s) in a comma-separated list.
The principal contact should be listed first and ideally there are a couple of
further co-maintainers that help keeping the task view up to date.

* `email` is the e-mail address of the principal contact or possibly a dedicated
mailing list shared by the co-maintainers.

* `version` is specified by a date in ISO format.

The information in the main text should be a short description of the packages,
explaining which packages are useful for which tasks. Standard Markdown format
(see <https://en.wikipedia.org/wiki/Markdown> for an overview) can be used to
structure the document with sections, itemized and enumerated lists, bold face,
italics, etc. Additionally, short R code chunks with special functions for linking
to resources in the same repository: `pkg()` for normal packages,
`pkg(..., priority = "core")` for important "core" packages,  and
`view()` for related task views. A convenience function `doi()` creates links for
DOIs (digital object identifiers). The distinction between "normal" and "core"
packages is only important for the installation of CRAN task views because the
user can specify whether all packages (default) or only the most important core
packages should be installed (with all their dependencies).

Moreover, code projects in other repositories can be linked by using the functions:

* `bioc()` for Bioconductor packages at <https://www.Bioconductor.org/>.
* `github()` for GitHub projects at <https://www.GitHub.com/>.
* `rforge()` for R-Forge projects at <https://R-Forge.R-project.org/>.
* `gcode()` for projects in the Google Code archive at <https://Code.Google.com/archive/>.
* `ohat()` for Omegahat packages at <http://www.Omegahat.net/>.

Note however that CRAN task views are intended mainly for packages on CRAN (as the
name conveys). Thus, links to other repositories should be used for _important_
packages/projects but not list _all_ potentially relevant repositories. Also, it
is not necessary to list the GitHub projects for all listed CRAN packages as these
are typically provided on the package's CRAN web page.

All CRAN packages included with the `pkg()` function will be listed in a dedicated
list below the information text when rendering the HTML version of the task view.
Also, the task views as well as packages/projects in other repositories will be
included automatically in the list of links at the end of the HTML version.

Finally, additional links - e.g., to books, papers, blogs, interest groups, mailing
lists, etc. - can be included in the `Links` section at the end of the file in
a standard itemized list. As explained above this list of links will be complemented
automatically with links generated from the functions `view()`, `bioc()`, `github()`,
etc.


## Working with task view files in R

To check whether a task view file has been formatted properly it can be read into
R and printed. This should display the metainformation and the list of packages.
Subsequently, it can be rendered to an HTML page and displayed in a browser for
checking whether the information text is processed correctly.

For illustration, the code below employs the `Econometrics.ctv` file shipped
within the `ctv` package. Instead a local `MyNewView.md` with resulting
`MyNewView.html` could be used as well.

```
library("ctv")
x <- read.ctv(system.file("ctv", "Econometrics.ctv", package = "ctv"))
print(x)
ctv2html(x)
browseURL("Econometrics.html")
```

Note that the code above is intended for authors of CRAN task views. For end-users
the functions `available.views()`, `install.views()`, and `update.views()` are
relevant. See <https://github.com/cran-task-views/ctv/> for more details.


## Converting the legacy XML format to R/Markdown

The `ctv` package provides an (unexported) R function to facilitate the transition
from the legacy XML format for the task view files to the new R/Markdown format
described above. Simply using

```
ctv:::ctv_xml_to_rmd("MyView.ctv")
```

will create a `MyView.Rmd` file from the `.ctv` file. This should do most necessary
transformations automatically. However, it is recommended to thoroughly check
the resulting R/Markdown file and improve it as appropriate.

