# Character-Level Text Prediction

## Overview
This repository trains and compares three recurrent neural network architectures, a Simple RNN, a GRU, and a two-layer LSTM, for next-character prediction on text. Each architecture is evaluated in two configurations, a baseline and a variant augmented with a self-attention layer, for six models in total. All work is implemented in Python (TensorFlow/Keras) inside a single Jupyter notebook that trains every variant, saves their weights and training histories, and reproduces all figures, tables, and text-generation results.

## Repository Structure
* `Character-LevelTextPrediction.ipynb`: Notebook with all preprocessing, model definitions, training, evaluation, figures, and text generation.
* `Character-Level Text Prediction Report.pdf`: Final written report.
* `Data/`: Saved model artifacts.
  * `Weights/`: Trained weights for the six models (`rnn`, `gru`, `lstm` × `baseline`, `attention`) as `.weights.h5` files.
  * `Histories/`: Per-model training histories (`history_*.h5`) for redrawing the loss/accuracy curves without retraining.
* `tinyshakespeare.txt`: Input text corpus used for training and evaluation.
* `requirements.yml`: Conda environment specification.
* `LICENSE`: MIT license.

## Getting Started

### 1. Clone the repository
```
git clone https://github.com/JRodriguezToledo/Character-LevelTextPrediction.git
cd Character-LevelTextPrediction
```

### 2. Create and activate the environment with Conda
Make sure you have [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://docs.anaconda.com/anaconda/install/) installed. Create the environment from `requirements.yml`:
```
conda env create -f requirements.yml
conda activate machine-learning
```
The notebook needs Python 3.12+ with `tensorflow` (Keras), `numpy`, `matplotlib`, and `h5py`.

### 3. Run the analysis
The corpus `tinyshakespeare.txt` is already included, so no download step is required. Launch Jupyter and open the notebook:
```
jupyter notebook Character-LevelTextPrediction.ipynb
```
Then choose **Kernel → Restart & Run All** to execute every section in order, regenerating the trained weights, training histories, figures, and text-generation samples. Pre-trained weights and histories are provided under `Data/` so the figures can be reproduced without retraining (the notebook loads them by filename from the working directory).

> **Reproducibility:** A fixed seed (`5721`) is set via `random.seed`, `np.random.seed`, and `tf.random.set_seed`. Minor numerical differences may still occur due to non-deterministic GPU/CUDA operations, and text generation is stochastic, so generated samples vary between runs.

## Citation
If you use this repository, please cite as follows:
```
@misc{CharacterLevelTextPrediction2026,
  author       = {Jorge Rodríguez Toledo},
  title        = {Character-Level Text Prediction},
  year         = {2026},
  howpublished = {\url{https://github.com/JRodriguezToledo/Character-LevelTextPrediction}}
}
```
