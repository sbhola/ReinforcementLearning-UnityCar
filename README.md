# Environment setup instructions for running Jupyter Notebook for Donkey Car Simulator Training

The following sequence of steps are to be followed to setup the environment for running donkey car simulator either on cloud or on local machine.

Create new conda environment with python:  
- conda create -n donkeygym python

- pip install gym

- pip install --upgrade pip

- pip install tensorflow

- pip install keras

- conda install scikit-learn

- pip install pillow

- conda install -c conda-forge opencv
 
- pip install scikit-image

- conda install -c conda-forge jupyter

- git clone https://github.com/sbhola/ReinforcementLearning-UnityCar.git

- cd donkey_rl/src/donkey_gym

- pip install -e .