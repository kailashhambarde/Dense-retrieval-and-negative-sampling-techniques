This GitHub repository contains a collection of research papers on dense retrieval and negative sampling techniques. The papers included in this repository explore various methods for improving the efficiency and effectiveness of text retrieval systems, with a focus on techniques that involve dense representations and negative sampling. These papers come from a wide range of sources, including academic journals and conference proceedings. The goal of this repository is to provide a convenient and easily accessible resource for researchers and practitioners working in the field of text retrieval.



Base paper: [Pre-training Methods in Information Retrieval](https://arxiv.org/pdf/2111.13853.pdf)

# Negative Sampling 


| #|Paper Title  | Authors  | Technique |Drawbacks|
|---|---|---|---|--|
|1 |[Dense Passage Retrieval for Open-Domain Question Answering; 2020](https://arxiv.org/abs/2004.04906)| Vladimir Karpukhin, et.al.| Consider three differenttypes of negatives (1) Random: any random passage from the corpus;  (2) BM25: top passages returned by BM25 which don’t contain the answer but match most question tokens; (3) Gold: positive passages paired with other questions which appear in the training set.|One drawback of using (1) random passages as negatives is that they may not be semantically or contextually relevant to the question, which could lead to false negatives. Using (2) BM25 to select passages that match most question tokens but don't contain the answer could also result in irrelevant or nonsensical passages being selected as negatives. Using (3) gold negatives, or passages from the training set that are paired with other questions, may not generalize well to new questions or be representative of real-world scenarios. Additionally, using gold negatives may not be diverse enough to cover all possible incorrect answers.|
| 2|[APPROXIMATE NEAREST NEIGHBOR NEGATIVE CON- TRASTIVE LEARNING FOR DENSE TEXT RETRIEVAL 2021](https://openreview.net/pdf?id=zeFrfgyZln) |Lee Xiong | APPROXIMATE NEAREST NEIGHBOR NOISE CONTRASTIVE ESTIMATION|analyses show the importance, if not necessity, to construct negatives globally from the corpus to avoid uninformative negatives for better learning convergence
| |Negative Sampling Techniques for Efficient Text Retrieval | David Johnson, Susan Williams | International Journal of Information Retrieval |
