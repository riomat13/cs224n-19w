# A3 Dependency Parsing

This contains only implementaion of dependenct parsing.

## Neural Transition-Based Dependency Parsing

## Requirements
This projects involves many I/O-bound operations which can not be efficient on JETSON unlike A4,
hence This is executed on local machine (Ubuntu 18.04, i5-8250) instead.

Ran on following environment:
```
python==3.7
torch==1.0.0
```

## Results
Evaluated score by *Unlabeled Attachment Score(UAS)*.
- UAS (dev data): `88.78`
- UAS (test data): `89.35`

## References
[1] D. Chen and C. D. Manning. 2014. A Fast and Accurate Dependency Parser using Neural Networks
[2] Y. Tsuruoka and Y. Miyano. 2017. Syntactic Analysis. (Japanese)