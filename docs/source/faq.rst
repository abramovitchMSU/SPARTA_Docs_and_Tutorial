.. _faq:

Frequently Asked Questions
==========================

**1. Does SPARTA support paired-end reads?**

Not yet. Currently, SPARTA only supports single-end reads as we have found it is the most common/inexpensive approach for differential   gene expression analysis. Paired-end read support will be incorporated in future releases of SPARTA. If you have paired-end reads and would like to use SPARTA, as a workaround, you can run just the forward reads.

**2. What if I only have a GFF file and not a GTF file for my organism?**

A GTF file is a more stringent version of a GFF file. Thus, your GFF file *may* work with HTSeq for counting transcript abundance. However, GFF file formating is more relaxed and thus, it may not work. As a potential workaround, you can open the GFF file in a plain text editor like TextEdit (Mac) or Notepad (Windows). Look at each line and see if the beginning of each line in the GFF file begins with the same phrase. In the example below the GTF line begins with *Chromosome* and the reference genome FASTA file begins with the same phrase *Chromosome*. Next, examine each line for a phrase that relates specifying a region for a gene. In the example below, HTSeq by default looks for the phrase **exon**. If your file **does not** have **exon** as the phrase, you can specify to SPARTA/HTSeq which phrase to look for through the option ``--type=your_gene_region_name`` where ``your_gene_region_name`` is the phrase specific to your file.

..note: The preferred location for downloading a reference genome file and GTF file is through Ensembl (http://bacteria.ensembl.org/info/website/ftp/index.html). This list is fairly comprehensive though not exhaustive (especially if there is no reference and you've had to assemble your own/annotate it).

GTF example:

*Chromosome*	protein_coding	**exon**	1	1524	.	+	.	 gene_id "MT0001"; transcript_id "AAK44224"; exon_number "1"; gene_name "dnaA"; transcript_name "dnaA/AAK44224"; seqedit "false";
Chromosome	protein_coding	CDS	1	1521	.	+	0	 gene_id "MT0001"; transcript_id "AAK44224"; exon_number "1"; gene_name "dnaA"; transcript_name "dnaA/AAK44224"; protein_id "AAK44224";
Chromosome	protein_coding	stop_codon	1522	1524	.	+	0	 gene_id "MT0001"; transcript_id "AAK44224"; exon_number "1"; gene_name "dnaA"; transcript_name "dnaA/AAK44224";

Reference genome example (FASTA):

*>Chromosome* dna:chromosome chromosome:GCA_000008585.1:Chromosome:1:4403837:1
TTGACCGATGACCCCGGTTCAGGCTTCACCACAGTGTGGAACGCGGTCGTCTCCGAACTT
AACGGCGACCCTAAGGTTGACGACGGACCCAGCAGTGATGCTAATCTCAGCGCTCCGCTG
ACCCCTCAGCAAAGGGCTTGGCTCAATCTCGTCCAGCCATTGACCATCGTCGAGGGGTTT
GCTCTGTTATCCGTGCCGAGCAGCTTTGTCCAAAACGAAATCGAGCGCCATCTGCGGGCC
CCGATTACCGACGCTCTCAGCCGCCGACTCGGACATCAGATCCAACTCGGGGTCCGCATC...

**3. I keep getting an error at the differential gene expression stage stating ``Error: unexpected symbol in "name_of_your_file" Execution halted``**

This error will occur if you have file names that begin with a number instead of a letter. R (the language used to do the DE analysis) doesn't like having variable names that begin with a number instead of a letter. Thus, the remedy is to ensure all of your sample files begin with a letter instead of a number.

**4. My sample files are split between multiple .fastq/.fq files. How can I put them into a single file?**

If you have sequenced many samples across several lanes of an Illumina flowcell (as an example), you can concatenate all of them into one file per sample using the following commands (though you will need to alter the file names to fit your needs).

1. Make a copy of your files in a different folder so that if something goes wrong, you still have the raw data.

2. Open the terminal and navigate to the folder containing your copied sample files. As an example, if they are in a folder on the Desktop and you're on a Mac/Linux machine, you can type ``cd ~/Desktop/your_folder_with_copied_sample_files``. This is changing directories/folders to the one containing your sample files on the Desktop.

3. To combine the files, ensure they are unzipped or decompressed to .fastq or .fq files (e.g. NOT .fastq.gz or .fq.gz or .fastq.zip or .fq.zip, etc).

4. Performing the concatenation can be accomplished as follows with an example for Mac/Linux machines.

``cat samplefile1.fastq samplefile2.fastq samplefileN.fastq >> new_combined_sample_file.fastq``
