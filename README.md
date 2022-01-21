# face-detection

### Dataset is not big! The quality of the finished model will be low!

#### Extracting control points to train the model:
python extract_embeddings.py --dataset dataset --embeddings output/embeddings.pickle --detector face_detection_model --embedding-model openface.nn4.small2.v1.t7

#### Train the model with extracted points:
python train_model.py --embeddings output/embeddings.pickle --recognizer output/recognizer.pickle --le output/le.pickle

#### Checking the model using images not participating in training:
python recognize.py --detector face_detection_model --embedding-model openface.nn4.small2.v1.t7 --recognizer output/recognizer.pickle --le output/le.pickle --image images\JaredLeto.jpg

#### Detecting faces from the webcam:
python recognize_video.py --detector face_detection_model --embedding-model openface.nn4.small2.v1.t7 --recognizer output/recognizer.pickle --le output/le.pickle
