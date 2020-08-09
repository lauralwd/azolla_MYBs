This repository contains a phylogenetic tree of R2R3 MYB transcription factors as shown in \[enter publication\].
Additionally, this repository details all code and intermediate files used in the process towards that tree.

\[enter doi link\]

### Quick links:
 * treefile
 * main text figure 
 png, pdf Inkscape_svg

Final alignment: [raw]
& [trimmed]
Final [complete fasta file ] used for the alignment which consists of: 
 


![myb_subfamiles+RNAseq_ufbootstrap.png](figures/myb_subfamiles+RNAseq_ufbootstrap.png)


### Guide through folders and files
The `data` folder contains (unaligned) fasta files, lists of sequence names, and aligned sequences in both trimmed and untrimmed versions. 
File names tend to be long, but are meant to reflect the history of that specific file. 
For example: `1kP_LAR_orthogroup_manual-selection-1_guidev4_aligned-mafft-linsi_trim-gt6-seq80.fasta` contains sequences from the 1kP LAR orthogroup from which a manual selection was taken. 
Second, a set of guide sequences (sequences whose function has been verified) was added.
These sequences were then aligned with mafft-linsi and trimmed with trimAL settings.....

The `analyses` folder contains tree inferences. 
These are organised in folders of starting dataset, and then in folders of alignment and trimming strategy.
Still, a folder may contain several tree inferences made with IQTree. 
The final part of the filename summarises the settings used to create a particular tree file. 
Note that intermediate trees are just that, intermediate results. 

The `figures` folder contains the final versions of the figures shown in ...... in several formats. 
These were made by importing a `.treefile` in [iToL](https://itol.embl.de/), then adding annotation manually, and downloading these as `.svg` file.
These `.svg` files were then finalised in Inkscape to their published form and exported as pdf or png. 

The workflows for which data is shared here, are documented in JuPyter notebooks (`*.ipynb`).
The workflow describing the final version of the tree is [tree_building_workflow_v5].

The other workflows are explorative and should be interpreted as such. 
A blank version of the workflow is maintained [here](https://github.com/lauralwd/lauras_phylogeny_wf).
Note that figures which are embedded in the JuPyter notebooks are not properly displayed online on Github. 
You may download the `.ipynb` files to display them locally, including images. 
Alternatively, a html export may be found [here].

Finaly, the `condaenv.yaml` file details all software names and versions that were used in this project.
This file may be used to recreate the exact software environment for this analysis using [miniconda](https://docs.conda.io/en/latest/miniconda.html).
To do so, issue a command like so `conda env create -f ./condaenv.yaml`. 
One specific perl script that is not included in the conda environment, is stored in the `opt` directory.

### Data sources used in this project
In building these trees, we have made use of publicly available data exclusively. 
_Azolla_ automated annotations are available on [fernbase](ftp://ftp.fernbase.org/Azolla_filiculoides/Azolla_asm_v1.1/)

Each of these sequences and their original accession number are listed in [this fasta file]
