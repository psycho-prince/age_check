**Age Estimation with Caffe Model
This project implements an age estimation system using a pre-trained Caffe model, tested on the UTKFace and Adience datasets. It includes a Jupyter Notebook with a real-time webcam streaming interface using ipywidgets for face detection and age prediction.
Project Overview**

Objective: Estimate age from facial images using a Caffe-based deep learning model.
Model: Uses SSD for face detection (res10_300x300_ssd_iter_140000) and a Caffe age estimation model (age_net).
Datasets:
UTKFace: Labeled images with exact ages.
Adience: Images with age bins.

**
Features:
Real-time age prediction via webcam.
Batch accuracy testing across UTKFace and Adience datasets.
Mean Absolute Error (MAE) evaluation (~15.96 years on combined datasets).**



Requirements

Python 3.8+
Libraries:pip install opencv-python numpy matplotlib ipywidgets pandas


Jupyter Notebook:pip install jupyter jupyter_contrib_nbextensions
jupyter contrib nbextension install --user
jupyter nbextension enable --py --sys-prefix widgetsnbextension


Model files (place in models/):
deploy.prototxt
res10_300x300_ssd_iter_140000.caffemodel
age_deploy.prototxt
age_net.caffemodel


Datasets (place in project root):
UTKFace/ (extracted images)
Adience/ (extracted faces/ and fold_*.txt files)


Webcam for real-time streaming.

**Setup

Clone the Repository:git clone https://github.com/your-username/age_check.git
cd age_check


Install Dependencies:pip install -r requirements.txt

(Optional: Create requirements.txt with pip freeze > requirements.txt after installing libraries.)
Download Models:
Place model files in models/ directory.
Example: Download models (Update with your link if hosted).

**
Download Datasets:
UTKFace: Download
Adience: Download


Launch Jupyter Notebook:jupyter notebook



Usage

Open Notebook:
Open age_check.ipynb in Jupyter Notebook.


Run Cells:
Cell 0: Test ipywidgets functionality.
Cell 1: Load models and initialize webcam.
Cell 2: Define model utility functions for face detection and age prediction.
Cell 3: Run accuracy tests on UTKFace and Adience datasets.
Cell 4: Launch ipywidgets UI for webcam streaming and batch testing.


Accuracy Testing:
Click "Run Accuracy Test" in Cell 4 or run:print(run_accuracy_test(datasets={"UTKFace": "UTKFace", "Adience": "Adience"}, max_images=50, age_range=(15, 20)))




Webcam Streaming:
Click "Start Stream" in Cell 4 to predict ages in real-time.



Results

Mean Absolute Error: ~15.96 years on combined UTKFace and Adience datasets (varies by age range).
Improvements:
Test additional datasets (e.g., IMDB-WIKI, FG-NET).
Fine-tune confidence thresholds in get_faces and predict_age_caffe.
Explore deepface for single-year age predictions (requires Python 3.9).



Contributing

Fork the repository.
Create a feature branch:git checkout -b feature/your-feature


Commit changes:git commit -m "Add your feature"


Push to your fork:git push origin feature/your-feature


Open a pull request.

License
MIT License
Contact

GitHub: psycho-prince
Email: princephilip514@gmail.com
