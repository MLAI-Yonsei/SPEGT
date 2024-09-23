
# Structural and positional ensembled encoding for Graph Transformer


## Abstract
 In the Transformer architecture, positional encoding is a vital component because it provides the model with
 information about the structure and position of data. In Graph Transformer, there have been attempts to
 introduce different positional encodings and inject additional structural information. Therefore, in terms of
 integrating positional and structural information, we propose a Structural and Positional Ensembled Graph
 Transformer (SPEGT). We developed SPEGT by noting the different properties of structural and positional
 encodings of graphs and the similarity of their computational processes. We have set a unified component
 that integrates the functionalities: (i) Random Walk Positional Encoding, (ii) Shortest Path Distance between
 each node, and (iii) Hierarchical Cluster Encoding. We find a problem with a well-known positional encoding
 and experimentally verify that combining it with other encodings can solve their problem. In addition, SPEGT
 outperforms previous models on a variety of graph datasets. We also show that SPEGT using unified positional
 encoding, performs well on structurally indistinguishable graph data through error case analysis.


## Results

Dataset       | #layers | #params | Metric         | Valid           | Test           |
--------------|---------|---------|----------------|-----------------|----------------|
PCQM4M-V2     | 24      | 90.1M   | MAE            | 0.0863          | 0.0868         |


## Requirements

* `python == 3.7`
* `pytorch == 1.12.1`
* `numpy == 1.23.5`
* `numba == 0.56.4`
* `ogb == 1.3.2`
* `rdkit==2019.03.1`
* `yaml == 0.2.5`
* 'network == 2.8.4'

## Run Training and Evaluations

You can specify the training/prediction/evaluation configurations by creating a `yaml` config file and also by passing a series of `yaml` readable arguments. (Any additional config passed as argument willl override the config specified in the file.)

* To run training: ```python run_training.py [config_file.yaml] ['config1: value1'] ['config2: value2'] ...```
* To perform evaluations: ```python do_evaluations.py [config_file.yaml] ['config1: value1'] ['config2: value2'] ...```

Config files for the results can be found in the configs directory. Examples:
```
python run_training.py configs/pcqm4mv2/egt_90m.yaml
python do_evaluations.py configs/pcqm4mv2/egt_90m.yaml
```


## Python Environment

The Anaconda environment in which the experiments were conducted is specified in the `environment.yml` file.

## Acknowledgements
Our overall experimental pipeline is based on EGT, MPGNNs-LSPE repository. For baseline construction. We appreciate the authors who Hussain et al. and Dwivedi et al. for sharing their code.


