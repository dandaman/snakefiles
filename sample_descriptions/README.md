# Generate samples.json from metadata tables

[Daniel Lang](@daniel.lang)

Simple workflow to create a `samples.json` from variable metadata tables

## Usage
Simply edit [input.json](input.json) and for each metadata table provide the fulling infos:
* `path`: path that contains the R1 and R2 FASTQ files described in the metadata
* `run`: column name that harbours the unique part of the FASTQ files names e.g. the run's accession number --> replicates
* `R1` or `R2`: `format()` pattern to generate the filename for the R1 and R2 FASTQ file respectively. Must contain `{acc}`at the position `sample`should be filled in
* `delimiter`: column separator used in the metadata table e.g. `\t`
* `sample`: column name that harbours info on biological samples that were treated the same way --> summarized as BioSample in NCBI --> `sample accession` (supports: `fixed_string::`)
* `experiment`: column name that harbours info summarizing the experimental setup that were treated the same way e.g. `experiment_accession` (supports: `fixed_string::`)
* `study`: column name that harbous the unique study name  (supports: `fixed_string::`)
### Fixed strings
With the pragma `fixed_string::` you can hard-code certain fields already in [input.json](input.json) to ensure they are used for all rows belonging to one metdata source. E.g. `"study":"fixed_string::Expression profiling of light stress"` will lead to a column `study`with the value `Expression profiling of light stress`.
