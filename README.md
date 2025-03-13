# **Steering Large Language Models using Conceptors** 🛞
[![arXiv](https://img.shields.io/badge/arXiv-2406.09477-b31b1b.svg)](https://arxiv.org/abs/2410.16314)
This repository introduces a novel technique called "Conceptor-Based Activation Engineering," which we use to steer the behavior of a GPT-J-6B model. This method is inspired by recent advancements in activation engineering and steering techniques.

**Authors**: Joris Postmus, Steven Abreu

## Project Overview
In this project, we explore the application of Conceptors to manipulate and control the behavior of large language models, specifically GPT-J-6B. Our work builds upon recent discoveries in the field of activation engineering, and we present a series of experiments demonstrating the efficacy of this approach.

## Description of the data saved in this repository
- `./Mean_Activation_Vectors`: contains mean activation vectors (used for mean-centering).
- `./data/functionvectors/*.json` contains tasks from the function vector paper.

## Requirements
To run the experiments and reproduce the results, please follow these steps:

### 1. Set up Python environment
First, ensure you have the correct Python version installed on your system. This project has been tested and works with:
- Python 3.10.10 (recommended)
- Python 3.12

**Note**: The installation may not work properly with the latest Python versions. We recommend using Python 3.10.x for the best compatibility.

Then, create a virtual environment and activate it:
```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

### 3. Run the experiments
You can run the experiments using the Jupyter notebooks provided in the `src/colabs` folder. 

In order to batch-run all experiments and store the logs, you can use the `src/functionvectors/run_experiments.py` file. Please read the options available through:
```bash
cd src/functionvectors
python run_experiment.py -h
```

You can then run an experiment, e.g. with:
```bash
cd src/functionvectors
python run_experiment.py \
    --experiment-type=conceptor <additional-arguments>
```

You can optionally also set the cache directory for HuggingFace using:
```bash
export HF_HOME=/path/to/your/cache/directory
```

If you are working on a SLURM-managed cluster, you can use the `*.sh` scripts in the root directory to reproduce the experiments from our paper. If you are not working on a SLURM cluster, simply replace the `sbatch` command with `source`.

## Additional Notes
- Ensure that your environment is correctly set up with the recommended Python version to avoid installation issues.
- If you encounter any errors or have questions, please refer to the project documentation or contact the authors.

## Memory usage for different models
Function vector experiments:
- GPT-J-6B: 14GB of VRAM (RTX A6000).
