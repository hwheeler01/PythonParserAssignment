# PythonParserAssignment

For better or worse, new file formats are developed frequently in computational biology, often every time a new method or software is released (see <https://www.biostars.org/p/55351/>). Thus, as budding computational biologists, you will often be tasked with converting files from one format to another in order to try out a shiny new method on your data. If you're lucky, someone will have written and posted a script to do exactly what you want. Often, however, it is quicker/safer/easier to write your own script. For this assignment, you are given the "real life" task of coverting imputed genotype data into a format appropriate for a new gene-based association method called PrediXcan. Write a script in Python that does the following:

**Input:** `*vcf.gz` file of imputed genotypes. VCF (variant call format) is a text file format (most likely stored in a compressed manner). It contains meta-information lines, a header line, and then data lines each containing information about a position in the genome.

**Output:** Genotype dosage file for PrediXcan.

For <a href="https://github.com/hakyimlab/PrediXcan/tree/master/Software">PrediXcan</a>, genotype dosage files are expected to be compressed files in the format below. Note: there is no header row in the dosage file, the comments just describe what is in the columns, the dosage file begins with the first SNP entry (the line starting with chr1 below).

```
# chr1.dosage.txt.gz sample content, made up of the following columns:
# chr rsid position Allele1 tAllele2 tAlleleFrequency tdosage1 ... tdosage_n
#
...
chr1 rs10399749 55299 C T 0.164302600472813 0 0 1 ... 0
...
```

- dosage for each person refers to the number of alleles for the 2nd allele listed (between 0 and 2).
- it is expected that there will be one file per chromosome.

An example input file and other useful data can be found at <https://github.com/hwheeler01/PythonParserAssignment>

Upload your commented Python script (`*.py` file) to Sakai by 11:59PM on the due date. Your code must be commented in your own words and turned in independently. Code should be commented sufficiently so someone learning Python can understand it and get the script to run properly. (1 pt for comments, 4 pts for functional code). If you had a partner for a problem, note his/her name in your code comments. Cheating includes submitting as your own work something that has been written by an outside person (or web site). If you are working with a partner, an “outside person” refers to someone other than your partner.
