## CRAN Task View Initiative <img src="https://avatars.githubusercontent.com/u/61115545" align="right" alt="CRAN Task Views logo" width="180" />

CRAN task views aim to provide some guidance which packages on the
[Comprehensive R Archive Network (CRAN)](https://CRAN.R-project.org/)
are relevant for tasks related to a certain topic. They give a brief
overview of the included packages and can be automatically installed using the
[ctv](https://CRAN.R-project.org/package=ctv) package. The views are intended to
have a sharp focus so that it is sufficiently clear which packages should be
included (or excluded) - and they are not meant to endorse the "best" packages
for a given task.


### Installation

To automatically install the views, the [ctv](https://CRAN.R-project.org/package=ctv)
package needs to be installed, e.g., via

```
install.packages("ctv")
```

and then the views can be installed via `install.views()` or `update.views()`
(where the latter only installs those packages which are not installed and up-to-date),
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

The current team is:

* [Roger Bivand](https://github.com/rsbivand)
* [Dirk Eddelbuettel](https://github.com/eddelbuettel)
* [Rocío Joo](https://github.com/rociojoo)
* [David Meyer](https://github.com/davidjohannesmeyer)
* [Nathalie Vialaneix](https://github.com/tuxette)
* [Achim Zeileis](https://github.com/zeileis)

Former contributors include: Henrik Bengtsson, Heather Turner.


### How to contribute?

For contributing to an existing task view please go to the respective repository
(see links above) and follow the guidelines in [Contributing](Contributing.md).

For proposing a new task view please follow the guidelines in [Proposal](Proposal.md).

Technical documentation about the task view format is in [Documentation](Documentation.md).
Some more details can be found R-Forge page of the [ctv package](https://ctv.R-Forge.R-project.org/).

For other questions regarding CRAN task views as a whole, please open an issue in this repository.
For contact via e-mail, please write to `CRAN-task-views@R-project.org`.

All contributions must be made under the [Code of conduct](CodeOfConduct.md).


### Available task views

* [Bayesian](https://github.com/cran-task-views/Bayesian/)
* [ChemPhys](https://github.com/cran-task-views/ChemPhys/)
* [ClinicalTrials](https://github.com/cran-task-views/ClinicalTrials/)
* [Cluster](https://github.com/cran-task-views/Cluster/)
* [Databases](https://github.com/cran-task-views/Databases/)
* [DifferentialEquations](https://github.com/cran-task-views/DifferentialEquations/)
* [Distributions](https://github.com/cran-task-views/Distributions/)
* [Econometrics](https://github.com/cran-task-views/Econometrics/)
* [Environmetrics](https://github.com/cran-task-views/Environmetrics/)
* [ExperimentalDesign](https://github.com/cran-task-views/ExperimentalDesign/)
* [ExtremeValue](https://github.com/cran-task-views/ExtremeValue/)
* [Finance](https://github.com/cran-task-views/Finance/)
* [FunctionalData](https://github.com/cran-task-views/FunctionalData/)
* [GraphicalModels](https://github.com/cran-task-views/GraphicalModels/)
* [HighPerformanceComputing](https://github.com/cran-task-views/HighPerformanceComputing/)
* [Hydrology](https://github.com/cran-task-views/Hydrology/)
* [MachineLearning](https://github.com/cran-task-views/MachineLearning/)
* [MedicalImaging](https://github.com/cran-task-views/MedicalImaging/)
* [MetaAnalysis](https://github.com/cran-task-views/MetaAnalysis/)
* [MissingData](https://github.com/cran-task-views/MissingData/)
* [ModelDeployment](https://github.com/cran-task-views/ModelDeployment/)
* [NaturalLanguageProcessing](https://github.com/cran-task-views/NaturalLanguageProcessing/)
* [NumericalMathematics](https://github.com/cran-task-views/NumericalMathematics/)
* [OfficialStatistics](https://github.com/cran-task-views/OfficialStatistics/)
* [Optimization](https://github.com/cran-task-views/Optimization/)
* [Pharmacokinetics](https://github.com/cran-task-views/Pharmacokinetics/)
* [Psychometrics](https://github.com/cran-task-views/Psychometrics/)
* [ReproducibleResearch](https://github.com/cran-task-views/ReproducibleResearch/)
* [Robust](https://github.com/cran-task-views/Robust/)
* [Spatial](https://github.com/cran-task-views/Spatial/)
* [SpatioTemporal](https://github.com/cran-task-views/SpatioTemporal/)
* [Survival](https://github.com/cran-task-views/Survival/)
* [TeachingStatistics](https://github.com/cran-task-views/TeachingStatistics/)
* [TimeSeries](https://github.com/cran-task-views/TimeSeries/)
* [Tracking](https://github.com/cran-task-views/Tracking/)
* [WebTechnologies](https://github.com/cran-task-views/WebTechnologies/)
