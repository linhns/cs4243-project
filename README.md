## How to run our programs
There are two ways to run the notebooks in this folder:

   1. **Preferred**: 
      1. Unzip in this folder and upload it onto Google Drive
      2. Download data according to the section *Download data* below and put it in the same folder as the code
      3. Run the code. Authorization to access Google Drive is required when mounting.
   2. **Alternative**:
      1. Download and unzip in this folder
      2. Create a conda environment according to `environment.yml`
      3. Download data according to the section *Download data* below and put it in the same folder as the code
      4. Remove all Google Drive mount code cells
      5. Adjust all the paths to the path where data is stored, e.g:
          ```python
          data_dir = pathlib.Path('/content/gdrive/MyDrive/CS4243/data')
          ```
      6. Run the code

This folder consists of 4 notebooks:
   * `project-resnet.ipynb`: Data preprocessing and transfer learning/finetuning of `ResNet50V2`.
   * `project-inception.ipynb`: Transfer learning of `Inception V3` (data pipeline is cut-and-paste from `project-resnet.ipynb`)
   * `project-simplecnn.ipynb`: Train a simple 3-layer CNN using same data pipeline as `project-resnet.ipynb`
   * `visualization.ipynb`: Visualize and inspect model deficiencies.

Trained models are available from https://drive.google.com/drive/folders/1lKvco8M4nsq1ChyirGbFB1TBdHyhjUHt?usp=sharing

### Download data
Data can be downloaded from https://drive.google.com/drive/folders/1n7yLSLjhXeUHMOcfPb2Nq57xVh3RjgiZ?usp=sharing

Input images are stored in the `data` subdirectory, classfied into `normal`, `threat` and `carrying` to utilize Tensorflow in-built preprocessing capability.
