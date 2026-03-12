# Class 6: R Functions
Daniel Kim

> Q. Write a first function generate_dna() that returns a user specified
> length DNA sequence

``` r
generate_dna <- function(length) {
  nuc <- c("A", "T", "G", "C")
  sample(nuc, size = length, replace = TRUE)
}
```

``` r
generate_dna(5)
```

    [1] "C" "A" "T" "G" "A"

> Q. Modify and improve our generate_dna() function to return it’s
> generated sequence in a more standard format like “AGTAGTA” rather
> than te vector “A”, “C”, “G”, “A”.

``` r
generate_dna <- function(length, fasta) {
  nuc <- c("A", "T", "G", "C")
  if (fasta) {
    sequence <- sample(nuc, size = length, replace = TRUE)
    paste(sequence, collapse = "")
  } else {
    sample(nuc, size = length, replace = TRUE)
  }
}
```

``` r
generate_dna(5, TRUE)
```

    [1] "GTCTA"

> Q. Write a function called generate_protein(), that generates a user
> specified length protein sequence. Use that function to generate
> random protein sequences between length 6 and 12.

``` r
generate_protein <- function(length, space) {
  aa <- c("A", "R", "N", "D", "C", "E", "Q", "G", "H", "I",
        "L", "K", "M", "F", "P", "S", "T", "W", "Y", "V")
  
  sequence <- sample(aa, size = length, replace = TRUE)
  
  if (space) {
    paste(sequence, collapse = "")
  } else {
    sequence
  }
}
```

> Q. Use that function to generate random protein sequences between
> length 6 and 12.

``` r
for (i in 6:12) {
  print(generate_protein(i, TRUE))
}
```

    [1] "NMRDYC"
    [1] "WIACGWV"
    [1] "FQNVFIQN"
    [1] "RNIHICSDC"
    [1] "MWWRRFHGWA"
    [1] "KGPWVHDNDCW"
    [1] "SGMASSPPRSCM"
