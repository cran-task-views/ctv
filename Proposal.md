## Proposing a new CRAN task view

In the following, we provide guidance for prospective maintainers that want to propose a new CRAN task view.
Prospective maintainers should read the guidelines below carefully and only propose
a new task view if they are willing to follow these guidelines and able to spend enough
time on both the review and onboarding process and the maintenance in the future.

All contributions must be made under the [Code of conduct](CodeOfConduct.md).


### Basic goals

* _Scope:_ A task view should be on a topic with a rather clear scope that should neither be too narrow nor too wide.
* _Packages:_ The goal is not to cover "every package" remotely related to the topic but rather the packages that clearly fall
  within the scope. The coverage should be similar to what an (introductory) text book on the topic would cover.
  Non-CRAN packages may also be included but the focus of CRAN task views should be packages on CRAN (as the name conveys).
* _Ratings:_ Task views should _not_ rate the packages or endorse certain "best" packages but rather give an overview
  of what is available. A bit of emphasis to the more important packages can be given in two ways: (1) The most important
  packages can be flagged as "core" packages. (2) In the information text the more important packages can be listed first
  in the respective sections.


### First proposal

* _Submission:_ [Open an issue](https://github.com/cran-task-views/ctv/issues) in the `ctv` repository with the title
   _CRAN task view proposal: MyTopic_ where _MyTopic_ should be replaced with the intended name of the task view in
   _CamelCase_.
* _Scope:_ Include one or two paragraphs about the scope of the task view, outlining the inclusion and exclusion criteria
  as well as relevant sections within the topic.
* _Packages:_ Include a _tentative list_ of packages for the task view. This should encompass the "core" packages
  and a collection of relevant packages, ideally grouped by sections within the topic. It is not important, yet,
  that the list of sections or packages is already exhaustive.
* _Overlap:_ Comment on potential overlap with already existing task views as well as with task views that might be
  created (or split off) in the future.
* _Maintainers:_ The proposal should be made by the person willing to act as the principal maintainer for the task view.
  Furthermore, task views should have teams of additional 1-5 co-maintainers to share the workload and reflect
  different perspectives. Ideally the co-maintainers should be a diverse group in terms of gender, origin,
  scientific field, etc. Possible candidates can be listed in the proposal.


### Review process

* _Format:_ Reviews are carried out openly by comments in the issue tracker.
* _Participants:_ All CRAN Task View Editors are generally invited to comment. Furthermore maintainers of related task views
  as well as further members of the community (e.g., maintainers of "core" CRAN packages on the topic) might
  be explicitly invited to comment. Such comments are also open to everybody else.
* _Endorsement:_ A proposal needs to be endorsed by at least three CRAN Task View Editors to be considered further.
  Otherwise the issue is closed.
* _Revisions:_ Even if the proposal is in principle endorsed, the CRAN Task View Editors might ask for revisions
  first. Typically, these could include refinements (or shifts) in the scope, avoiding overlap with other task views,
  or suggesting alternative/additional co-maintainers, etc.
* _Acceptance:_ After potential revisions the proposal needs to be accepted by at least three CRAN Task View Editors
  in order to become an official task view.
  

### Onboarding and release

* _Setup:_ The CRAN Task View Editors set up a new `MyTopic` (see above) repository in the `cran-task-views` organization
  on GitHub.
* _Editor:_ One CRAN Task View Editor becomes officially responsible for onboarding the new task view. They set up the
  repository and `README.md` file as well as a rudimentary `MyTopic.md` source file.
* _Onboarding:_ The designated co-maintainers are given access to the `MyTopic` repository and should turn their proposal
  into a proper Markdown file following the official [Documentation](Documentation.md).
* _Feedback:_ The designated CRAN Task View Editor provides feedback during this phase and tries to enforce that the
  onboarding process is completed in a timely manner. Such feedback is typically provided either by opening issues or
  by making pull requests or even direct commits to the repository.
* _Release:_ When the task view co-maintainers and the CRAN Task View Editors agree that the task view is ready for
  release, it is published by Achim Zeileis on CRAN.


### Maintenance

* _Updates:_ The team of maintainers should check CRAN regularly (a couple of times per year) for relevant
  new packages.
* _Contributions:_ The team of maintainers should be open for suggestions from the community (as described in
  the [contribution guide](Contributing.md)) and handle them regarding the inclusion/exclusion criteria adopted
  for the task view.
* _Guidelines:_  More details are provided in the [maintenance guidelines](Maintenance.md).
