# Emotion Analysis Dataset
## Overview
This dataset is designed for training machine learning models to perform emotion analysis. It contains text samples from Twitter labeled with six different emotions: sadness, joy, love, anger, fear, and surprise. The dataset is balanced, meaning that it has an equal number of samples for each label.

This dataset is originally sourced from [Hugging Face's Datasets Hub](https://huggingface.co/datasets/dair-ai/emotion), but the initial dataset was unbalanced and had some duplicates samples. Thus, this dataset has been deduplicated and balanced to ensure an equal number of samples for each emotion label.

## Labels
Label 0: Sadness
Label 1: Joy
Label 2: Love
Label 3: Anger
Label 4: Fear
Label 5: Surprise

## File structure
The dataset is divided into three folders:

* <b>Raw</b>: Contains the raw data with the text and emotion in string (sadness, joy...)
* <b>Unsplit</b>: Contains the full dataset balanced and properly labeled
* <b>Split</b>: Contains the split_emotion_balanced with 20,000 samples, the train.jsonl with 16,000 samples for training, the validation.jsonl with 2,000 samples for validation and the test.jsonl with 2,000 samples for testing.

Each line in these JSONL files is a JSON object with the following format:
```json
{
  "text": "sample text",
  "label": 0
}
```
## Usage
To load the dataset into Python, you can use the following code snippet:
```
import pandas as pd

# Load a JSONL file into a DataFrame
df = pd.read_json('path/to/file.jsonl', lines=True)

# Show the first few samples
print(df.head())
```
## Notebooks
* [Google colab notebook](https://colab.research.google.com/drive/1nwCE6b9PXIKhv2hvbqf1oZKIGkXMTi1X#scrollTo=t23zHggkEpc-) for fine-tuning a pretrained language model on an emotion classification task.
* [Google colab notebook](https://colab.research.google.com/drive/176NSaYjc2eeI-78oLH_F9-YV3po3qQQO?usp=sharing) which shows how to fine-tune T5 model for emotion classification along with other tasks.

## References
```
@inproceedings{saravia-etal-2018-carer,
    title = "{CARER}: Contextualized Affect Representations for Emotion Recognition",
    author = "Saravia, Elvis  and
      Liu, Hsien-Chi Toby  and
      Huang, Yen-Hao  and
      Wu, Junlin  and
      Chen, Yi-Shin",
    booktitle = "Proceedings of the 2018 Conference on Empirical Methods in Natural Language Processing",
    month = oct # "-" # nov,
    year = "2018",
    address = "Brussels, Belgium",
    publisher = "Association for Computational Linguistics",
    url = "https://www.aclweb.org/anthology/D18-1404",
    doi = "10.18653/v1/D18-1404",
    pages = "3687--3697",
    abstract = "Emotions are expressed in nuanced ways, which varies by collective or individual experiences, knowledge, and beliefs. Therefore, to understand emotion, as conveyed through text, a robust mechanism capable of capturing and modeling different linguistic nuances and phenomena is needed. We propose a semi-supervised, graph-based algorithm to produce rich structural descriptors which serve as the building blocks for constructing contextualized affect representations from text. The pattern-based representations are further enriched with word embeddings and evaluated through several emotion recognition tasks. Our experimental results demonstrate that the proposed method outperforms state-of-the-art techniques on emotion recognition tasks.",
}
```

## Further Details
For more information about the dataset and the emotion classification task, you can visit the original dataset page on [Hugging Face's Datasets Hub](https://huggingface.co/datasets/dair-ai/emotion).
