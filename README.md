# 2040FBDBIC - Chemo-informatics and computational drug design

All code and course materials that are used in the course of "Chemo-informatics and computational drug design" at the University of Antwerp can be found in this repository. The course is divided into five topics:

1. Representing molecules in the computer
2. Clustering and machine learning
3. Molecular docking, virtual screening and pharmacophore searching
4. Molecular mechanics and dynamics
5. Artificial intelligence and virtual reality in computational drug design

All topics can be studied in any order, but there are some dependencies so it is recommended to follow the order as shown below.

It is advantage to have some basic knowledge of the Python programming language. For users that need a refresh, or for those that are not familiar with Python, we have prepared some basic refresher notes in the course material:

- [Chapter 1: Introduction to Python](https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/Topic_01/1-Introduction_to_Python.pdf) [pdf]

An interesting refresher is available on YouTube:

- [Python for beginners - Learn Python in 1 hour](https://www.youtube.com/watch?v=kqtD5dpn9C8&t=70s) [YouTube - 60'05"]

Finally, you can test your `Python` skills in these `Google Colab` environments:

- [Python refresher code](https://colab.research.google.com/github/UAMCAntwerpen/2040FBDBIC/blob/master/Basic_Python_Refresher.ipynb) [Google Colab]
- [Python refresher exercises](https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/Basic_Python_Refresher_Exercises.ipynb) [Google Colab]

## Topic 1 - Representing molecules in the computer

In this part you will learn how molecules are stored and manipulated by the computer. You will learn about the different formats, and you will write your first chemo-informatics code.

#### Prepare yourself:

It is highly recommended that you prepare yourselves by first going through the following papers and movie:

- [String-based representations of molecules: SMILES, SMARTS and SELFIES](https://www.youtube.com/watch?v=w9SV2mNSBMk) [YouTube - 15'00"]
- [A review of molecular representation in the age of machine learning](https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/Topic_01/Review_of_molecular_representation_in_the_age_of_machine_learning.pdf) [pdf]
- [The RDKit documentation](https://www.rdkit.org/docs/) [website]


#### Course manuals:

- [Chapter 2: Representing molecules in the computer](https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/Topic_01/2-Representing_molecules_in_the_computer.pdf) [pdf]
- [Chapter 3: Chemical informatics with RDKit](https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/Topic_01/3-Chemical_informatics_with_RDKit.pdf) [pdf]

#### Slides:

- [Lecture slides of topic 01](https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/Topic_01/Slides_01.pdf) [pdf]

#### Exercises:

With the following Google Colab sessions, you can bring to practice all that has been learned in this lessons:

- [Chemical informatics with RDKit](https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/Topic_01/Chemical_informatics_with_RDKit.ipynb) [Google Colab]
- [Extra exercises](https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/Topic_01/Topic_01_exercises.ipynb) [Google Colab]




## Topic 2 - Clustering and machine learning

In this part of the course, you will be introduced to molecular fingerprints and how these are used in similarity searches and clustering algorithms. Following this, you will be introduced to QSAR and learn to build a number of machine learning models in Google Colab.

#### Prepare yourself:

In order to make full use of this lessons, it is highly recommended to prepare yourselves by reading the following review papers and movies:

- [Machine learning and metrics](https://www.youtube.com/watch?v=xK9wHHQfGYA&list=LL&index=1) [YouTube - 24'48"]
- [Molecular strings and fingerprints](https://www.youtube.com/watch?v=kBk8HbjWwCw) [YouTube - 17'25"]
- [Supervised and unsupervised learning](https://www.youtube.com/watch?v=TJveOYsK6MY) [YouTube - 2'47"]
- [Molecular fingerprint similarity search in virtual screening](https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/Topic_01/Molecular_fingerprints.pdf) [pdf]
- [Applications of machine learning in drug discovery and development](https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/Topic_01/Machine_learning.pdf) [pdf]

#### Course manuals:

- [Chapter 4: Fingerprints, molecular similarity and clustering](https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/Topic_02/4-Fingerprints,_molecular_similarity_and_clustering.pdf) [pdf]
- [Chapter 5: QSAR models](https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/Topic_02/5-QSAR_models.pdf) [pdf]

#### Slides:

- [Lecture slides of topic 02](https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/Topic_02/Slides_02.pdf) [pdf]

#### Exercises:

In order to get acquainted with all the concepts that have been covered, these Google Colab links allow you to do some exercise:

- [Clustering and machine learning with RDKit](https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/Topic_02/Clustering_and_machine_learning.ipynb) [Google Colab]
- [Extra exercises](https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/Topic_02/Topic_02_exercises.ipynb) [Google Colab]




## Topic 3 - Molecular docking, virtual screening and pharmacophore searching

In this serie of lessons, the general concepts of docking, virtual screening and pharmacophore searching are explained. Several of these methods are highlighted. In addition, we will show you how to setup the Schrödinger virtual teaching platform so that the theory in these lessons can be applied in practice.

#### Prepare yourself:

It is highly recommended that you prepare yourselves by reading the following scientific papers in advance:

- [What's the difference between structure based and ligand based virtual screening?](https://www.youtube.com/watch?v=fMbVB_huh28) [YouTube - 2'14"]
- [What is molecular docking?](https://www.youtube.com/watch?v=EI7ojGoLLUk) [YouTube - 5'48"]
- [A systematic analysis of atomic protein–ligand interactions in the PDB](https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/Topic_03/MedChemComm_2017_8_1970.pdf) [pdf]
- [Glide: A New Approach for Rapid, Accurate Docking and Scoring. 1. Method
and Assessment of Docking Accuracy](https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/Topic_03/Glide.pdf) [pdf]
- [Ligand binding efficiency: trends, physical basis, and implications](https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/Topic_03/JMedChem_2008_51_2432.pdf) [pdf]
- [Pharao: Pharmacophore alignment and optimization](https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/Topic_03/Pharao.pdf) [pdf]
- [A practical guide to large-scale docking](https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/Topic_03/Guide_To_Docking.pdf) [pdf]

#### Course manual:

- [Chapter 6: Virtual screening](https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/Topic_03/6-Virtual_screening.pdf) [pdf]

#### Slides:

- [Lecture slides of topic 03](https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/Topic_03/Slides_03.pdf) [pdf]


#### Exercises:

To practice the lessons learned, we make use of a [virtual workstation](https://teaching2-soc-eu-west2.gcp.tsg.schrodinger.com/workstation/#/) with the software tool Maestro from [Schrödinger](https://www.schrodinger.com) already installed. You need an account that will provided to you after inscription to this course. Tutorials of the different exercises can be donwloaded from these links:

- [Protein-ligand docking exercise](https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/Topic_03/gb-docking-ls.pdf) [pdf]
- [Structure-based virtual screening exercise](https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/Topic_03/bs-sbvs-ls.pdf) [pdf]
- [Pharmacophore searching exercise](https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/Topic_03/https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/Topic_03/Pharmacophore_Searching.pdf) [pdf]



## Topic 4 - Force fields, molecular mechanics and dynamics

In this serie of lessons, the general concepts of a force field are explained. Buidling further upon this, concept of moelcular mechanics and molecular dynamics are highlighted.

#### Prepare yourself:

It is highly recommended that you prepare yourselves by go through the following scientific paper and movie well in advance:

- [Molecular mechanics and dynamics](https://www.youtube.com/watch?v=A9awBW-Gczk&t=85s) [YouTube - 5'12"]
- [Computational chemistry: molecular mechanics, dynamics and force fields](https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/Topic_04/Computational_chemistry_paper.pdf) [pdf]

#### Course manual:

- [Chapter 7: Molecular mechanics and conformational analysis](https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/Topic_04/7-Molecular_mechanics_and_conformational_analysis.pdf) [pdf]
- [Chapter 8: Molecular dynamics](https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/Topic_04/8-Molecular_dynamics.pdf) [pdf]

#### Slides:

- [Lecture slides of topic 04](https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/Topic_04/Slides_04.pdf) [pdf]



## Topic 5 - Artificial intelligence and virtual reality in computational drug design

In the first part, you will learn how artificial intelligence and computational drug design are integrated in the pharmaceutical industry. In the second part of this topic, aspects of how virtual reality can ve used to visualise protein structures and protein-ligand complexes is illustrated.

The AI part of this course is prepared and presented by Dr. Dries Van Rompay, a scientist at Johnson & Johnson in Beerse.

#### Prepare yourself:

Have a look at the following overview papers and movie to get yourselves acquainted with the topic:

- [AI-enabled drug discovery](https://www.youtube.com/watch?v=RPBDhogTIT0) [YouTube - 4'07"]
- [Virtual reality for drug discovery](https://www.youtube.com/watch?v=beYyi0p0L5Y) [YouTube - 2'24"]
- [Artificial intelligence: a novel approach for drug discovery](https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/Topic_05/AI_and_DD.pdf) [pdf]
- [Advancing drug discovery via artificial intelligence](https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/Topic_05/AI_and_industry.pdf) [pdf]
- [The emerging potential of interactive virtual reality in drug discovery](https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/Topic_05/The_emerging_potential_of_interactive_virtual_reality_in_drug_discovery.pdf) [pdf]


#### Slides:

- [Lecture slides of topic 05](https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/Topic_05/AI_in_drug_discovery.pdf) [pdf]

</br>

---

</br>

> **Note**
> This course and accompanying course material has been developed with financial support of the [European Union Recovery and Resilience Facility](https://www.esf-vlaanderen.be/herstel-en-veerkrachtfaciliteit-van-de-europese-unie-rrf) (RRF).


<pre>
<img src="https://github.com/UAMCAntwerpen/2040FBDBIC/blob/master/rrf_logo.png" width="300px">
</pre>
