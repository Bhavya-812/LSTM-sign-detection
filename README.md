This is a LSTM-based model for sign language detection project effectively captures the temporal dependencies in hand gesture sequences, allowing for accurate recognition of sign language gestures in real-time. This project utilizes various scripts to collect data, preprocess it, train a deep learning model for sign language detection, and finally deploy the trained model in a real-time application for gesture recognition. Each script plays a crucial role in different stages of the project, contributing to the overall functionality of the sign language detection system.

Complete Architecture of the Project:
1.	Data Collection:
        •	Hand gestures are collected using a webcam and saved as image sequences corresponding to different gestures (A-Z).
2.	Data Preprocessing:
        •	Keypoints are extracted from the hand landmarks detected in the images using MediaPipe.
        •	Keypoints sequences are processed and saved as NumPy arrays, representing the temporal aspect of gestures.
3.	Model Training:
        •	The LSTM-based deep learning model is constructed and trained using the processed data.
        •	The model learns to recognize sign language gestures based on the sequential patterns in the input sequences of keypoints.
4.	Real-Time Detection:
        •	The trained model is deployed in an application that captures live video frames from a webcam.
        •	Hand landmarks are detected in real-time using MediaPipe, and sequences of keypoints are fed into the trained model.
        •	The model predicts the gesture being performed, and the results are displayed on the screen along with their probabilities.

LSTM Layers:

1.	First LSTM Layer (LSTM(64)):
        •	Units: 64
        •	Activation Function: ReLU
        •	Input Shape: (80, 63) (80 timesteps, 63 features)
        •	Return Sequences: True
        
2.	Second LSTM Layer (LSTM(128)):
        •	Units: 128
        •	Activation Function: ReLU
        •	Return Sequences: True
  	
3.	Third LSTM Layer (LSTM(64)):
        •	Units: 64
        •	Activation Function: ReLU
        •	Return Sequences: False

Dense Layers:

1.	First Dense Layer (Dense(64)):
        •	Units: 64
        •	Activation Function: ReLU

2.	Second Dense Layer (Dense(32)):
        •	Units: 32
        •	Activation Function: ReLU

3.	Output Dense Layer (Dense(3)):
•	Units: 3 (Number of classes or gestures)
•	Activation Function: Softmax

Trained Model:

1.	Model Configuration:
        •	Architecture: Sequential
        •	Input Shape: (80, 63) (80 timesteps, 63 features)
        •	Loss Function: Categorical Crossentropy
        •	Optimizer: Adam
        •	Metrics: Categorical Accuracy
        •	Training Epochs: 200
  	•       Test Train Split: 80 20
