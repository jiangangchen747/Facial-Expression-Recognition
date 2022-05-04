## Steps
1. Download Fer2013 dataset and the Face Landmarks model

    - [Kaggle Fer2013 challenge](https://www.kaggle.com/c/challenges-in-representation-learning-facial-expression-recognition-challenge/data)
    - [Dlib Shape Predictor model](http://dlib.net/files/shape_predictor_68_face_landmarks.dat.bz2)

2. Unzip the downloaded files

    And put the files `fer2013.csv` and `shape_predictor_68_face_landmarks.dat` in the root folder of this package.

3. 

4. Convert the dataset to extract Face Landmarks and HOG Features

    ```
    python convert_fer2013_to_images_and_landmarks.py
    ```

    You can also use these optional arguments according to your needs:
    `-j`, `--jpg` (yes|no): **save images as .jpg files (default=no)**
    `-l`, `--landmarks` *(yes|no)*: **extract Dlib Face landmarks (default=yes)**
    `-ho`, `--hog` (yes|no): **extract HOG features (default=yes)**
    `-hw`, `--hog_windows` (yes|no): **extract HOG features using a sliding window (default=yes)**
    `-o`, `--onehot` (yes|no): **one hot encoding (default=no)**
    `-e`, `--expressions` (list of numbers): **choose the faciale expression you want to use: *0=Angry, 1=Disgust, 2=Fear, 3=Happy, 4=Sad, 5=Surprise, 6=Neutral* (default=0,1,2,3,4,5,6)**

    Example
    ```
    python convert_fer2013_to_images_and_landmarks.py --landmarks=yes --hog=no --how_windows=no --jpg=no --onehot=no --expressions=1,3,4
    ```

5. Train the model

    ```
    python train.py --train=yes
    ```

6. Evaluate the model

    If you have already a pretrained model

    ```
    python train.py --evaluate=yes
    ```

7. Train and evaluate [instead of step 5 and 6]

    ```
    python train.py --train=yes --evaluate=yes 
    ```

8. Customize the training parameters:

    Feel free to change the values of the parameters in the `parameters.py` file according to your needs.

9. Find the best hyperparameters (using hyperopt):

    ```
    python optimize_parameters.py --max_evals=15
    ```
    The argument `max_evals` specifies the number of combinaisions hyperopt will try.
    After finding the best hyperparameters, you should change the corresponding values in `parameters.py` and retrain the model.
    N.B: the accuracies displayed during hyperoptimization are for validation_set only (not test_set)
    
## Contributing

Some ideas for interessted contributors:
- Add other features extraction techniques?
- Predict expression from a .jpg|.png file?
