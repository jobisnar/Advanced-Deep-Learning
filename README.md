# CoE 197F Advanced Deep Learning Project
## Semantic Segmentation Network

This project is a Pytorch reproduction of a semantic segmentation network that was originally written in Keras: <br>
https://github.com/PacktPublishing/Advanced-Deep-Learning-with-Keras/tree/master/chapter12-segmentation


In the link below, is a pre-trained weights file with batch size = 5, epochs = 40 <br>
https://drive.google.com/file/d/1K9hGNf2aRlDiLuxoC1FhAmoCzNzFr4mR/view?usp=sharing

### Running the Semantic Segmentation Network
To run the code, we enter this example line of code inside the jupyter notebook: <br>
fcn = FCN(train = True, batch_size = 5, epochs = 40, save = True, restore_weights_path = "3layer-drinks-best-iou.h5", device = 'cuda')<br>
train: set to True if you want to train the network<br>
batch_size: set the batch size<br>
epochs: set the number of epochs. If you load a pretrained weight that has already reached the set epoch, it won't train.<br>
save: set to True if you want to automatically save weights at the end of training<br>
restore_weights_path: the filename of the pre-trained or saved weights you want to load.<br>
evaluate: set to True if you want to evaluate the network using the test set after training it.<br>

can run "fcn.eval()" on next line of code if you want to run evaluation on the test set separately.<br>

### Other Parameters
label_file: filename of train npy segmentation annotation file<br>
test_labels: filename of test npy segmentation annotation file<br>
n_layers:
backbone: set backbone network<br>
transform: transform for data<br>
image_file: can be set to a specific image filename when evaluate is set to true, to test on that specific image<br>
root_dir: directory for the dataset<br>
shuffle: shuffles data when training<br>
dataset: name of dataset<br>


def __init__(self, restore_weights_path = "", label_file = "segmentation_train.npy", 
                 n_layers = 3, backbone = build_resnet, 
                 transform = None, image_file = None,
                 test_labels = "segmentation_test.npy",
                 root_dir = "data/drinks", batch_size = 1, shuffle = True,
                 dataset = "drinks", epochs = 5, plot = True,
                 in_channels = 3, save_dir = "weights",
                 evaluate = False, train = False, save = False, device = 'cpu'

### Below are some examples of the output images 

### Example of train image

<img width="400" alt="Input train image" src="https://github.com/jobisnar/Advanced-Deep-Learning/blob/master/images/0000107-input.png">

### Output segmentation on example train image

<img width="400" alt="Input train image" src="https://github.com/jobisnar/Advanced-Deep-Learning/blob/master/images/0000107-mask-epoch-40.png">

### Examples of test images

### Test image 1
<img width="400" alt="Test image 1" src="https://github.com/jobisnar/Advanced-Deep-Learning/blob/master/images/0010010-input.png">
<img width="400" alt="Segmentation 1" src="https://github.com/jobisnar/Advanced-Deep-Learning/blob/master/images/0010010-mask-epoch-40.png">

### Test image 2
<img width="400" alt="Test image 2" src="https://github.com/jobisnar/Advanced-Deep-Learning/blob/master/images/0010028-input.png">
<img width="400" alt="Segmentation 2" src="https://github.com/jobisnar/Advanced-Deep-Learning/blob/master/images/0010028-mask-epoch-40.png">

### Test image 3
<img width="400" alt="Test image 3" src="https://github.com/jobisnar/Advanced-Deep-Learning/blob/master/images/0010031-input.png">
<img width="400" alt="Segmentation 3" src="https://github.com/jobisnar/Advanced-Deep-Learning/blob/master/images/0010031-mask-epoch-40.png">
