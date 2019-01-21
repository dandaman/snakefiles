# Generate samples.json from metadata tables

[Daniel Lang](@daniel.lang)

Simple workflow to create a `samples.json` from variable metadata tables

## Usage
Simply edit [input.json](input.json) and for each metadata table provide the fulling infos:
* `path`: path that contains the R1 and R2 FASTQ files described in the metadata
* `sample`: column name that harbours the unique part of the FASTQ files names e.g. the run's accession number
* `R1` or `R2`: `format()` pattern to generate the filename for the R1 and R2 FASTQ file respectively. Must contain `{acc}`at the position `sample`should be filled in
* `delimiter`: column separator used in the metadata table e.g. `\t`
