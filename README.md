# Plant Disease Detection

This project identifies plant diseases from leaf images using a trained Keras model and a Streamlit web app.

## Contents
- `training_model.ipynb` — Model training notebook  
- `test_plant_disease.ipynb` — Model testing and evaluation notebook  
- `trained_model.h5` — Trained Keras model  
- `app.py` — Streamlit app for predictions  
- `train/`, `valid/`, `test/` — Dataset folders  
- `requirements.txt` — Dependencies list  

## How to Run

1. **Create a virtual environment**
   ```bash
   python -m venv .venv
   source .venv/bin/activate
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the Streamlit app**
   ```bash
   streamlit run app.py
   ```

Then open the link shown in the terminal (usually http://localhost:8501).

## Model Info
- Input image size: **128x128 RGB**  
- Pixel values are normalized to [0, 1]  
- Model file: `trained_model.h5` (must be in the project root)

## Dataset Structure
```
train/
    <class_1>/
    <class_2>/
valid/
    <class_1>/
    <class_2>/
test/
    <class_1>/
    <class_2>/
```
Around 38 plant classes (e.g. `Apple___healthy`, `Tomato___Late_blight`, etc.).

## Notes
- Make sure all dependencies are installed in the same environment.  
- If the app fails to load the model, check that `trained_model.h5` exists in the project root.  
- Update preprocessing in `app.py` if you used different image scaling during training.
