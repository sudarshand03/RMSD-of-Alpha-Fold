# RMSD-of-Alpha-Fold

RMSD deviation between predicted Alpha Fold strucutres using Alpha Fold multimer and crystal structures from Protein Data Bank


Experiment 1: Can AlphaFold Predict Static Structure 

Introduction and Background

The first experiment focuses on the structural analysis of PLCC proteins as a sample for whether AlphaFold 2 Multimer can reliably predict SH2 binding complexes. SH2 domains were chosen due to the diversity in the peptide binder and sequence, which lead to a large conformational landscape.

Materials and Methods

Data Collection

Downloading PLCC PDB Files: The research commenced with the retrieval of PLCC PDB files from the Protein Data Bank,

Acquiring FASTA Sequences: Alongside, FASTA sequences for each PLCC structure were obtained from the same database to query AlphaFold2 

Structure Prediction using AlphaFold 2

Running AlphaFold 2 Multimer on ColabFold: Using ColabFold, AlphaFold 2 multimer was executed to predict the structures of PLCC proteins. This involved querying the sequences for both the SH2 domain and the peptide sequence based on the provided FASTA sequences in the protein data bank. AlphaFold2 outputs five different protein structures ranked based on the DockQ index, with lower scores meaning more accurate structures. All further analysis was conducted using the rank one pdb file.

Sanity Check with PyMol
Visualizing Structures: The predicted structures were visualized in PyMol, and regions with large deviations were colored based on RMSD and side chains.

Data Analysis

Computing Root Mean Square Deviation (RMSD)
Loading Structures for Analysis: The structures were loaded into a Jupyter notebook and analyzed using the mdtraj package.
RMSD Between Predicted and Crystal Structures: The root mean square deviation (RMSD) was calculated between the predicted AlphaFold structure and the crystal structure and produces values of roughly 4Å.
RMSD per Residue: The RMSD per residue between the AlphaFold rank one pdb and the crystal structure's protein and peptide was computed to provide a granular understanding of the structural deviations. 
Analysis of RMSD Values

Comparison with Experimental Values: The computed RMSD per residue values are a factor of 10 smaller than generally accepted experimental values.

The analysis revealed that the folded regions of the proteins exhibited the lowest RMSD values, indicating a higher structural accuracy in these areas. Conversely, the flexible regions and the terminal ends of the peptide sequence showed higher RMSD values, aligning with expectations regarding structural variability in these regions. The findings align with existing literature on protein flexibility and structure prediction accuracy. 

Next Steps
The next phase of this research will involve performing k-nearest means clustering of the RMSD values per residue across different PLCC proteins. This step aims to determine patterns in structural prediction accuracy and identify common characteristics among similarly clustered proteins.
