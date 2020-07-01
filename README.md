Initially, I used the source code from  lecture for handwriting.py to set up my neural network. Imitating that structure, I set up a convolutional feed-forward neural network with first a convolusional 2D layer with 32 layers using a 3x3 kernel. 
Next, a max pooling layer is added of pool size 2x2 to reduce the data required to be analyzed. 
In order to be able to model more than just simply linear behavior, a hidden layer is added with 128 nodes which act as "hidden variables" to facilitate learning of more complex relationships between input and output. 
Dropout is defaulted to 50%, which actually turns out to be a good value for this application. 
Finally, the output layer has NUM_CATEGORIES nodes, as we want each node to map to a type of traffic sign. 

Finding the accuracy to be less than ideal at a measly ~5%, I decided to add another layer of convolution and pooling to be able pick up on more details, as pictures of street signs have more features than handwritten numbers. 
I also increased the amount of hidden layers to 512, to better reflect how traffic signs have many more variables than digits. 
Dropout is ideal at around 50%, as the accuracy at the end of epoch 10 is fairly close to accuracy of the test batch. A lower dropout rate increases epoch accuracy but testing accuracy lowers, while increasing dropout lowers both epoch accuracy and testing accuracy. 
By using these layers combined, my neural network can reach ~96% accuracy and ~0.2 loss. 
I can further increase accuracy to ~97% by removing the max pooling layers, but this increases learning time by 4-5 times, while not yielding significant enough improvements in accuracy. 