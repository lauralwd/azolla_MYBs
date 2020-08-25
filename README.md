This repository contains a phylogenetic tree of R2R3 MYB transcription factors as shown in \[enter publication\].
Additionally, this repository details all code and intermediate files used in the process towards that tree.

\[enter doi link\]

### Quick links:
 * [treefile](analyses/combi-I-to-VIII-Azfi-Arabidopsis_sequences_linear_trees/aligned-mafft-einsi_trim-gt4/combi-I-to-VIII-Azfi-Arabidopsis_sequences_linear_aligned-mafft-einsi_trim-gt4_iqtree-b1000.treefile)
 * main text figure 
 [png](figures/myb_subfamiles+RNAseq_normalbootstrap-600dpi.png), 
 [pdf](figures/myb_subfamiles+RNAseq_normalbootstrap.pdf) and 
 [Inkscape_svg](figures/myb_subfamiles+RNAseq_normalbootstrap.svg). 

Final input data: 
 * Input sequences [fasta ](data/combi-I-to-VIII-Azfi-Arabidopsis_sequences_linear.fasta) 
 * Aligned input sequences [fasta](data/alignments_raw/combi-I-to-VIII-Azfi-Arabidopsis_sequences_linear_aligned-mafft-einsi.fasta),
or [png](data/alignments_raw/combi-I-to-VIII-Azfi-Arabidopsis_sequences_linear_aligned-mafft-einsi.png)
 * Trimmed input sequences [fasta](data/alignments_trimmed/combi-I-to-VIII-Azfi-Arabidopsis_sequences_linear_aligned-mafft-einsi_trim-gt4.fasta)
or [png](data/alignments_trimmed/combi-I-to-VIII-Azfi-Arabidopsis_sequences_linear_aligned-mafft-einsi_trim-gt4.png)

 
 

### Final figure with added MSA
The MSA shown here is not included in the manuscript for size limitations. 
It shows the region of R2R3 MYBs that is used to differentiate the different subfamilies as described by J&R.

![myb_subfamiles+RNAseq_normalbootstrap+MSA-600dpi.png](figures/myb_subfamiles+RNAseq_normalbootstrap+MSA-600dpi.png)


### Guide through folders and files
The `data` folder contains (unaligned) fasta files, lists of sequence names, and aligned sequences in both trimmed and untrimmed versions. 
File names tend to be long, but are meant to reflect the history of that specific file. 
For example: `combi-I-to-VIII-Azfi-Arabidopsis_sequences_linear_aligned-mafft-einsi_trim-gt4.fasta` contains sequences from the subfamiles I to VIII and sequenes from _Azolla filiculoides_ and _Arabidopsis thaliana_. 
The sequences were aligned with `mafft-einsi` and trimmed with a gap threshold of .4 (40%).

The `analyses` folder contains tree inferences and annotation information for use in iToL.
These are organised in folders of starting dataset, and then in folders of alignment and trimming strategy.
Still, a folder may contain several tree inferences made with IQTree. 
The final part of the filename summarises the settings used to create a particular tree file. 
Note that intermediate trees are just that, intermediate results. 

The `figures` folder contains the final versions of the figures shown in the manuscript in several formats. 
These were made by importing a `.treefile` in [iToL](https://itol.embl.de/), then adding annotation manually, and downloading these as `.svg` file.
Annotation files for use in itol can be found in the different directories in the `analyses` directory
These `.svg` files were then finalised in Inkscape to their published form and exported as pdf or png. 

The workflows for which data is shared here, are documented in JuPyter notebooks (`*.ipynb`).
~~The workflow describing the final version of the tree is [tree_building_workflow_v5].~~

A blank version of the workflow is maintained [here](https://github.com/lauralwd/lauras_phylogeny_wf).
Note that figures which are embedded in the JuPyter notebooks may not properly displayed online on Github. 
You may download the `.ipynb` files to display them locally, including images. 
Alternatively, a html export may be found accompanying the JuPy notebook file.

Finaly, the `envs` directory contains conda environment export files detailing all software names and versions that were used in this project.
This file may be used to recreate the exact software environment for this analysis using [miniconda](https://docs.conda.io/en/latest/miniconda.html).
To do so, issue a command like so `conda env create -f ./condaenv.yaml`. 

### Data sources used in this project
In building these trees, we have made use of publicly available data exclusively. 
Most notably, we build here upon the work of [Jiang & Rao (2020)](https://doi.org/10.1104/pp.19.01082).
_Azolla_ automated annotations are available on [fernbase](ftp://ftp.fernbase.org/Azolla_filiculoides/Azolla_asm_v1.1/)

Each of these sequences and their original accession number are listed in [this fasta file]
