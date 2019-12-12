# ncbi-data
Data extraction from NCBI based on Entrez Programming Utilities (https://www.ncbi.nlm.nih.gov/books/NBK179288/).

# NCBI Extract Accessions (ncbi-extract-acc.sh)
`ncbi-extract-acc.sh` extracts BioSample and BioProject accessions from given Sequence Read Archive (SRA) accessions.
* BioSample database stores metadata about each sample
* BioProject database stores information about research projects and links to data

*__Input:__* list of SRA accessions\
Note: DRR, ERR, and SRR prefixes means submitted to different databases:  SRR to NCBI, ERR to EBI and DRR to DDBJ

*__Output:__* tab-separated file with SRA accession, corresponding BioSample accession, and corresponding BioProject accession

Example: the optional `|& tee "warning.txt"` shows missing accessions in stderr and stores them in "warning.txt". 
``` bash
input="SRA-accessions.txt"
output="extracted-acc.tsv"
bash ncbi-extract-acc.sh -i "$input" -o "$output" |& tee "warning.txt"
```
## What to do in case of warnings:
Rerunning on failed accessions can work if the connection timed out while running.
If rerunning multiple times does not work, search manually on NCBI.
