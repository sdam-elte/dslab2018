# Signatures of mutational processes in human cancer

Cancer is caused by somatic mutations of the DNA in the tumor cells. In this project, you will use lists of somatic mutations detected in different samples originating from different tumor types and try to decompose the mutational spectra of each sample to the weighted combination of the operating mutational processes in the specific disease.

The general task is to perform the analysis pipeline described in [1] on a restricted dataset to identify "mutational signatures" in sample sets of different cancer types. As a final step, the clustering of these signatures across disease types can help with establishing a set of consensus mutational signatures.

---

## Tasks

### Understanding the goals of the project

To get an idea about the basic aims of the project, read [1] and [2]. Many more publications are available on the topic [3-6], but the main concepts are best described in the papers mentioned above. Make sure you understand what a mutational catalog means.

### Downloading the necessary data

1. Lists of somatic mutations for different cancer types, for many samples are included with the task description. These are:

    - LUAD (lung adenocarcinoma) [`LUAD.maf.gz`]
    - LUSC (lung squamous cell carcinoma) [`LUSC.maf.gz`]
    - KIRC (kidney renal clear cell carcinoma) [`KIRC.maf.gz`]
    - OV (ovarian cancer) [`OV.maf.gz`]
    - PRAD (prostate adenocarcinoma) [`PRAD.maf.gz`]


2. The human reference genome version hg19. Use [this](http://hgdownload.cse.ucsc.edu/goldenPath/hg19/chromosomes/) website and download the reference genome for each chromosome separately. (Download the files named "chr[chromosome_name].fa.gz".) These files are compressed [FASTA files](https://en.wikipedia.org/wiki/FASTA_format). Make sure you understand their structure.

### Determining sequence context for an arbitrary genomic position

1. Define the genomic position by the name of the chromosome and the position of the base on that chromosome (chr:pos). (Genomic positions are not absolute, the numbering starts from 1 for each chromosome.)
2. Search the above downloaded reference genome file of the appropriate chromosome and find the nucleobase at the given position. Also get the bases immediately before and after the given genomic position. 
3. To check your results for a few cases, you can use the [UCSC Genome Browser](https://genome-euro.ucsc.edu/cgi-bin/hgTracks?db=hg19&lastVirtModeType=default&lastVirtModeExtraState=&virtModeType=default&virtMode=0&nonVirtPosition=&position=chrY%3A6736165%2D6736167&hgsid=229442204_XaWTGjCNSa2TpUAtuiOWqlgS5kLf). (For example, sequence context for chrY:6736166 is CAT.)

### Creating a mutational catalog for the 5 lists of somatic mutations separately

1. Filter the tables so that only SNP variants are kept (insertions and deletions are ignored).
2. Get sequence context for the remaining mutations with the method designed in the previous task. (Check if the base you find there is the same as the base listed in the `Reference_Allele` field.)
3. For each sample in the set (indicated by the sample ID in field `Tumor_Sample_UUID`), collect the mutations and categorize them to 96 mutational categories based on the reference and the alternate (field `Tumor_Seq_Allele2`) allele and the sequence context.
4. Create a mutational catalog $C$ (a matrix), where $C_{ij}$ is the number of mutations found in sample $j$ in the mutational category $i$. (Samples are listed as columns, mutational categories as rows.)
5. Do this separately for the 5 different cancer types.

### Performing non-negative matrix factorization to extract signatures

1. Extract mutational signatures by using non-negative matrix factorization on the mutational catalogs separately. Choose the minimal set of signatures for each catalog that reconstructs the original matrix "fairly well". (Make sure to address this issue in a quantitative manner.)
2. Play around with different types of normalization and rescaling of the data. (For example, what happens if you normalize the mutational catalog so that the total number of mutations for a single sample sum to 1. What happens if the number of the mutations in a given mutational type sum to 1 across samples?) Do you get different results? Discuss!
3. Perform signature extraction for all 5 mutational catalogs.

### Condensing signatures

1. Once your signatures are extracted from all 5 mutational catalogs, try clustering them using different methods. Try to decrease the total number of signatures by combining "reasonably similar" ones. Make sure your criteria are clearly explained. Also, be very specific about how you actually "combine" similar signatures.
2. Show the most dominant consensus signatures and their contributions for each cancer type.

---

## References

[1] Alexandrov LB, et al. (2013) Signatures of mutational processes in human cancer. Nature 500(7463):415–21.

[2] Nik-Zainal S, et al. (2012) Mutational processes molding the genomes of 21 breast cancers. Cell 149(5):979–93.

[3] Alexandrov LB, Nik-Zainal S, Wedge DC, Campbell PJ, Stratton MR (2013) Deciphering signatures of mutational processes operative in human cancer. Cell Rep 3(1):246–59.

[4] Helleday T, Eshtad S, Nik-Zainal S (2014) Mechanisms underlying mutational signatures in human cancers. Nat Rev Genet 15(9):585–98.

[5] Alexandrov LB, Stratton MR (2014) Mutational signatures: the patterns of somatic mutations hidden in cancer genomes. Curr Opin Genet Dev 24(100):52–60.

[6] Alexandrov L, et al. (2018) The Repertoire of Mutational Signatures in Human Cancer. bioRxiv:322859.
