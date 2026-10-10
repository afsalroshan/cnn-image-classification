# Building a CNN Model for Image Classification

## Project Overview
This project builds a Convolutional Neural Network (CNN) to classify images into six categories using TensorFlow and Keras. The notebook covers data exploration, image preprocessing, model development, and evaluation.

## Dataset
The project uses the Intel Image Classification dataset, organized into six categories:

- Buildings
- Forest
- Glacier
- Mountain
- Sea
- Street

The notebook expects the training and test folders to follow this structure:

```text
dataset/
├── seg_train/
│   └── seg_train/
│       ├── buildings/
│       ├── forest/
│       ├── glacier/
│       ├── mountain/
│       ├── sea/
│       └── street/
└── seg_test/
    └── seg_test/
        ├── buildings/
        ├── forest/
        ├── glacier/
        ├── mountain/
        ├── sea/
        └── street/
```

Obtain the dataset from the original dataset source or the source specified by your course. The dataset is not included in this repository.

## Technologies Used
- Python
- TensorFlow and Keras
- NumPy
- Matplotlib
- Seaborn
- scikit-learn
- Google Colab

## Project Structure

```text
cnn-image-classification/
├── README.md
├── requirements.txt
└── cnn_image_classification.ipynb
```

## Methodology

### 1. Data Understanding and Preprocessing
- Explore the six image classes and visualize sample images.
- Resize images to 150 × 150 pixels.
- Normalize pixel values to the range 0–1.
- Set the batch size to 32.
- Split the training data into training and validation subsets using an 80/20 split.
- Apply image augmentation, including rotation, width and height shifts, zoom, and horizontal flipping.

### 2. CNN Model Development
The Sequential CNN architecture consists of:
- Four convolutional layers with ReLU activation.
- Max-pooling layers for dimensionality reduction.
- A flatten layer.
- A dense layer with 512 units.
- A dropout layer with a rate of 0.5.
- A six-unit softmax output layer.

The model uses the Adam optimizer, categorical cross-entropy loss, and accuracy as its evaluation metric. Early stopping and model checkpointing help manage training.

### 3. Model Evaluation
The model is evaluated using:
- Test loss and test accuracy.
- Training and validation accuracy plots.
- Training and validation loss plots.
- Classification report with precision, recall, F1-score, and support.
- Confusion matrix.
- Sample predictions compared with actual labels.

## Results

The recorded notebook results are:

| Metric | Result |
|---|---:|
| Test accuracy | 87.43% |
| Test loss | 0.3685 |
| Test images | 3,000 |
| Classes | 6 |

The classification report shows an overall accuracy of approximately 87%.

Results may vary when retraining the model because of random initialization, data shuffling, and differences in the training environment.

## How to Run

### Using Google Colab
1. Open `cnn_image_classification.ipynb` in Google Colab.
2. Upload the dataset to Google Drive or download it from the appropriate source.
3. Update `train_dir` and `test_dir` to match the dataset locations.
4. Run the notebook cells in order.

### Using a Local Python Environment
1. Install Python.
2. Install the dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Update the dataset paths in the notebook.
4. Replace the Google Colab-specific Drive mounting code if running locally.
5. Run the notebook using Jupyter Notebook or JupyterLab.

## Notes
- The dataset is not included because of its size.
- The best model checkpoint is saved as `best_model.keras` in the notebook's working directory.
- Ensure that the dataset folder structure and paths are correct before training.

## Author
Afsal E.
