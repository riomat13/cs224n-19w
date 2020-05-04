# A2 Word2Vec

Understanding *word2vec* and implemnenting it.

The written part is skipped because coding part includes theoritical parts, 
which means that it is necessary to calculate derivatives by hand to implement codes for this assignment.

[Note] this is only tested with provided codes, so that it is not guranteed that the code is correctly implemented.

## Requirements
This is run in following conditions:
```
python==3.7
matplotlib=3.2.1
numpy==1.18.3
```

## Implementation
1. Naive model
   
   This model only computes word relation between center word and other words in window and the loss is calculated by *softmax* in entire vocabulary.
   This would not efficient because this involves a lot of computation in *softmax*.

2. Skip-gram model

    Whereas, *skip-gram* model computes vectors simplar to naive model but including words sampled by *negative-sampling*.
    Each word include

## Computation
In order to execute code, run following commands:
```
sh get_datasets.sh
python run.py
```

According to hand-out, this would take approximately an hour (3600 sec.) if implemented efficiently,
however, the current implementation takes 1.7 hours (6200 sec.) in local machine (Ubuntu 18.04, intel corei5-8250U) so there might be some overheads and/or bottlenecks.

## Result
As intrinsic evaluation in vector space, it looks work well in some cases, and not so well in some cases.
For instance, the relation, `male:female::king:queen` distributes well but `man` and `woman` are located differently.
More specifically, `femail` and `woman` are postioned close, which makes sence semantically, however `man` and `male` are not.

Other relationship, such as between `amazing` and `wonderful` and between `tea` and `coffee` are both located close.

Since provided dataset is small (20MB), it might be inevitable to located inappropriate
such as `man` is located near `female` and `enjoyable` is near `annoying`. I think it is because *Skip-gram* is counting on context, thus this happens in small dataset. Additionally, this is dimensionally reduced to plot, and this also may affect somehow.
(based on provided code, simply *SVD* is used and take two first vector spaces are taken to plot,
so the result is strongly correlated to the vector spaces.)