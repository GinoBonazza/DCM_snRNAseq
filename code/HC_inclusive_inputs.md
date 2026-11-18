# HC-inclusive analyses

Run the R Markdown files in the order listed in `analysis/HC_inclusive_reports.Rmd`, from the project root. The final step writes `output/Datasets/Dataset_EV1.xlsx` through `Dataset_EV11.xlsx`. Each report records its R session information.

The analysis uses R 4.5.2, Seurat 4.4.0 and the project package environment. Paths are resolved with `here`. Raw and large processed data are not stored in Git. Place the supplied count matrices, clinical spreadsheets, Olink and mass-spectrometry inputs under `data/`, retaining their relative paths.

`data/processed/QC` contains the initial count, normalization, integration and annotation checkpoints. `data/processed/SoupX` contains the donor count inputs and empirical empty-droplet profiles. `RNA_quality_control.qs2` is the 191,570-nucleus SoupX-corrected RNA object; `RV_cell_states_RNA.qs2` is the final 190,794-nucleus, 29-donor object. The six lineage directories contain baseline, annotated and activity checkpoints. The scripts show the computations used to produce those checkpoints and validate reused values where applicable.

Small frozen inputs are versioned here: curation decisions, marker tables, the exact heatmap cell order, gene memberships, gene-ID mappings, enrichment objects and activity networks. RNA matrices, raw assay files, the NicheNet ligand–target matrix and large fitted-object checkpoints must be supplied separately. `code/HC_inclusive_frozen_inputs.csv` lists the versioned frozen inputs and checksums.

The proteomics analysis includes PK79. Reactome analyses and the PK79-excluded sensitivity analysis are omitted. Existing DCM-only reports and the original homepage are retained unchanged.

All reports use data/Donor_ages.csv: one nearest-whole-year age per donor, with CZD7 explicitly set to 38. EV1 contains one Age_years column. Raw source metadata are preserved; the visible set_donor_age function applies the common age before analysis. Age-adjusted models and their downstream results are refitted. Age-independent expression, clustering, marker, network and activity checkpoints retain their existing validation gates.

HC/DCM Gene Ontology enrichment is recomputed from the corrected ranks. Pre-correction `data/processed/DCM_control_GSEA/` objects are not consumed or included in this delivery. Existing repository copies remain protected.
