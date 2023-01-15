This GitHub repository contains a collection of research papers on dense retrieval and negative sampling techniques. The papers included in this repository explore various methods for improving the efficiency and effectiveness of text retrieval systems, with a focus on techniques that involve dense representations and negative sampling. These papers come from a wide range of sources, including academic journals and conference proceedings. The goal of this repository is to provide a convenient and easily accessible resource for researchers and practitioners working in the field of text retrieval.



Base paper: [Pre-training Methods in Information Retrieval](https://arxiv.org/pdf/2111.13853.pdf)

# Negative Sampling 


| #|Paper Title  | Authors  | Technique |Drawbacks|
|---|---|---|---|--|
|1 |[Dense Passage Retrieval for Open-Domain Question Answering; 2020](https://arxiv.org/abs/2004.04906)| Vladimir Karpukhin, et.al.| Consider three differenttypes of negatives (1) Random: any random passage from the corpus;  (2) BM25: top passages returned by BM25 which don’t contain the answer but match most question tokens; (3) Gold: positive passages paired with other questions which appear in the training set.|One drawback of using (1) random passages as negatives is that they may not be semantically or contextually relevant to the question, which could lead to false negatives. Using (2) BM25 to select passages that match most question tokens but don't contain the answer could also result in irrelevant or nonsensical passages being selected as negatives. Using (3) gold negatives, or passages from the training set that are paired with other questions, may not generalize well to new questions or be representative of real-world scenarios. Additionally, using gold negatives may not be diverse enough to cover all possible incorrect answers.|
| 2|[APPROXIMATE NEAREST NEIGHBOR NEGATIVE CON- TRASTIVE LEARNING FOR DENSE TEXT RETRIEVAL 2021](https://openreview.net/pdf?id=zeFrfgyZln) |Lee Xiong | APPROXIMATE NEAREST NEIGHBOR NOISE CONTRASTIVE ESTIMATION|analyses show the importance, if not necessity, to construct negatives globally from the corpus to avoid uninformative negatives for better learning convergence selects negatives from the entire corpus using an asynchronously updated ANN index. ANCE samples negatives from the top retrieved documents via the DR model from the ANN index. $$\theta^* = argmin_{\theta} \sum\limits_{q \in Q} \sum\limits_{d^+\in D^+} \sum\limits_{d^- \in D^-} l(f(q, d^+), f(q, d^-))$$
| 3|[Multi-stage Training with Improved Negative Contrast for Neural Passage Retrieval 2021](https://aclanthology.org/2021.emnlp-main.492.pdf) | Jing Lu | `1. Random sampling` samples negatives passages from Y with equal chance, i.e., treats PN (y) as a uniform distribution. `2. Context negatives` samples negative passages from those occurred in the same document as yi, assuming these negatives are less relevant to the question than yi, but more relevant than rest of the passage collection. Documents that contain only one passage are split in half, and the half that does not contain the answer span is picked as negative. `3. BM25` negatives samples negatives from top passages returned by a BM25 model. `Neural retrieval` negatives employs neural re- trieval models to sample negative passages. Authot did this by running the models on the questions in the training set and then sampling negatives from the top K predictions; In particular, the `4. coarse negatives` are sampled from a dual encoder model with 3 Transformer layers, and just 25 dimensions in the encoding outputs; the `5. fine` and `6. super` fine negatives are sampled from dual encoders with 12 Transformer layers with encoding dimension 512 and 768, respectively.|






# Negative Sampling Techniques

| # | Technique | Description |
|---|---|---|
| 1 | Random sampling | Samples negatives passages from Y with equal chance, i.e., treats PN (y) as a uniform distribution. |
| 2 | Context negatives | Samples negative passages from those occurred in the same document as yi, assuming these negatives are less relevant to the question than yi, but more relevant than rest of the passage collection. Documents that contain only one passage are split in half, and the half that does not contain the answer span is picked as negative. |
| 3 | BM25 negatives | Samples negatives from top passages returned by a BM25 model. |
| 4 | Neural retrieval negatives - Coarse | Employs neural retrieval models to sample negative passages. Authot did this by running the models on the questions in the training set and then sampling negatives from the top K predictions. Sampled from a dual encoder model with 3 Transformer layers, and just 25 dimensions in the encoding outputs. |
| 5 | Neural retrieval negatives - Fine | Employs neural retrieval models to sample negative passages. Authot did this by running the models on the questions in the training set and then sampling negatives from the top K predictions. Sampled from dual encoders with 12 Transformer layers with encoding dimension 512. |
| 6 | Neural retrieval negatives - Super Fine | Employs neural retrieval models to sample negative passages. Authot did this by running the models on the questions in the training set and then sampling negatives from the top K predictions. Sampled from dual encoders with 12 Transformer layers with encoding dimension 768. |

