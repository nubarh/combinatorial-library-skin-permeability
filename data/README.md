# Data Sources

Raw data files are not included due to file size constraints.

## ChEMBL Building Blocks
Download from: https://www.ebi.ac.uk/chembl/
Filters: Small molecule, Ro5 violations = 0, Version 36
Expected: ~1,348,305 compounds in CSV format

## Skin Permeability Reference Datasets
DOI: https://doi.org/10.57745/ZUU1DH
Files: huskin_depot.csv, skinpix_depot.csv, inrs_depot.csv

## Key Generated Files
- chembl_standardized_dedup.smi — 1,094,666 unique BBs
- chembl_skin_focused.smi — 470 focused BBs
- library_final.sdf — 1,047 enumerated compounds
- all_predictions.csv — logKp predictions
