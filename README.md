# Brief introduction  
  
# MLGs
**Mollusca Linkage groups (N=20)** constructed by the representative species from Conchifera and Aculifera, which enables researchers to investigate the chromosomal event in species with the chromosome-level genome.  
  
In this version, seven genomes were employed in constructing the protein database via the guideline in *Science Advances* (Simakov et al., 2022), including 1 snail (*Gibbula magus*), 1 bivalve (*Mizuhopecten yessonensis*), and 5 chitons (*Acanthochitona rubrolineata*, *Acanthochitona discrepans*, *Callochiton septemvalvis*, *Deshayesiella sirenkoi*, *Liolophura japonica*). Specifically, only proteins were kept in the database if they were present at all seven species and also the best hit from each other. It consists of **4,729** homologs (Mollusca_7sp.bed), with pseudo-locations (only for visualization, not the real gene order in ancestor) of them via the AGORA v3.1 (Muffato et al., 2023).  

**Guideline**: The linkage groups between every two genomes were checked by Fisher’s exact test using R package macrosyntR (Sami El & Richard, 2023) with a significant threshold of p-value below 0.001, but it might define the group as an insignificant item falsely if the number of linkages in the group was small. Therefore, the manual check of linkage groups between two genomes is needed using pairwise dot plots in JCVI version 1.2.7 (Tang et al., 2008), especially for organisms with genome duplication (e.g., *Acthatina fulica* and *Arion vulgaris*) or the recent insertion event (*Pomacea canaliculata*) or the two organisms with far relationships (e.g., Mollusca and Porifera). Coupling with the chromosomal location of proteins from .gff3 file, any potential linkage groups at the chromosome level would be constructed using ‘groups_six_species.py’ (a specified script). Accordingly, the ancient linkage groups (ALGs) were extracted based on the significant linkage groups on every two genomes. For example, similar to the definition of MBH, there were three chromosomal associations among three organisms: 1) chromosome 1 in organism A and chromosome 2 in organism B, 2) chromosome 1 in organism A and chromosome 3 in organism C, 3) chromosome 2 in organism B and chromosome 3 in organism C; then, it should be a linkage group from organism A-B-C as chromosome 1-2-3.
  
# How to use
Generally, it is used to look into the chromosomal evolution in organisms. With the MLGs, it will help us to identify the ancestral stat and chromosomal events in Mollusca, including 1) the identification of chromosome duplication (or fission), insertion, and fusion and 2) the real sense of whole genome duplication.   
1) **Similarity search**: diamond blastp (or blastp in blast+) could be adopted to find the hits between them (MLGs as the query and proteins from genomes as databases). The protein was defined as a significant match against the mollusk ancestors if it was hit by at least 6 of 7 proteins from a linkage in MLGs (evalue < 0.001).  
2) **Fisher’s exact test**: The linkage groups between MLGs and the specific genome are checked by Fisher’s exact test using R package macrosyntR (Sami El & Richard, 2023) with a significant threshold of p-value below 0.001.  
3) **Visualizaion**: It needs your effort via python or R. Personally, I would recommend Oxford plot (https://bitbucket.org/viemet/public/src/master/CLG/).


# Citation:  
If you adopt the database in research, please cite the below work. Thanks!  

# Reference:  
1) Muffato, M., Louis, A., Nguyen, N. T. T., Lucas, J., Berthelot, C., & Roest Crollius, H. (2023). Reconstruction of hundreds of reference ancestral genomes across the eukaryotic kingdom. Nature Ecology & Evolution, 7(3), 355-366. doi:10.1038/s41559-022-01956-z
2) Sami El, H., & Richard, R. C. (2023). macrosyntR : Drawing automatically ordered Oxford Grids from standard genomic files in R. bioRxiv, 2023.2001.2026.525673. doi:10.1101/2023.01.26.525673
3) Simakov, O., Bredeson, J., Berkoff, K., Marletaz, F., Mitros, T., Schultz, D. T., . . . Rokhsar, D. S. (2022). Deeply conserved synteny and the evolution of metazoan chromosomes. Science Advances, 8(5), eabi5884. doi:doi:10.1126/sciadv.abi5884
4) Tang, H., Bowers, J. E., Wang, X., Ming, R., Alam, M., & Paterson, A. H. (2008). Synteny and Collinearity in Plant Genomes. Science, 320(5875), 486-488. doi:doi:10.1126/science.1153917
