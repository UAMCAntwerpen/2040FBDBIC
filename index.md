---
title: Welcome to the Chemoinformatics and Computational Drug Design course
layout: home
---

This course introduces computational drug design and chemoinformatics, disciplines that use computer simulations and data analysis to discover and develop new medicines. You will learn how to model drug-target interactions, screen chemical libraries, and identify molecular candidates with therapeutic potential. The course focuses on digital tools and computational methods that streamline the drug discovery process before compounds proceed to experimental validation.

All course materials and code examples are available in this repository. The course is part of the <a href="https://www.uantwerpen.be/nl/studeren/aanbod/alle-opleidingen/biochemie-en-biotechnologie/master/studieprogramma/" target="_blank">Master of Biotechnology</a> and the <a href="https://www.uantwerpen.be/en/study/programmes/all-programmes/pharmaceutical-sciences-programmes/master/drug-development-pharmacist/" target="_blank">Master of Drug Development: Pharmacist</a> programmes at the University of Antwerp.

This course follows a typical workflow in computational drug design. Throughout the course, this workflow is demonstrated using the MDM2-P53 protein-protein interaction as a test system, for which potential inhibitors are identified and evaluated. The objective is not only to understand individual computational techniques, but also to see how they integrate into a coherent drug discovery pipeline. Students are encouraged to use this example as inspiration for applying the same strategy to their own protein targets. A typical workflow consists of the following steps:

1. Gathering and analysing **prior knowledge about the therapeutic target of interest**. This includes collecting information on small molecules previously reported to be active against the target. This step is covered in [topic 1](Topic-1/index.md), where you will learn how to represent small molecules and protein structures computationally, and how to store and organise these data for subsequent analyses.
2. Building a small-molecule dataset from prior-art information and using it to train a simple machine-learning model to identify promising candidates. In [topic 2](Topic_2/index.md), you will learn how to build and validate such a model. The typical output of this step is a compound database enriched in molecules with a higher likelihood of activity against the target.
3. Docking compounds from the enriched small-molecule database into the protein target. In [topic 3](Topic_3/index.md), you will learn how to prepare a protein crystal structure for docking, and how to run and validate docking experiments.
4. Refining and validating docking results using state-of-the-art molecular dynamics simulations of protein-ligand complexes. In [topic 4](Topic_4/index.md), you will learn how to set up and run a typical MD simulation, and how to assess docking outcomes based on protein-ligand interactions during the simulations.


# Before you start

To participate successfully in this course, please complete the following preparations:

## 1. Install PyMol

PyMOL is a molecular graphics program used to visualise ligands and protein structures. Two versions are available: a commercial version and an open-source version. Installation of the open-source version is straightforward: download the appropriate installer for your operating system and follow the instructions.

- [Download PyMol for Windows (v3.1.0.4)](assets/pymol/PyMOL_Open_source_v3.1.0.4+1_WINx64_setup.exe)
- [Download PyMol for Mac (v3.1.0.4)](assets/pymol/PyMOL_Open_source_v3.1.0.4+2.dmg)

More recent versions may be available. You can always <a href="https://github.com/kullik01/pymol-open-source-setup/releases" target="_blank">visit the official PyMol GitHub releases page</a> to check for updates.

## 2. Review Python basics

Basic Python knowledge is required for this course. If you need a refresher, or if you are new to Python, the following resources are available:

- <a href="assets/python/1-Introduction_to_Python.pdf" download>Chapter 1: Introduction to Python</a> [pdf]
- <a href="https://www.youtube.com/watch?v=kqtD5dpn9C8&t=70s" target="_blank">Python for beginners - Learn Python in 1 hour</a> [YouTube - 60'05"]

You can also practise your skills using these interactive Google Colab notebooks:

- <a href="https://githubtocolab.com/UAMCAntwerpen/2040FBDBIC/blob/master/assets/python/Basic_Python_Refresher.ipynb" target="_blank">Python refresher code</a> [Google Colab]
- <a href="https://githubtocolab.com/UAMCAntwerpen/2040FBDBIC/blob/master/assets/python/Basic_Python_Refresher_Exercises.ipynb" target="_blank">Python refresher exercises</a> [Google Colab]

Please note: a Google account is required to use Google Colab.

## 3. Obtain a CalcUA account

A CalcUA account is required to perform docking and molecular dynamics simulations. Students enrolled in this course will automatically receive access.

# Ready to begin?

You can now proceed to the first topic:

- [Topic 1: Gathering information about your protein target](Topic-1/index.md)

<br>

Note: This course and its accompanying materials were developed with financial support from the <a href="https://www.esf-vlaanderen.be/herstel-en-veerkrachtfaciliteit-van-de-europese-unie-rrf" target="_blank">European Union Recovery and Resilience Facility (RRF)</a>.
