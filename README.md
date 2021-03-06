This repository contains a phylogenetic tree of R2R3 MYB transcription factors.
Additionally, this repository details all code and intermediate files used in the process towards infering that tree.
Many of these results are intermediate and should be treated as such.
For the final results, please refer to the quick links listed below

Manuscript DOI:  [preprint on bioRXiv](https://www.biorxiv.org/content/10.1101/2020.09.09.289736v2)

Repository DOI: [![DOI](https://zenodo.org/badge/283424814.svg)](https://zenodo.org/badge/latestdoi/283424814)

### Quick links:
 * [treefile](analyses/combi-I-to-VIII-Azfi-Arabidopsis_sequences_linear_trees/aligned-mafft-einsi_trim-gt4/combi-I-to-VIII-Azfi-Arabidopsis_sequences_linear_aligned-mafft-einsi_trim-gt4_iqtree-b1000.treefile)
 * Main text figure 
 [png](figures/myb_subfamiles+RNAseq_normalbootstrap-600dpi.png), 
 [pdf](figures/myb_subfamiles+RNAseq_normalbootstrap.pdf) and 
 [Inkscape_svg](figures/myb_subfamiles+RNAseq_normalbootstrap.svg). 
 * Input sequences [fasta ](data/combi-I-to-VIII-Azfi-Arabidopsis_sequences_linear.fasta) 
 * Aligned input sequences [fasta](data/alignments_raw/combi-I-to-VIII-Azfi-Arabidopsis_sequences_linear_aligned-mafft-einsi.fasta),
or [png](data/alignments_raw/combi-I-to-VIII-Azfi-Arabidopsis_sequences_linear_aligned-mafft-einsi.png)
 * Trimmed input sequences [fasta](data/alignments_trimmed/combi-I-to-VIII-Azfi-Arabidopsis_sequences_linear_aligned-mafft-einsi_trim-gt4.fasta)
or [png](data/alignments_trimmed/combi-I-to-VIII-Azfi-Arabidopsis_sequences_linear_aligned-mafft-einsi_trim-gt4.png)

### Final figure as shown in Dijkhuizen et al. 2021 with added MSA 
The MSA shown below is not included in the manuscript for size limitations. 
It shows the region of R2R3 MYBs used to differentiate the different subfamilies as described by [Jiang & Rao (2020)](https://doi.org/10.1104/pp.19.01082).
The figure actually included in the paper is available [here](figures/myb_subfamiles+RNAseq_normalbootstrap-600dpi.png).

![myb_subfamiles+RNAseq_normalbootstrap+MSA-600dpi.png](figures/myb_subfamiles+RNAseq_normalbootstrap+MSA-600dpi.png)

### Guide through folders and files

The `data` folder contains (unaligned) fasta files, lists of sequence names, and aligned sequences in both trimmed and untrimmed versions. 
File names reflect the history of that specific file and therefore tend to be rather long.
For example `combi-I-to-VIII-Azfi-Arabidopsis_sequences_linear_aligned-mafft-einsi_trim-gt4.fasta` contains a combination of sequences from the subfamilies I to VIII and sequences from _Azolla filiculoides_ and _Arabidopsis thaliana_. 
Those sequences were then aligned with `mafft-einsi` and trimmed with a gap threshold of .4 (40%).

The `analyses` folder contains tree inferences and annotation information for use in iToL.
These are organised in folders of starting dataset, and then in folders of alignment and trimming strategy.
Still, a folder may contain several tree inferences made with IQTree. 
The final part of the filename summarises the settings used to create a particular tree file. 
Note that intermediate trees are just that, intermediate results. 

The `figures` folder contains the final versions of the figures shown in the manuscript in several formats. 
These were made by importing a `.treefile` in [iToL](https://itol.embl.de/), then adding annotation manually, and downloading these as `.svg` file.
Annotation files for use in iToL can be found in the different directories in the `analyses` directory
These `.svg` files were then finalised in Inkscape to their published form and exported as pdf or png. 

### Jupyter notebooks
The workflows shared here are documented in JuPyter notebooks (`*.ipynb`).
Most notebooks contain intermediate work that is shared for transparency and reproducibility purposes and should be treated as such. 
Alternativelly, the git history may be explored for more information.
Note that figures which are embedded in the JuPyter notebooks may not be correctly displayed online on Github. 
You may download the `.ipynb` files to display them locally, including images. 
Alternatively, a html export may be found accompanying the JuPy notebook file.

 * In `step1_differentiate_subfamilies_VI_and_VII` 
 ([html preview](https://htmlpreview.github.io/?https://raw.githubusercontent.com/lauralwd/azolla_MYBs/main/html_step1_differentiate_subfamilies_VI_and_VII.html) & 
 [ipynb preview](https://github.com/lauralwd/azolla_MYBs/blob/main/step1_differentiate_subfamilies_VI_and_VII.ipynb))
 we gather R2R3 MYB sequences of subfamily VI & VII and reproduce findings by [Jiang & Rao (2020)](https://doi.org/10.1104/pp.19.01082).
 * In `step2_classify-Azfi-RNAseq-targets` 
 ([html preview](https://htmlpreview.github.io/?https://raw.githubusercontent.com/lauralwd/azolla_MYBs/main/html_step2_classify-Azfi-RNAseq-targets.html) & 
 [ipynb preview](https://github.com/lauralwd/azolla_MYBs/blob/main/step2_classify-Azfi-RNAseq-targets.ipynb))
 we placed several _Azolla filiculoides_ sequences in the phylogeny of subfamily VI & VII R2R3 MYBs and compare the differentiating domains as described by [Jiang & Rao (2020)](https://doi.org/10.1104/pp.19.01082).
 * In `step3_VI-subfam_in_azolla` 
 ([html preview](https://htmlpreview.github.io/?https://raw.githubusercontent.com/lauralwd/azolla_MYBs/main/html_step3_VI-subfam_in_azolla.html) & 
 [ipynb preview](https://github.com/lauralwd/azolla_MYBs/blob/main/step3_VI-subfam_in_azolla.ipynb))
 missing type VI sequences were identified in the _Azolla filiculoides_ genome with hmms and added to the phylogeny.
 * In `step4_expanding-phylogeny`
 ([html preview](https://htmlpreview.github.io/?https://raw.githubusercontent.com/lauralwd/azolla_MYBs/main/html_step4_expanding-phylogeny.html) & 
 [ipynb preview](https://github.com/lauralwd/azolla_MYBs/blob/main/step4_expanding-phylogeny.ipynb))
 the phylogenetic analysis was expanded with R2R3 MYB sequences from all subfamilies (I to VIII). Sequences were taken from the [Jiang & Rao (2020)](https://doi.org/10.1104/pp.19.01082) paper.
 * Finally, in `step5_supplement-with-arabidopsis-sequences` 
 ([html preview](https://htmlpreview.github.io/?https://raw.githubusercontent.com/lauralwd/azolla_MYBs/main/html_step5_supplement-with-arabidopsis-sequences.html) & 
 [ipynb preview](https://github.com/lauralwd/azolla_MYBs/blob/main/step5_supplement-with-arabidopsis-sequences.ipynb))
 some uninformative and rogue sequences were removed, _Arabidopsis thaliana_ sequences were added, more _Azolla filiculoides_ sequences were added, and the tree was annotated with RNA-seq data for _A. filiculoides_.
 
A template version of the workflow is maintained [here](https://github.com/lauralwd/lauras_phylogeny_wf).

Finally, the `envs` directory contains conda environment export files detailing all software names and versions that were used in this project.
This file may be used to recreate the exact software environment for this analysis using [miniconda](https://docs.conda.io/en/latest/miniconda.html).
To do so, issue a command like so `conda env create -f ./condaenv.yaml`. 

### Data sources used in this project
In building these trees, we have made use of publicly available data exclusively. 
Most notably, we build here upon the work of [Jiang & Rao (2020)](https://doi.org/10.1104/pp.19.01082).
_Azolla_ automated annotations are available on [fernbase](ftp://ftp.fernbase.org/Azolla_filiculoides/Azolla_asm_v1.1/).
The manually re-ananotated _A. filiculoides_ R2R3 MYB sequence is made available in ENA and NCBI under accession number [....] .
This sequence, and all raw RNA-seq reads used in this project are also made availble in ENA and NCBI under project accession number [....] .

All sequences taken from the several databases used here and their original accession numbers are listed in the data folder, organised in files per subfamily type.
These sequences originate from several databases, each with a slightly different naming system.
The [Jiang & Rao (2020)](https://doi.org/10.1104/pp.19.01082) paper lists each of the species used here, and where to find the right database to search for accession numbers. 
Those are predominantly:
 * NCBI nucleotide and protein.
 * [Fernbase](https://www.fernbase.org/) for _Azolla filiculoides_ and _Salvinia cuculata_.
 * [Congenie](http://www.congenie.org/) for _Picea abies_.
 * [marchantia.info](https://marchantia.info/search) for _Marchantia polymorpha_.
 * [uniprot](http://www.uniprot.org) for _Arabidopsis thaliana_ sequences.

## Links
 * [The Azolla lab](https://www.uu.nl/en/research/molecular-plant-physiology/research-topics/azolla-for-the-circular-economy) at Utrecht University
 * [A MIKC phylogeny workflow](https://github.com/lauralwd/MIKC_tree), similar to this one and featured in the same preprint.
 * [A blank version of this workflow](https://github.com/lauralwd/lauras_phylogeny_wf)

## Authors
The analyses in this repository were conceived and executed by 
Dr. Henriette Schluepmann ([orcid](https://orcid.org/0000-0001-6171-3029)
                           [Utrecht University](https://www.uu.nl/staff/hschlupmann)
                          )
and PhD candidate 
Laura Dijkhuizen ([orcid](https://orcid.org/0000-0002-4628-7671) 
                  [Utrecht University](https://www.uu.nl/staff/lwdijkhuizen)
                  [website](https://www.lauradijkhuizen.com))
.
