# MutationalPatterns sample data repository

This repository contains sample data files that can be used with
[MutationalPatterns](https://github.com/CuppenResearch/MutationalPatterns).

The following function can be used to download the files in this repository to
a single directory on your computer:

```{r}
download_example_data <- function(data_dir, samples) {
  dir.create(data_dir, recursive = TRUE, mode = "0755")
  for (i in 1:length(samples)) {
    download.file (paste("https://raw.githubusercontent.com/CuppenResearch/",
                         "MutationalPatterns-data/master/", samples[i], ".vcf",
                         sep=""), paste(data_dir, "/", samples[i], ".vcf", sep=""))
  }
}
```

## Usage

You can invoke this function as follows:

```{r}
sample_names = c("colon1", "colon2", "colon3",
                 "intestine1", "intestine2", "intestine3",
				 "liver1", "liver2", "liver3")

download_example_data("example_data", sample_names)
```

## License

The data in this repository is considered part of the MutationalPatterns
software, and is therefore licensed under the MIT license.
