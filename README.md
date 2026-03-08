## Mitag4taxa: A tool for getting 16S rRNA (v4 zone) and 18S rRNA (v9 zone) seqence for analysising from metagenome and metatranscriptome.

## Dependencies
Python 3.10

Packages  | Version |
--------- | --------|
perl  | 5.32.1.1 |
seqkit  | 2.9.0 |
hmmer  | 3.4 |
biopython  | 1.84 |
pandas  | 2.2.3 |

## Installation
conda install heyinghui0722::mitag4taxa

## run
mitag4taxa -i ./ -t 16S/18S -th 10

The Mitag4taxa software is a tool designed for the extraction and analysis of 16S or 18S rDNA sequences from Illumina sequencing data. 

The command provided, mitag4taxa -i ./testdata -t 16S/18S -th 10, outlines the basic usage of the software with the following parameters:

    -i, --input_folderpath: This option specifies the parent directory that contains the folder with Illumina sequencing sequences. Within this directory, there should be a folder named illu that holds the sequences intended for 16S or 18S rDNA analysis. For example, This command tells the mitag_analysis software to look for the Illumina sequencing sequences in the illu folder within the testdata directory, and to perform the analysis on the testdata.fastq file for 16S or 18S rDNA sequences with 10 threads.

    -t, --type: This parameter is used to define the type of rDNA to be analyzed, which can be either 16S or 18S.

    -th, --thread: This option allows the user to set the number of threads to be used for the analysis, which can affect the processing speed. In the example command, the value is set to 10.

After processing, it will create an output folder within ./testdata to store the results of the analysis. 

## Usage Guide （example）
1. Prepare Input Folder Structure
Crucial: Before running the software, you must organize your input data exactly as follows:

（1）Create a parent directory (e.g., ./testdata/).

（2）Create a subfolder named illu/ inside the parent directory.

（3）Place your raw Illumina sequencing files (.fastq or .fq) into the illu/ folder.


**Target Structure:**
```text
./testdata/
└── illu/
    └── your_raw_data.fastq


2. Run the Analysis
Execute the following command in your terminal:

For 16S rRNA analysis
mitag4taxa -i ./testdata/ -t 16S -th 10

For 18S rRNA analysis
mitag4taxa -i ./testdata/ -t 18S -th 10

3. After processing, a series of folders will be automatically generated within your input parent directory to organize the results:

./testdata/

    └── illu/             # Original input data

    └── seqkit/           # FASTA files converted from FASTQ

    └── rRNA_prediction/  # Full rRNA sequences predicted by HMMER

    └── 16S/ (or 18S/)    # Extracted 16S or 18S rRNA sequences

    └── v4/ (or v9/)      # Fasta sequences of the specific variable region (V4/V9)

    └── v4seq/ (or v9seq/)# Fastq sequences of the specific variable region (V4/V9)


Development environment: Linux  
Development tool: Pycharm and VScode

## Contact

If you have any questions, please feel free to contact: heyinghu23@mails.tsinghua.edu.cn






