## Maintaining CRAN task views

In the following, we provide guidelines for maintainers of the official CRAN task views
that are overseen by the [CRAN Task View Initiative](https://github.com/cran-task-views/ctv).


### GitHub repository

* _Name:_ For each approved task view, say `MyTopic`, a dedicated GitHub repository is set up
  within the `cran-task-views` organization: `https://github.com/cran-task-views/MyTopic`.
  
* _Access:_ All CRAN Task View Editors have "Admin" access to the repositories within the organization.
  Moreover, the principal maintainer (listed first in task view Markdown file) gets "Admin"
  rights and co-maintainers get "Maintainer" rights.
  
* _Basic configuration:_ The CRAN Task View Editors set up the basic structure of the repository:
  `README.md`, `main` branch, "About" description. These configurations should not be modified by
  the task view maintainers.

* _Main task view file:_ The main task view file follows the naming convention above, say
  `MyTopic.md`, and is written following the corresponding [documentation](Documentation.md).
  All (co-)maintainers are responsible for keeping the file valid and up to date (see also below).
  Changes may also be made by the CRAN Task View Editors.
  
* _Further files and configuration:_ Additional content may be added to the repository by the
  maintainers, e.g., additional documentation of their specific workflow, development branches,
  R scripts for auxiliary tasks, GitHub Actions like
  [validate-ctv](https://github.com/cran-task-views/ctv/tree/main/validate-ctv), etc.
  It is recommended, though, to keep the repository simple.

* _Code of conduct:_ The official [code of conduct](CodeOfConduct.md) of the CRAN Task View Initiative
  applies to all respositories and contributions.


### Task view updates

* _Releases:_ CRAN task views use a rolling release, i.e., all modifications made in the main
  branch are released regularly on CRAN. Packages (or other content) can be added or removed
  at any time.

* _Development versions:_ As the main branch gets released to CRAN regularly, development versions
  of the task view (if necessary, e.g., when the maintainers coordinate the text for a new paragraph, etc.)
  should be hosted in separate branches.

* _Sanity checks:_ When making changes to the task view file (say, `MyTopic.md`) or accepting pull
  requests, the maintainers should make sure that the version/date in the YAML header is updated
  appropriately and that the file still works correctly. For the latter it is recommended to run:
  
  ```
  ctv::check_ctv_packages("MyView.md")
  ctv::ctv2html("MyView.md")
  browseURL("MyView.html")
  ```
  
  These checks can be done manually or through the GitHub Action
  [validate-ctv](https://github.com/cran-task-views/ctv/tree/main/validate-ctv) (which additionally
  does a few further checks).
  
* _Content checks:_ In addition to the more technical sanity checks above, the content of the task
  view should be checked thoroughly, at least twice a year. Are there relevant new packages on CRAN
  that should be included? Are the descriptions in the taks view still up to date? Should packages
  be removed that have been archived on CRAN or are otherwise outdated?  
  The package [CTVsuggest](https://github.com/DylanDijk/CTVsuggest) can help with discovering new
  relevant packages.
  
* _Community contributions:_ All (co-)maintainers are responsible for responding to community
  contributions, typically raised through GitHub issues or pull requests. Follow-up should be timely
  and must adhere to the [code of conduct](CodeOfConduct.md). Suggestions made via e-mail should be
  handled by the principal maintainer, possibly by setting up a GitHub issue in case help from
  other co-maintainers is needed.

* _Major revisions:_ In case the maintainers want to make major changes in the task view - such as
  major rewrites, changes of maintainers, etc. - these should be announced to the editors before
  they are implemented/released.


### CRAN package archivals

* _Goal:_ The CRAN packages listed in a task view should ideally be actively maintained. While this
  is not easy to check automatically, the archival of a package on CRAN is always a signal that the
  package should be checked thoroughly.
  
* _Possible actions:_ When a listed package gets archived on CRAN, the task view maintainers have a
  range of possible actions to take. (1) They may remove the package immediately from the task view
  as well. (2) They may wait for some time and decide after a certain period of grace (see below).
  (3) They may actively reach out to the package maintainer, offer support, or try to find new
  maintainers for orphaned packages.
  
* _Immediate removal:_  Action (1) is typically appropriate if a package was archived for policy
  violations or at the request of the maintainer. It may also be appropriate if the package did not
  have any updates for many years and is not associated with a public repository.
  
* _Period of grace:_ If action (2) is taken, then archived packages may be kept in the task view
  for a certain period of grace. Unless it is clear that the package should be removed immediately,
  it is ok to wait for 60 days. And after 100 days some other action (typically 1) should be taken.
  
* _Actively reaching out:_ To help keeping useful packages on CRAN, is is appreciated if task view
  maintainers take action (3) for archived packages. A simple e-mail to the maintainer or creating
  an issue the package's repository are typically a good start, asking for plans of CRAN resubmission,
  possibly also offering help. However, it is at the task view maintainers' discretion to decide
  whether action (3) is sufficiently promising or whether actions (1) or (2) seem more appropriate.
  
* _CRAN support:_ To help discovering archived packages and initiating one of the actions above,
  the CRAN team regularly checks whether any task views contain packages that have been archived
  on CRAN for 60 days or more. If so, they create an issue in the corresponding task view, currently
  from the acount [statmath-IT](https://github.com/statmath-it), asking for appropriate actions.
  The task view maintainers should respond in a timely manner (see also "Community contributions"
  above).
