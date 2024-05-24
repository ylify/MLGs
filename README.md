# Brief introduction  
  
# MLGs
**Mollusca Linkage groups (N=20)** constructed by the representative species from Conchifera and Aculifera, which enables researchers to investigate the chromosomal event in species with the chromosome-level genome.  
  
In this version, seven genomes were employed in constructing the protein database via the guideline in *Science Advances* (Simakov et al., 2022), including 1 snail (*Gibbula magus*), 1 bivalve (*Mizuhopecten yessonensis*), and 5 chitons (*Acanthochitona rubrolineata*, *Acanthochitona discrepans*, *Callochiton septemvalvis*, *Deshayesiella sirenkoi*, *Liolophura japonica*). Specifically, only proteins were kept in the database if they were present at all seven species and also the best hit from each other. It consists of **4,729** homologs (Mollusca_7sp.bed), with pseudo-locations (only for visualization, not the real gene order in ancestor) of them via the AGORA v3.1 (Muffato et al., 2023).  
  
# How to use
Generally, it is used to look into the chromosomal evolution in organisms. With the MLGs, it will help us to identify the ancestral stat and chromosomal events in Mollusca, including 1) the identification of chromosome duplication (or fission), insertion, and fusion and 2) the real sense of whole genome duplication.   
1) Similarity search: diamond blastp (or blastp in blast+) could be adopted to find the hits between them (MLGs as the query and proteins from genomes as databases). The protein was defined as a significant match against the mollusk ancestors if it was hit by at least 6 of 7 proteins from a linkage in MLGs (evalue < 0.001).  
2) Fisher’s exact test: The linkage groups between MLGs and the specific genome is checked by Fisher’s exact test using R package macrosyntR (Sami El & Richard, 2023) with a significant threshold of p-value below 0.001.  
3) Visualizaion: It needs your effort via python or R. Personally, I would recommend Oxford plot.


# Citation:  
If you adopt the database in research, please cite the below work. Thanks!  

# Reference:  
>Simakov, O., Bredeson, J., Berkoff, K., Marletaz, F., Mitros, T., Schultz, D. T., . . . Rokhsar, D. S. (2022). Deeply conserved synteny and the evolution of metazoan chromosomes. Science Advances, 8(5), eabi5884. doi:doi:10.1126/sciadv.abi5884  
>Muffato, M., Louis, A., Nguyen, N. T. T., Lucas, J., Berthelot, C., & Roest Crollius, H. (2023). Reconstruction of hundreds of reference ancestral genomes across the eukaryotic kingdom. Nature Ecology & Evolution, 7(3), 355-366. doi:10.1038/s41559-022-01956-z  
