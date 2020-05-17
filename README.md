# zoo_attack

Keras with the Tensorflow backend has been used for the development of the models, and there is currently no support for Theano or CNTK backends. The weights have not been tested with those backends.

Note : The input to the Input layer of all models will be pre-shuffled to be in the shape (Batchsize, Number of variables, Number of timesteps), and the input will be shuffled again before being applied to the CNNs (to obtain the correct shape (Batchsize, Number of timesteps, Number of variables)). This is in contrast to the paper where the input is of the shape (Batchsize, Number of timesteps, Number of variables) and the shuffle operation is applied before the LSTM to obtain the input shape (Batchsize, Number of variables, Number of timesteps). These operations are equivalent.

MLSTM FCN model : model = generate_model()

Training
To train the a model, uncomment the line below and execute the script. Note that '???????' will already be provided, so there is no need to replace it. It refers to the prefix of the saved weight file. Also, if weights are already provided, this operation will overwrite those weights.

train_model(model, DATASET_INDEX, dataset_prefix='???????', epochs=250, batch_size=128)

Evaluate
To evaluate the performance of the model, simply execute the script with the below line uncommented.

evaluate_model(model, DATASET_INDEX, dataset_prefix='???????', batch_size=128)
