# Homology-Detection
Sex Chromosome Evolution Analysis

## Overview

This project aims to explore the homology between the human X chromosome and the chicken Z chromosome. We will compare protein sequences from both species to identify orthologous genes and investigate whether these chromosomes are homologous. The analysis utilizes sequence alignment scoring (with the BLOSUM62 substitution matrix) and the Best Reciprocal Hit (BRH) method for identifying orthologous gene pairs.

## Objectives
Land vertebrates exhibit a variety of sex-determination systems. One interesting question in evolutionary biology is whether the mammalian X chromosome and the avian (chicken) Z chromosome are homologous. To explore this, compare genes from humans and chickens using sequence alignment techniques and the Best Reciprocal Hit (BRH) method.

The primary objective is to identify whether the X and Z chromosomes share orthologous genes, which would suggest homology. If no such orthologs are found, it would support the hypothesis that these chromosomes evolved independently.

## Getting Started

Prerequisites
To run this analysis, you need the following files:

- humanChickenProteins.py: Contains protein data for both human and chicken genes.
- blosum62.py: Provides the BLOSUM62 substitution matrix for sequence alignments.
- SexChromosomeEvolution.ipynb: The main Jupyter notebook to run the analysis.

## Installation
Clone the repository or download the necessary files.
Install the required dependencies:
- Python 3.x (preferably 3.6+)
- Jupyter Notebook (for running the ipynb file)
- numpy for numerical operations (can be installed via pip install numpy)
Files
- humanChickenProteins.py: Contains the gene data for humans and chickens, including gene names, chromosome information, and protein sequences.
- blosum62.py: The BLOSUM62 matrix used for sequence alignment scoring.
- SexChromosomeEvolution.ipynb: The Jupyter notebook where the sequence alignment and BRH analysis is performed.

## Usage

- Ensure that the required files are in the same directory as SexChromosomeEvolution.ipynb or modify the paths in the notebook accordingly.

- Open SexChromosomeEvolution.ipynb in a Jupyter Notebook environment.

- Follow the instructions in the notebook to perform the analysis and interpret the results.

## Functions

- memoAlignScore(S1, S2, gap, substitutionMatrix, memo)
Computes the alignment score between two sequences using memoization to improve efficiency.
Parameters:
S1, S2: Sequences to align.
gap: Gap penalty for sequence alignment.

- substitutionMatrix: The substitution matrix to use (BLOSUM62 in this case).
memo: A dictionary for memoization to store previously computed scores.
allScores(geneList1, geneList2)
Computes the alignment scores between all pairs of genes from two gene lists (human and chicken).
Parameters:
geneList1, geneList2: Lists of gene names for human and chicken.
Returns a dictionary with gene pairs as keys (e.g., ('h0', 'c3')) and alignment scores as values.
closestMatch(geneName, allScoresD)
Finds the closest match for a given gene from the other species based on the highest alignment score.
Parameters:
- geneName: The gene name to search for in the alignment scores dictionary.

- allScoresD: A dictionary of alignment scores between genes from human and chicken.

- printBRH(geneName, allScoresD)
Finds and prints the Best Reciprocal Hit (BRH) for a given gene from the other species.
Parameters:
geneName: The gene name to search for in the alignment scores dictionary.
allScoresD: A dictionary of alignment scores between genes from human and chicken.
Sample Data

### Example Data Files
The following sample gene lists are provided for testing the functions:

sampleHumanGeneList: A small subset of human genes.
sampleChickenGeneList: A small subset of chicken genes.
geneD: A dictionary that contains gene information such as chromosome location and protein sequence.
Sample Run
def runBRHSample():
    '''Print best reciprocal hits for sample data. First in human
    chromosome order, then in chicken chromosome order.'''
    allScoresD = allScores(sampleHumanGeneList, sampleChickenGeneList)
    print('human --- chicken')
    for geneName in sampleHumanGeneList:
        printBRH(geneName, allScoresD)
    print()
    print('chicken --- human')
    for geneName in sampleChickenGeneList:
        printBRH(geneName, allScoresD)
**Sample Output:**

human --- chicken
chr11 118415243 h4 --- chr24 5629899 c19
chr11 133938820 h6 --- chr24 2542440 c17
chr14 72399156 h9 --- chr5 28862733 c22
chr3 45016733 h17 --- chr2 43123243 c8

chicken --- human
chr2 43123243 c8 --- chr3 45016733 h17
chr24 2542440 c17 --- chr11 133938820 h6
chr24 5629899 c19 --- chr11 118415243 h4
chr5 28862733 c22 --- chr14 72399156 h9
How to Run the Analysis

Open SexChromosomeEvolution.ipynb in Jupyter Notebook.
Run all cells in sequence to compute the alignment scores and identify Best Reciprocal Hits (BRH).
Review the results, which will include the alignment scores, chromosome mappings, and orthologs for each gene.
Interpret the results to answer the central question: Are the human X chromosome and the chicken Z chromosome homologous?
Example Analysis
After running the analysis with the full data set, you will interpret the output to determine if the human X and chicken Z chromosomes share orthologous genes. If they do, the chromosomes may be homologous; if not, they likely evolved independently.

## Results Interpretation

If the Best Reciprocal Hits indicate that human X and chicken Z chromosomes share orthologs, we can conclude that they are homologous. If no such orthologs are found, it supports the hypothesis that X-Z homology is unlikely and suggests independent evolution of these chromosomes.

## License

This project is licensed under the MIT License 



