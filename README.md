Age Estimation with Caffe Model
<!-- Replace with actual path if hosted elsewhere -->

This project implements an age estimation system using a pre-trained Caffe model, tested on the UTKFace and Adience datasets. It includes a Jupyter Notebook with a real-time webcam streaming interface using ipywidgets for face detection and age prediction.

🚀 Project Overview
🎯 Objective: Estimate age from facial images using a Caffe-based deep learning model.

🧠 Model:

Face Detection: SSD (Single Shot Detector) using res10_300x300_ssd_iter_140000

Age Estimation: Pre-trained Caffe model (age_net)

📊 Datasets:

UTKFace: Images labeled with exact ages

Adience: Images labeled with age ranges (bins)

🔧 Features
✅ Real-time webcam-based age prediction using ipywidgets

✅ Batch accuracy evaluation on UTKFace and Adience datasets

✅ MAE (Mean Absolute Error): ~15.96 years (combined datasets)

🛠️ Requirements
Python 3.8+

Libraries:

bash
Copy
Edit
pip install opencv-python numpy matplotlib ipywidgets pandas
Jupyter Notebook:

bash
Copy
Edit
pip install jupyter jupyter_contrib_nbextensions
jupyter contrib nbextension install --user
jupyter nbextension enable --py --sys-prefix widgetsnbextension
📁 Project Structure
bash
Copy
Edit
age_check/
├── models/
│   ├── deploy.prototxt
│   ├── res10_300x300_ssd_iter_140000.caffemodel
│   ├── age_deploy.prototxt
│   └── age_net.caffemodel
├── UTKFace/       # Dataset folder
├── Adience/       # Dataset folder
├── images/
│   └── age_demo.png  # Example prediction image
├── age_check.ipynb
└── requirements.txt
⚙️ Setup
Clone the Repo

bash
Copy
Edit
git clone https://github.com/your-username/age_check.git
cd age_check
Install Dependencies

bash
Copy
Edit
pip install -r requirements.txt
Download Models

Place the following files in models/:

deploy.prototxt

res10_300x300_ssd_iter_140000.caffemodel

age_deploy.prototxt

age_net.caffemodel

Download Datasets

UTKFace: Download here

Adience: Download here

Launch Notebook

bash
Copy
Edit
jupyter notebook
▶️ Usage
Open age_check.ipynb in Jupyter.

Run Cells sequentially:

Cell 0: Validate ipywidgets

Cell 1: Load models and initialize webcam

Cell 2: Define utility functions for face detection and age prediction

Cell 3: Evaluate accuracy using UTKFace and Adience

Cell 4: Interactive UI for real-time webcam and batch testing

Run Accuracy Test

python
Copy
Edit
print(run_accuracy_test(datasets={"UTKFace": "UTKFace", "Adience": "Adience"}, max_images=50, age_range=(15, 20)))
Webcam Streaming

Click "Start Stream" in Cell 4 to begin real-time prediction


![Webcam Age Detection Demo](images/age_demo.png)

📈 Results <p align="center">
  <img src="images/age_demo.png" alt="Webcam Age Detection Demo" width="400"/>
</p>

Mean Absolute Error: ~15.96 years (combined dataset)

Note: Accuracy varies by age group and image quality

🧪 Potential Improvements
Use additional datasets like IMDB-WIKI, FG-NET

Optimize age binning and thresholds

Fine-tune get_faces() and predict_age_caffe() confidence levels

Consider deepface for more granular (year-wise) predictions

🤝 Contributing
Fork the repo

Create a new branch:

bash
Copy
Edit
git checkout -b feature/your-feature
Commit and push:

bash
Copy
Edit
git commit -m "Add your feature"
git push origin feature/your-feature
Open a Pull Request

📄 License
This project is licensed under the MIT License.

📬 Contact
GitHub: psycho-prince

Email: princephilip514@gmail.com

