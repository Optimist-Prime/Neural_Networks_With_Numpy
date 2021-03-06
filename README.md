# Description
>1. Digit Classification using Two Layer Neural Network and Back Propagation. Written in Python3 and depends only on Numpy.
>2. Implimentation of:<br/>
>>* Artificial Neural Network. (Notebooks/ANN.ipynb)
>>* Convolutional Neural Network. (Notebooks/CNN.ipynb)
>>* Recurrent Neural Network. (Notebooks/RNN.ipynb)

## Getting Started

## Getting Data
1) Download the data in csv format from here :- https://pjreddie.com/projects/mnist-in-csv/.
2) Already downloaded and kept the MNIST test data in the ./data/ folder. Training data size was large for Github.

## Loading the data
1) Python script, dataloader.py helps in converting the data from csv to numpy format.
2) Verify your above steps are correct by running the script
3) The script requires two user inputs
  i) datapath = path to the data folder inside which the MNIST CSVs files are stored. <br />
  ii) mode = 'train' or 'test' to extract the training or test data<br />
  iii) For example :-<br />
      ```python3 dataloader.py ./data test
       ```
 
## Training the model
1) Python Script , neural_net.py contains all the APIs used for training the model, saving the model and running over the test data
2) The script requires three user inputs<br />
    i)   mode = 'train' or 'test' <br />
    ii)  datapath = path to the data folder inside which the MNIST CSVs files are stored. <br />
    iii) modelpath = path to store the trained weight or load the weights during the test time <br />
    
    iv) Example:-
    
        ```python3 neural_net.py train ./data ./new_model
        ```

## Testing the model
1) I have already provided the trained model inside the model folder and the test data inside the data folder.
2) To get started, use the follwing command.
    
    ```python3 neural_net.py test ./data ./model_bn
    ```

  If everything is set-up well, you should see the following results on your console.<br />
                        Loading Dataset===><br />
                        Done!<br />
                        Loading Trained Weights......<br />
                        Testing Iteration===>0, Acc ====>0.9766<br />
                        Testing Iteration===>1, Acc ====>0.9609<br />
                        Testing Iteration===>2, Acc ====>0.9844<br />
                                    -- -- -- -- -- -- --<br/>
                                    -- -- -- -- -- -- --<br/>
                        Testing Iteration===>76, Acc ====>0.9297<br />
                        Testing Iteration===>77, Acc ====>0.9687<br />

## Run on sample images
1) I have kept some images from MNIST inside the images folder.
2) To use this code, install opencv to read the image.
3) Run using :-
  
  ```python
      python3 run_on_image.py images/img_4.png ./model_bn/
  ```  
## Model Description
1) Number of Hidden Layers - 2
2) Hidden Layer Sizes - (1024, 2048)
3) Learning Rate - 0.001
4) Batch Size - 128
5) Number of epoch for training - 1000000
6) Batch Norm Decay Rate - 0.9

## Observations
1) Faster Convergence and better accuracy by using Batch Normalization before Relu operation. Please refere to the plots below.
2) Experiments with increasing the hidden layers and size might help us in finding a sweet spot where we are neither underfitting nor overfitting.
