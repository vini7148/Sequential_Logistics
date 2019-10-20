# Sequential_Logistics

A sequntial logistics model for predicting the label, which is salary of differents adults based on their 'age','workclass','education',etc.

## Getting started

Use the following command to clone the repository on to your system
```
git clone https://github.com/vini7148/Sequential_Logistics.git
cd Seqential_Logistics
```

### Prerequisites

An environment for running .ipynb files is required along with the following python libraries
```
pandas
matplotlib
seaborn
sklearn
tensorflow-gpu
tensorflow.keras
```

### Running the model

After acquiring all the required pyhton libraries and an envitronment for executing .ipynb files along with this model. Open the "Adults using Sequential Logistic.ipynb" file

Note: if you don't have tensorflow-gpu or cannot use a discrete GPU then please comment out the 'with tf.device("/device:GPU:1"):' in the executable cell numbered 12 of the .ipynb file and correct the indentation of the following lines of code for it to run successfully.

## Built with

* [Python 3](https://www.python.org/ftp/python/3.8.0/python-3.8.0.exe)
* [Anaconda](https://www.anaconda.com/distribution/#download-section)
* [Jupyter notebook]```conda install -c conda-forge jupyterlab```

Note if you have not install Anaconda, you can still install Jupyter Notebook by ```pip install jupyterlab```

## Description of the keras.sequential model

The activation function used is
```
activation = tf.nn.sigmoid
```
The optimizer used is
```
optimizer = tf.keras.optimizers.Adam(0.01)
```
The summary of the model is 
```
_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
dense (Dense)                (None, 64)                3712      
_________________________________________________________________
dense_1 (Dense)              (None, 64)                4160      
_________________________________________________________________
dense_2 (Dense)              (None, 64)                4160      
_________________________________________________________________
dense_3 (Dense)              (None, 1)                 65        
=================================================================
Total params: 12,097
Trainable params: 12,097
Non-trainable params: 0
_________________________________________________________________

```
### Training of the model

This sequential model was trained for 100 epochs

Note: if you are not  using tensorflow-gpu, you might want to decrease the number of epochs as it will take a long time to train on CPU. Use 20 epochs for effective results on CPU.

## Outcome of this model

For the last epoch the loss, mean absolute error, etc. is
```
   loss     mean_absolute_error mean_squared_error val_loss val_mean_absolute_error val_mean_squared_error epoch
99 0.183517 0.366432            0.183517           0.186422 0.363392                          	 0.186422               99
```

The confusion matrix for the test dataset("Adults_Test.csv") is as follows
```
[[11360     0]
 [ 3609    91]]
```