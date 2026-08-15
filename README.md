# Comparative Deep Learning Evaluation for Underwater Trash Detection

This repository contains the computing artefact developed for an MSc Data Science dissertation evaluating deep learning object detection approaches for underwater trash detection.

## Project Overview

The project implements a comparative evaluation framework for three object detection architectures:

- Faster R-CNN
- YOLOv8n
- YOLOv10n

The models are evaluated using the TrashCan 1.0 underwater marine debris benchmark dataset.

The purpose of the framework is to provide a standardised evaluation process, as far as possible, for comparing the detection performance and computational efficiency of the selected architectures.

## Dataset

The project uses the TrashCan 1.0 benchmark dataset.

The original dataset contains 22 annotated classes. During preprocessing, these were aggregated into three broader categories:

- Trash
- Bio
- ROV

The mapping followed the following rules:

- Categories beginning with `trash_` → Trash
- Categories beginning with `animal_` and `plant` → Bio
- `rov` → ROV

The dataset itself is not redistributed through this repository and should be obtained from its original source.

## Dataset Partitioning

The official TrashCan 1.0 training data was divided into:

- 90% training
- 10% validation

The official validation set was retained as the independent test set.

A random seed of 42 was used to make the training-validation partition reproducible.

## Models

The following models were evaluated:

### Faster R-CNN
Implemented using PyTorch and Torchvision.

### YOLOv8n
Implemented using the Ultralytics framework.

### YOLOv10n
Implemented using the Ultralytics framework.

## Evaluation Metrics

Model performance was evaluated using:

- mAP@0.5
- mAP@0.5:0.95
- Precision
- Recall
- Inference time
- Frames per second (FPS)

Both quantitative metrics and qualitative prediction examples were used to assess model performance.

## Repository Structure

`notebooks/`
Contains the Google Colab/Jupyter notebook used for dataset preprocessing, model training and evaluation.

`results/`
Contains the final quantitative results produced during evaluation.

`figures/`
Contains selected quantitative visualisations and qualitative prediction examples.

## Reproducibility

The notebook contains the preprocessing, class mapping, dataset partitioning, training and evaluation procedures used in the dissertation.

Users wishing to reproduce the experiments must obtain the TrashCan 1.0 dataset separately and update the dataset paths within the notebook for their local or Google Colab environment.

## Academic Context

This repository accompanies an MSc Data Science dissertation investigating the comparative performance of Faster R-CNN, YOLOv8n and YOLOv10n for underwater trash detection.

The repository is provided to support transparency and reproducibility of the experimental methodology.
