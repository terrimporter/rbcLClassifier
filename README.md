# Introduction

This repository contains training sets that can be used with the Ribosomal Database Project classifier (Wang et al., 2007) to taxonomically assign Eukaryote rbcL cpDNA sequences including plants.  The latest release can be downloaded from https://github.com/terrimporter/rbcLClassifier/releases .  The trained files ready to be used with the RDP Classifier are available as well as the original files used for training (a taxonomy file and a FASTA file) are available as 'version-ref'.  A diatom-specific rbcL classifier is also available https://github.com/terrimporter/rbcLdiatomClassifier .

# How to cite

If you use this rbcL reference set in a publication, please add a link to this page to acknowledge this reference database and if you use the rbcL classifier, please cite:

Wang et al. (2007) Naïve Bayesian classifier for rapid assignment of rRNA sequences into the new bacterial taxonomy.  Applied and Environmental Microbiology, 73: 5261.

# How to use

Decompress the tar.gz file:

$ tar -xvzf FileName.tar.gz

Use with the RDP classifier:

java -Xmx8g -jar /path/to/rdp_classifier_2.12/dist/classifier.jar classify -t /path/to/mydata_trained/rRNAClassifier.properties -o ClassifiedQueryFilename QueryFilename

# Releases

### v1

The rbcLv1_trained.tar.gz file should be decompressed and used directly with the RDP Classifier to make taxonomic assignments.  

RbcL records were mined from the NCBI nucleotide database [Jan. 10/20]. Sequences were filtered to retain only those that are 500bp+, contain no non-nucleotide characters, and have Linnean binomial species names.  Sequences were screened for bacterial contaminants. Bacterial outgroup sequences were added.

Taxonomic assignment results should be filtered according to their bootstrap support values to reduce false positive assignments. Cutoffs are based on leave-one-sequence-out testing of non-singleton genera. Here we recommend MINIMUM bootstrap cutoffs according to query length and assignment rank. Assuming your query sequences are represented in the reference set, using the cutoffs presented in the first table below should ensure 99% accuracy. If you wish to cast a wider net, you can use the second table below for 95% accuracy.

Bootstrap support cutoffs, 99% accuracy:

Rank | 500 bp+ | 400 bp | 300 bp | 200 bp | 100 bp 
--- |:---:|:---:|:---:|:---:|:---:
Superkingdom | 0 | 0 | 0 | 0 | 0 
Kingdom | 0 | 0 | 0 | 0 | 0 
Phylum | 0 | 0 | 0 | 0 | 0   
Class | NA | 70 | NA | NA | NA 
Order | NA | NA | NA | NA | NA 
Family | NA | NA | NA | NA | NA 
Genus | NA | NA | NA | NA | NA  
Species | NA | NA | NA| NA | NA 

NA = No cutoff available will result in 99% correct assignments

Bootstrap support cutoffs, 95% accuracy:

Rank | 500 bp+ | 400 bp | 300 bp | 200 bp | 100 bp  
--- |:---:|:---:|:---:|:---:|:---:  
Superkingdom | 0 | 0 | 0 | 0 | 0  
Kingdom | 0 | 0 | 0 | 0 | 0  
Phylum | 0 | 0 | 0 | 0 | 0   
Class | 0 | 0 | 0 | 0 | 0  
Order | 0 | 0 | 0 | 0 | 20  
Family | 0 | 0 | 0 | 0 | 50  
Genus | 95 | NA | NA | NA | NA   
Species | NA | NA | NA | NA | NA  

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

# References

Wang, Q., Garrity, G. M., Tiedje, J. M., & Cole, J. R. (2007). Naive Bayesian Classifier for Rapid Assignment of rRNA Sequences into the New Bacterial Taxonomy. Applied and Environmental Microbiology, 73(16), 5261–5267. Available from https://sourceforge.net/projects/rdp-classifier/

# Acknowledgements

We acknowledge support from the Canadian federal Genomics Research & Development Initiative (GRDI), Metagenomics-Based Ecosystem Biomonitoring (Ecobiomics) project.

Last updated: July 16, 2020
