# MNIST Digit Classification

A fully connected neural network, built with Keras, that classifies handwritten digits (0–9) from the [MNIST dataset](https://en.wikipedia.org/wiki/MNIST_database).

All of the work lives in a single Jupyter notebook: [`MNIST Digit Clasification.ipynb`](MNIST%20Digit%20Clasification.ipynb).

## What the notebook does

1. **Loads the data** – 60,000 training images and 10,000 test images (28×28 greyscale) via `keras.datasets.mnist`.
2. **Visualises examples** – plots one sample of each digit class.
3. **Prepares the data**
   - One-hot encodes the labels with `keras.utils.to_categorical`
   - Normalises pixel values from `0–255` to `0–1`
   - Flattens each image from `28×28` to a 784-length vector
4. **Builds the model** – a simple feed-forward network:

   | Layer   | Output shape | Activation | Params  |
   |---------|--------------|------------|---------|
   | Dense   | 128          | ReLU       | 100,480 |
   | Dense   | 128          | ReLU       | 16,512  |
   | Dropout | 128 (rate 0.25) | –       | 0       |
   | Dense   | 10           | Softmax    | 1,290   |

   **Total parameters:** 118,282. Optimiser: Adam.
5. **Trains** for 10 epochs with a batch size of 512.
6. **Evaluates** on the held-out test set and generates predictions.
7. **Shows a single example** – picks a random test image and displays it with the predicted and true labels.

## Results

| Metric        | Value  |
|---------------|--------|
| Test accuracy | ~97.8% |
| Test loss     | ~0.072 |

## Getting started

### Requirements

- Python 3.12 (tested; use a version TensorFlow supports)
- Jupyter (Notebook or Lab)
- `keras` (Keras 3, with the TensorFlow backend)
- `tensorflow`
- `numpy`
- `matplotlib`
- `scikit-learn`
- `seaborn`

### Installation

```bash
git clone https://github.com/Scereweir61/MNIST-Digit-Classification.git
cd MNIST-Digit-Classification
pip install tensorflow keras numpy matplotlib scikit-learn seaborn jupyter
```

### Running

```bash
jupyter notebook "MNIST Digit Clasification.ipynb"
```

Then run the cells in order (**Kernel → Restart & Run All**). The MNIST dataset downloads automatically the first time it runs.

## Project status

Work in progress:

- [ ] Add a confusion matrix to see which digits get confused with each other

## License

No license has been chosen yet.
