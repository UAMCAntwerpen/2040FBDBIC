# Input files for notebook 6 (molecular docking)

Everything in this folder is read by `Notebook-6-molecular-docking.ipynb`, so that the notebook
runs without an internet connection (as on the CalcUA compute nodes).

| File | What it is |
|---|---|
| `4HG7_receptor.pdbqt` | MDM2 from PDB 4HG7, prepared for AutoDock Vina. **Used for all docking runs except one diagnostic.** |
| `4HG7_receptor_waters.pdbqt` | The same receptor plus the three crystallographic waters that contact nutlin-3a (HOH 307, 327, 338). Only used in the redocking diagnosis of section 6. |
| `known_inhibitors_potency.csv` | Median biochemical potency (pChEMBL) of the five validation inhibitors of notebook 5, from ChEMBL. |
| `pharmacophore_refined_collection_reference.csv` | A copy of `scratch/pharmacophore_refined_collection.csv` from the reference run of notebook 5 (116 compounds). Only used when a student has not run notebooks 4 and 5. |

## Software environment (important)

The notebook needs **AutoDock Vina 1.2.7**, whose PyPI wheels cover **Python 3.8-3.12 only** (there
is no cp313 or cp314 wheel, so `pip install vina` on Python 3.13+ attempts a source build and
fails). conda-forge does provide py313 and py314 builds. The other notebooks of this course run on
Python 3.13, so this is the one notebook that may need an environment of its own:

```
conda create -n docking -c conda-forge python=3.12 vina
conda activate docking
pip install meeko rdkit py3Dmol pandas numpy matplotlib tqdm jupyter
```

The notebook checks the Python version in its first code cell and prints this advice if needed.
It was developed and tested with Vina 1.2.7, Meeko 0.8.0, RDKit 2026.03.6 on Python 3.12.14.

## How the receptor files were made

Software: Meeko 0.8.0, RDKit 2026.03, Python 3.12.

1. Start from `assets/databases/notebook-5/4HG7.pdb` (MDM2 residues 18-108, chain A, 1.6 A,
   with the E69A/K70A surface-entropy mutations of the crystallised construct).
2. Keep only the `ATOM` records of chain A. Removed: nutlin-3a (`NUT 201`), the half-occupancy
   sulfate (`SO4 202`) and all 97 waters. For `4HG7_receptor_waters.pdbqt` the waters HOH 307,
   327 and 338 (the three within 3.2 A of the ligand) were kept.
3. Alternate locations: altloc `A` everywhere (`default_altloc="A"`). Nine residues have two
   conformations; of these only Leu57 lines the pocket (altloc A is its major conformation,
   occupancy 0.8), and Gln59 sits at the rim (two conformations at 0.5 each).
4. Protonation: Meeko's residue templates, i.e. the standard states at pH 7 (Lys, Arg positive;
   Asp, Glu negative). The two pocket histidines were assigned explicitly from their hydrogen-bond
   partners in the crystal: His73 as **HID** (its N-delta1 is 2.6 A from a sulfate oxygen) and
   His96 as **HIE** (its N-epsilon2 is 3.3 A from the Val93 backbone carbonyl). The chain ends
   (Gln18, Val108) are artificial ends of the construct and were left uncharged (Meeko's default
   template padding).
5. Hydrogens added by Meeko; the PDBQT keeps the polar hydrogens only (AutoDock united-atom
   convention), with Gasteiger charges from the templates (Vina itself does not use charges).

Equivalent command line:

```
mk_prepare_receptor.py --read_pdb protein.pdb --default_altloc A -n "A:73=HID,A:96=HIE" -o 4HG7_receptor -p
```

The notebook contains an optional cell that regenerates both files with the Meeko Python API;
its output is identical to the committed files.

## Why 4HG7 and not 1YCR

The Tyr100 side chain acts as a lid on the Leu26 subpocket and changes rotamer between the
peptide-bound and the inhibitor-bound forms. Measured chi1 (N-CA-CB-CG, altloc A):

| Structure | ligand | Tyr100 chi1 |
|---|---|---|
| 1YCR | p53 peptide | -162.3 deg |
| 4HG7 | nutlin-3a | -92.9 deg |
| 5TRF | SAR405838 | -101.1 deg |
| 5OC8 | siremadlin | -77.1 deg |
| 4ZYF | NVP-CGM097 | -91.0 deg |
| 4OAS | piperidinone | -90.4 deg |

1YCR is the outlier, which is why the notebook docks into 4HG7 and keeps 1YCR only as the reference
for the Phe19/Trp23/Leu26 hot-spot positions.

## Whether the three waters are conserved

The notebook states that each of the three bridging waters is displaced by at least one other MDM2
inhibitor. This was checked by superposing each complex on 4HG7 over the MDM2 C-alpha atoms of
residues 25-104 (C-alpha RMSD 0.66-1.08 A) and measuring, for each 4HG7 water position, the distance
to the nearest ligand atom and to the nearest water of that structure:

| Structure | ligand | HOH 307 | HOH 327 | HOH 338 |
|---|---|---|---|---|
| 5TRF | SAR405838 | displaced, ligand atom 1.8 A | water 2.9 A | displaced, ligand atom 2.7 A |
| 5OC8 | siremadlin | water 2.1 A | water 1.9 A | water 3.8 A |
| 4ZYF | NVP-CGM097 | water 1.1 A | water 2.7 A | no water within 5 A |
| 4OAS | piperidinone | displaced, ligand atom 0.6 A | water 2.0 A | water 2.8 A |

## Where the potencies come from

ChEMBL web services, target CHEMBL5023 (human MDM2), retrieved on 2 October 2026. For each
compound all activity records with a pChEMBL value and assay type `B` (binding) were taken,
records whose description reports a cellular readout ("cell-based", "cell line",
"in human ... cells") were dropped, and the median pChEMBL is reported together with the range
and the number of measurements. IC50, Ki and Kd values are pooled, which is an approximation.
