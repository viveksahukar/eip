# EIP AI Course

Assignment 1

Accuracy : 99.24%

1. Convolution: It's the process where a window or filter or kernel (size n x n pixels : n is odd) moves through the entire image covering n x n pixels at any given time. The dot product of the matrix in the image and the filter is calculated and this output shows in next layer. By this process of convolution, the filter has seen the entire image in each layer.

2. Filter/ Kernels: A window of size n x n pixels (where n is odd number) which is used to extract features from the images in each layer. n=3 or 3 x 3 filter is the most commonly used filter 

3. Epochs: Epoch refers to the one complete iteration of the model over the entire training data. At the end of each epoch, the gradient of the weights w.r.t loss on the training batch is calculated and all the weights are updated accordingly.  

4. 1x1 Convolution: It's process where the filter size is 1x1 pixel. The filter size is same as each pixel on the image. The output of 1x1 convolution is the product of filter and the value in image pixel. The net effect is either the amplification or deamplification of the values in the images in the next layer.

5. 3x3 Convolution: It's convolution process where the filter size is 3x3 pixels. The filter is convoluted through the entire image covering 3x3 pixels at a given time. The dot product of the matrix (size 3x3) in image under convolution and the filter is calculated and this output is sent to next layer.

6. Feature Maps: They are the response created by the convolving a fixed size filter on the input in the previous layer in the convolutional neural network. They show where the pattern in the filter is located in the input image.

7. Activation Function: The dot product of the input and weight at the node is calculated and bias is added. This final result is passed through the activation function. If the output of the activation function is above a certain threshold, the node is fired up, otherwise, the node is not activated. RELU is the most commonly used activation function.

8. Receptive Field: It's the number of pixels in the previous layers seen by the pixel in the current layer. The local receptive field refers to the number of pixels in the immediate previous layer have been seen by the pixel in the current layer. The local receptive field is always equal to the size of the filter (for example, local receptive field for 3x3 filter is always 9). The global receptive field refers to the number of pixels in all the previous layers have been seen by the pixel in the current layer. 

