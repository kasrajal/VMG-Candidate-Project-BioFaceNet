# VMG-Candidate-Project-BioFaceNet


Here are the files that are my recreation of BioFaceNet.
I ran these file in Google Colab and have left out that I mounted my drive as well. First call the imports in order to attach all the libaries necessary for the program like PyTorch. The helpers function contains helper functions that allow for calculating the difference between two images and show images during training and testing. After unzipping the CSV files and placing them in a folder, call Param_and_DataSet_Init to unpack the CSV files into tensors to be used in the model-based encoder and throughout the network. This will also pack all variables necessary for training and testing the network in 'options'. The call_train file when ran will load training and validation images, input and ground truth shading, and call the training fucntion. The call_test file when ran will test the network in the same manner that call_train does by loading test data. This file also contains code that could be used to load save weights for the model if necessary. Both call blocks require Param_and_DataSet to be called prior to initialize 'options'. During training and testing the CNN_based_encoder will be called. This contains the primary PyTorch implementation of the CNN Encoder framework that contains the encoder within the encoder as well the fully connected network and four decoders for the feature maps. After the encoder and decoders, the network calls upon the model_based_decoder file. This file contains the model-based decoder that undergoes the image formation pipeline. This file also contains the extra processing function required for the illuminant D data. the decoder finally will return the reconstructed RGB image, the input images, both diffuse and specular shading maps, as well as the melanin and haemoglobin maps. 
I was not able to train the network due to lack of data obtained by pre-processing images to have the facial region segmented and have diffuse ground truth shading maps. However if you would like to test to ensure the shapes of the output maps are equivalent to the input image, you may call the test_map_shape function. Currently the network can only take 128x128 images.
