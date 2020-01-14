# Introduction

This repository contains training sets that can be used with the Ribosomal Database Project classifier (Wang et al., 2007) to taxonomically assign Eukaryote rbcL cpDNA sequences.  The latest release can be downloaded from https://github.com/terrimporter/rbcLClassifier/releases .  The trained files ready to be used with the RDP Classifier are available as well as the original files used for training (a taxonomy file and a FASTA file) are available as 'version-ref'.

## The RDP classifier 
Wang et al. (2007) Naïve Bayesian classifier for rapid assignment of rRNA sequences into the new bacterial taxonomy.  Applied and Environmental Microbiology, 73: 5261.

### v1

The rbcLv1_training.tar.gz file should be decompressed.  The folder contains the original taxonomy and fasta files that are included here for reference only. 

The rbcLv1_trained.tar.gz file should be decompressed and used directly with the RDP Classifier to make taxonomic assignments to the genus rank.

The rbcLv1_training.tar.gz file should be decompressed.  The folder contains the original taxonomy and fasta files that are included here for reference only.  They were originally mined from GenBank in January 2020.  Only sequences identified to the species rank in the NCBI nucleotide database.  All sequences here are at least 500bp long and have been screened to remove any bacterial contaminant sequences.  Taxonomic composition is largely Eukaryota with some Bacterial outgroup taxa.  

# How to use

Decompress the tar.gz file:

$ tar -xvzf FileName.tar.gz

Use with the RDP classifier:

java -Xmx8g -jar /path/to/rdp_classifier_2.12/dist/classifier.jar classify -t /path/to/rbcLversion_trained/rRNAClassifier.properties -o ClassifiedQueryFilename QueryFilename

# Additional information

For additional information on how to run the RDP classifier, see the RDPclassifier 2.12 README.

The RDP classifier v2.12 can be downloaded from:
https://sourceforge.net/projects/rdp-classifier/

# Acknowledgements

We acknowledge support from the Canadian federal Genomics Research & Development Initiative (GRDI), Metagenomics-Based Ecosystem Biomonitoring (Ecobiomics) project.

Last updated: January 20, 2020
