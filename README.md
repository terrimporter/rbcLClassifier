# Introduction

This repository contains training sets that can be used with the Ribosomal Database Project classifier (Wang et al., 2007) to taxonomically assign Eukaryote rbcL cpDNA sequences.  The latest release can be downloaded from https://github.com/terrimporter/rbcLClassifier/releases .  The trained files ready to be used with the RDP Classifier are available as well as the original files used for training (a taxonomy file and a FASTA file) are available as 'version-ref'.

# How to cite

If you use this rbcL reference set in a publication, please add a link to this page to acknowledge this reference database and if you use the rbcL classifier, please cite:

## The RDP classifier 
Wang et al. (2007) Naïve Bayesian classifier for rapid assignment of rRNA sequences into the new bacterial taxonomy.  Applied and Environmental Microbiology, 73: 5261.

### v1

The rbcLv1_trained.tar.gz file should be decompressed and used directly with the RDP Classifier to make taxonomic assignments to the genus rank.  

Assuming that your query sequences are present in the reference set, using these cutoffs should result in ~99% correct assignments:

Rank | 500bp+ | 400 bp | 300 bp | 200 bp | 100 bp 
--- |:---:|:---:|:---:|:---:|:---:
Superkingdom | 0 | 0 | 0 | 0 | 0 
Kingdom | 0 | 0 | 0 | 0 | 0 
Phylum | 0 | 0 | 0 | 0 | 0   
Class |  | 70 | NA | NA | NA 
Order |  | NA | NA | NA | NA 
Family |  | NA | NA | NA | NA 
Genus |  | NA | NA | NA | NA  
Species |  | NA | NA| NA | NA 

NA = No cutoff available will result in 99% correct assignments

To work with assignments to the family rank, assuming that your query sequences are present in the reference set, using these cutoffs should result in ~95% correct assignments:

Rank | 500bp+ | 400 bp | 300 bp | 200 bp | 100 bp  
--- |:---:|:---:|:---:|:---:|:---:  
Superkingdom | 0 | 0 | 0 | 0 | 0  
Kingdom | 0 | 0 | 0 | 0 | 0  
Phylum | 0 | 0 | 0 | 0 | 0   
Class | 0 | 0 | 0 | 0 | 0  
Order | 0 | 0 | 0 | 0 | 20  
Family | 0 | 0 | 0 | 0 | 50  
Genus |  | NA | NA | NA | NA   
Species |  | NA | NA | NA | NA  

NA = No cutoff available will result in 95% correct assignments

### v1-ref

The rbcLv1-ref_training.tar.gz file should be decompressed.  The folder contains the original taxonomy and fasta files that are included here for reference only.  Sequences were mined from the NCBI nucleotide database in January 2020 and only includes sequences identified to the species rank that are at least 500bp long.  The sequences have been screened to remove any potential bacterial contaminant sequences.  Taxonomic composition is largely Eukaryota with some Bacterial outgroup taxa.  

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

Last updated: January 24, 2020
