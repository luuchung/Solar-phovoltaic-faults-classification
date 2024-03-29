# Solar-phovoltaic-faults-classification
# PV faults classification
Firstly, I used Simulink to collect data. Check the file named  **Data_Collection_method.pdf** for more details.\
In order to classify the faults of the PV system, I used a neural network that consists of 3 fully connected layers. The Keras implementation can be found in the **final_thesis.ipynb file.**
## Detect fault locations
Second, I used Yolov3 to detect fault locations (all files in Coursework2_Chung). The dataset contains 120 thermal images of PV panel, split into 100 images for training and 20 images for testing.

**A brief overview of the steps needed to do this**:
  1. Collect a few hundred images that contain your object - The bare minimum would be about 100, ideally more like 500+, but, the more images you have, the more tedious step 2 is...
  2. Annotate/label the images, ideally with a program. We used LabelImg. This process is basically drawing boxes around your object(s) in an image. The label program automatically will create an XML file that describes the object(s) in the pictures.
  3. Split this data into train/test samples
  4. Setup a .config file for the model of choice (you could train your own from scratch, but we'll be using transfer learning)
  5. Train
  6. Export graph from new trained model\
LabelImg : https://pypi.org/project/labelImg/
