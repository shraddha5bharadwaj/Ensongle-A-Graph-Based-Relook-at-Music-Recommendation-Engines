# Ensongle-A-Graph-Based-Relook-at-Music-Recommendation-Engines
##Introduction

This project focusses on Graph neural network implementation  for music recommendation.    

* Dataset - Million song dataset Kaggle sampled dataset was used which can be found [here](https://www.kaggle.com/c/msdchallenge/data)
* The feture vectors of song and user node in the heterogenous graph will be as follows:
* Neural graph collabrative filtering was implemented with the embeddings computed from data available on MSD.

```
Song - song's raw audio content as well as metadata information  
User - user's listening charecteristics i.e, songs he has played and its playcount
```

* In order to validate our vectorisation methods we conducted genre classification on the song vectors we created and obtained an validation accuracy of 63 pecrcent.

 Following recommender models have been imlemented:
```
1.Random Recommender (baseline)
2.Popularity Recommender (baseline)
3.Collaborative Filtering (baseline)
4.Content Based Recommendation (baseline)
5.NGCF with user and song node with random embedding (baseline)
6.NGCF with user and song custom embedding

```

Following evaluation metrics are used to compare the models

```
Mean Average precision @K
Mean Average Recall @K
Prediction coverage
Mean Reciprocal rank

```
##Directory description


* RawAudio - 
  * DownloadRawAudio.ipynb - Code to download raw audio for all the songs using Youtube API 
  * AutoEncoder.ipynb - to reduce (256,4096) to a (64,1) length vector
  * AudioToMelSpec.ipynb - converting mp4 to mel spectrograms 
* Vectorisation - 
  * Vectorisation.ipynb - song metadata is present in all_features.csv which is converted to a (64,1) vector using FAMD 
  * track_features .csv and song metadat vector is used to create song and user vectors
* GenreClassification - GenreClassifier.ipynb implements a genre classifier on previously created song vectors using labels present in genre_labels.csv
* NGCFModel - NGCF implementation with our vectors
  * NGCF reference
```
@inproceedings{NGCF19,
  author    = {Xiang Wang and
               Xiangnan He and
               Meng Wang and
               Fuli Feng and
               Tat{-}Seng Chua},
  title     = {Neural Graph Collaborative Filtering},
  booktitle = {Proceedings of the 42nd International {ACM} {SIGIR} Conference on
               Research and Development in Information Retrieval, {SIGIR} 2019, Paris,
               France, July 21-25, 2019.},
  pages     = {165--174},
  year      = {2019},
}
```
* Collaborative Filtering -  Contains the data and code [CF.ipynb] for Item-item collaborative filtering and recommendation generation.
* Evaluation -
  * remetrics - contains the implementation of all metrics and their plots that can be imported as a package
  * CalculationMetrics.ipynb - generates recommendation lists for all models and computes metrics and plots for all the proposed models.
  * Miscellaneous -  Contains implementations of Hinsage and Metapath2Vec recommenders taken from pytorch used to predict playcount.


