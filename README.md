# **Concentration and Diversity in Collaboration Networks in Electrical Engineering: Evidence from Brazilian Researchers**

This repository contains the implementation used to generate the results presented in the paper "Concentration and Diversity in Collaboration Networks in Electrical Engineering: Evidence from Brazilian Researchers" presented at the 2026 IEEE Latin America Transactions.

---

### **Authors**

- [Fernando A. do Carmo](https://orcid.org/0000-0003-4594-5924)
- [Gustavo S. Silva](https://orcid.org/0009-0001-1559-3465)
- [Raimundo C. S. Freire](https://orcid.org/0000-0002-5395-7143)
- [Antonio F. L. Jacob Jr](https://orcid.org/0000-0002-9415-7265)
- [Fábio M. F. Lobato](https://orcid.org/0000-0002-6282-0368)

---

### Abstract
Scientific collaboration networks shape research dynamics in fields such as Electrical Engineering, where Brazil’s CNPq productivity grant system constitutes a central incentive structure. Building on previous analyses focused on Microelectronics, this study examines collaboration networks across the broader field of Electrical Engineering, encompassing seven subareas: Electrical Materials; Electrical, Magnetic, and Electronic Measurements and Instrumentation; Electrical, Magnetic, and Electronic Circuits; Power Systems; Industrial Electronics, Systems, and Electronic Controls; and Telecommunications. The analysis considers 419 CNPq productivity grant holders and 18,386 publications. The results reveal a hierarchical collaboration structure in which higher grant levels concentrate influence and centrality, while lower levels remain more peripheral despite active collaboration. The network exhibits pronounced geographic concentration in Brazil’s Southeast and South regions, as well as marked gender disparities. Compared with prior subfield-focused analyses, Electrical Engineering displays greater thematic heterogeneity and broader inter-level interaction, while maintaining persistent structural inequality. Temporal analysis indicates increasing average author influence and more compact collaboration clusters over time. These findings suggest that collaboration patterns in Electrical Engineering reflect cumulative advantage mechanisms associated with hierarchical funding structures.

---
### 📁 `data/` (Databases)
* `nodes_dataset.csv`: Contains the attributes of the 323 CNPq EE productivity fellows (grant level, gender, geographic region, institution, PageRank).
* `edges_dataset.csv`: Contains the co-authorship relationships.
* `publications_topics.csv`: Contains the processed publication titles (18,386 articles).

### 📁 `scripts/` (Source Code)
* `01_network_analysis.py`: Script using NetworkX to build the undirected graph, calculate the Density Index, and compute the PageRank and components over time.
* `02_topic_modeling.py`: Script containing the BERTopic pipeline (UMAP, HDBSCAN, KeyBERTInspired) used to cluster publication titles.

### Citing this work
```
@{
}
```
