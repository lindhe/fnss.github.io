---
layout: index
title: Fast Network Simulation Setup
---

### Overview
Fast Network Simulation Setup (FNSS) is a toolchain allowing network researchers and engineers to simplify the process of setting up a network experiment scenario. It allows users to:

* Parse a topology from a dataset or a topology generator or generate it according to a number of synthetic models
* Configure links with capacity, weights, delays and buffer sizes
* Deploy applications and protocol stacks on nodes
* Generate traffic matrices
* Generate event schedules
* Deploy network and workload configuration to a number of simulators and emulators

FNSS comprises a core library (written in Python) and a set of adapters. The core library provides all capabilities for generating the experiment scenario. The adapters allow users to export scenarios generated with the core library to [ns-2](http://www.isi.edu/nsnam/ns/), [ns-3](http://www.nsnam.org/), [Mininet](http://www.mininet.org/), [Omnet++](http://www.omnetpp.org/), [Autonetkit](http://www.autonetkit.org/) and [jFed](http://jfed.iminds.be/) as well other simulators or emulators through the Python core library itself or the provided Java and C++ libraries.

### Usage
To use FNSS you would normally use the following workflow.

 1. Create an experiment scenario (topology, traffic matrices, event schedules) using the Python core library.
 2. Export the created scenario in your target simulator/emulator.
      * If your target simulator/emulator is ns-2, Mininet, Autonetkit or a Python program, the core library include functions to export the scenario created in your target environment.
      * Otherwise, if you wish to run your experiments on ns-3 or a Java or C++ program, then export the scenario to XML files using the provided functions and use the Java, C++ or ns-3 library to import the scenario XML files into your target simulator/emulator.

### Install

This section explains how to install the FNSS Python core library.

If you wish to use FNSS to deploy experiment scenarios in a C++ or a Java program or in the ns-3 simulator then you also need the relevant library, which you can download from the links further below.

#### Ubuntu (version 12.04+)

If you use Ubuntu, you can install the FNSS core library along with the Python interpreter and all required dependencies by running the following script:

    $ wget https://github.com/fnss/fnss/raw/master/core/ubuntu_install.sh -O - | sh

You need superuser privileges to run this script. If you don't trust running this script, you can inspect its source code [here](https://github.com/fnss/fnss/blob/master/core/ubuntu_install.sh).

#### Other operating systems

The easiest way to install the core Python library is to download it and install it from the [Python Package Index](http://pypi.python.org/pypi/fnss). To do so, you must have [Python](http://www.python.org) (required version >= 2.6, preferred >= 2.7) installed on your machine and [`pip`](http://www.pip-installer.org/), which is a package manager for Python.

To install FNSS using `pip`, you just need to run the following command:

    $ pip fnss
   
Depending on the configuration of your machine you may need to run `pip` as superuser. Running this command will download the latest version of the FNSS core library and install it on your machine together with all required dependencies.

At this stage you are ready to use the Python core library. To use the Java or C++ APIs or the ns-3 adapters, please download the specific components that you need from the links below.

#### Virtual Machine

You can also run FNSS within a virtual machine. [This repository](https://github.com/fnss/fnss-vm/) contains scripts and documentation to set up a virtual machine with FNSS and all dependencies.

### Download

You can either browse the code from the [FNSS GitHub repository](http://www.github.com/fnss/fnss) or choose among the following download options:

#### Latest stable release (0.6.1)

Complete toolchain    | [tar.gz](https://github.com/fnss/fnss/archive/v0.6.1.tar.gz) | [zip](https://github.com/fnss/fnss/archive/v0.6.1.zip)
----------------------|:------------------------------------------------------------:|:-------------------------------------------------------:
Core (Python) library | [tar.gz](download/core/fnss-core-0.6.1.tar.gz)               | [zip](download/core/fnss-core-0.6.1.zip)
C++ library           | [tar.gz](download/cpp/fnss-cpp-api-0.6.1.tar.gz)             | [zip](download/cpp/fnss-cpp-api-0.6.1.zip)
Java library          | [tar.gz](download/java/fnss-java-api-0.6.1-all.tar.gz)       | [zip](download/java/fnss-java-api-0.6.1-all.zip)
ns-3 library          | [tar.gz](download/ns3/fnss-ns3-api-0.6.1.tar.gz)             | [zip](download/ns3/fnss-ns3-api-0.6.1.zip)


#### Development branch
You can download the latest version of the code from the development branch using [Git](http://git-scm.com/). The code on the development branch is generally stable and can be used safely.
Open a command shell, move to the directory where you want to download FNSS and type:

    $ git clone https://github.com/fnss/fnss.git

Alternatively, you can get a compressed archive of the development branch:

 * [master.tar.gz](https://github.com/fnss/fnss/archive/master.tar.gz)
 * [master.zip](https://github.com/fnss/fnss/archive/master.zip)

### Documentation and examples
Here you can find links to browse documentation and examples of the various components of the FNSS toolchain. Documentation and examples are also included in the component packages that can be downloaded from the links above.

Component             | Documentation | Examples
--------------------- |:-------------:|:--------:
Core (Python) library |  [Browse](doc/core/) | [Browse](https://github.com/fnss/fnss/tree/master/core/examples)
C++ library           | [Browse](doc/cpp/) | [Browse](https://github.com/fnss/fnss/tree/master/cpp/examples)
Java library          | [Browse](doc/java/) | [Browse](https://github.com/fnss/fnss/tree/master/java/examples)
ns-3 library          | [Browse](doc/ns3/) | [Browse](https://github.com/fnss/fnss/tree/master/ns3/fnss/examples)

Further information about FNSS architecture and the models it implements can be found in this paper:

 L. Saino, C. Cocora, G. Pavlou, [A Toolchain for Simplifying Network Simulation Setup](http://www.ee.ucl.ac.uk/~lsaino/publications/fnss-simutools13.pdf),
 in *Proceedings of the 6th International ICST Conference on Simulation Tools and Techniques (SIMUTOOLS '13)*, Cannes, France, March 2013 \[[PDF](http://www.ee.ucl.ac.uk/~lsaino/publications/fnss-simutools13.pdf)\] \[[Slides](http://www.ee.ucl.ac.uk/~lsaino/publications/fnss-simutools13-slides.pdf)\]

You can also have a look at [these slides](aims2014/slides.pdf) that were used for a tutorial on FNSS given at the [AIMS 2014 conference](http://www.aims-conference.org/2014/labs.html).

### Citing
If you cite FNSS in your paper, please refer to the following publication:

L. Saino, C. Cocora, G. Pavlou, [A Toolchain for Simplifying Network Simulation Setup](http://www.ee.ucl.ac.uk/~lsaino/publications/fnss-simutools13.pdf), in *Proceedings of the 6th International ICST Conference on Simulation Tools and Techniques (SIMUTOOLS '13)*, Cannes, France, March 2013

    @inproceedings{fnss,
         author = {Saino, Lorenzo and Cocora, Cosmin and Pavlou, George},
         title = {A Toolchain for Simplifying Network Simulation Setup},
         booktitle = {Proceedings of the 6th International ICST Conference on Simulation Tools and Techniques},
         series = {SIMUTOOLS '13},
         year = {2013},
         location = {Cannes, France},
         numpages = {10},
         publisher = {ICST},
         address = {ICST, Brussels, Belgium, Belgium},
    }


### Contact
For any information please contact [Lorenzo Saino](http://www.ee.ucl.ac.uk/~lsaino).
