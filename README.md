# Surface Energy Manuscript

This repository contains various scripts/notebooks we used to create the results in our paper.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Usage](#usage)
  - [Surface energy dataset](#dataset)
  - [Train a CGCNN model](#train-a-CGCNN-model)
  - [Analyze CGCNN results](#analyze-CGCNN-results)


## Prequistes
* Crystal Graph Convolutional Neural Networks ([CGCNN](https://github.com/ulissigroup/cgcnn/tree/sklearn_refactor))

* Additional packages required for cgcnn environmnet:
- [PyTorch](http://pytorch.org)
- [scikit-learn](http://scikit-learn.org/stable/)
- [pymatgen](http://pymatgen.org)


## Usage

### Surface energy dataset

Located in the `surface_energy_dataset` folder. 

We have included a pickel file that contain our surface data, along with a Jupyter notebook (`read_data.ipynb`) that shows you how we turn the pickel items into `ase.Atoms` objects.

### Train a cgcnn model

Located in the `train_CGCNN_model` folder.

We have included 2 different training methods. `random_split.ipynb` notebook splits the data randomly into 8:2 training: test set, and uses CGCNN to train a model. `leave_one_out.ipynb` uses a composition of interest as the test set, and the rest of the data as the training set to train a model. **You need to clone the CGCNN repository and install all the prerequisite packages in order to run these notebooks** 

We have included the optimized paramters we used for CGCNN: 
"atom_fea_len": 43, 
"batch_size": 87, 
"step": "0.1", 
"epochs": 218, 
"h_fea_len": 114,
"log_learning_rate": -6.465085550816676,
"n_conv": 8,
"n_h": 3,
"max_num_nbr": 12,
"optimizer": "Adam"


### Analyze CGCNN results

Located in the `analyze_prediction_results` folder.

The results from CGCNN predictions are stored in the `CGCNN_prediction_results` folder. You can use `generate_parity_plots.ipynb` to visualize the prediction accuracy for each training method. 







