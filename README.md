# **Concentration and Diversity in Collaboration Networks in Electrical Engineering: Evidence from Brazilian Researchers**

This repository contains the datasets, notebooks, and figures associated with the paper "Concentration and Diversity in Collaboration Networks in Electrical Engineering: Evidence from Brazilian Researchers" presented at the 2026 IEEE Latin America Transactions. The study analyzes the co-authorship network of Brazilian Electrical Engineering researchers who hold CNPq productivity grants (levels 1A, 1B, 1C, 1D, and 2). Using network science metrics such as PageRank, the work identifies the most influential researchers within and across grant levels, examines intra-group and inter-group collaboration patterns, and investigates geographic and gender distributions as well as research topic trends.

---

**Manuscript ID:** IEEE LATAM Submission ID: `10313`

### **Authors**

- [Fernando A. do Carmo](https://orcid.org/0000-0003-4594-5924) - (UEMA)
- [Gustavo S. Silva](https://orcid.org/0009-0001-1559-3465)  - (UEMA)
- [Raimundo C. S. Freire](https://orcid.org/0000-0002-5395-7143) - (UFCG)
- [Antonio F. L. Jacob Jr](https://orcid.org/0000-0002-9415-7265) - (UEMA)
- [Fábio M. F. Lobato](https://orcid.org/0000-0002-6282-0368) - (UFOPA/UEMA)

---

## Repository Structure

```
├── data/
│   ├── edges_dataset_anon.csv
│   ├── edges_intra_anon.csv
│   ├── nodes_dataset_anon.csv
│   └── nodes_intra_anon.csv
├── imgs/
│   └── table2-full.png
├── ieee_latam_ee_gender_geographic.ipynb
├── ieee_latam_ee_topics.ipynb
├── ieee_latam_network_analysis.ipynb
└── README.md
```

---
## File Descriptions

### Data Files (`data/`)

| File | Description |
|------|-------------|
| `nodes_dataset_anon.csv` | Anonymized node list for the full co-authorship network. Each row represents a researcher with a numeric `author_id` and their CNPq `grant_level` (1A, 1B, 1C, 1D, or 2). |
| `edges_dataset_anon.csv` | Anonymized edge list for the full co-authorship network. Each row represents a co-authorship link between two researchers (`source`, `target`) with the corresponding `grant_level`. |
| `nodes_intra_anon.csv` | Anonymized node list restricted to intra-group collaborations (co-authorships where both researchers share the same grant level). |
| `edges_intra_anon.csv` | Anonymized edge list restricted to intra-group collaborations. |

### Notebooks

| Notebook | Related Figures/Tables | Description |
|----------|----------------------|-------------|
| `ieee_latam_network_analysis.ipynb` | Figs. 2, 6, Tables 2, 4 | Builds the co-authorship network graph, computes PageRank centrality per grant level, identifies the top-5 most influential researchers per group, and analyzes intra-group vs. inter-group collaboration patterns. |
| `ieee_latam_ee_gender_geographic.ipynb` | Figs. 7, 8 | Analyzes the geographic distribution of researchers across Brazilian states and institutions, and examines gender representation across grant levels. |
| `ieee_latam_ee_topics.ipynb` | Figs. 1, 3, 4, Tables 1 | Performs research topic analysis based on declared areas of expertise, identifying the most frequent topics per grant level and across the full dataset. |

### Images (`imgs/`)

| File | Description |
|------|-------------|
| `table2-full.png` | Full version of Table 2 from the manuscript, showing the most influential researchers by CNPq grant level with PageRank scores, research areas, institutions, and PhD year. |

## Requirements

### Common dependencies (all notebooks)

- Python 3.8 or later
- `pandas`, `numpy`, `matplotlib`

### Per-notebook dependencies

| Notebook | Additional packages | Notes |
|----------|-------------------|-------|
| `ieee_latam_network_analysis.ipynb` | `networkx`, `python-louvain`, `scikit-learn` | — |
| `ieee_latam_ee_gender_geographic.ipynb` | `geobr`, `seaborn`, `requests`, `tqdm` | — |
| `ieee_latam_ee_topics.ipynb` | `sentence-transformers`, `cuml`, `bertopic`, `datamapplot`, `llama-cpp-python` | ⚠️ **Requires a CUDA-capable GPU** (tested on Google Colab T4). |

---

## Usage

### Option 1: Google Colab (recommended)

All notebooks were developed and tested on [Google Colab](https://colab.research.google.com/). Required `pip install` commands are included in the notebook cells, so no manual setup is needed.

> **Note:** The topics notebook (`ieee_latam_ee_topics.ipynb`) requires a GPU runtime.  
> In Colab, go to **Runtime → Change runtime type → T4 GPU** before running.

1. Upload the repository contents to a folder in Google Drive.
2. Open the desired notebook in Colab.
3. Mount your Drive and adjust the data path if needed:
```python
   from google.colab import drive
   drive.mount('/content/drive')
```
4. Run all cells sequentially.

### Option 2: Local execution

1. Clone the repository:
```bash
   git clone https://github.com/gustaph/IEEE-LATAM-Collaboration-Networks-Brazilian-EE-Researchers.git
   cd 
```

2. Install common dependencies:
```bash
   pip install pandas numpy matplotlib networkx python-louvain scikit-learn seaborn geobr requests tqdm
```

3. For the topics notebook (GPU required):
```bash
   pip install sentence-transformers bertopic datamapplot
   CMAKE_ARGS="-DGGML_CUDA=on" pip install llama-cpp-python
```
   Additionally, the [RAPIDS cuML](https://docs.rapids.ai/install) library must be installed following the official instructions for your CUDA version. A pre-trained GGUF model is also downloaded at runtime (OpenHermes-2.5-Mistral-7B, ~5 GB).

4. Open and run any notebook:
```bash
   jupyter notebook ieee_latam_network_analysis.ipynb
```

All notebooks read data from the `data/` folder using relative paths.


### Citing this work
```
@{
}
```
