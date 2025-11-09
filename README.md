# Plant Disease Detection

This repository contains an image classification project for identifying plant diseases from leaf images. It includes training notebooks, a trained Keras model (`trained_model.h5`), and a simple Streamlit app (`app.py`) for running predictions from uploaded images.

## Contents

- `training_model.ipynb` — Notebook used to train the model.
- `test_plant_disease.ipynb` — Notebook with utilities for evaluating the model on the `test/` folder.
- `trained_model.h5` — Pretrained Keras model used by the Streamlit app.
- `app.py` — Streamlit application to upload an image and get predictions.
- `train/`, `valid/`, `test/` — Dataset folders (organized by class subfolders).
- `requirements.txt` — Python dependencies.

## Quickstart (run the Streamlit app)

1. Create a Python virtual environment (recommended):

```bash
python -m venv .venv
source .venv/bin/activate
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Start the Streamlit app:

```bash
streamlit run app.py
```

The app opens in your browser. Use the **Disease Recognition** page to upload a leaf image and view top predictions.

## Project details

- Image size used for the model: 128x128 (RGB).
- The app expects the model file `trained_model.h5` in the repository root. If you use a different path, update `app.py` accordingly.
- Preprocessing: images are resized to 128x128, converted to RGB, and pixel values normalized to [0, 1].

## Dataset structure

The dataset is organized into three top-level folders with subfolders per class:

```
train/
	<class_1>/
	<class_2>/
	...
valid/
	<class_1>/
	<class_2>/
	...
test/
	<class_1>/
	<class_2>/
	...
```

There are ~38 classes in the project (e.g. `Apple___healthy`, `Tomato___Late_blight`, etc.). See `app.py` for the exact ordering used to map model outputs to class names.

## Notebooks

- `training_model.ipynb` contains the model architecture, training pipeline, and augmentation. It uses Keras / TensorFlow.
- `test_plant_disease.ipynb` shows how to load the saved model and create a test dataset with `tf.keras.utils.image_dataset_from_directory`.

## Troubleshooting

- If the app crashes with import errors (e.g. `streamlit`, `tensorflow`, `PIL`), make sure you installed the packages from `requirements.txt` into the active environment.
- If the model fails to load, confirm `trained_model.h5` exists at the repository root and is compatible with the installed TensorFlow version.
- If predictions are wrong/unexpected, verify the preprocessing used during training (rescaling, center-crop, normalization). Adjust `preprocess_image` in `app.py` to match training preprocessing.

## Extending

- To show class labels instead of indices, edit `class_list()` in `app.py`.
- To support batching / bulk predictions, adapt the notebooks to read directories and call `model.predict` on batches.

## License

Add your preferred license information here.

---

If you'd like, I can:
- Add a short `README` badge and usage examples.
- Generate a `CONTRIBUTING.md` with contribution guidelines.
- Add a small script to list class counts from the `train/` folder.

Tell me which of those you'd like next.