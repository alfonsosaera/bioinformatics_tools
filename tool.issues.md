# Tool placement review

All 316 entries in `README.md` were checked against the rules in `sections_guide.txt`. Nothing was modified. About 95% are consistent; the findings are grouped below by how firmly the rules point to a change.

## A. Clear conflicts with the rules

| Entry | Now in | Rule says | Suggestion |
|---|---|---|---|
| Automatic T-Cell Annotation (starCAT) | SC › Immune Repertoire | Immune Repertoire is for TCR/BCR analysis. Annotation goes to Cell Type Annotation. | Move, or cross-list to Cell Type Annotation. You chose to leave it earlier, and the guide now contradicts that. |
| ProjecTILs | SC › Immune Repertoire | It projects onto a reference atlas, which is annotation or reference mapping. | Cross-list to Cell Type Annotation and/or Batch Integration. |
| Stator | SC › Cell Type Annotation | De novo cell type/state discovery belongs in Dim. Reduction & Clustering. | Cross-list or move. |
| scIB-E | SC & Spatial › Benchmarking | It benchmarks single-cell integration only (no spatial). The rule puts a benchmark with its own topic, in the same section. | Move to SC › Batch Integration. |
| Stack, PerturbGen | SC › Perturbation Modeling only | Both describe themselves as foundation models. Foundation models go to Foundation Models, with a cross-list if the task is the main claim. | Cross-list to Single-cell Foundation Models. |
| CytoCommunity | Spatial › Domains & Tissue Architecture | Cellular neighborhoods belong in Neighborhood & Microenvironment. | Move or cross-list. |
| TISSUE, SpaIM | Spatial › SVGs & Gene Prediction only | Both need a scRNA-seq reference plus spatial data. Tools that need both go to Single-cell & Spatial Integration. | Cross-list to Spatial Cell Mapping & Reconstruction. |
| spaSim (in "SPIAT & spaSim") | Spatial › Neighborhood only | spaSim is a simulator. | Cross-list to Spatial › Simulation & Benchmarking. |
| spDDB | SC & Spatial › Benchmarking only | It benchmarks 21 deconvolution and 18 domain-detection methods, and domain detection is spatial-only. | Cross-list to Spatial › Simulation & Benchmarking. |

## B. Cross-list candidates (fit two subsections; decide which you want)

| Entry | Now in | Also fits |
|---|---|---|
| TAP-seq, MitoPerturb-Seq, sci-Plex-GxE | Experimental (sci-Plex-GxE is in Perturbation) | The other one of Experimental Technologies and Perturbation Modeling (TAP-seq and MitoPerturb-Seq are screening platforms; sci-Plex-GxE is a perturbation platform) |
| SEC-seq, Vivo-seq | Experimental | Single-cell Proteomics (secretion / phospho-signaling) |
| scEpi2-seq, scTAM-seq, ScISOr-ATAC | Experimental | Epigenomics (ScISOr-ATAC also Long-read) |
| VDJcraft | Immune Repertoire | Long-read & Isoform |
| Cellector, MitoPerturb-Seq | Preprocessing / Experimental | Genotyping (mtDNA and foreign-genotype detection) |
| scATAcat, SifiNet | Epigenomics / Dim. Reduction | Cell Type Annotation |
| DeepScence | SC › Cell Type Annotation | Spatial › Cell Type Annotation (it works on both) |
| CellChat | SC › Cell–Cell Communication | Spatial CCC (V2 uses spatial locations) |
| Numbat | SC › Genotyping | It also targets spatial data, and Spatial has no CNV subsection |
| SHARE-Topic | Multimodal | GRN or Epigenomics (gene–region links) |
| SLIDE, scTREND, TissueFormer | Multimodal / Deconvolution / FM | Phenotype & Clinical Outcome Association |
| Continual Learning (CL) & RR Mapping | Perturbation | Batch Integration |
| Context-dependent GRNs from Literature | LLMs | Gene Regulatory Network Inference |
| SPACEL | Spatial › Domains | Deconvolution; Multi-sample Spatial Integration (3D alignment) |
| SpaTRACE, SOAPy | Spatial CCC / Domains | Spatiotemporal Dynamics |
| TRINUS, CONCERT | Spatial CCC / SC Perturbation | Both do in silico perturbation, but Spatial has no perturbation subsection |
| Nicheformer | Spatial FM | Single-cell FM (it integrates both data types) |
| DGAT, scLinear | Single-cell Proteomics | Spatial (protein inferred from spatial data) |
| NeMO Analytics | SC › Visualization | Data Infrastructure (an atlas/resource portal) |
| SCIMAP | Spatial › Visualization | Neighborhood & Microenvironment (multiplex-imaging analysis) |

## C. Scope doubts (possibly not single-cell/spatial)

- ~~**TEA-GCN** (GRN): a plant co-expression pipeline that looks bulk-based, not single-cell.~~
- ~~**Clair3-RNA, ClairS-TO** (Genotyping): long-read variant callers that don't look single-cell.~~
- ~~**polars-bio** (Data Infrastructure): genomic-interval DataFrame library with no single-cell link.~~
- ~~**Pan-Cancer Epigenetic Atlas** (Epigenomics): a multi-omic atlas, not clearly single-cell. It may belong under resources.~~
- **SMAGLinker** (Experimental Technologies): a computational binning method using single-cell genomics and metagenomics. It isn't a wet-lab tool, and no subsection covers metagenomics.
- ~~**Organelle Immuno-Capture Spatial Proteomics** (Spatial › Experimental): mass-spec subcellular proteomics, not tissue spatial omics. You chose this placement, so it is only a doubt.~~
- ~~**GeneGPT, OncoGPT, NetMedGPT** (LLMs): general biomedical LLMs. The guide allows "biomedical LLMs", so these are only flagged.~~

## D. Smaller placement doubts

- **scLDM:** could be Simulation & Benchmarking (where it is) or Single-cell Foundation Models.
- **scSemiProfiler** (Deconvolution): it mainly generates single-cell data economically for cohorts, with bulk deconvolution as one mode. It might fit Simulation better.
- **CellScope:** it builds atlases with tree visualizations, so it could be Visualization instead of Dim. Reduction.
- **Cell Synergy, HESTIA, SpaHDmap:** all sit in Domains. They are H&E-integrated methods, and the guide has no "histology-integrated" subsection.
- **Thin subsections:** Spatial DE and Spatiotemporal Dynamics have 1 entry each, Histopathology Foundation Models has 1, and Single-cell Hi-C has 1.

## E. Other observations

- **Removed entry:** ggkegg is no longer in the file. It was removed in an earlier commit (`16b51d1`), so it is flagged in case that wasn't intended.
- **Guide gap:** the guide has no rule for tools that use both single-cell and spatial data as inputs when they are foundation models, and no rule for spatial perturbation tools.
