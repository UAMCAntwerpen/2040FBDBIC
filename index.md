---
title:  Welcome to the chemo-informatics and computational drug design course site
layout: home
---

This course introduces computational drug design and chemo-informatics — disciplines that use computer simulations and data analysis to discover and develop new medicines. You will learn how to model drug–target interactions, screen chemical libraries, and identify molecular candidates with therapeutic potential. The focus lies on digital tools and computational methods that streamline the drug discovery process before compounds move to experimental validation.

All course materials and code examples are available in this repository. The course is part of the <a href="https://www.uantwerpen.be/nl/studeren/aanbod/alle-opleidingen/biochemie-en-biotechnologie/master/studieprogramma/" target="_blank">Master of Biotechnology</a> and the <a href="https://www.uantwerpen.be/en/study/programmes/all-programmes/pharmaceutical-sciences-programmes/master/drug-development-pharmacist/" target="_blank">Master of Drug Development: Pharmacist</a> programmes at the University of Antwerp.

This course illustrates a typical workflow used in computational drug design. Throughout the course, this workflow is demonstrated using the enzyme trypsin as a model system, for which potential inhibitors will be identified and evaluated. The objective is not only to understand the individual computational techniques, but also to see how they fit together into a coherent drug discovery pipeline. Students are encouraged to use this example as inspiration for applying the same strategy to their own protein target. A typical workflow consists of four main steps: (1) gathering and analysing prior knowledge about the protein of interest and preparing its crystal structure for computational studies; (2) preparing a ligand database for subsequent docking experiments; (3) performing molecular docking to identify promising candidate molecules; and (4) refining and validating the results through molecular dynamics (MD) simulations.

The course is therefore organized into four main **topics**:

1. [Gathering information about your protein target](01-Topic/index.md)
2. [Working with small molecules in silico](02-Topic/index.md)
3. [Docking: finding needles in the haystack](03-Topic/index.md)
4. [Molecular mechanics and dynamics: taking a closer look](04-Topic/index.md)

# Before you start

To participate successfully in this course, please complete the following preparations:

## 1. Install PyMol

PyMOL is a molecular graphics program used to visualise ligands and protein structures. Two versions are available: a commercial version and an open-source version. Installation of the open-source version is straightforward — download the appropriate installer for your operating system and follow the instructions.

- [Download PyMol for Windows (v3.1.0.4)](assets/00-Intro/pymol-software-downloads/PyMOL_Open_source_v3.1.0.4+1_WINx64_setup.exe)
- [Download PyMol for Mac (v3.1.0.4)](assets/00-Intro/pymol-software-downloads/PyMOL_Open_source_v3.1.0.4+2.dmg)

It could be that more recent versions are available in the meantime. You can always <a href="https://github.com/kullik01/pymol-open-source-setup/releases" target="_blank">visit the official PyMol GitHub download page</a> to check for this.

## 2. Review Python basics

Basic knowledge of Python is required for this course. If you need a refresher — or if you are new to Python — the following resources are available:

- <a href="assets/00-Intro/1-Introduction_to_Python.pdf" download>Chapter 1: Introduction to Python</a> [pdf]
- <a href="https://www.youtube.com/watch?v=kqtD5dpn9C8&t=70s" target="_blank">Python for beginners - Learn Python in 1 hour</a> [YouTube - 60'05"]

You can also practise your skills using these interactive Google Colab notebooks:

- <a href="https://githubtocolab.com/UAMCAntwerpen/2040FBDBIC/blob/master/assets/00-Intro/Basic_Python_Refresher.ipynb" target="_blank">Python refresher code</a> [Google Colab]
- <a href="https://githubtocolab.com/UAMCAntwerpen/2040FBDBIC/blob/master/assets/00-Intro/Basic_Python_Refresher_Exercises.ipynb" target="_blank">Python refresher exercises</a> [Google Colab]

Please note: A Google account is required to use Google Colab.

## 3. Obtain a CalcUA account

A CalcUA account is required to perform docking and molecular dynamics simulations. Students enrolled in this course will automatically receive access.

# Ready to begin?

You can now proceed to the first topic:

- [Topic 1: Gathering information about your protein target](01-Topic/index.md)

<br>

Note: This course and accompanying course material has been developed with financial support of the <a href="https://www.esf-vlaanderen.be/herstel-en-veerkrachtfaciliteit-van-de-europese-unie-rrf" target="_blank">European Union Recovery and Resilience Facility (RRF)</a>.
