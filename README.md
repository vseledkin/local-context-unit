# Bag of region embeddings via local context units for text classification
Tensorflow implementation of ICLR 2018 paper [A new method of region embedding for text classification](https://openreview.net/forum?id=BkSDMA36Z).

## 0. Requirements 

### General
Python (verified on 2.7.13)

### Python Packages
tensorflow(verified on 1.0)
    

## 1. Datasets
We use publicly available datasets from Zhang et al.(2015) to evaluate our models.
The datasets can be obtained from [here](https://github.com/zhangxiangxiao/Crepe).

## 2. Pre-processing
First, download the datasets and place them in `data` directory.
    
Second, pre-process the datasets:

```
	sh run.sh preprocess $data_dir
```

## 3. Training
To ensure the reproducibility of the experiment, we provide detailed configs binding corresponding dataset. Specify the target dataset config and run:  

|Dataset| Command|
|-----------------|----------|
|Yelp Polarity. | ```	sh run.sh train conf yelp.p.model.config``` |
|Yelp Full. | ```sh run.sh train conf/yelp.full.model.config```|
|Amazon Polarity.|```	sh run.sh train conf/amazon.p.model.config```|
|Amazon Full.|```	sh run.sh train conf/amazon.full.model.config```|
|Ag news.|```	sh run.sh train conf/ag_news.model.config```|
|Sogou.|```	sh run.sh train conf/sogou.model.conf```|
|Yahoo Answer. |```sh run.sh train conf/yahoo.answer.model.conf```|
|DBPedia.| ```sh run.sh train conf/dbpedia.model.config```|


## 4. Exploratory experiments
We provide the exploratory method involved in the paper if readers are interesed in reproducing them. Readers can specific the mode setting in configure to run different expriments:

|Mode|Experiments|
|----|-----------|
|WC  |Word-Context |
|CW  |Context-Word |
|win_pool| FastText(Win-pool)|
|scalar  |Scalar version of W.C.region.emb |
|multi_region| Multi-region version of W.C.region.emb|

We have placed some example configs for the exploratory experiments on Yelp.Full. You can just run folowing comands to try them:

|Experiments| Command|
|-----------| -------|
|Multi-region version of W.C.region.emb |```sh run.sh train conf/yelp.full.multi-region.model.config```|
|Scalar version of W.C.region.emb |```sh run.sh train conf/yelp.full.scalar.model.config```|
|FastText(Win-pool)|```sh run.sh train conf/yelp.full.winpool.model.config```|

