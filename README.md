This repository contains a phylogenetic tree of R2R3 MYB transcription factors as shown in \[enter publication\].
Additionally, this repository details all code and intermediate files used in the process towards that tree.

\[enter doi link\]

### Quick links:
 * [treefile](analyses/combi-I-to-VIII-Azfi-Arabidopsis_sequences_linear_trees/aligned-mafft-einsi_trim-gt4/combi-I-to-VIII-Azfi-Arabidopsis_sequences_linear_aligned-mafft-einsi_trim-gt4_iqtree-b1000.treefile)
 * main text figure 
 [png](figures/myb_subfamiles+RNAseq_normalbootstrap-600dpi.png), 
 [pdf](figures/myb_subfamiles+RNAseq_normalbootstrap.pdf) and 
 [Inkscape_svg](figures/myb_subfamiles+RNAseq_normalbootstrap.svg). 
 * Input sequences [fasta ](data/combi-I-to-VIII-Azfi-Arabidopsis_sequences_linear.fasta) 
 * Aligned input sequences [fasta](data/alignments_raw/combi-I-to-VIII-Azfi-Arabidopsis_sequences_linear_aligned-mafft-einsi.fasta),
or [png](data/alignments_raw/combi-I-to-VIII-Azfi-Arabidopsis_sequences_linear_aligned-mafft-einsi.png)
 * Trimmed input sequences [fasta](data/alignments_trimmed/combi-I-to-VIII-Azfi-Arabidopsis_sequences_linear_aligned-mafft-einsi_trim-gt4.fasta)
or [png](data/alignments_trimmed/combi-I-to-VIII-Azfi-Arabidopsis_sequences_linear_aligned-mafft-einsi_trim-gt4.png)

### Final figure with added MSA
The MSA shown here is not included in the manuscript for size limitations. 
It shows the region of R2R3 MYBs that is used to differentiate the different subfamilies as described by J&R.
The figure that is used in the manuscript can be found [here](figures/myb_subfamiles+RNAseq_normalbootstrap-600dpi.png).

![myb_subfamiles+RNAseq_normalbootstrap+MSA-600dpi.png](figures/myb_subfamiles+RNAseq_normalbootstrap+MSA-600dpi.png)

### Guide through folders and files
The `data` folder contains (unaligned) fasta files, lists of sequence names, and aligned sequences in both trimmed and untrimmed versions. 
File names tend to be long, but are meant to reflect the history of that specific file. 
For example: `combi-I-to-VIII-Azfi-Arabidopsis_sequences_linear_aligned-mafft-einsi_trim-gt4.fasta` contains a combination of sequences from the subfamiles I to VIII and sequences from _Azolla filiculoides_ and _Arabidopsis thaliana_. 
Those sequences were then aligned with `mafft-einsi` and trimmed with a gap threshold of .4 (40%).

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
Several notebooks are made available here, most contain intermediate work that is shared for transparency and reproducibility purposes.
 * In `step1_differentiate_subfamilies_VI_and_VII` we gather R2R3 MYB sequences type 6 & 7 and reproduce findings by [Jiang & Rao (2020)](https://doi.org/10.1104/pp.19.01082).
 * In `step2_classify-Azfi-RNAseq-targets` we placed several _Azolla filiculoides_ sequences in the phylogeny of type 6 & 7 R2R3 MYBs and compare the differentiating domains as described by [Jiang & Rao (2020)](https://doi.org/10.1104/pp.19.01082).
 * In `step3_VI-subfam_in_azolla` missing type VI sequences were identified in the _Azolla filiculoides_ genome and added to the phylogeny.
 * In `step4_expanding-phylogeny` the phylogenetic analysis was expanded with R2R3 MYB sequences from all subfamilies and not just VI and VII were taken into account.
 * Finally, in `step5_supplement-with-arabidopsis-sequences` some uninformative and rogue sequences were removed, _Arabidopsis thaliana_ sequences were added, more _Azolla filiculoides_ sequences were added, and the tree was annotated with RNA-seq data for _A. filiculoides_.
 
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

Each of these sequences and their original accession number are listed in the data folder, organised in files per subfamily type.
These sequences originate from several databases, each with a slightly different naming system.
The [Jiang & Rao (2020)](https://doi.org/10.1104/pp.19.01082) paper lists each of the species used here, and where to find the right database to search for accession numbers. 
Those are predominantly:
 * NCBI nucleotide and protein.
 * [Fernbase](https://www.fernbase.org/) for _Azolla filiculoides_ and _Salvinia cuculata_.
 * [Congenie](http://www.congenie.org/) for _Picea abies_.
 * [marchantia.info](https://marchantia.info/search) for _Marchantia polymorpha_.
 * [uniprot](http://www.uniprot.org) for _Arabidopsis thaliana_ sequences.

