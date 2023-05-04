# Clearing Electricity Market of Variable Size with Graph Neural Networks
Repository for Master's Thesis 'Clearing Electricity Market of Variable Size with Graph Neural Networks' by N.Angermeier  (TUM)

## Project Description
The energy market clearing and the associated optimal power flow (OPF) problem create energy distribution schedules while balancing generation and demand. The goal is to optimize global welfare under complex technical constraints. As of the present day, solutions are computed via mixed-integer programming (MIP). This optimization problem is very complex, requiring the best techniques and technologies as well as time. Changes in energy sources, demand and distribution pose challenges for market optimization. In order to ensure energy reliability and to give the right impulses in almost real-time, the energy market clearing needs to become faster. Machine learning (ML) techniques offer the potential to mimic these linear optimizers with almost real-time predictions after training phases. Since the OPF problem is repeatedly solved, the high amount of unused historical data provides the needed conditions for such statistical data-based models.

In our paper, we solve an advanced version of the DC-OPF model with a full inclusion of the unit commitment problem. In the literature review of ML application in OPF so far, we come across the limit of not including variable grid sizes into the ML approaches so far. However, the energy grid is continuously changing and growing, and real-life OPF optimization support tools need to be able to handle these changes. This paper inspects and defines approaches to account for this data structure within OPF optimization. Within the paper, we define a method to create feasible dynamic data sets for DC-OPF optimization from the IEEE OPF Benchmarking cases and the PJM Data Miner. 

We then apply a (dynamic) recursive graph neural network, implemented with the PYTorch Geometric Temporal library, to mimick the MIP optimization and give the test results. While the model can handle this data structure and creates good test scores for fixed-size generation prediction (91\%), variance in the data and specifically different grid sizes pose significant challenges to the model.

## Contents
* Scripts
  * Data
    * Data Preparation
    * Dynamic Sets
    * Gurobi
  * RGNN Tests
    * CPU
    * GPU
* Data Sets
* Test Logs

The Repository consists of three types of artifacts: *Scripts*, *data sets* and *test logs*. 


Summaries of the used scipts for data cleaning as well as data preparation and feasibility adjustments to the data sets are included in *Data Preparation*. Then we propose scripts for formatting the data and creating dynamic grid sizes in *Dynamic Sets*. The last step of the data preparation is the Gurobi optimization with the respective script and sampling method.

In *RGNN Tests* we provide the scripts for test the PyTorch Geometric implementation. Some of the mentioned test results are given in the TensorFlow format in *Test Logs*.
The scripts were continuously adapted within their use, so only their last versions are provided. They can be adapted with the configuration details and hyperparameters discussed in the Model Test section of the actual thesis.

Within *Data Sets* we provide three finished sets, generated and optimized with the discussed methods and scripts.

## Use
We provide Jupyter Notebooks.  
For the Gurobi optimization, the *gurobipy* library needs to be installed after a license was created or using Google Colab. Details on the environment setup are given in the paper in Section 4.3.4.  
For the RGNN Tests, the *PyTorch*, *PyTorch Geometric* and *PyTorch Geometric Temoral* libraries are needed. If tested on GPU, a CUDA-capable system (NVIDIA GPU) is needed and the libraries need to be installed in the CUDA version. Additionally install *PyTorch Lightning* and *TensorFlow*. We additionally provide a yml file for quick setup of the environment with Anaconda. Details on the environment setup are given in the paper in Section 5.2.3.

## Credits
This project was fully created by Nadine S. Angermeier within her Master's Thesis at the Chair of Decision Science & Systems, Department of Computer Science, School of Computation, Information and Technology at the Technical University of Munich under the supervision of Mete S. Ahunbay (Oct 2022- May 2023).
