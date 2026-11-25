# KC-ML2-Take-Home-Project
## Topic: CV Classification and Quantization

This KC-ML2 take-home project trains a compact ResNet-34 on CIFAR-10 and evaluates the effect of INT8 post-training quantization (PTQ) on model size, CPU inference time, and test accuracy.

## Files
- [Experiment notebook](Take_Home_Project_INT8.ipynb) — data preparation, training curves, checkpoint selection, INT8 conversion, and evaluation.
- [Technical report](KC-ML2%20Technical%20Report.pdf) — experimental setup, results, and discussion.
- [Technical_report(part4)](KC-ML2%20Technical%20Report(Part%204).pdf) - 2 pages report addressing analysis of quantization

Note that
"Due to Google Colab usage limits, the output values in the report differ from those in the notebook."

## Run the notebook
1. Open the notebook in Google Colab. A T4 GPU can be used for training. Quantization and benchmarking run on the CPU.
2. Run the data preparation cells and authorize Google Drive access when prompted. The notebook downloads or reuses the CIFAR-10 cache under MyDrive/datasets/cifar10.
3. Run the remaining cells from top to bottom to train, load the best validation checkpoint, and compare FP32, Static INT8, and Dynamic INT8. To reproduce the saved calibration setup, pass train_set to the calibration DataLoader.
