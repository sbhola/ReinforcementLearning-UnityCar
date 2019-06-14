# Train Donkey Car in Unity Simulator with Reinforcement Learning(Double-Q-Learning)

### Environment setup instructions for running Jupyter Notebook for Donkey Car Simulator Training


## Setup

You need to have [Unity](https://unity3d.com/get-unity/download) installed, and all python modules listed in the Requirements section below.

### Download Donkey Unity Environment
The Donkey Car simulator is created with Unity. There are 3 Unity scenes available (created by Tawn Kramer) for training now, which are generated roads, warehouse, and Sparkfun AVC. Before we run the RL training script, we have to either build the Donkey Car Unity environment ourselves (need to install Unity) or download the pre-built environment executables below:

Linux: [donkey.x86_64](https://drive.google.com/file/d/1p5Sn27o7YJC2SUBatCfUSlt9t-8xatDw/view?usp=sharing) | MacOS: [donkey.app](https://drive.google.com/drive/folders/1qfFkxlBy-nST3qcJzSQboVpIquzPHmsL?usp=sharing)

Then place the executable inside the `donkey_rl/src` folder. 

You need python 3.4 or higher, 64 bit. You can create a virtual env if you like:
```bash
virtualenv -p python3 env
source env/bin/activate
```
Install required dependencies:
```bash
pip install -r requirements.txt
```

This will install [Donkey Gym](https://github.com/tawnkramer/donkey_gym) and [Donkey Car](https://github.com/tawnkramer/donkey) packages from source.

If you have an cuda supported GPU - probably NVidia
```bash
pip install tensorflow-gpu
```


### Train Donkey car with Reinforcement Learning

- We have provided the DDQN algorithm in both jupyyter notebook(DonkeyCar.ipynb) and Python(ddqn.py). They will save the trained model in save_models folder.
- aws.h5 model is trained for 10,000 episodes on AWS. save_model.h5 is trained only for 100 episodes.
- Open the unity simulator while training/testing to see the progress run simulated on the unity simulator.
- If the script runs successfully, you should see some printouts in the command prompt with the training statistics (e.g. episode number, action, reward, etc). 
- Notice that by default a Unity GUI will be launched where you can see the Donkey car being trained. If you want to train in headless mode (i.e. no GUI), you can edit `donkey_rl/src/donkey_gym/donkey_gym/envs/donkey_env.py` and set `headless` flag to `True`.

### Testing out saved model

1) Start the prediction server with the pre-trained model.

```bash
cd sdsandbox/src
python predict_server.py --model ../save_model/aws.h5
```
2) Load the Unity project sdsandbox/sdsim in Unity. Double click on Assets/Scenes/main to open that scene.  

3) Hit the start button to launch. Then the "Use NN Steering".  
