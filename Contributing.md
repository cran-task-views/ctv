## Contributing to a CRAN task view

Contributions to task views from members of the community are very welcome and
in fact crucial for keeping the task views up to date. Typical contributions
would be improvements in existing content (e.g., adding details, clarifications,
or corrections) or suggestions of additional content (e.g., packages or links).
To facilitate such contributions each task view includes the e-mail address of
the principal maintainer as well as a link to the associated GitHub repository.

Thus, to make such a contribution, please use one of the following alternatives
which is most convenient for you:

* **Send an e-mail** to the principal maintainer.
* **Raise an issue** in the GitHub repository.
* **Provide a pull request** in the GitHub repository.


## Checking pull requests

Before making a pull request for a task view file (say `MyTopic.md`) please
ensure that the resulting HTML page is properly formatted:

```
library("ctv")
ctv2html("MyTopic.md")
browseURL("MyTopic.html")
```

Also check that the information text and the package list are consistent and
that all packages are available from CRAN:

```
check_ctv_packages("MyTopic.md")
```

Further information about the CRAN task view format is available in the
corresponding [Documentation](Documentation.md).
