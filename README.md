# CartanFM: Symmetric Space Learning for Combinatorial Generalization

This repository contains the official implementation of **CartanFM**, as introduced in the paper:

> **[Symmetric Space Learning for Combinatorial Generalization](https://openreview.net/forum?id=e8t9F4vX9N)**<br>
> Jaehyoung Jeong, Hee-Jun Jung, and Kangil Kim<br>
> *The Fourteenth International Conference on Learning Representations (ICLR 2026)*

## Overview
CartanFM introduces a novel approach to combinatorial generalization by leveraging symmetric space learning and optimal transport flow matching with cycle consistency (`OTFlowMatchingCycleConsistency`). 

## Installation

Create a python environment and install the dependencies listed in `requirements.txt`:

```bash
pip install -r requirements.txt
```

### Main Requirements
- `torch>=1.9.0`
- `torchvision>=0.10.0`
- `numpy>=1.21.0`
- `wandb>=0.12.0` (Optional, for logging)
- `matplotlib>=3.3.0`
- `Pillow>=8.0.0`

## Usage

The `main.py` script serves as the primary entry point for configuring, training, and testing the CartanFM model.

### Training

To start training the model, simply run:

```bash
python main.py --train
```

If you have Weights & Biases (`wandb`) installed and properly set up, logging will be automatically configured based on your settings. The training script will save the checkpoints to the automatically generated output directory.

### Testing

To evaluate a trained model, use the `--test` flag:

```bash
python main.py --test --model_path path/to/your/cartanfm_checkpoint.pt
```

If you omit the `--model_path` argument, the script will automatically attempt to locate and load the latest trained checkpoint from the output directory.

## Repository Structure

- `main.py`: Main executable for training and evaluation.
- `models/`: Contains model architectures including `CartanFM` and ablation models.
- `source/`: Contains core source codes and lie algebra implementations (`LieBasisModule_GeneralCartan`).
- `data/`: Data loading pipelines and preprocessing scripts.
- `training/`: Functions handling the training loop, validation, wandb integration, and testing.
- `utils/`: Helper functions such as argument parsing, config setup, and seed initialization.
- `cartan_sphere_clean.ipynb`: A clean Jupyter notebook illustrating the operations and evaluations on the Cartan sphere.

## Citation

If you find this code or our paper useful in your research, please consider citing:

```bibtex
@inproceedings{
jeong2026symmetric,
title={Symmetric Space Learning for Combinatorial Generalization},
author={Jaehyoung Jeong and Hee-Jun Jung and Kangil Kim},
booktitle={The Fourteenth International Conference on Learning Representations},
year={2026},
url={https://openreview.net/forum?id=e8t9F4vX9N}
}
```
