# Face Recognition Attendance System

This project implements a real-time face recognition attendance system using DeepFace for face embedding extraction and a Support Vector Machine (SVM) classifier for identity recognition. It includes functionality for image augmentation, training, and logging attendance in an Excel file based on live webcam input.

## Features

- Image augmentation using Keras `ImageDataGenerator`
- Face embedding extraction using DeepFace with the Facenet model
- SVM-based identity classification with scikit-learn
- Real-time face recognition using OpenCV and webcam
- Attendance logging to `attendance.xlsx`
- Prevents duplicate attendance entries per person per day

## Requirements

Install the required Python packages:

```bash
pip install opencv-python deepface scikit-learn tensorflow pandas numpy
Ensure that your system has a webcam and supports OpenCV.

Project Structure
graphql
Copy
Edit
project/
├── attendance.xlsx         # Automatically created after attendance is logged
├── svm_model.pkl           # Saved trained SVM model
├── label_dict.pkl          # Dictionary mapping labels to names
├── main.py                 # Main Python script
├── README.md               # Project documentation
└── Facial Dataset/         # Folder containing images organized in subfolders by person
    ├── Person1/
    │   ├── image1.jpg
    │   └── ...
    └── Person2/
        └── ...
How to Use
Prepare the dataset:

Create a directory named Facial Dataset.

Inside it, create one subfolder per individual (e.g., John_Doe/, Jane_Doe/) containing facial images.

Update the dataset path:
In the main() function of main.py, update the folder path accordingly:

python
Copy
Edit
folder_path = r"F:\\Facial Dataset"
Run the script:
Execute the following command:

bash
Copy
Edit
python main.py
System workflow:

Preprocesses and augments dataset images

Extracts embeddings from each image

Trains an SVM classifier on embeddings

Starts real-time face recognition via webcam

Logs attendance to attendance.xlsx

Notes
The system uses DeepFace's Facenet model for embedding extraction.

You can adjust the confidence threshold for recognition (default is 0.6) in the real_time_attendance() function.

Attendance is recorded only once per individual per day to avoid duplicates.

Author
Muhammad Muzammil
BlackAlpha-debug
mj.muzammiljawad@gmail.com
