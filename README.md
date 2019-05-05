# CS7641 Assignment 2 - Randomized Optimization

_GitHub Link:_ https://github.gatech.edu/kkishinani3/CS7641Assignment2

## References
- ABAGAIL: https://github.com/pushkar/ABAGAIL
- Base code: https://github.com/cmaron/CS-7641-assignments/tree/master/assignment2
- Adult Data Set: https://archive.ics.uci.edu/ml/datasets/Adult

## Problems

This repository uses the ABAGAIL Repository to implement:

1. Finding Neural Networks Weights using Random Search Algorithms:
    - `NN-Backprop.py` Backpropagation (baseline for comparison)
    - `NN-RHC.py` Randomized Hill Climbing (RHC)
    - `NN-GA.py` Genetic Algorithms (GA)
    - `NN-SA.py` Simulated Annealing (SA)

2. Three randomized optimization toy problems using RHC, SA, GA, and MIMIC:
    - `continuouspeaks.py` Continuous Peaks
    - `flipflop.py` Flip Flop
    - `tsp.py` Travelling Salesman
    
_Note_: All these code files above have been written in Jython. Please refer to the Jython section below for information on how to run each one.

## Dataset

For this assignment we use the *Adult Census Dataset* (obtained from UC-Irvine) preprocessed from our Assignment 1.

The dataset is contained in the `./data` directory as a CSV file `adult.csv`

## Languages, Dependencies, and How to Run the Code

### ABAGAIL

The main code used for implementing the Randomized Optimization Algorithms is written in JAVA obtained from the ABAGAIL library contained in the `./ABAGAIL` directory.

Make sure have `Java` and `ant` installed in your machine. 

Before running all the code, make sure you recompile the ABAGAIL library by running `ant` from the ABAGAIL directory.

This should generate the `ABAGAIL.jar` file. Make sure there is a symboling reference to this JAR file from within the main directory where the python scripts are stored.

### Python and Data Processing

1. Before you start working with the Python files install the dependencies listed in `requirements.txt` using pip:

    `pip install -r requirements.txt`

2. The code for processing the dataset and preparing it for our neural network `run_experiment.py` is written using Python. 
Please make sure you have Python 3.7.2 installed in your machine. Then run the following command:

    `python3 run_experiment.py --dump_data`
    
    This will create the training `adult_train.csv`, validation `adult_validate.csv`, and test set `adult_test.csv` files in the `./data` to be used in ABAGAIL.
    
### Jython and Running the Problems

1. Please make sure you have Jython 2.7.1 installed in your machine. If you have Homebrow installed in your machine, run the following command to install the latest version of Jython:

    `brew install jython`
    
2. Each of the experiment files for the neural network and optimization toy problems are writting using Jython. To run each individual experiment run the following from the home directory:

    `jython <filename>.py`
    
    This will automatically generate the data needed to create plots in the `./output/images` directory.
    
### Generating Plots

The code for generating plots is contained in the `plotting.py` file. This is writting using Python. Run the following command to generate the plots which will be stored in the `./output/images` directory.

`python3 plotting.py`
