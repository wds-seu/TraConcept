# Peng-Gao-Conceptual-System-Construction

# Requirements

conda env: `/penngao_conda_environment.yaml`

pip package: `/penngao_pip_packages.txt`

# Datasets

HITT-h: `/examples/training/hypernymy/datasets/hypernymydetection.tsv.gz`

HITT-a: `/examples/training/attribute/datasets/attributedetection.tsv.gz`

HITT-m: `/examples/training/multirelation/datasets/multi-relation-detection-detection.tsv.gz`

Statistical information of datasets is below:

| Datasets | Train  |  Dev   |  Test  |
| :------: | :----: | :----: | :----: |
|  HITT-h  | 18,847 | 6,302  | 6,292  |
|  HITT-a  | 40,412 | 13,449 | 13,451 |
|  HITT-m  | 19,100 | 6,120  | 6,515  |

# Main File

Hypernymy Detection: `/examples/training/hypernymy/training_hypernymy_benchmark.py`

Concept Attribute Detection: `/examples/training/attribute/training_attribute_benchmark.py`

Multi-relation Detection: `/examples/training/multirelation/training_multi_relation_benchmark.py`

# Run

```
python training_*_benchmark.py
```

# Results

Binary relation detection:

| Model    | Dataset | Accuracy  | Precision | Recall    | F1        |
| -------- | ------- | --------- | --------- | --------- | --------- |
| D-Tensor | HITT-h  | 87.78     | 74.88     | 61.56     | 67.45     |
| D-Tensor | HITT-a  | 83.27     | 70.15     | 60.18     | 65.38     |
| Bran     | HITT-h  | 91.52     | 82.31     | 79.68     | 81.32     |
| Bran     | HITT-a  | 85.34     | 71.25     | 65.48     | 68.56     |
| U_Teal   | HITT-h  | 78.47     | 41.55     | 9.38      | 15.30     |
| U_Teal   | HITT-a  | 77.36     | 40.15     | 10.16     | 16.20     |
| S_Teal   | HITT-h  | 90.85     | 87.03     | 84.31     | 85.56     |
| S_Teal   | HITT-a  | 89.90     | 74.22     | 73.44     | 73.83     |
| AS_Teal  | HITT-h  | **93.36** | **88.67** | 86.22     | 87.89     |
| AS_Teal  | HITT-a  | **92.92** | **80.89** | 79.60     | **79.70** |
| CEE      | HITT-h  | 92.34     | 85.25     | 83.56     | 84.46     |
| CEE      | HITT-a  | 88.56     | 72.17     | 70.86     | 71.56     |
| Ours     | HITT-h  | 93.00     | 87.88     | **89.79** | **88.18** |
| Ours     | HITT-a  | 91.09     | 77.66     | **81.02** | 79.31     |

> D-Tensor: Dual tensor model for detecting asymmetric lexicosemantic relations. EMNLP 2017
>
> Bran: Simultaneously self-attending to all mentions for full-abstract biological relation extraction. NAACL 2018
>
> Teal: Improving hypernymy prediction via taxonomy enhanced adversarial learning. AAAI 2019
>
> CCE: Learning Conceptual-Contextual Embeddings for Medical Text. AAAI 2020

Multi-relation detection:

| Model    | Dataset | Accuracy  | Macro_p   | Macro_R   | Macro_F1  |
| -------- | ------- | --------- | --------- | --------- | --------- |
| D-Tensor | HITT-m  | 75.30     | 76.52     | 73.34     | 74.78     |
| Bran     | HITT-m  | 78.89     | 79.32     | 75.18     | 77.56     |
| CCE      | HITT-m  | 80.12     | 65.89     | 75.30     | 69.53     |
| Ours     | HITT-m  | **81.57** | **82.23** | **81.56** | **81.80** |

# Reference

