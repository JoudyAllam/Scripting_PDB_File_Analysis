# Statistical Analysis of Protein Structures: Retrieving and Evaluating PDB Data

## Project Overview

This project focuses on retrieving and analyzing data from the Protein Data Bank (PDB), a repository for the three-dimensional structural data of biological molecules such as proteins. Using Python, the program automates: 

- **Part 1:** Download and validation of user‐specified PDB IDs from the database
- **Part 2:** Statistical analysis on the amino acid content of proteins  
- **Part 3:** Computation and visualization of interatomic distances within protein structures.

<div align="right" style="font-size:16px; color:black; font-family:Segoe UI, sans-serif;">
Developed by Joudy Allam & Haya Mazyad 
    
As part of the *Script Programming* course
</div>

---

## Table of Contents
- [Project Overview](#project-overview)
- [Part 1: Retrieving PDB Files](#part-1-retrieving-pdb-files)
- [Part 2: Amino Acid Frequency Analysis](#part-2-amino-acid-frequency-analysis)
- [Part 3: Interatomic Distance Calculations](#part-3-interatomic-distance-calculations)
- [Requirements](#requirements)

---

## Part 1: Retrieving PDB Files

The first part of the project focuses on downloading PDB files using Python's web-scraping libraries (such as Selenium and BeautifulSoup). 

### Key Features:
- **Input:** Users enter a list of PDB file identifiers (4-character unique codes).
- **Validation:** Checks if entered IDs are valid and if the corresponding files are already downloaded.
- **Filtering:** Retrieves only files with protein structures determined by X-ray diffraction. Any non-protein or incompatible files are discarded.
- **Error Handling:** Returns an error message for invalid or non-existent PDB identifiers.

### Example:
For example, to retrieve the PDB file with identifier `3GWD`, the URL would be: 
```
http://files.rcsb.org/view/3GWD.pdb
```

## Part 2: Amino Acid Frequency Analysis

The second part calculates and visualizes the frequency and percentage of amino acids within the retrieved PDB files.

### Amino Acids:
Proteins are composed of 20 standard amino acids, which can be categorized based on their properties:
- **Positively charged:** R, H, K
- **Negatively charged:** D, E
- **Polar:** N, C, Q, S, T, Y
- **Non-polar:** A, I, L, M, F, P, W, V, G

### Analysis Options:
1. **All Amino Acids:** Displays the frequency and percentage for all 20 amino acids, sorted in descending order.
2. **By Category:** Displays the frequency and percentage for amino acids grouped by category (positively charged, negatively charged, polar, non-polar).
3. **Within a Category:** Prompts the user to select a specific category and displays the corresponding amino acids' statistics.
4. **Specific Amino Acid:** Prompts the user for a single amino acid and returns its percentage in the protein.

### Visualization:
The program generates interactive plots (using libraries such as Plotly) to visualize the frequency and percentage data, allowing users to export these graphs as HTML files for easy sharing.
- Note: Plotly plots may not display properly in Jupyter notebook or HTML format due to their large size. However, the plots can be viewed by copying their permalink and pasting it into https://nbviewer.org/, which renders the interactive charts correctly.

## Part 3: Interatomic Distance Calculations

In the third part, the program calculates the interatomic distances between the C-alpha (CA) atoms of the first and last standard amino acids in each protein PDB file.

### Output:
- **Statistics:** The script computes the minimum, maximum, median, mean, and standard deviation of the CA distances across all retrieved proteins.
- **Visualization:** A plot illustrating the distribution of these distances is also generated to provide insight into the protein structure's spatial characteristics.

## Requirements

- **Python**: The script is written in Python 3 and utilizes modern Python libraries.
- **plotly**: Required for generating interactive plots and visualizations of the amino acid data.
- **urllib**: This is a standard Python library used for fetching data from URLs (in this case, to download PDB files).
- **re (Regular Expressions)**: Another standard Python library used to validate and parse identifiers in the script.
- **os**: This is a standard Python module used for file handling (e.g., checking if files exist).
- **numpy**: Used in the script for numerical operations.

#### Optional (if needed):
- **plotly.offline**: For saving and viewing the generated plots offline.
