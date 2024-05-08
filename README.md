1. Set up the environment
1.1 Installing Anaconda
Anaconda is a Python distribution for data science that provides convenient environmental management tools.
1.2 Creating a Virtual Environment
Code: Conda create - n CFG_SI_YOLO Python=3.8
Conda activate CFG_SI_YOLO
1.3 Installing PyTorch
CFG_SI_YOLO relies on the PyTorch framework and can be installed using the following command:
Code: pip install torch torch vision torch studio
1.4 Cloning YOLOv7 Warehouse
Git clone https://github.com/ultralytics/yolov7.git
1.5 Installation Dependencies
Pip install - r requirements. txt
3. Run code
2.1 Preparation of data
Place your dataset in the datasets directory, including the training set, validation set, and test set, and organize them in the YOLOv7 data format.
2.2 Configuration Model
We need an initial weight file and create a. yaml file to match your dataset and model settings.
2.3 Training Model
Run the following command to train the model:
Python train. py -- img 640-- batch 6-- epochs 200-- datasets datasets/. yaml -- cfg models/CFG_SI_YOLO. yaml -- weights' '
The parameters here need to be adjusted according to your dataset and requirements.
2.4 Reasoning
Run the following command for inference:
Python detect.py -- source data/images/-- weights runs/train/exp/weights/best. pt -- conf 0.4
The -- source parameter here is the path to the input image, the -- weights parameter is the weight file path of the trained model, and the -- conf is the confidence threshold.
4. Reproduction experiment
3.1 Ensure consistent code versions
Ensure that the same code version and dependencies are used during the replication experiment.
Detect: Used to detect test set images.
Requirements: The software packages that need to be installed to build the environment.
Test: Used to calculate accuracy.
Train: Need to create. yaml and initial weight files for training.
3.2 Using the same dataset, parameters, and experimental settings
The experimental environment for the network was trained using the Adam optimizer on PyTorch 1.12.1, Python 3.8, and NVIDIA GTX 3060 GPU, with batch size and training epochs set to 6 and 200, respectively. The initial learning rate is 0.01, and the momentum and weight attenuation are set to 0.937 and 0.0005, respectively. The weight attenuation value is 0.0005, and the warmup epochs is set to 3.0.