[SentenceTransformers]([SentenceTransformers Documentation — Sentence-Transformers documentation (sbert.net)](https://www.sbert.net/))

> refer to [Sentence-BERT: Sentence Embeddings using Siamese BERT-Networks](https://arxiv.org/abs/1908.10084)(EMNLP 2019)

This framework provides an easy method to compute dense vector representations for sentences and paragraphs (also known as sentence embeddings). The models are based on transformer networks like BERT / RoBERTa / XLM-RoBERTa etc. and are tuned specificially meaningul sentence embeddings such that sentences with similar meanings are close in vector space.


We provide an increasing number of **[state-of-the-art pretrained models](https://www.sbert.net/docs/pretrained_models.html)** for more than 100 languages, fine-tuned for various use-cases.

Further, this framework allows an easy  **[fine-tuning of custom embeddings models](https://www.sbert.net/docs/training/overview.html)**, to achieve maximal performance on your specific task.


For the **full documentation**, see [www.SBERT.net](https://www.sbert.net), as well as our publications:
- [Sentence-BERT: Sentence Embeddings using Siamese BERT-Networks](https://arxiv.org/abs/1908.10084) (EMNLP 2019)
- [Making Monolingual Sentence Embeddings Multilingual using Knowledge Distillation](https://arxiv.org/abs/2004.09813) (EMNLP 2020)
- [Augmented SBERT: Data Augmentation Method for Improving Bi-Encoders for Pairwise Sentence Scoring Tasks](https://arxiv.org/abs/2010.08240) (arXiv 2020)




## Installation
We recommend **Python 3.6** or higher, **[PyTorch 1.6.0](https://pytorch.org/get-started/locally/)** or higher and **[transformers v3.1.0](https://github.com/huggingface/transformers)** or higher. The code does **not** work with Python 2.7.



**Install with pip**

Install the *sentence-transformers* with `pip`:
```
pip install -U sentence-transformers
```

**Install from sources**

Alternatively, you can also clone the latest version from the [repository](https://github.com/UKPLab/sentence-transformers) and install it directly from the source code:
````
pip install -e .
````

**PyTorch with CUDA**
If you want to use a GPU / CUDA, you must install PyTorch with the matching CUDA Version. Follow
[PyTorch - Get Started](https://pytorch.org/get-started/locally/) for further details how to install PyTorch.



## Getting Started

See [Quickstart](https://www.sbert.net/docs/quickstart.html) in our documenation.


[This example](https://github.com/UKPLab/sentence-transformers/tree/master/examples/applications/computing-embeddings/computing_embeddings.py) shows you how to use an already trained Sentence Transformer model to embed sentences for another task.

First download a pretrained model.
````python
from sentence_transformers import SentenceTransformer
model = SentenceTransformer('distilbert-base-nli-mean-tokens')
````
Then provide some sentences to the model.
````python
sentences = ['This framework generates embeddings for each input sentence',
    'Sentences are passed as a list of string.', 
    'The quick brown fox jumps over the lazy dog.']
sentence_embeddings = model.encode(sentences)
````
And that's it already. We now have a list of numpy arrays with the embeddings.
````python
for sentence, embedding in zip(sentences, sentence_embeddings):
    print("Sentence:", sentence)
    print("Embedding:", embedding)
    print("")
````

## Pre-Trained Models

We provide a large list of [Pretrained Models](https://www.sbert.net/docs/pretrained_models.html) for more than 100 languages. Some models are general purpose models, while others produce embeddings for specific use cases. Pre-trained models can be loaded by just passing the model name: `SentenceTransformer('model_name')`.

[»  Full list of pretrained models](https://www.sbert.net/docs/pretrained_models.html)



## Training
This framework allows you to fine-tune your own sentence embedding methods, so that you get task-specific sentence embeddings. You have various options to choose from in order to get perfect sentence embeddings for your specific task. 

See [Training Overview](https://www.sbert.net/docs/training/overview.html) for an introduction how to train your own embedding models. We provide [various examples](https://github.com/UKPLab/sentence-transformers/tree/master/examples/training) how to train models on various datasets.


Some highlights are:
- Support of various transformer networks including BERT, RoBERTa, XLM-R, DistilBERT, Electra, BART, ...
- Multi-Lingual and multi-task learning
- Evaluation during training to find optimal model
- [10+ loss-functions](https://www.sbert.net/docs/package_reference/losses.html) allowing to tune models specifically for semantic search, paraphrase mining, semantic similarity comparison, clustering, triplet loss, constrative loss.



## Performance

Our models are evaluated extensively and achieve state-of-the-art performance on various tasks. Further, the code is tuned to provide the highest possible speed.

| Model    | STS benchmark | SentEval  |
| ----------------------------------|:-----: |:---:   |
| Avg. GloVe embeddings             | 58.02  | 81.52  |
| BERT-as-a-service avg. embeddings | 46.35  | 84.04  |
| BERT-as-a-service CLS-vector      | 16.50  | 84.66  |
| InferSent - GloVe                 | 68.03  | 85.59  |
| Universal Sentence Encoder        | 74.92  | 85.10  |
|**Sentence Transformer Models**    ||
| bert-base-nli-mean-tokens         | 77.12  | 86.37 |
| bert-large-nli-mean-tokens        | 79.19  | 87.78 |
| bert-base-nli-stsb-mean-tokens    | 85.14  | 86.07 |
| bert-large-nli-stsb-mean-tokens   | 85.29 | 86.66|
| roberta-base-nli-stsb-mean-tokens | 85.44 | - |
| roberta-large-nli-stsb-mean-tokens | 86.39 | - |
| distilbert-base-nli-stsb-mean-tokens | 85.16 | - |





## Application Examples
You can use this framework for:
- [Computing Sentence Embeddings](https://www.sbert.net/examples/applications/computing-embeddings/README.html)
- [Semantic Textual Similarity](https://www.sbert.net/docs/usage/semantic_textual_similarity.html)
- [Clustering](https://www.sbert.net/examples/applications/clustering/README.html)
- [Paraphrase Mining](https://www.sbert.net/examples/applications/paraphrase-mining/README.html)
 - [Translated Sentence Mining](https://www.sbert.net/examples/applications/parallel-sentence-mining/README.html)
 - [Semantic Search](https://www.sbert.net/examples/applications/semantic-search/README.html)
 - [Information Retrieval](https://www.sbert.net/examples/applications/information-retrieval/README.html) 
 - [Text Summarization](https://www.sbert.net/examples/applications/text-summarization/README.html) 

and many more use-cases.


For all examples, see [examples/applications](https://github.com/UKPLab/sentence-transformers/tree/master/examples/applications).

## Citing & Authors
If you find this repository helpful, feel free to cite our publication [Sentence-BERT: Sentence Embeddings using Siamese BERT-Networks](https://arxiv.org/abs/1908.10084):
``` 
@inproceedings{reimers-2019-sentence-bert,
    title = "Sentence-BERT: Sentence Embeddings using Siamese BERT-Networks",
    author = "Reimers, Nils and Gurevych, Iryna",
    booktitle = "Proceedings of the 2019 Conference on Empirical Methods in Natural Language Processing",
    month = "11",
    year = "2019",
    publisher = "Association for Computational Linguistics",
    url = "https://arxiv.org/abs/1908.10084",
}
```


If you use one of the multilingual models, feel free to cite our publication [Making Monolingual Sentence Embeddings Multilingual using Knowledge Distillation](https://arxiv.org/abs/2004.09813):
``` 
@inproceedings{reimers-2020-multilingual-sentence-bert,
    title = "Making Monolingual Sentence Embeddings Multilingual using Knowledge Distillation",
    author = "Reimers, Nils and Gurevych, Iryna",
    booktitle = "Proceedings of the 2020 Conference on Empirical Methods in Natural Language Processing",
    month = "11",
    year = "2020",
    publisher = "Association for Computational Linguistics",
    url = "https://arxiv.org/abs/2004.09813",
}
```


If you use the code for [data augmentation](https://github.com/UKPLab/sentence-transformers/tree/master/examples/training/data_augmentation), feel free to cite our publication [Augmented SBERT: Data Augmentation Method for Improving Bi-Encoders for Pairwise Sentence Scoring Tasks](https://arxiv.org/abs/2010.08240):
``` 
@article{thakur-2020-AugSBERT,
    title = "Augmented SBERT: Data Augmentation Method for Improving Bi-Encoders for Pairwise Sentence Scoring Tasks",
    author = "Thakur, Nandan and Reimers, Nils and Daxenberger, Johannes and  Gurevych, Iryna", 
    journal= "arXiv preprint arXiv:2010.08240",
    month = "10",
    year = "2020",
    url = "https://arxiv.org/abs/2010.08240",
}
```


The main contributors of this repository are:
- [Nils Reimers](https://github.com/nreimers)
- [Gregor Geigle](https://github.com/aaronsom)

Contact person: Nils Reimers, info@nils-reimers.de

https://www.ukp.tu-darmstadt.de/


Don't hesitate to send us an e-mail or report an issue, if something is broken (and it shouldn't be) or if you have further questions.

> This repository contains experimental software and is published for the sole purpose of giving additional background details on the respective publication.







