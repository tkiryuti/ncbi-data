# ncbi-data

# Data extraction from NCBI.
Based on Entrez Programming Utilities (https://www.ncbi.nlm.nih.gov/books/NBK179288/).

``` bash
input="ACC-LIST.txt"
output="sra-sample-proj.tsv"
bash ncbi-extract-acc.sh -i "$input" -o "$output" |& tee "warning.txt"
```
