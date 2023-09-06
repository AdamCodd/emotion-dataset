# Emotion Analysis Dataset
## Overview
This dataset is designed for training machine learning models to perform emotion analysis. It contains text samples from Twitter labeled with six different emotions: sadness, joy, love, anger, fear, and surprise. The dataset is balanced, meaning that it has an equal number of samples for each label.

This dataset is originally sourced from [Hugging Face's Datasets Hub](https://huggingface.co/datasets/dair-ai/emotion), but the initial dataset was unbalanced. We have balanced it to ensure an equal number of samples for each emotion label.

## Labels
Label 0: Sadness
Label 1: Joy
Label 2: Love
Label 3: Anger
Label 4: Fear
Label 5: Surprise

## File structure
The dataset is divided into three JSONL files:

* train.jsonl: Contains 16,000 samples for training.
* validation.jsonl: Contains 2,000 samples for validation.
* test.jsonl: Contains 2,000 samples for testing.

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
## Further Details
For more information about the dataset and the emotion classification task, you can visit the original dataset page on [Hugging Face's Datasets Hub](https://huggingface.co/datasets/dair-ai/emotion).
