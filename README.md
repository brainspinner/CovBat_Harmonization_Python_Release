# CovBat_Harmonization
### Correcting Covariance Batch Effects (CovBat): Harmonization of mean and covariance for multi-site data

--------
**Maintainer**: Andrew Chen, andrewac@pennmedicine.upenn.edu

**License**: Artistic License 2.0

## Table of content
- [1. Installation](#id-section1)
- [2. Background](#id-section2)
- [3. Software](#id-section3)
- [4. Citation](#id-section4)

<div id='id-section1'/>

## 1. Installation
The R package can be installed via devtools by running the following code

```
# install.packages("devtools")
devtools::install_github("andy1764/CovBat_Harmonization/R")
```

Then, you can load this package via

```
library(CovBat)
```

The R package provides the `covbat` function for harmonization of covariance and the `combat` function which is adapted from an older version of the original [ComBat](https://github.com/Jfortin1/ComBatHarmonization) package. For applying ComBat, please visit the main [ComBat](https://github.com/Jfortin1/ComBatHarmonization) repository.

For Python, please visit the Python subdirectory.

<div id='id-section2'/>

## 2. Background
Current harmonization methods often focus on addressing scanner differences in the mean and variance of features. However, machine learning methods employed in multivariate pattern analysis (MVPA) are known to leverage additional properties of the data, including covariance. In our recent [paper](https://doi.org/10.1002/hbm.25688), we show that ComBat, a state-of-the-art method designed to harmonize mean and variance, is unable to fully prevent detection of scanner manufacturer through MVPA in the Alzheimer's Disease Neuroimaging Initiative data. We design CovBat to harmonize the covariance of multivariate features and show that it can almost fully prevent detection of scanner properties.

CovBat is meant to be applied after initial preprocessing of the images to obtain a set of features and before statistical analyses. The application of CovBat is not limited to neuroimaging data; however, it has yet to be tested in other types of data.

<div id='id-section3'/>

## 3. Software
The R implementation of CovBat is based on the [ComBat](https://github.com/Jfortin1/ComBatHarmonization) package maintained by Jean-Philippe Fortin. The Python implementation of CovBat is a modification of the ComBat package for Python [here](https://github.com/brentp/combat.py). 

<div id='id-section4'/>

## 4. Citation
If you are using CovBat for harmonization of mean and covariance, please cite the following article:

> Chen, A. A., Beer, J. C., Tustison, N. J., Cook, P. A., Shinohara, R. T., Shou, H., & Initiative, T. A. D. N. (2022). Mitigating site effects in covariance for machine learning in neuroimaging data. *Human Brain Mapping*, 43(4), 1179–1195. https://doi.org/10.1002/hbm.25688)
