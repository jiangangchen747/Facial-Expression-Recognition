# Steps

1. Install the required packages in 'requirements.txt'.
2. For testing ESR on image, video or webcam, run following commands.

    image: python main_esr9.py image -i ./test.jpg -d -s 2 -c

    video: python main_esr9.py video -i ./media/big_bang.mp4 -d -f 15 -s 2 -fd 3 -c

    webcam: python main_esr9.py webcam -d -s 2 -b -fd 3 -w 0 -c
4. Testing on CK+, run the 'main_ck_plus.py' script. The images in the CK+ must be pre-processed including cropping the face and rescaling to 96x96 pixels.
5. Testing on AffectNet,  run the 'main_affectnet_discrete.py' script. Call the method 'pre_process_affect_net(base_path_to_images, base_path_to_annotations)' from ./model/utils/udata.py. The images will be cropped (to get the face only), re-scaled to 96x96 pixels, and renamed to follow the pattern "[id][emotion_idx][valence times 1000]_[arousal times 1000].jpg".
6. Testing on Fer+, run the script 'main_fer_plus.py' script. set the experimental variables including the base path to the dataset (base_path_to_dataset = "./FER_2013/Dataset/").
