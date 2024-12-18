# PPRInt2.0
# Introduction
PPRInt2.0 is developed for predicting the RNA-interacting residues in the protein using primary sequence information.
# Models
In this program, four different models have been incorporated for predicting the RNA-interacting residues, based on four different features such as, Amino Acid Binary (AAB) profile, Physico-chemical based binary (PCB) profile, Position-Specific Scoring Matrix (PSSM) profile, and Hybrid (AAB+PCB+PSSM) features. The model is trained on patterns of length 17 generated using protein sequences classified as RNA-interacting and non-interacting.

# Modules/Jobs
This program implement four modules (job types); 
- Model 1: AAB profile used as input feature
- Model 2: PCB profile used as input feature
- Model 3: PSSM profile used as input feature 
- Model 4: Hybrid of all features (AAB,PSB,PSSM) used as input feature 

# Minimum USAGE
```
python pprint2.py -i example_seq.fa
```
where example_seq.fa is a input fasta file. This will predict the residues in the seqqeunces provided  in fasta format as RNA-interacting and non-interacting. It will use other parameters by default. It will save output in "outfile.csv" in CSV (comma seperated variables).

# Full Usage
```
Following is complete list of all options, you may get these options by following command: 

python pprint2.py -h 

usage: pprint2.py [-h] -i INPUT [-o OUTPUT] [-j {1,2,3,4}] [-t THRESHOLD]
                 [-p PATH]

Please provide following arguments

optional arguments:
  -h, --help            show this help message and exit
  -i INPUT, --input INPUT
                        Input: Protein sequences in FASTA format
  -o OUTPUT, --output OUTPUT
                        Output: File for saving results by default outfile.csv
  -j {1,2,3,4}, --job {1,2,3,4}
                        Feature Type:
                        1: Amino Acid Binary (AAB) profile
                        2: Physico-chemical based binary (PCB) profile
                        3: Position-Specific Scoring Matrix (PSSM) profile
                        4: Hybrid (AAB+PCB+PSSM), by default 3 (PSSM)
  -t THRESHOLD, --threshold THRESHOLD
                        Threshold: Value between 0 to 1 by default 0.5
  -p PATH, --path PATH  Path: Please provide the path of python which has all libraries installed
 ```

**Input File:** It allow users to provide input in i) FASTA format (standard) and ii) Simple Format. The program will generate the patterns of length 17 for each sequence. 

**Output File:** Program will save result in CSV format, in case user do not provide output file name, it will be stored in outfile.csv. In the output file, three lines will be displayed for each sequence, where, first line represents the ID, second row explains the sequence, and third line exhibits the '+' and '-' sign, where '+' corresponds to residues which are involved in RNA-interaction, and '-' represents the residues which are not involved in RNA-interaction.

**Threshold:** User should provide threshold between 0 and 1, please note score is propotional to the RNA interacting potential of the resiudes..


PPRInt2.0 Package Files
=======================
It contantain following files, brief descript of these files given below


README.md     			: This file provide information about this package

pprint2.py 			: Main python program 

example_output_AAB.txt		: Example output file in csv format for job 1, i.e. AAB based model

example_output_PCB.txt		: Example output file in csv format for job 2, i.e. PCB based model

example_output_PSSM.txt		: Example output file in csv format for job 3, i.e. PSSM based model

example_output_Hybrid.txt	: Example output file in csv format for job 4, i.e. Hybrid profile based model

example_seq.fa			: Example file contain peptide sequenaces in FASTA format

envfile                 	: It is a file which contains the path various tools required to generate PSSM profile

# Reference:

Patiyal S, Dhall A, Bajaj K, Sahu H, Raghava GPS. Prediction of RNA-interacting residues in a protein using CNN and evolutionary profile. Brief Bioinform. 2022 Dec 14:bbac538. <a href="https://pubmed.ncbi.nlm.nih.gov/36516298/">doi: 10.1093/bib/bbac538.</a> PMID: 36516298.
