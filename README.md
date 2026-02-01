# This is for EuchroGene Members.

TPpred3 is a machine learning-based bioinformatics tool designed to predict the subcellular 
localization of eukaryotic proteins, distinguishing mitochondrial and chloroplastic targeting 
peptides from secretory or cytosolic signals based on sequence profiles.

Functions:
- Predict Organelle Targeting: Classifies N-terminal sorting signals to determine if proteins
  are destined for mitochondria, chloroplasts, or other subcellular locations.
- Identify Cleavage Sites: Pinpoints the specific site where the transit peptide is cleaved, 
  defining the boundary between the targeting signal and the mature protein.
- Analyze Sequence Features: Utilizes N-to-1 Extreme Learning Machines (ELM) and Support Vector 
  Machines (SVM) to recognize physicochemical patterns and motifs associated with protein transport.
- Screen High-Throughput Data: Efficiently processes large-scale proteomic datasets to annotate 
  organelle-targeted proteins and refine subcellular localization predictions.

## To install, copy and paste the following commands in a Jupyter Terminal, and execute:

1. install the software:
```
wget https://github.com/euchrogene/TPpred3/raw/refs/heads/main/Installer.sh
sudo bash Installer.sh
sudo rm Installer.sh
```

2. display installed software
```
EG_tools
```

3. download example protein sequence
```
wget https://github.com/euchrogene/TPpred3/raw/refs/heads/main/Example_protein.fa
```

4. example command line
```
TPpred3 -f Example_protein.fa -k N
```

5. show help contents
```
TPpred3
```

## Help contents:
```
________________________________________________________________________________________________

Tool Type: TPpred3

TPpred3 is a machine learning-based bioinformatics tool designed to predict the subcellular localization 
of eukaryotic proteins, specifically identifying N-terminal targeting peptides that direct proteins to 
chloroplasts or mitochondria.

Functions:

- Predict Organelle Targeting: Classifies proteins based on the presence of N-terminal sorting signals, 
  determining if they are targeted to the mitochondrion, chloroplast, or neither (secretory/cytosolic).

- Identify Cleavage Sites: Detects the specific cleavage site where the transit peptide is removed upon 
  import, delineating the boundary between the targeting signal and the mature protein.

- Analyze Sequence Motifs: Utilizes N-to-1 extreme learning machines (ELM) and Grammatical Restrained 
  Hidden Conditional Random Fields (GRHCRF) to recognize subtle physicochemical patterns and motifs 
  associated with organelle transport.

- Process Large Datasets: Suitable for high-throughput analysis of proteomes to annotate organelle-targeted 
  proteins and refine the characterization of subcellular localization signals.

If you find any bugs, please email: bioinformatics@euchrogene.com

________________________________________________________________________________________________

Parameter instruction:
- The name of the input FASTA file containing protein sequences to be predicted.
- The output file name where predictions will be stored.
- The kingdom the sequences belong to. You must specify "P" for plant species or "N" for non-plant species. 
  When a plant (P) is specified, TPpred3 predicts chloroplastic targeting signals, whereas only 
  mitochondrial signals are predicted for non-plant sequences. The default value is plant mode (P).

You can run this software by modifying the following example:

TPpred3 -f Example_protein.fa -k N
________________________________________________________________________________________________

Usage;

TPpred3 -f FASTA_File -o out_file [-k P,N] [-m [json|gff3]] [-t threads] 

 TPpred3: Prediction of organelle targeting peptides in proteins.

   Copyright (C) 2015 Castrense Savojardo
   Bologna Biocomputing Group
   University of Bologna, Italy.
   savojard@biocomp.unibo.it

optional arguments:
  -h, --help            show this help message and exit
  -m {json,gff3}        The output format: json or gff3 (default)
  -t THREADS            Number of threads (default 32)

OPTIONS:
  -f FASTA              Protein sequences in FASTA format. Required.
  -o FILE               Output prediction file. Optional, default: STDOUT.
  -k {P,N}              Protein kingdom: P="Plant" or N="non-Plant"

______________________________________________________________________________________________
```


# Citation

## TPpred3
Castrense Savojardo, Pier Luigi Martelli, Piero Fariselli, Rita Casadio, TPpred3 detects and discriminates mitochondrial and chloroplastic targeting peptides in eukaryotic proteins, Bioinformatics, Volume 31, Issue 20, October 2015, Pages 3269–3275, https://doi.org/10.1093/bioinformatics/btv367
