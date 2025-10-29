---
layout: default
title: Topic 3
---

# Topic 3 - Pharmacophore searching, docking and virtual screening

In this serie of lessons, the general concepts of docking, virtual screening and pharmacophore searching are explained. Several of these methods are highlighted. In addition, we will show you how to setup the Schrödinger virtual teaching platform so that the theory in these lessons can be applied in practice.


## Prepare yourself:

It is highly recommended that you prepare yourselves by first having a look at the following movies:

- <a href="https://www.youtube.com/watch?v=fMbVB_huh28" target="_blank">What's the difference between structure based and ligand based virtual screening?</a> [YouTube - 2'14"]
- <a href="https://www.youtube.com/watch?v=EI7ojGoLLUk" target="_blank">What is molecular docking?</a> [YouTube - 5'48"]

Now you should be ready to have a look at these papers:

- <a href="Topic_03/MedChemComm_2017_8_1970.pdf" download>A systematic analysis of atomic protein–ligand interactions in the PDB</a> [pdf]
- <a href="Topic_03/Pharao.pdf" download>Pharao: Pharmacophore alignment and optimization</a> [pdf]
- <a href="Topic_03/Glide.pdf" download>Glide: A New Approach for Rapid, Accurate Docking and Scoring. 1. Method and Assessment of Docking Accuracy</a> [pdf]
- <a href="Topic_03/JMedChem_2008_51_2432.pdf" download>Ligand binding efficiency: trends, physical basis, and implications</a> [pdf]
- <a href="Topic_03/Guide_To_Docking.pdf" download>A practical guide to large-scale docking</a> [pdf]


## Course manual:

- <a href="Topic_03/6-Virtual_screening.pdf" download>Chapter 6: Virtual screening</a> [pdf]


## Slides:

- <a href="Topic_03/Slides_03.pdf" download>Lecture slides of topic 03</a> [pdf]


## Exercises:

To practice the lessons learned, we make use of a <a href="https://teaching2025-eu.gcp.tsg.schrodinger.com/workstation/#/" target="_blank">virtual workstation</a> with the software tool Maestro from <a href="https://www.schrodinger.com" target="_blank">Schrödinger</a> already installed. You need an account that will provided to you after inscription to this course.

**_NOTE:_**  The virtual workstations work best on *Google Chrome* or *Safari* browsers.


Tutorials of the different exercises can be downloaded from these links:

- <a href="Topic_03/gb-docking-ls.pdf" download>A protein-ligand docking exercise</a> [pdf]
- <a href="Topic_03/Pharmacophore_Searching.pdf" download>A pharmacophore searching exercise</a> [pdf]
- <a href="Topic_03/bc-sbvs-ls.pdf" download>A structure-based virtual screening exercise</a> [pdf]


## Finished?

If you are finished with these exercises, then you are ready to start working on your own virtual drug design project. The steps that need to be followed are:

1. Open the <a href="https://teaching2025-eu.gcp.tsg.schrodinger.com/workstation/#/" target="_blank">virtual workstation</a> and create a workfolder on the desktop.
2. Download the compound library into this workfolder. You can do by opening a terminal, move into the workfolder, and run this command `wget https://github/com/UAMCAntwerpen/2040FBDBIC/raw/master/Project-materials/2023-2024/LigPrep_Enamine_Discovery_Diversity_Set.maegz`.
3. Start Maestro and set the workfolder as being the default folder.
4. Download your protein of interest from the PDB and prepare as usual. Make sure to optimise the hydrogen atom positions.
5. Generate a docking grid, and make sure you note the name that the grid was given (it is written in de workfolder).
6. Setup the virtual screening workflow. Make sure to write out the command line and input file, and **not** launch the job.
7. Edit the shell script and launch the job from the command line. The command should read `"$SCHRODINGER/vws" job_name.inp -OVERWRITE -adjust -TMPLAUNCHDIR` (`job_name.inp` should be the name of the input file).
8. Do not close the virtual workstation as long as the job is running.

A tutorial is available on <a href="https://youtu.be/bX4-nFmLkjM?si=tFrrmJxgkvNSgjhv" target="_blank">YouTube</a>. In this tutorial, it is also shown how you can submit jobs that take a long time by specifying multiple processor cores on the virtual workstation.
