#ChIP-Seq-Pipeline
A pipeline for processing ChIP-Seq-Data

Requirements:
	Snakemake (http://snakemake.readthedocs.io/en/stable/getting_started/installation.html)
	FastQC (http://www.bioinformatics.babraham.ac.uk/projects/fastqc/)
	FASTX_Toolkit (http://hannonlab.cshl.edu/fastx_toolkit/download.html)
	STAR (https://github.com/alexdobin/STAR)
	Homer (http://homer.ucsd.edu/homer/download.html)

create target file targets.csv in same directory as Snakefile:
	Column 1: SampleID 
	Column 2: Treatment 
	Column 3: Replicate 
	Column 4: fastqRead1 
	Column 5: fastqRead2 ("-" if single end")
	Column 6: ControlID 
	Column 7: fastqControl1 
	Column 8: fastqControl2 ("-" if single end")
	
	e.g.:
	SampleID,Treatment,Replicate,fastqRead1,fastqRead2,ControlID,fastqControl1,fastqControl2
	DM-n1,DM,1,p1_DM_H3K9_boeckel_R1.fastq,-,p1_DM_input,p1_DM_input_boeckel_R1.fastq,-
	DM-n2,DM,2,p2_DMT_H3K9me3_boeckel_R1.fastq,-,p2_DMT_input,p2_DMT_Input_boeckel_R1.fastq,-
	DM-n3,DM,3,p3_DMT_H3K9me3_boeckel_R1.fastq,-,p3_DMT_input,p3_DMT_Input_boeckel_R1.fastq,-
	VM-n1,VM,1,p1_VM_H3K9_boeckel_R1.fastq,-,p1_VM_input,p1_VM_input_boeckel_R1.fastq,-
	VM-n2,VM,2,p2_VM_H3K9me3_boeckel_R1.fastq,-,p2_VM_input,p2_VM_Input_R1_boeckel_R1.fastq,-
	VM-n3,VM,3,p3_VM_H3K9me3_boeckel_R1.fastq,-,p3_VM_input,p3_VM_Input_boeckel_R1.fastq,-

run Snakefile:
	open terminal, go to Snakefile directory, start pipeline:
	snakemake --config genome <path/to/genome> peakType <histone|factor|etc>


