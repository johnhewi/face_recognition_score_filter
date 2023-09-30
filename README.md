# Face Recognition Score Filter
This tool allows the user to create a facial recognition model from a set of images. The model can then be used to analyze another set of images and score each photo on its similarity to the model. The list of scores can then be used to filter the image files by score.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/johnhewi/face_recognition_score_filter/blob/main/ImageScore.ipynb#scrollTo=wW0_c0MnYbDG)

### 1. Create a model using [face_recognition](https://pypi.org/project/face-recognition/)

Create a facial recognition model from a set of photos. (If you already have a .npy file you'd like to use, you can skip this step) You will need to enter the path to the folder that contains the images you want to use to train your facial recognition model. Additionally, you will need to select the path to the folder where you want the model to be stored. Finally, you must pick a name for the model file itself. 


### 2. Use model to generate similarity scores for a set of images

Create the similarity scores for a set of images using the facial recognition model created in a previous step. You will need to input the filepath to your facial recognition model, the filepath to the directory containing the images you want to generate similarity scores for, whether or not you want to search all subdirectories (select "search_recursively"), your desired name for the file containing the similarity score and the filepath to the directory where you want the similarity score file saved.
If you search the directory recurively, a similarity score file will be created in all subdirectories containing image files. (.jpg or .png) A file containing the similarity scores for all the images will also be created and placed in the directory you specify.
If a face is detected in photo, it will be scored on its similarity to the model. The score is a value between 0 and 1, with 1 corresponding to a perfect match. The similarity_score files contain, per line: the filepath to the photo and the similarity score for that photo.

### 3. Compile and Analyze Similarity Scores

Basic statistical analysis on the similarity scores. This will find the max, min, mean and standard deviation of your similarity scores as well as give you a table of percentile data. You will need to enter the path of the directory containing photos or subfolders. Script will look for similarity_scores.txt in all subdirectories. These will have been created automatically if you tested images against model recursively in previous step. If you are not searching recursively, you can just enter the filepath of the file containing the similarity scores you wish to analyze. You will also need to enter the directory where the analysis file will be written as well as the name of the file.

### 4. Filter the images by similarity score

Photos can be filtered either percentile or score. A file will be generated with the filepaths and scores of the photos that meet the selected filter criteria. You will need to enter the path of directory containing photos or subfolders. Will look for similarity_scores.txt in all subdirectories. These will have been created automatically if you tested images against model recursively in previous step. Alternatively, you can just specify a filepath for a similarity_scores file. You will also need to enter your filter parameters, either max and min percentile or score. You will need to input the path of the directory where you want the list of filtered photos to be written as well as name the file itself. 

### 5. Move the filtered images to a directory of your choice

Using the file generated in step 4, move the filtered images into a new directory. Simply enter the filepath of the filtered photos list file created in the previous step as well as the filepath of the directory you wish the photos moved to.