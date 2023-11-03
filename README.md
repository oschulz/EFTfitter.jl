
# EFTfitter.jl

[![CI](https://github.com/tudo-physik-e4/EFTfitter.jl/actions/workflows/ci.yml/badge.svg)](https://github.com/tudo-physik-e4/EFTfitter.jl/actions/workflows/ci.yml)
[![Documentation for stable version](https://img.shields.io/badge/docs-stable-blue.svg)](https://tudo-physik-e4.github.io/EFTfitter.jl/stable)
[![Documentation for development version](https://img.shields.io/badge/docs-dev-blue.svg)](https://tudo-physik-e4.github.io/EFTfitter.jl/dev)
[![License](http://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat)](LICENSE.md)
[![badge](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/tudo-physik-e4/EFTfitter.jl/binder?urlpath=git-pull%3Frepo%3Dhttps%253A%252F%252Fgithub.com%252Ftudo-physik-e4%252FEFTfitter.jl%26urlpath%3Dtree%252FEFTfitter.jl%252Fexamples%252Fnotebooks%252F%26branch%3Dmain)


New implementation of the [EFTfitter](https://github.com/tudo-physik-e4/EFTfitterRelease) in the [Julia languange](https://julialang.org/).  

EFTfitter is a tool for constraining the parameters of physics models using Bayesian inference by combining measurements of (different) observables.
It is particularly suited for EFT (effective field theory) interpretations, but is not limited to these use cases.

Work-in-progress, interfaces and functionalities might be subject to changes.

## News
Since version 0.2 of the package, the following new features are available:
- Model uncertainties: The functions giving the predictions for the observable values can now also return a parameter-dependent value quantifying the uncertainty on the prediction. These uncertainties are currently treated as uncorrelated and are added to the total covariance matrix.
- The data type of the (inverse) covariance matrix can now be set by the user. This can allow to increase the performance by speeding up the vector-matrix multiplication, e.g. in the case of sparse covariance matrices. The function `run_speed_test` can be used to determine which data type of the covariance matrix is the most suitable for the current model.
- `MeasurementDistribution` is now called `BinnedMeasurement`
  

## Installation
The EFTfitter.jl package can be installed using:
```julia
julia> using Pkg
julia> pkg"add EFTfitter"
```

Please see the [installation guide](https://tudo-physik-e4.github.io/EFTfitter.jl/dev/installation/) for further information on the installation of Julia, EFTfitter.jl and its dependencies.


## Documentation & Tutorials
Please see the [documentation](https://tudo-physik-e4.github.io/EFTfitter.jl/dev/) for tutorials and information on how to use EFTfitter.jl.  
Executable versions of the tutorials and examples can also be found [here](https://github.com/tudo-physik-e4/EFTfitter.jl/tree/main/examples).

You can also try running the tutorials right now: [![badge](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/tudo-physik-e4/EFTfitter.jl/binder?urlpath=git-pull%3Frepo%3Dhttps%253A%252F%252Fgithub.com%252Ftudo-physik-e4%252FEFTfitter.jl%26urlpath%3Dtree%252FEFTfitter.jl%252Fexamples%252Fnotebooks%252F%26branch%3Dmain)


## Template
A template for starting the implementation of your own analysis is provided [here](https://github.com/tudo-physik-e4/EFTfitter.jl/tree/main/examples/empty_template).


## Citing EFTfitter.jl
When using EFTfitter.jl for your work, please consider citing:

Nuno Castro, Johannes Erdmann, Cornelius Grunwald, Kevin Kroeninger, Nils-Arne Rosien, *EFTfitter - A tool for interpreting measurements in the context of effective field theories*,  [Eur. Phys. J. C 76 (2016) 8, 432](https://link.springer.com/article/10.1140/epjc/s10052-016-4280-9)
```
@article{EFTfitter2016,
    author = {Castro, Nuno and Erdmann, Johannes and Grunwald, Cornelius and Kr\"oninger, Kevin and Rosien, Nils-Arne},
    title = "{EFTfitter---A tool for interpreting measurements in the context of effective field theories}",
    eprint = "1605.05585",
    archivePrefix = "arXiv",
    primaryClass = "hep-ex",
    doi = "10.1140/epjc/s10052-016-4280-9",
    journal = "Eur. Phys. J. C",
    volume = "76",
    number = "8",
    pages = "432",
    year = "2016"
}
```
