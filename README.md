# Digital Pathology Benchmarking

CENG 4391 research at the University of Houston–Clear Lake, by Hozaif Awan. This project studies a PatchCamelyon (PCam) classification workload and its performance across compute architectures.

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/HozaifAwan/digital-pathology-benchmarking/blob/main/HC_Digital_Pathology_Experiment_01.ipynb)

## Current results

- Fine-tuned an ImageNet-pretrained ResNet18 with PyTorch and CUDA on an NVIDIA Tesla T4.
- Used 8,192 training patches and 2,048 held-out validation patches; achieved **82.81% validation accuracy** after three epochs.
- Completed an FP32 T4 inference baseline over 1,024 fixed validation images, testing batch sizes from 1 to 1,024 with 20 warm-up iterations and 50 measured trials.
- Recorded median and p95 latency, throughput, GPU memory, and host/device transfer overhead. The measured throughput peaked at approximately **5,210 images/second at batch size 256** for this benchmark configuration.
- Apple Silicon MPS comparison and architecture-aware optimization remain planned; cross-architecture benchmarking is ongoing.

Results describe this notebook and hardware configuration, rather than general performance guarantees.

## Notebook and data

`HC_Digital_Pathology_Experiment_01.ipynb` contains the data preparation, training, saved outputs, and CUDA benchmarking workflow. The notebook uses Python, PyTorch, NumPy, HDF5/h5py, and Google Colab.

PCam dataset files and trained checkpoints are not stored in this repository. Follow the notebook setup cells, select a T4 GPU runtime when available, and configure the Google Drive paths for your own dataset and checkpoint. Run the training cells to produce a checkpoint before running the benchmark cells that load it. Colab GPU availability can vary.

## Save future work to GitHub

1. Open the notebook in Colab and make your changes.
2. Choose **File → Save a copy in GitHub**.
3. Select `HozaifAwan/digital-pathology-benchmarking`, branch `main`, and the same notebook filename.
4. Write a short message describing the actual change and save.

Each GitHub save creates a commit. Regular Colab autosaves save to Google Drive and do not automatically create GitHub commits. Save meaningful revisions after each work session to keep the repository and contribution history up to date.
