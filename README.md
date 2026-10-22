# Medicine Strip Recognition using Deep Learning

Identifying a medicine from a photo of its strip, so pharmacy billing and stock-keeping don't depend on reading small print by hand.

Final-year B.Tech project (Computer Science and Engineering, AI & ML) at Presidency University, Bengaluru, completed in January 2024 by a team of four: Erina Rifa, Anuj M, Harshid P and Muhammed Jasbin K, under the guidance of Dr. Murali Parameswaran. The work was published in the *International Journal of Creative Research Thoughts* (IJCRT, Volume 12, Issue 1, January 2024).

## What's here

| Path | What it is |
|---|---|
| [`code/backend.ipynb`](code/backend.ipynb) | Training and prediction notebook (TensorFlow / Keras) |
| [`code/ezyzip/`](code/ezyzip) | Front-end mock-up: upload or capture a photo and see the result |
| `PROJECT REPORT final.pdf` | Full project report: literature survey, method, design and discussion |
| `REVIEW_1[CAI-G05]*.pptx` | Project review presentations |

## How it works

1. **Data:** photos of medicine strips, organised into one folder per medicine. The model covers 17 medicines, including Dolo-650, Nicip Plus, Okacet, Rantac 150 and Zeroder-MR.
2. **Preprocessing:** images resized to 224 × 224 and scaled to 0–1. Training images are augmented with shear, zoom and horizontal flips so the model copes with different angles and framing.
3. **Model:** a convolutional neural network built from scratch: three convolution and max-pooling blocks (32, 64 and 128 filters), a 128-unit dense layer and a 17-way softmax. Trained with Adam and categorical cross-entropy for 10 epochs.
4. **Prediction:** a new photo goes through the same preprocessing, and the class with the highest probability is returned as the medicine name.

## Run the notebook

```bash
pip install tensorflow numpy
jupyter notebook code/backend.ipynb
```

Point `train_dir` and `validation_dir` at your own image folders (one sub-folder per medicine) and `image_path` at a test photo.

## Limitations

- Only part of the dataset is published: the [`dataset`](https://github.com/anuj1102001/MEDICINE-STRIP-RECOGNITION/tree/dataset) branch has 100 photos covering 7 of the 17 medicines. The notebook has no saved outputs, so accuracy can't be reproduced from the repository alone.
- The front-end is a mock-up: its buttons show a placeholder result and aren't connected to the model.
- The notebook uses absolute local paths from the original training machine.

## Tech

Python · TensorFlow / Keras · CNN · image augmentation · HTML, CSS, JavaScript
