This repository contains the dataset from our NAACL 2024 paper [Improving Adversarial Data Collection by Supporting Annotators: Lessons from GAHD, a German Hate Speech Dataset](https://arxiv.org/abs/2403.19559).

`gahd.csv` contains the following columns:
- `gahd_id`: unique identifier of the entry
- `text`: text of the entry
- `label`: `0` = "not-hate speech", `1` = "hate speech"
- `round`: round in which the entry was created
- `split`: "train", "dev", or "test"
- `contrastive_gahd_id`: `gahd_id` of its contrastive example

`gahd_disaggregated.csv` contains the following additional columns:
- `source`: 
    - if annotators entered the entry via the Dynabench interface: `dynabench`
    - if the entry was translated from the Vidgen et al. 2021 dataset: `translation` 
    - if the entry stems from the Leipzit news corpus: `news`
- `model_prediction`: label predicted by the target model, `0` or `1`
- `annotator_id`: unique identifier of the annotator that created the entry
- `annotator_labels`: a string containing a forward slash-separated list of all labels by annotators
- `expert_labels`: `0` or `1` if an expert annotator annotated the entry, otherwise empty

The dataset is also available on [Huggingface](https://huggingface.co/datasets/jagoldz/gahd).

When using GAHD, please cite our paper:
```
@inproceedings{goldzycher-etal-2024-improving,
    title = "Improving Adversarial Data Collection by Supporting Annotators: Lessons from {GAHD}, a {G}erman Hate Speech Dataset",
    author = {Goldzycher, Janis  and
      R{\"o}ttger, Paul  and
      Schneider, Gerold},
    editor = "Duh, Kevin  and
      Gomez, Helena  and
      Bethard, Steven",
    booktitle = "Proceedings of the 2024 Conference of the North American Chapter of the Association for Computational Linguistics: Human Language Technologies (Volume 1: Long Papers)",
    month = jun,
    year = "2024",
    address = "Mexico City, Mexico",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2024.naacl-long.248",
    doi = "10.18653/v1/2024.naacl-long.248",
    pages = "4405--4424",
    abstract = "Hate speech detection models are only as good as the data they are trained on. Datasets sourced from social media suffer from systematic gaps and biases, leading to unreliable models with simplistic decision boundaries. Adversarial datasets, collected by exploiting model weaknesses, promise to fix this problem. However, adversarial data collection can be slow and costly, and individual annotators have limited creativity. In this paper, we introduce GAHD, a new German Adversarial Hate speech Dataset comprising ca. 11k examples. During data collection, we explore new strategies for supporting annotators, to create more diverse adversarial examples more efficiently and provide a manual analysis of annotator disagreements for each strategy. Our experiments show that the resulting dataset is challenging even for state-of-the-art hate speech detection models, and that training on GAHD clearly improves model robustness. Further, we find that mixing multiple support strategies is most advantageous. We make GAHD publicly available at https://github.com/jagol/gahd.",
}
```
