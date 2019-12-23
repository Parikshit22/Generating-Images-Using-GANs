# Generating-Images-Using-GANs

Aim:- We are genrating the fake samples of digits learned from the input images of digit. Using GANs(generated adversial network),
      we learned the formation of images first and then appying those learned parameters on noise data and upsampling the noise dimension
      to 784 so that it can form the image of 28*28 dimension.

Data Preparation Part:-
    Training Data:- We'll be using mnist dataset and refering the label part to be 1 so as to mentioning that this is real data.
                    Also we'll be generating the fake data and labeling it to 0 so as to mention this data to be fake.
                    Also we'll reshape each image in 784 dimension vector and will normalize the image pixel values b/w -1 to 1.
                    

Model Planning:- 
     We'll have two parts first is generator which will generate the fake samples of data from the noise vector by upsampling the data.
     second part is discriminator part which will discrminate b/w the fake and real data coming from generator and database respectively.
     
     So, we'll intialize the noise vector randomly by np.random.normal this will generate the vector values b/w 0-1 and pass the noise
     vector through generator sequential model and it'll output a vector of 784 dim vector.
     after that 784 dim vector can be passed through discrminator model as giving the actual label to be 0, so as to train both the model
     by back-propogating the loss using Keras-Functional API.
     
Model Building:-
    The generator part consists of Keras Sequential API having serval Dense Layers and activation function as LeakyRelu, so that while
    back-propogating it will show gradient change effect on negative preceptron also will not change it to zero.
    On last layer will use activation function as tanh so as to get the output value b/w -1 to 1.
    
    word collocation
    
