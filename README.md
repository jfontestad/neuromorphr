<!-- README.md is generated from README.Rmd. Please edit that file -->
[![Travis-CI Build Status](https://api.travis-ci.org/jefferislab/neuromorphr.svg?branch=master)](https://travis-ci.org/jefferislab/neuromorphr)

neuromorphr
===========

The goal of *neuromorphr* is to provide R client utilities for interacting with the [API](http://neuromorpho.org/api.jsp) for [neuromorpho.org](http://neuromorpho.org), which is a well-known centrally curated inventory of digitally reconstructed neurons associated with peer-reviewed publications. It is continuously updated as new morphological reconstructions are collected, published and shared. It contains contributions from hundreds of laboratories worldwide (see many [here]()). To date, [neuromorpho.org](http://neuromorpho.org) is the largest collection of publicly accessible 3D neuronal reconstructions (&gt;100,000) and associated metadata which can be used for detailed single cell simulations. This R package was built to work with veriosn 7.7 of [neuromorpho.org](http://neuromorpho.org). In the following, we detail some of its functionality, and copy and paste some text from [neuromorpho.org](http://neuromorpho.org) in order to fill you in on its database and outlook. If python is more your poison, there are a few python client available, for example from [BonsaiNet](https://github.com/BonsaiNet/Neuromorpho.org). Using this R package in concert with the [nat](https://github.com/jefferis/nat) ecosystem developed primarily by Greg Jefferis is highly recommended. The curators of [neuromorpho.org](http://neuromorpho.org) can be contacted at .

Installation
------------

``` r
# install
if (!require("devtools")) install.packages("devtools")
devtools::install_github("jefferislab/neuromorphr")

# use 
library(neuromorphr)
```

Key Functions
-------------

Now we can have a look at what is available, here are some of the key functions. Their help details examples of their use. You can summon the help in RStudio using followed by the function name.

``` r
# Sometimes neuromorphr.org can be slow, or down from capacity issues or have a faulty API. Can I check this?
neuromorpho_is_api_healthy()

# And how can I read neurons from neuromorpho?
?neuromorphr_read_neurons()

# But first I need neuron names and/or neuron IDs, how do I get those?
?neuprint_search()

# I see, so what meat data do I get with my neurons?
?neuprint_search()

# Interesting, see a pubmed ID (pmid) is also given. Can I find the scientific artices that descrie these neurons?
?neuprint_search()

# I heard somethign about persistence vectors, they're used to describe describe meaningful morphological features? Can I get those?
?neuromorpho_persistence_vectors
```

Each neuron in [neuromorpho.org](http://neuromorpho.org) is represented by a name, general information (metadata) and a standardised [SWC](http://www.neuronland.org/NLMorphologyConverter/MorphologyFormats/SWC/Spec.html) file for the digital morphological reconstruction. Most neurons also have some basic measurements calculated, incluidng for example cable length, in micrometers, and volume, in micrometers cubed. The functions above can get you this information.

Submit to neuromorpho.org
-------------------------

As well as using this package to interact with neuromorpho.org curated data, you can consider submitted your own neurons if you have been involved in lab work that has acquired 3D reconstructions. The submission process is very straightforward:

1.  E-mail the reconstruction files (zipped, if possible) to:
2.  Fill in as much information possible in the [Metadata Form](http://neuromorpho.org/about.jsp) and include it in your e-mail

Feed the beast.

Acknowledging the data and tools
--------------------------------

The [neuromorpho.org](http://neuromorpho.org) has a [terms of use](http://neuromorpho.org/useterm.jsp), which proviides guidance on how best to credit This package was created by Alexander Bates, while in the hroup of Gregory Jefferis. You can cite this package as:

``` r
citation(package = "neuromorphor")
```

**Bates AS** (2019). *neuromorphr: R client utilities for interacting with the neuromorpho.org repository.* **R package** version 0.1.0. <https://github.com/jefferislab/neuromorphr>

Acknowledgements
----------------

[neuromorpho.org](http://neuromorpho.org) was started and is maintained by the Computational Neuroanatomy Group at the Krasnow Institute for Advanced Study, George Mason University, under the direction of Prof. Giorgio Ascoli, PhD. This project is part of a consortium for the creation of a "Neuroscience Information Framework," endorsed by the Society for Neuroscience, funded by the National Institutes of Health, led by Cornell University (Dr. Daniel Gardner), and including numerous academic institutions such as Yale University (Dr. Gordon Shepherd), Stanford University (Dr. Paul Sternberg), and University of California, San Diego (Dr. Maryann Martone). The [neuromorpho.org](http://neuromorpho.org) mission statement can be found [here](http://neuromorpho.org/about.jsp).

References
----------

**Ascoli GA** (2006) *Mobilizing the base of neuroscience data: the case of neuronal morphologies*. **Nature Rev. Neurosci.**, 7:318-324

**Ascoli GA, Donohue DE, Halavi M.** (2007) *NeuroMorpho.Org: a central resource for neuronal morphologies.* **J Neurosci.**, 27(35):9247-51
