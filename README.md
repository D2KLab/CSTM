# Common-sense Topic Modeling

This repository contains the code for reproducing the results reported in the paper "Discovering Interpretable Topicsby Leveraging Common Sense Knowledge" (under review).

## Dependencies
Before running any code in this repo, please install the following dependencies:
* numpy
* pandas 
* gensim
* faiss
* nltk
* sklearn
* tqdm

## train.py
This is the master script for training all models. 

```
usage: train.py [-h] [-m {lda,kmeans,gmm,nmf}] [-n NUMBER_OF_TOPICS] [-t THRESH] [-c CLASSES] -d DATASET_PATH [-i ITERATIONS] [-p PREPROCESSING] [-r REDO] [-s SAVE_PATH] [-e CACHE_PATH]
                [-x] [-g GLOVE_PATH]

Topic Model Training

optional arguments:
  -h, --help            show this help message and exit
  -m {lda,kmeans,gmm,nmf}, --model {lda,kmeans,gmm,nmf}
                        Which model to user
  -n NUMBER_OF_TOPICS, --number_of_topics NUMBER_OF_TOPICS
                        Number of topics ('auto' = number of labels)
  -t THRESH, --thresh THRESH
                        Cut-off threshold for numberbatch similarity
  -c CLASSES, --classes CLASSES
                        Specify which labels to keep (comma-separated, or 'all')
  -d DATASET_PATH, --dataset_path DATASET_PATH
                        Path to the dataset CSV
  -i ITERATIONS, --iterations ITERATIONS
                        Maximum number of iterations
  -p PREPROCESSING, --preprocessing PREPROCESSING
                        Specify which preprocessing pipeline to use
  -r REDO, --redo REDO  Number of runs (with different seeds) to do
  -s SAVE_PATH, --save_path SAVE_PATH
                        Path to save the results
  -e CACHE_PATH, --cache_path CACHE_PATH
                        Where to cache preprocessed data
  -x, --external_vocab  Whether or not to add external vocabulary
  -g GLOVE_PATH, --glove_path GLOVE_PATH
                        Path to pickled GloVe embeddings
```


## Human Evaluation
Under `human_eval`, you can find the results from the end-user surveys done to evaluate the performance of different topic models on topic interpretability tasks.
`generate_test.ipynb` allows to generate the questions randomly from the resulting trained topics.
