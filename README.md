# Global-Locally Self-Attentive Dialogue State Tracker

### Download dataset

The dataset can be found in https://github.com/tanyuqian/dialog-state-tracker

### Install dependencies


```
pip install -r requirements.txt
```


### Train model

You can checkout the training options via `python train.py -h`.
By default, `train.py` will save checkpoints to `exp/glad/default`.

```
python train.py --gpu 0
```


### Evaluation


You can also dump a predictions file by specifying the `--fout` flag.
In this case, the output will be a list of lists.
Each `i`th sublist is the set of predicted slot-value pairs for the `i`th turn.
Please see `evaluate.py` to see how to match up the turn predictions with the dialogues.

```
python evaluate.py --gpu 0 --split test exp/glad/default
```

### Download and annotate data if you dont have dataset

This project uses Stanford CoreNLP to annotate the dataset.
In particular, we use the [Stanford NLP Stanza python interface](https://github.com/stanfordnlp/stanza).

```
python preprocess_data.py
```