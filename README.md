# PythonParserAssignment

For better or worse, new file formats are developed frequently in computational biology, often every time a new method or software is released. Thus, as budding computational biologists, you will often be tasked with converting files from one format to another in order to try out a shiny new method on your data. If you're lucky, someone will have written and posted a script to do exactly what you want. Often, however, it is quicker/safer/easier to write your own script. For this assignment, you are given the "real life" task of converting imputed genotype data into a format appropriate for a new gene-based association method called PrediXcan. Imputation in genetics refers to the statistical inference of unobserved genotypes. Because SNPs are linked throughout the genome, we can genotype a subset of known SNPs (~1 million) and then use reference populations like 1000 Genomes to estimate the unmeasured genotypes (~10 million). Write a script in Python that does the following:

**Input:** `*vcf.gz` file of imputed genotypes. VCF (variant call format) is a text file format (most likely stored in a compressed manner). It contains meta-information lines, a header line, and then data lines each containing information about a position in the genome.

**Output:** Genotype dosage file for PrediXcan (`chr*.dosage.txt.gz`) and a list of samples in that file (`samples.txt`).

For <a href="https://github.com/hakyimlab/PrediXcan/tree/master/Software">PrediXcan</a>, genotype dosage files are expected to be compressed files in the format below. Note: there is no header row in the dosage file, the comments just describe what is in the columns, the dosage file begins with the first SNP entry (the line starting with `chr1` below).

```
# chr1.dosage.txt.gz sample content, made up of the following columns:
# chr rsid position Allele1 tAllele2 tAlleleFreq tdos_sample1 tdos_sample2 ... tdos_samplen
#
chr1 rs10399749 55299 C T 0.16430 0 1 ... 0
chr1 rs3091273 55302 C T 0.16132 0 1 ... 0
...
```

- Dosage for each person refers to the number of alleles for the 2nd allele listed (between 0 and 2).
- It is expected that there will be one file per chromosome.
- Make sure your SNPs have reference numbers (`rsid`), note the `*.vcf.gz` file labels SNPs by their positions.
- We only want to include imputed SNPs that we are confident were estimated correctly. Use an "Estimated Imputation Accuracy" threshold of 0.8 and above.

```
# samples.txt is a list of the dosage column headers from the *vcf.gz file.
sample1
sample2
.
.
.
samplen
```


An example input file from chromosome 22 and other useful data can be found at <https://github.com/hwheeler01/PythonParserAssignment>.

Upload your commented Python script (`*.py` file) to Sakai by 11:59PM on the due date. Your code must be commented in your own words and turned in independently. Code should be commented sufficiently so someone learning Python can understand it and get the script to run properly. (1 pt for comments, 4 pts for functional code). Parsing the example input file should not take more than an hour. If it does, you will not get full credit. If you had a partner for a problem, note his/her name in your code comments. Cheating includes submitting as your own work something that has been written by an outside person (or web site). If you are working with a partner, an “outside person” refers to someone other than your partner.
