# ERBS Genome Annotation and Visualization

This repository contains R Markdown tutorial and lecture materials for working with estrogen receptor binding site (ERBS) peak data in R.

The tutorial shows how to import genomic peak coordinates, represent them as `GRanges`, annotate them with gene and transcript context, summarize the results, and visualize the ESRRA locus with `Gviz`.

## Main Workflow

The tutorial follows this flow:

1. Check required R and Bioconductor packages
2. Import ERBS peak data from the `ERBS` package
3. Convert the peak file into a `GRanges` object
4. Load hg19 genome sequence and gene annotation resources
5. Annotate peaks with nearest genes, TSS distance, promoter overlap, exon overlap, and genomic context
6. Build an annotated peak table
7. Summarize the full peak set
8. Visualize ERBS peaks around the ESRRA locus using `Gviz`

## Required R Packages

The tutorial uses

- `GenomicRanges`
- `GenomeInfoDb`
- `IRanges`
- `S4Vectors`
- `rtracklayer`
- `ERBS`
- `BSgenome.Hsapiens.UCSC.hg19`
- `TxDb.Hsapiens.UCSC.hg19.knownGene`
- `Homo.sapiens`
- `AnnotationDbi`
- `GenomicFeatures`
- `Biostrings`
- `Gviz`
- `ggplot2`

Install missing packages from inside R if needed

```r
install.packages(c("BiocManager", "ggplot2", "remotes"))

BiocManager::install(c(
  "GenomicRanges",
  "GenomeInfoDb",
  "IRanges",
  "S4Vectors",
  "rtracklayer",
  "BSgenome.Hsapiens.UCSC.hg19",
  "TxDb.Hsapiens.UCSC.hg19.knownGene",
  "Homo.sapiens",
  "AnnotationDbi",
  "GenomicFeatures",
  "Biostrings",
  "Gviz"
))

remotes::install_github("genomicsclass/ERBS")
```


## Notes

The workflow uses the `hg19` genome build throughout. Keeping the peak data, reference genome, and gene annotation database on the same genome build is important for correct overlap, distance, and visualization results.

The ERBS peaks used in the tutorial come from the same GM12878 ERBS dataset used in the official course example.
