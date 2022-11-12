## How to run our programs
---
There are two ways to run the notebooks in this folder:

   1. **Preferred**: Unzip in this folder and upload it onto Google Drive, after that all the code can be run without modification. Authorization to access Google Drive is required when mounting.
   2. **Alternative**:
      1. Download and unzip in this folder
      2. Remove all Google Drive mount code cells
      3. Adjust all the paths to the path where data is stored, e.g:
        ```python
        data_dir = pathlib.Path('/content/gdrive/MyDrive/CS4243/data')
        ```
      4. Run the code

This folder consists of 4 notebooks:
   * `project-resnet.ipynb`: Data preprocessing and transfer learning/finetuning of `ResNet50V2`.
   * `project-inception.ipynb`: Transfer learning of `Inception V3` (data pipeline is cut-and-paste from `project-resnet.ipynb`)
   * `project-simplecnn.ipynb`: Train a simple 3-layer CNN using same data pipeline as `project-resnet.ipynb`
   * `visualization.ipynb`: Visualize and inspect model deficiencies.

Input images are stored in the `data` subdirectory, classfied into `normal`, `threat` and `carrying` to utilize Tensorflow in-built preprocessing capability.

All trained models are saved in the `saved_models` subdirectory.
```python
def save_model(model, name):
  export_path = '/content/gdrive/MyDrive/CS4243/saved_models/{}-{}'.format(name, datetime.datetime.now().strftime("%Y%m%d-%H%M%S"))
  model.save(export_path)
```
Using the `save_model` function above, the trained model can be saved with a unique name as current datetime is padded.

