## Overview

CRAN task views aim to provide some guidance which packages on the [Comprehensive
R Archive Network (CRAN)](https://CRAN.R-project.org/) are relevant for tasks
related to a certain topic. They give a brief overview of the included packages
which can also be automatically installed using the
[ctv](https://CRAN.R-project.org/package=ctv) package. The views are intended to
have a sharp focus so that it is sufficiently clear which packages should be
included (or excluded) - and they are not meant to endorse the "best" packages
for a given task.

For more details on how to use task views and how to contribute to them, see the
[CRAN Task View Initiative on GitHub](https://github.com/cran-task-views/ctv/).
In the following the technical details of the R/Markdown format for CRAN task views
are presented which is intended primarily for task view maintainers.


## Format

The file format for CRAN task views leverages the R/Markdown format
(see [Xie, Allaire, Grolemund 2019](https://bookdown.org/yihui/rmarkdown/))
so that standard Markdown can be used for formatting and structuring the
text and a handful of special R functions are provided to link to CRAN
packages, other task views, GitHub projects, etc.

> In `ctv` versions prior to 0.9-0 (released in late 2021), task views used
> an XML-based format (introduced in Zeileis 2005, _R News_, **5**(1), 39-40
> [[PDF](https://www.R-project.org/doc/Rnews/Rnews_2005-1.pdf)]).
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
maintainer: Achim Zeileis, Grant McDermott, Kevin Tappe
email: Achim.Zeileis@R-project.org
version: 2022-09-13
source: https://github.com/cran-task-views/Econometrics/
---

Base R ships with a lot of functionality useful for (computational) econometrics,
in particular in the stats package. This functionality is complemented by many
packages on CRAN, a brief overview is given below. There is also a certain
overlap between the tools for econometrics in this view and those in the task
views on ``r 'r'` view("Finance")`, ``r 'r'` view("TimeSeries")`, and
``r 'r'` view("CausalInference")`.

Further information can be formatted with standard Markdown syntax, e.g., for
_emphasizing text_ or showing something really important in **bold face**.
R/Markdown syntax with special functions can be used to link to a standard
package like `r pkg("mlogit")` or an important "core" package like
`r pkg("AER", priority = "core")`.

### Links
- Articles: [Special Volume on "Econometrics in R" in JSS (2008)](http://www.jstatsoft.org/v27/)
- [The Title of a Relevant Homepage](http://path/to/homepage/)
```

The document structure consists of three main blocks: (1) Some metainformation
is given in the YAML header at the beginning (separated by lines with `---`),
followed by (2) the information in the main text, and (3) a concluding special
section called `### Links`.


## Details

### Metainformation

The metainformation needs to provide the following elements:

* `name` gives the name of the task view in _CamelCase_. This is used as the
identifier for installing the view and as the name for the Markdown file, e.g.,
`Econometrics.md`, and the auto-generated HTML file, e.g., `Econometrics.html`.
Hence, it should be not too long (typically 1-3 words) and contain no special
characters like spaces, hyphens, etc.

* `topic` is a plain text specification of the topic of the task view. In the
example above it is identical to the `name` but is often a somewhat longer and
more detailed title (in title case).

* `maintainer` gives the name(s) of the maintainer(s) in a comma-separated list.
The principal contact should be listed first, followed by a couple of further
co-maintainers that help keeping the task view up to date.

* `email` is the e-mail address of the principal contact or possibly a dedicated
mailing list shared by the co-maintainers.

* `version` is specified by a date in ISO 8601 format (yyyy-mm-dd).

* Additionally, there are may be optional elements: `source` can be used to link
to the source repository (typically on GitHub) and `url` for the URL of the
published task view, respectively. The latter is inserted automatically for the
official task views on CRAN.


### Main text

The information in the main text should be a short description of the packages,
explaining which packages are useful for which tasks.
[Standard Markdown format](https://en.wikipedia.org/wiki/Markdown) can be used to
structure the document with sections, itemized and enumerated lists, bold face,
italics, etc.

Additionally, short R code chunks with special functions are used for linking to
resources in the same repository: `pkg()` for normal packages,
`pkg(..., priority = "core")` for important "core" packages,  and `view()` for
related task views. A convenience function `doi()` creates links for
DOIs (digital object identifiers).

* The distinction between "normal" and "core" packages is only important for the
installation of CRAN task views because the user can specify whether all
packages (default) or only the most important core packages should be installed
(with all their dependencies).

* If a core package is mentioned several times in the document, it is sufficient
to indicate `priority = "core"` for one of the occurrences.

* Rather than linking to another task view as a whole, e.g.,
`view("Econometrics")`, it is also possible to link to specific sections of that
view, e.g., `view("Econometrics", "Instrumental variables")`.

Moreover, code projects in other repositories can be linked by using the functions:

* `bioc()` for Bioconductor packages at <https://www.Bioconductor.org/>.
* `github()` for GitHub projects at <https://github.com/>.
* `rforge()` for R-Forge projects at <https://R-Forge.R-project.org/>.
* `gcode()` for projects in the Google Code archive at <https://Code.Google.com/archive/>.
* `ohat()` for Omegahat packages at <https://www.Omegahat.net/>.

Note however that CRAN task views are intended mainly for packages on CRAN (as the
name conveys). Thus, links to other repositories should be used for _important_
packages/projects but not list _all_ potentially relevant repositories. Also, it
is not necessary to list the GitHub projects for all listed CRAN packages as these
are typically provided on the package's CRAN web page.


### Links

All CRAN packages included with the `pkg()` function will be listed in a dedicated
list below the information text when rendering the HTML version of the task view.
Also, the task views as well as packages/projects in other repositories will be
included automatically in the list of links at the end of the HTML version.

Finally, additional links - e.g., to books, papers, blogs, interest groups, mailing
lists, etc. - can be included in the `### Links` section at the end of the file in
a standard itemized list. As explained above this list of links will be complemented
automatically with links generated from the functions `view()`, `bioc()`, `github()`,
etc.


## Working with task view files in R

To check whether a task view file has been formatted properly it can be read into
R and printed. This should display the metainformation and the list of packages.
Subsequently, it can be rendered to an HTML page and displayed in a browser for
checking whether the information text is processed correctly. Finally, the
function `check_ctv_packages()` can be used to check whether some of the listed
packages are actually not available on CRAN or not currently maintained
(archived).

For illustration, the code below employs the `Econometrics.md` file shipped
within the `ctv` package. Instead a local `MyNewView.md` with resulting
`MyNewView.html` could be used as well.

```
library("ctv")
file.copy(system.file("ctv", "Econometrics.md", package = "ctv"), "Econometrics.md")
read.ctv("Econometrics.md", cran = TRUE)
ctv2html(x)
browseURL("Econometrics.html")
check_ctv_packages("Econometrics.md")
```

Note that the code above is intended for authors of CRAN task views. For end-users
the functions `ctv()`, `available.views()`, `install.views()`, and
`update.views()` are relevant. See <https://github.com/cran-task-views/ctv/> for
more details.


## Dealing with archived packages

The CRAN packages listed in task views should ideally be maintained actively,
so that improved versions are released by the corresponding maintainers in case
the daily CRAN checks discover any issues.

However, as even actively maintained packages may be temporarily archived on
CRAN, the following strategy is adopted:

* When a CRAN package from a task view is archived, it is still listed in the
task view like before. It is only flagged as archived in the text and not
installed automatically anymore by `install.views()` and `update.views()`.

* If the package is still archived after (more than) 60 days, CRAN creates an
issue in the GitHub repository of the task view (as in
[this example](https://github.com/cran-task-views/Econometrics/issues/11)).

* At this point the task view maintainers can decide to

  - _exclude_ the package from the task view immediately, e.g., if they feel
    it had not been that relevant and/or not been updated in a very long time;
  - _reach out to the package maintainer_ to help with releasing an improved
    version; or
  - _wait some more_ for an improved version, e.g., when they see that the
    package maintainers already started addressing the problem.

* If the package is still archived after (more than) 100 days, CRAN follows
up on the issue and requests removal of the package from the task view.
(For sufficiently relevant packages it may be sensible to replace the `pkg()`
link by a `github()` link in the task view.)


## Converting the legacy XML format to R/Markdown

The `ctv` package provides an (unexported) R function to facilitate the transition
from the legacy XML format for the task view files to the new R/Markdown format
described above. Simply using

```
ctv:::ctv_xml_to_rmd("MyView.ctv")
```

will create a `MyView.md` file from the `.ctv` file. This should do most necessary
transformations automatically. However, it is recommended to thoroughly check
the resulting file and improve it as appropriate. To check the resulting HTML output
use

```
ctv2html("MyView.md")
browseURL("MyView.html")
```

Note that one important difference between the XML and R/Markdown format is that
the "package list" does not need to be listed separately anymore, it is auto-generated
from the "info" text. Similarly, the "links" just need to provide those links that
are not auto-generated from the "info" text.


## Using GitHub Actions to validate task views

The functions recommended above for validating that a task view can be processed
correctly, `ctv2html()` and `check_ctv_packages()`, can also be run automatically
using a GitHub Action provided by the CRAN Task View Initiative. The action checks
that the HTML conversions works without error, its links work correctly, and that
no new archived packages were introduced in the task view.

The GitHub Action can be installed as demonstrated an described in
[validate-ctv/](validate-ctv/).
In its current version, it is automatically run at push or merge requests 
performed in the main branch of the task view file. More general guidance about
[GitHub Actions](https://github.com/features/actions) can be found in the the
GitHub documentation.
