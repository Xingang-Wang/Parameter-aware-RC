# **Project Name**: Parameter-aware Reservoir Computing

## **Features**
We use the parameter-aware RC method to predict the time series, return map, and bifurcation diagram of the Logistic map. We also use the same method to predict the time series, phase diagram, and bifurcation diagram of the Chua circuit. In addition, we apply the RC method to predict the bifurcation diagram of the Lorenz 96 system, a higher-dimensional chaotic system. We demonstrate that for Reservoirs of the same size with the same system, after training with the same method, the prediction accuracy is affected by the number and position of the bifurcation parameters in the training set.

## **Table of Contents**
- [Introduction](#introduction)
- [Logistic Map Prediction](#logistic-map-prediction)
- [Chua Circuit Bifurcation Prediction](#chua-circuit-bifurcation-prediction)
- [Lorenz 96 Bifurcation Prediction](#lorenz-96-bifurcation-prediction)
- [Training Process](#training-process)
- [Testing and Plotting](#testing-and-plotting)

## **Introduction**
This project implements key results in bifurcation prediction using parameter-aware reservoir computing (RC). The main goal is to reconstruct bifurcation diagrams for the Logistic map, Chua circuit, and Lorenz 96 system using the parameter-aware method. The RC method is employed to predict bifurcations of complex systems and optimize hyperparameters for accurate system prediction.

## **Logistic Map Prediction**
The code for Fig 3(a) is located in the `predicted logistic map` folder. In this folder:
- `data_logistic_dif4a.m`: Generates training data (`traindata.mat`).
- `predicted_log_bif.m`: The main script, which reconstructs the Logistic map bifurcation using the parameter-aware RC method.

## **Chua Circuit Bifurcation Prediction**
The code for Fig 5(a) is in the `predicted bifurcation of chua circuit` folder. It uses the parameter-aware RC method to reconstruct the Chua circuit bifurcation with four bifurcation parameter sample points.

- **Training Process**
The training process for optimizing hyperparameters is implemented in the `train` folder:
- `opt_attractor_with_lable.m`: The main script for optimizing hyperparameters. Before running this script, you need to place two empty matrices named `min_rng_set.mat` and `min_rmse_dynamic_set.mat` in the same folder. These matrix names can be modified as per your requirements.
- `func_train_attractor_with_lable.m`: The function used for training the RC model.

- **Testing and Plotting**
In the `predict and plot` folder:
- `chua_bif_predict_main_test.m`: The main script for reconstructing the Chua circuit bifurcation.
  - The matrix `bif_chua_pre5.mat` contains the data for the reconstructed bifurcation diagram of Chua circuit.
  - The matrix `bif_chua_processed_data.mat` contains the data for the true bifurcation diagram of Chua circuit.
  - `traindata.mat`: The training data matrix.
  - `opt_attractor_chua.mat` and `min_rng_set.mat`: Optimized data matrices.
 
## **Lorenz 96 Bifurcation Prediction**
The code for predicting the bifurcation diagram of the Lorenz 96 system is located in the `lorenz_96` folder. This high-dimensional system is used to test the RC method in predicting bifurcations for more complex chaotic systems. The prediction process is divided into training and testing subfolders:

- **Train**: In the `train` subfolder, you can find scripts for the entire training process, including data generation and hyperparameter optimization. This is crucial for ensuring the model is properly trained to predict bifurcations in the Lorenz 96 system.
    - `func_dataset_lorenz_96.m`: Generates training data (`train_lorenz96.mat`).
    - `opt_lorenz_96.m`: The main script for training the RC model, including the optimization of hyperparameters for the Lorenz 96 system.

- **Predict**: In the `bif_predict` subfolder, you can find scripts that use the optimized RC model to predict the bifurcation diagram of the Lorenz 96 system.
    - `bif_test_m_5.m`: The main script for predicting and visualizing the bifurcation diagram of the Lorenz 96 system.
    - `bif_RC.m`: A script used for plotting the bifurcation diagram of the Lorenz 96 system.
