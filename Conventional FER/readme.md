## Steps
1. Download Fer2013 dataset and the Face Landmarks model
    - [Kaggle Fer2013 challenge](https://www.kaggle.com/c/challenges-in-representation-learning-facial-expression-recognition-challenge/data)
    - [Dlib Shape Predictor model](https://github.com/italojs/facial-landmarks-recognition/blob/master/shape_predictor_68_face_landmarks.dat)
2. Unzip the downloaded files
    And put the files `fer2013.csv` and `shape_predictor_68_face_landmarks.dat` in the root folder of this package.
3. Install the required packages in 'requirements.txt'.
4. Convert the dataset to extract Face Landmarks and HOG Features
    python convert_fer2013_to_images_and_landmarks.py --landmarks=yes --hog=no --how_windows=no --jpg=no --onehot=no --expressions=1,3,4
5. Train and evaluate
    python train.py --train=yes --evaluate=yes 
8. Customize the training parameters:
    Feel free to change the values of the parameters in the `parameters.py` file according to your needs.
9. Find the best hyperparameters (using hyperopt):
    python optimize_parameters.py --max_evals=15
