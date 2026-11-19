# Cancer Research Data Portals Survey

A curated, living directory of major pan-cancer and specialized disease/foundation cancer research data portals—comparing **preliminary browser-based analysis capacity**, **data scale**, **molecular & clinical modalities**, **development stages**, and **operational tradeoffs** (as of November 2026).

> **Companion files:**
> - [cancer-data-portals.csv](cancer-data-portals.csv) — Machine-readable matrix of all 19 portals (major + specialized/foundation tier).
> - **citation:** [Zenodo](https://zenodo.org/records/24381576) (DOI 10.5281/zenodo.24381575).

---

## Key Findings

1. **7 of 9 major portals** support built-in preliminary analysis or interactive variant exploration without writing local code.
2. **Three architectural tiers** have emerged:
   - **No-code browser analytics:** [cBioPortal](https://www.cbioportal.org/), [NCI GDC](https://gdc.cancer.gov/), [Broad DepMap](https://depmap.org/), and [UCSC Xena](https://xena.ucsc.edu/).
   - **Hybrid (web visualization + cloud/external workflows):** [St. Jude Cloud](https://stjude.cloud/), [AACR Project GENIE](https://aacrprojectgenie.org/data/), and [COSMIC](https://cancer.sanger.ac.uk/cosmic).
   - **Discovery-first / cloud handoff:** [Kids First DRC](https://kidsfirstdrc.org/) and [ICGC ARGO](https://platform.icgc-argo.org/).
3. **A large specialized & foundation tier** complements the pan-cancer giants: [RRID / SciCrunch](https://rrid.site/data/source/nlx_144509-1/search?q=data%20repository&l=data%20repository&facet[]=Related%20Condition%3Acancer&facet[]=Related%20Condition%3Acardiovascular%20disease&sort=asc&column=Record%20Last%20Update&sort=asc&layout=table) indexes **34 cancer data repositories** (within [3,479 repositories](https://mira.mcmaster.ca/resources/data-repos-datasets/) in re3data), the [NCI Childhood Cancer Data Catalog (CCDC)](https://datacatalog.ccdi.cancer.gov/) lists **100+ participating pediatric/AYA resources**, and the [NCI Cancer Research Data Commons (CRDC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC11063685/) spans **7 specialized modality/domain nodes**.

---

## 1. Major Pan-Cancer & Pediatric Data Portals (9 Platforms)

| Portal & Host | Preliminary Analysis | Data Size & Scale | Core Data Types | Access Model |
| :--- | :--- | :--- | :--- | :--- |
| [cBioPortal](https://www.cbioportal.org/) (MSK & Consortium) | **Yes (No-Code Built-In):** OncoPrint, lollipop plots, KM survival, group comparisons | 552 studies · 414,693 samples | Somatic mutations, CNAs, structural variants, mRNA/miRNA, methylation, RPPA/MS, clinical timelines | Open web access; open-source code for local private instances |
| [NCI GDC](https://gdc.cancer.gov/) (National Cancer Institute) | **Yes (Cohort & Gene Tools):** Cohort Builder, Analysis Center (mutation freq, clustering, survival) | >2 PB · 50,571 cases · 93 projects · 27 programs | Harmonized WGS, WXS, RNA-Seq, miRNA, ATAC-Seq, methylation, CNV, RPPA, SVS slides, clinical | Open metadata & processed tiers; dbGaP for controlled BAM/FASTQ |
| [AACR Project GENIE](https://aacrprojectgenie.org/data/) (AACR & 19+ Centers) | **Yes (via cBioPortal):** Interactive OncoPrints, mutation frequency & cohort filtering | >289,000 samples · >242,000 patients (v20.0) | Clinical targeted NGS panels (SNVs, indels, CNAs, fusions), baseline clinical; deep BPC treatment data | Public after registration on [Synapse](https://synapse.org/genie) & `genie.cbioportal.org` |
| [DepMap Portal](https://depmap.org/) (Broad Institute) | **Yes (No-Code Explorers):** Data Explorer 2.0, Target Discovery, Celligner, Custom Analyses | 2,000+ cell lines · ~18,000 genes · 400+ drugs | CRISPR & RNAi gene dependency, PRISM/GDSC drug sensitivity, WES/WGS, RNA-seq, Olink proteomics | Open for non-profit research; commercial use requires license |
| [UCSC Xena](https://xena.ucsc.edu/) (UC Santa Cruz) | **Yes (Visual & Stats):** Visual Spreadsheet, KM survival, box/scatter plots, UMAP/spatial | >1,500 datasets · 50+ cancers · ≤1M cells | Derived SNVs, CNV, Toil TCGA+GTEx expression, methylation, scRNA/scATAC-seq, spatial omics | Open access (no login); private local Xena Hubs supported |
| [St. Jude Cloud](https://stjude.cloud/) (St. Jude Children's) | **Yes (Web + Cloud):** PeCan ProteinPaint, GenomePaint, cloud RNA-Seq/ChIP workflows | >1.25 PB · 12,000+ pts · +5,161 PeCan samples | Pediatric WGS, WXS, RNA-seq, ChIP-seq, CUT&RUN, methylation, survivorship (St. Jude LIFE/CCSS) | Open PeCan/Viz; Data Access Committee approval for raw cloud data |
| [COSMIC](https://cancer.sanger.ac.uk/cosmic) (Wellcome Sanger) | **Yes (Variant Browser):** Gene/tissue mutation browsers, COSMIC-3D, Signatures, Actionability | >70M mutations · >29,000 curated papers | Expert-curated somatic variants (SNVs, indels, fusions, CNAs), Cancer Gene Census, 3D protein impacts | Free web & academic downloads; paid license for commercial use |
| [Kids First DRC](https://kidsfirstdrc.org/) (NIH / CHOP) | **Limited (Cloud-Linked):** Portal cohort/variant browser; analysis runs via CAVATICA cloud | >1.44 PB · 147k+ samples · 1.25M+ files · 37 studies | Pediatric cancer & birth defect WGS, WXS, RNA-seq, family trios, germline/somatic VCFs, clinical | Open metadata; dbGaP approval for individual-level genomic data |
| [ICGC ARGO](https://platform.icgc-argo.org/) (ICGC Consortium) | **No (Discovery Only):** Federated cohort browser; downstream compute runs externally | 7,056 ARGO donors (63k committed) + legacy 25K | Harmonized WGS, WXS, RNA-seq, somatic/germline variants, standardized longitudinal clinical data | Open summary tiers; [ICGC DACO](https://daco.icgc-argo.org/) approval for controlled data |

### Pros & Cons Highlights (Major Portals)

- **cBioPortal:** *Pros:* Fastest zero-code hypothesis testing with [OncoKB annotations](https://d-nb.info/1355234018/34) and treatment timelines. *Cons:* Processed matrices only (no raw BAM/FASTQ); multi-study queries limited to mutations/CNAs.
- **NCI GDC:** *Pros:* [hg38-harmonized](https://gdc.cancer.gov/about-data/gdc-data-quality) TCGA/TARGET/CPTAC/CCDI data, BAM slicing, REST API. *Cons:* Browser downloads cap at [5 GB / 10,000 files](https://docs.gdc.cancer.gov/Data_Portal/Users_Guide/Repository/); no automatic cross-project batch correction.
- **AACR Project GENIE:** *Pros:* Largest public real-world clinico-genomic registry ([289,000+ samples](https://aacrprojectgenie.org/data/)). *Cons:* Targeted NGS panels miss non-panel genes and transcriptomics; sparse treatment history outside BPC sub-cohorts.
- **Broad DepMap:** *Pros:* Links [CRISPR/RNAi dependencies](https://casrai.org/guides/depmap) with PRISM drug sensitivity. *Cons:* 2D cell lines lack immune/microenvironment context; scores cannot be mixed across pipeline releases.
- **UCSC Xena:** *Pros:* [Toil-realigned TCGA+GTEx](https://www.biorxiv.org/content/10.1101/326470v1.full) plus [spatial/single-cell](https://aacrjournals.org/cancerres/article/85/8_Supplement_1/1077/754889) overlays; private local hubs. *Cons:* Basic built-in stats (often paired with [UCSCXenaShiny](https://academic.oup.com/bioinformatics/article/38/2/527/6330614)).
- **St. Jude Cloud:** *Pros:* Largest pediatric cancer & [survivorship](https://www.stjude.org/research/progress/2023/st-jude-cloud-survivorship-portal-offers-a-treasure-trove-of-data-for-discovery-in-childhood-cancers.html) ecosystem with cloud pipelines. *Cons:* Pediatric-focused; DNAnexus cloud runs incur compute fees.
- **COSMIC:** *Pros:* Gold-standard manual curation ([29,000+ papers](https://pmc.ncbi.nlm.nih.gov/articles/PMC10767972/)) and [COSMIC-3D](https://www.mutographs.org/news_item/a-cosmic-catalogue-of-cancer-data/). *Cons:* Variant-centric (no cohort survival/expression clustering); commercial license required for pharma/industry.
- **Kids First DRC:** *Pros:* Bridges childhood cancer & birth defects with trio WGS and [CRDC interoperability](https://aacrjournals.org/cancerres/article/83/7_Supplement/6576/721976/Abstract-6576-Gabriella-Miller-Kids-First-Data). *Cons:* dbGaP required for individual-level data; requires CAVATICA setup for analysis.
- **ICGC ARGO:** *Pros:* Rigorous [standardized clinical dictionary](https://pmc.ncbi.nlm.nih.gov/articles/PMC12635221/) across 13+ countries. *Cons:* Still scaling toward 100k donors; minimal built-in analysis tools.

---

## 2. Specialized & Foundation Portals (10 Notable Platforms)

| Portal & Sponsor | Focus & Scale | Preliminary Analysis Capacity | Development Stage |
| :--- | :--- | :--- | :--- |
| [MMRF Virtual Lab](https://themmrf.org/for-researchers/data-access-via-virtual-lab/) (MMRF) | Multiple myeloma: CoMMpass (1,143 longitudinal patients), Myeloma Immune Atlas, Horizon trials | **Yes (Built-in + Notebooks):** CoMMpass Explorer, survival/mutation plots, Shiny app, RStudio & Jupyter | **Production v2 (Modernized):** Replaced legacy Researcher Gateway in Sept 2025 on Gen3 ([MMRF Blog](https://themmrf.org/mmrf-blogs/mmrf-virtual-lab-data-platform/)) |
| [CTF NF Data Portal](https://nf.synapse.org/) (Children's Tumor Foundation & NTAP) | Neurofibromatosis: [233 studies, 27,704 files, 1,147 tools](https://www.re3data.org/repository/r3d100013571) | **Discovery + Linked Tools:** Synapse-hosted workflows for drug efficacy & molecular response | **Mature / Upgrading:** Launched Oct 2018; added OpenSearch & AI Portal Assistant in Oct 2026 ([Sage Bionetworks](https://sagebionetworks.org/community/nf-data-portal)) |
| [PCDC](https://academic.oup.com/jamiaopen/article/7/1/ooae004/7595632) (UChicago / St. Baldrick's) | Pediatric cancers: >46,000 patients across 13 cancer types ([St. Baldrick's](https://blog.stbaldricks.org/pediatric-cancer-data-commons-pcdc-what-it-is-and-why-it-is-matters/)) | **Yes (Built-in):** Custom Gen3 Kaplan–Meier survival & cohort explorer | **Mature / Expanding:** Live on Gen3 with open-source analytics microservices & GDC/Kids First links |
| [Beat AML / Vizome](https://vizome.readthedocs.io/) (OHSU / LLS) | Acute myeloid leukemia: [805 patients, 942 specimens](https://datacatalog.ccdi.cancer.gov/dataset/Vizome-BEATAML2.0) (WES, RNA-seq, *ex vivo* drug sensitivity) | **Yes (Built-in):** Interactive Vizome knowledge viewer + [cBioPortal](https://www.frontiersin.org/journals/hematology/articles/10.3389/frhem.2023.1302328/full) | **Mature (v2.0):** Harmonized cohort 2.0 published; stable discovery & analysis portal |
| [CBTN](https://cbtn.org/research/platforms/) & [PedcBioPortal](https://kidsfirstdrc.org/tools/) (CHOP / 32 Centers) | Pediatric brain tumors: >4,700 subjects, >1,000 multi-omic tumors (>5,000 underway) | **PedcBioPortal + CAVATICA:** Browser plotting in PedcBioPortal; pipelines in CAVATICA | **Mature / Scaling:** Core pediatric neuro-oncology infrastructure feeding Kids First & CCDI |
| [HTAN Data Portal](https://docs.humantumoratlas.org/data_access/portal/) (NCI Moonshot) | 3D/spatial & single-cell tumor atlases across multiple cancer types | **Discovery + Cloud Handoff:** Assay/file filtering; analysis via SB-CGC & CELLxGENE | **Active Scaling (Phase 2):** [First Phase 2 data release live](https://humantumoratlas.org/center/hta7); Synapse + CRDC backed |
| [GLASS Consortium](https://glass-consortium.org/datasets/) | Longitudinal primary & recurrent adult glioma ([Synapse](https://www.synapse.org/glass)) | **Discovery + cBioPortal:** Raw/processed data on Synapse; interactive plots on [cBioPortal](https://www.cbioportal.org/study/summary?id=difg_glass) | **Active Scaling:** Updated Sept 30, 2025; consortium-contributed heterogeneous cohorts |
| [BloodPAC Data Commons](https://pmc.ncbi.nlm.nih.gov/articles/PMC8140805/) | Liquid biopsy: 57 studies, >4,100 cases, 31,000+ files | **Workspace Hub:** Gen3 portal + working-group compute workspaces | **Mature / Federated:** Operational 4+ years on Gen3; interoperable with NCI CRDC |
| [Count Me In](https://joincountmein.org/) (Broad / Dana-Farber) | Direct-to-patient cohorts (e.g., [3,742 MBCproject, 491 ASCproject](https://pmc.ncbi.nlm.nih.gov/articles/PMC11650472/)) | **Via cBioPortal:** Publishes cohorts directly to cBioPortal & GDC | **Mature / Federated:** Ongoing patient-partnered enrollment with periodic public releases |
| [PanCAN SPARK](https://pmc.ncbi.nlm.nih.gov/articles/PMC10803046/) (PanCAN) | Pancreatic cancer: >600 Know Your Tumor patients + clinical trials & pathology ([Aignostics](https://www.prnewswire.com/news-releases/aignostics-partners-with-the-pancreatic-cancer-action-network-to-advance-pancreatic-cancer-research-302794401.html)) | **Cloud Pipelines:** Velsera/Seven Bridges ARIA cohort builder & reproducible task workflows | **Pilot / Early Expansion (v1):** DUA-gated (~48-hour review), iterating on pilot user feedback |

---

## Contributing

Know a disease-specific or regional cancer data portal that should be added? Open a Pull Request updating both `README.md` and `cancer-data-portals.csv` with a verified documentation URL, analysis capabilities, and current development stage.

---

## License

Data in this repository is licensed under CC-BY-4.0.
