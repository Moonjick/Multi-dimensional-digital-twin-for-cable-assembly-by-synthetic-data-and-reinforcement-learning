# Project README

## 1. Setting Up the Environment Using Anaconda
To create and activate a new Anaconda environment for your project, follow these steps:

```bash
# Create a new conda environment named 'ml-agent-env' with Python 3.8
conda create -n ml-agent-env python=3.8

# Activate the newly created environment
conda activate ml-agent-env

# Install Unity ML-Agent 0.28.0
pip install mlagents==0.28.0
```

### Important Note
Ensure that you are using the exact versions of `Numpy` (1.24.0) and `Protobuf` (3.20.0) to avoid compatibility issues with ML-Agent 0.28.0.
```bash
pip install numpy==1.24.0
pip install protobuf==3.20.0
```
### Additional Step
Install PyTorch compatible with your personal PC GPU:

Refer to the [PyTorch installation guide](https://pytorch.org/get-started/locally/) and install the appropriate version based on your GPU specifications.


## 2. Building the Unity Project
To build your Unity project for training:
1. Open your Unity project.
2. Go to **File > Build Settings**.
3. Add your main scene to the build by clicking **Add Open Scenes**.
4. Choose **PC, Mac & Linux Standalone** as the platform and set **Windows** as the target (or the appropriate platform).
5. Click **Build** and choose a directory to save the build (e.g., a folder named `build`).
6. Wait for the build process to complete.

## 3. Train the Model
To start training using the ML-Agent with a predefined configuration file and an environment, execute the following command:

```bash
cd "build path"
mlagents-learn "yaml file path" --env="build exe file path" --run-id="ID"
```

### Explanation of Command:
- `--num-envs []`: Utilizes four parallel environments for faster training.
- `--width [] --height []`: Sets the display resolution of the training environment.
- `--resume ["Run-id"]`: Resumes training from the last checkpoint if a previous training session with the same --run-id exists.
- `--time-scale []`: Adjusts the simulation speed, where N is the multiplier for the normal speed (useful for faster training).
- `--base-port []`: Specifies the starting port number for communication between the training process and environments (useful when running multiple training sessions).
- `--force`: Overwrites existing training results with the same --run-id if they exist.
- `--no-graphics`: Runs the environment in a non-graphical mode to save computation resources.
- `--inference`: Runs the environment in inference mode to test a trained model without updating it.

Follow these steps to successfully set up and train your model.

## Acknowledgement
This work is supported by Institute of information & communications Technology Planning & Evaluation (IITP) grant funded by the Korea government(MSIT) (No.RS-2022-00155911, Artificial Intelligence Convergence Innovation Human) Resources Development(Kyung Hee University)) 
