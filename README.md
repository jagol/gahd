This repository contains the dataset from our NAACL 2024 paper "Improving Adversarial Data Collection by Supporting Annotators: Lessons from GAHD, a German Hate Speech Dataset".
You can also find this dataset on the [Hugging Face Hub](https://huggingface.co/datasets/davanstrien/gahd).

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

When using GAHD, please cite our preprint on Arxiv:
```
@misc{goldzycher2024improving,
      title={Improving Adversarial Data Collection by Supporting Annotators: Lessons from GAHD, a German Hate Speech Dataset}, 
      author={Janis Goldzycher and Paul Röttger and Gerold Schneider},
      year={2024},
      eprint={2403.19559},
      archivePrefix={arXiv},
      primaryClass={cs.CL}
}
```
