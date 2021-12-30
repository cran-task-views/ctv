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

When using the last alternative, ensure that the task view is properly 
formatted by checking the resulting HTML before the pull request:

```
ctv2html("MyView.md")
browseURL("MyView.html")
```

Also check that the info and packagelist sections are consistent with each 
other and that all packages are available from the repository with:

```
check_ctv_packages("MyView.md")
```

Further information about the CRAN task view format is available in the
[Documentation](https://github.com/tuxette/ctv/blob/main/Documentation.md).
