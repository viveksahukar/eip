# eip
eip ai course assignment 3 depthwise convolution
Final validation accuracy for base model: 82.66%
My model best validation accuracy: 

Original Model: "sequential_1"
_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
conv2d_1 (Conv2D)            (None, 32, 32, 48)        1344      
_________________________________________________________________
activation_1 (Activation)    (None, 32, 32, 48)        0         
_________________________________________________________________
conv2d_2 (Conv2D)            (None, 30, 30, 48)        20784     
_________________________________________________________________
activation_2 (Activation)    (None, 30, 30, 48)        0         
_________________________________________________________________
max_pooling2d_1 (MaxPooling2 (None, 15, 15, 48)        0         
_________________________________________________________________
dropout_1 (Dropout)          (None, 15, 15, 48)        0         
_________________________________________________________________
conv2d_3 (Conv2D)            (None, 15, 15, 96)        41568     
_________________________________________________________________
activation_3 (Activation)    (None, 15, 15, 96)        0         
_________________________________________________________________
conv2d_4 (Conv2D)            (None, 13, 13, 96)        83040     
_________________________________________________________________
activation_4 (Activation)    (None, 13, 13, 96)        0         
_________________________________________________________________
max_pooling2d_2 (MaxPooling2 (None, 6, 6, 96)          0         
_________________________________________________________________
dropout_2 (Dropout)          (None, 6, 6, 96)          0         
_________________________________________________________________
conv2d_5 (Conv2D)            (None, 6, 6, 192)         166080    
_________________________________________________________________
activation_5 (Activation)    (None, 6, 6, 192)         0         
_________________________________________________________________
conv2d_6 (Conv2D)            (None, 4, 4, 192)         331968    
_________________________________________________________________
activation_6 (Activation)    (None, 4, 4, 192)         0         
_________________________________________________________________
max_pooling2d_3 (MaxPooling2 (None, 2, 2, 192)         0         
_________________________________________________________________
dropout_3 (Dropout)          (None, 2, 2, 192)         0         
_________________________________________________________________
flatten_1 (Flatten)          (None, 768)               0         
_________________________________________________________________
dense_1 (Dense)              (None, 512)               393728    
_________________________________________________________________
activation_7 (Activation)    (None, 512)               0         
_________________________________________________________________
dropout_4 (Dropout)          (None, 512)               0         
_________________________________________________________________
dense_2 (Dense)              (None, 256)               131328    
_________________________________________________________________
activation_8 (Activation)    (None, 256)               0         
_________________________________________________________________
dropout_5 (Dropout)          (None, 256)               0         
_________________________________________________________________
dense_3 (Dense)              (None, 10)                2570      
=================================================================
Total params: 1,172,410
Trainable params: 1,172,410
Non-trainable params: 0
_________________________________________________________________
from keras.preprocessing.image import ImageDataGenerator
​
datagen = ImageDataGenerator(zoom_range=0.0, 
                             horizontal_flip=False)
​
​
​
# train the model
start = time.time()
# Train the model
model_info = model.fit_generator(datagen.flow(train_features, train_labels, batch_size = 128),
                                 samples_per_epoch = train_features.shape[0], nb_epoch = 50, 
                                 validation_data = (test_features, test_labels), verbose=1)
end = time.time()
print ("Model took %0.2f seconds to train"%(end - start))
​
C:\Users\vivek\Anaconda3\envs\tfgpu\lib\site-packages\ipykernel_launcher.py:12: UserWarning: The semantics of the Keras 2 argument `steps_per_epoch` is not the same as the Keras 1 argument `samples_per_epoch`. `steps_per_epoch` is the number of batches to draw from the generator at each epoch. Basically steps_per_epoch = samples_per_epoch/batch_size. Similarly `nb_val_samples`->`validation_steps` and `val_samples`->`steps` arguments have changed. Update your method calls accordingly.
  if sys.path[0] == '':
C:\Users\vivek\Anaconda3\envs\tfgpu\lib\site-packages\ipykernel_launcher.py:12: UserWarning: Update your `fit_generator` call to the Keras 2 API: `fit_generator(<keras.pre..., validation_data=(array([[[..., verbose=1, steps_per_epoch=390, epochs=50)`
  if sys.path[0] == '':
Epoch 1/50
390/390 [==============================] - 12s 32ms/step - loss: 1.8536 - accuracy: 0.2839 - val_loss: 1.4168 - val_accuracy: 0.4762
Epoch 2/50
390/390 [==============================] - 9s 23ms/step - loss: 1.3433 - accuracy: 0.5111 - val_loss: 1.2041 - val_accuracy: 0.5743
Epoch 3/50
390/390 [==============================] - 9s 23ms/step - loss: 1.1183 - accuracy: 0.6019 - val_loss: 0.9509 - val_accuracy: 0.6574
Epoch 4/50
390/390 [==============================] - 9s 23ms/step - loss: 0.9694 - accuracy: 0.6602 - val_loss: 0.8606 - val_accuracy: 0.6993
Epoch 5/50
390/390 [==============================] - 9s 23ms/step - loss: 0.8716 - accuracy: 0.6980 - val_loss: 0.7998 - val_accuracy: 0.7254
Epoch 6/50
390/390 [==============================] - 9s 23ms/step - loss: 0.8012 - accuracy: 0.7243 - val_loss: 0.7333 - val_accuracy: 0.7488
Epoch 7/50
390/390 [==============================] - 9s 23ms/step - loss: 0.7467 - accuracy: 0.7437 - val_loss: 0.6943 - val_accuracy: 0.7603
Epoch 8/50
390/390 [==============================] - 9s 23ms/step - loss: 0.6958 - accuracy: 0.7628 - val_loss: 0.6830 - val_accuracy: 0.7665
Epoch 9/50
390/390 [==============================] - 9s 23ms/step - loss: 0.6690 - accuracy: 0.7728 - val_loss: 0.6463 - val_accuracy: 0.7803
Epoch 10/50
390/390 [==============================] - 9s 23ms/step - loss: 0.6319 - accuracy: 0.7829 - val_loss: 0.6177 - val_accuracy: 0.7903
Epoch 11/50
390/390 [==============================] - 9s 23ms/step - loss: 0.6182 - accuracy: 0.7909 - val_loss: 0.6645 - val_accuracy: 0.7784
Epoch 12/50
390/390 [==============================] - 9s 23ms/step - loss: 0.5911 - accuracy: 0.8008 - val_loss: 0.6240 - val_accuracy: 0.7940
Epoch 13/50
390/390 [==============================] - 9s 23ms/step - loss: 0.5630 - accuracy: 0.8091 - val_loss: 0.6501 - val_accuracy: 0.7840
Epoch 14/50
390/390 [==============================] - 9s 23ms/step - loss: 0.5562 - accuracy: 0.8105 - val_loss: 0.6008 - val_accuracy: 0.7974
Epoch 15/50
390/390 [==============================] - 9s 22ms/step - loss: 0.5377 - accuracy: 0.8160 - val_loss: 0.6023 - val_accuracy: 0.7971
Epoch 16/50
390/390 [==============================] - 9s 22ms/step - loss: 0.5256 - accuracy: 0.8200 - val_loss: 0.5744 - val_accuracy: 0.8122
Epoch 17/50
390/390 [==============================] - 9s 22ms/step - loss: 0.5068 - accuracy: 0.8272 - val_loss: 0.5879 - val_accuracy: 0.8060
Epoch 18/50
390/390 [==============================] - 9s 22ms/step - loss: 0.4934 - accuracy: 0.8293 - val_loss: 0.5961 - val_accuracy: 0.8076
Epoch 19/50
390/390 [==============================] - 9s 23ms/step - loss: 0.4890 - accuracy: 0.8338 - val_loss: 0.5902 - val_accuracy: 0.8096
Epoch 20/50
390/390 [==============================] - 9s 22ms/step - loss: 0.4716 - accuracy: 0.8385 - val_loss: 0.5507 - val_accuracy: 0.8183
Epoch 21/50
390/390 [==============================] - 9s 23ms/step - loss: 0.4545 - accuracy: 0.8458 - val_loss: 0.5993 - val_accuracy: 0.8084
Epoch 22/50
390/390 [==============================] - 9s 23ms/step - loss: 0.4546 - accuracy: 0.8450 - val_loss: 0.5787 - val_accuracy: 0.8143
Epoch 23/50
390/390 [==============================] - 9s 23ms/step - loss: 0.4513 - accuracy: 0.8478 - val_loss: 0.5797 - val_accuracy: 0.8122
Epoch 24/50
390/390 [==============================] - 9s 22ms/step - loss: 0.4421 - accuracy: 0.8495 - val_loss: 0.5758 - val_accuracy: 0.8173
Epoch 25/50
390/390 [==============================] - 9s 23ms/step - loss: 0.4314 - accuracy: 0.8526 - val_loss: 0.5767 - val_accuracy: 0.8180
Epoch 26/50
390/390 [==============================] - 9s 23ms/step - loss: 0.4320 - accuracy: 0.8541 - val_loss: 0.5762 - val_accuracy: 0.8113
Epoch 27/50
390/390 [==============================] - 9s 23ms/step - loss: 0.4300 - accuracy: 0.8567 - val_loss: 0.5851 - val_accuracy: 0.8162
Epoch 28/50
390/390 [==============================] - 9s 23ms/step - loss: 0.4085 - accuracy: 0.8617 - val_loss: 0.5998 - val_accuracy: 0.8147
Epoch 29/50
390/390 [==============================] - 9s 23ms/step - loss: 0.4054 - accuracy: 0.8636 - val_loss: 0.5597 - val_accuracy: 0.8189
Epoch 30/50
390/390 [==============================] - 9s 23ms/step - loss: 0.4041 - accuracy: 0.8625 - val_loss: 0.5933 - val_accuracy: 0.8157
Epoch 31/50
390/390 [==============================] - 9s 23ms/step - loss: 0.3997 - accuracy: 0.8652 - val_loss: 0.5609 - val_accuracy: 0.8213
Epoch 32/50
390/390 [==============================] - 9s 22ms/step - loss: 0.4047 - accuracy: 0.8655 - val_loss: 0.5961 - val_accuracy: 0.8156
Epoch 33/50
390/390 [==============================] - 9s 23ms/step - loss: 0.3920 - accuracy: 0.8681 - val_loss: 0.5492 - val_accuracy: 0.8279
Epoch 34/50
390/390 [==============================] - 9s 23ms/step - loss: 0.3833 - accuracy: 0.8700 - val_loss: 0.5930 - val_accuracy: 0.8165
Epoch 35/50
390/390 [==============================] - 9s 23ms/step - loss: 0.3886 - accuracy: 0.8702 - val_loss: 0.5563 - val_accuracy: 0.8285
Epoch 36/50
390/390 [==============================] - 9s 23ms/step - loss: 0.3769 - accuracy: 0.8727 - val_loss: 0.5545 - val_accuracy: 0.8214
Epoch 37/50
390/390 [==============================] - 9s 23ms/step - loss: 0.3808 - accuracy: 0.8720 - val_loss: 0.5724 - val_accuracy: 0.8236
Epoch 38/50
390/390 [==============================] - 9s 23ms/step - loss: 0.3706 - accuracy: 0.8742 - val_loss: 0.5740 - val_accuracy: 0.8261
Epoch 39/50
390/390 [==============================] - 9s 23ms/step - loss: 0.3684 - accuracy: 0.8765 - val_loss: 0.5725 - val_accuracy: 0.8198
Epoch 40/50
390/390 [==============================] - 9s 23ms/step - loss: 0.3593 - accuracy: 0.8780 - val_loss: 0.5581 - val_accuracy: 0.8298
Epoch 41/50
390/390 [==============================] - 9s 23ms/step - loss: 0.3588 - accuracy: 0.8821 - val_loss: 0.6166 - val_accuracy: 0.8159
Epoch 42/50
390/390 [==============================] - 9s 23ms/step - loss: 0.3546 - accuracy: 0.8802 - val_loss: 0.5906 - val_accuracy: 0.8167
Epoch 43/50
390/390 [==============================] - 9s 23ms/step - loss: 0.3514 - accuracy: 0.8822 - val_loss: 0.5767 - val_accuracy: 0.8273
Epoch 44/50
390/390 [==============================] - 9s 23ms/step - loss: 0.3534 - accuracy: 0.8814 - val_loss: 0.5961 - val_accuracy: 0.8196
Epoch 45/50
390/390 [==============================] - 9s 23ms/step - loss: 0.3451 - accuracy: 0.8837 - val_loss: 0.5861 - val_accuracy: 0.8203
Epoch 46/50
390/390 [==============================] - 9s 23ms/step - loss: 0.3394 - accuracy: 0.8870 - val_loss: 0.6082 - val_accuracy: 0.8177
Epoch 47/50
390/390 [==============================] - 9s 23ms/step - loss: 0.3399 - accuracy: 0.8885 - val_loss: 0.5991 - val_accuracy: 0.8252
Epoch 48/50
390/390 [==============================] - 9s 23ms/step - loss: 0.3358 - accuracy: 0.8895 - val_loss: 0.5716 - val_accuracy: 0.8258
Epoch 49/50
390/390 [==============================] - 9s 23ms/step - loss: 0.3363 - accuracy: 0.8874 - val_loss: 0.5776 - val_accuracy: 0.8269
Epoch 50/50
390/390 [==============================] - 9s 23ms/step - loss: 0.3269 - accuracy: 0.8896 - val_loss: 0.6111 - val_accuracy: 0.8266
Model took 450.77 seconds to train

Model: "sequential_23"
_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
separable_conv2d_100 (Separa (None, 30, 30, 48)        219       
_________________________________________________________________
batch_normalization_182 (Bat (None, 30, 30, 48)        192       
_________________________________________________________________
separable_conv2d_101 (Separa (None, 28, 28, 48)        2784      
_________________________________________________________________
batch_normalization_183 (Bat (None, 28, 28, 48)        192       
_________________________________________________________________
max_pooling2d_51 (MaxPooling (None, 14, 14, 48)        0         
_________________________________________________________________
batch_normalization_184 (Bat (None, 14, 14, 48)        192       
_________________________________________________________________
dropout_60 (Dropout)         (None, 14, 14, 48)        0         
_________________________________________________________________
separable_conv2d_102 (Separa (None, 12, 12, 96)        5136      
_________________________________________________________________
batch_normalization_185 (Bat (None, 12, 12, 96)        384       
_________________________________________________________________
dropout_61 (Dropout)         (None, 12, 12, 96)        0         
_________________________________________________________________
separable_conv2d_103 (Separa (None, 10, 10, 96)        10176     
_________________________________________________________________
batch_normalization_186 (Bat (None, 10, 10, 96)        384       
_________________________________________________________________
dropout_62 (Dropout)         (None, 10, 10, 96)        0         
_________________________________________________________________
max_pooling2d_52 (MaxPooling (None, 5, 5, 96)          0         
_________________________________________________________________
batch_normalization_187 (Bat (None, 5, 5, 96)          384       
_________________________________________________________________
dropout_63 (Dropout)         (None, 5, 5, 96)          0         
_________________________________________________________________
separable_conv2d_104 (Separa (None, 3, 3, 192)         19488     
_________________________________________________________________
batch_normalization_188 (Bat (None, 3, 3, 192)         768       
_________________________________________________________________
dropout_64 (Dropout)         (None, 3, 3, 192)         0         
_________________________________________________________________
separable_conv2d_105 (Separa (None, 1, 1, 192)         38784     
_________________________________________________________________
batch_normalization_189 (Bat (None, 1, 1, 192)         768       
_________________________________________________________________
dropout_65 (Dropout)         (None, 1, 1, 192)         0         
_________________________________________________________________
separable_conv2d_106 (Separa (None, 1, 1, 10)          2122      
_________________________________________________________________
batch_normalization_190 (Bat (None, 1, 1, 10)          40        
_________________________________________________________________
flatten_13 (Flatten)         (None, 10)                0         
_________________________________________________________________
activation_59 (Activation)   (None, 10)                0         
=================================================================
Total params: 82,013
Trainable params: 80,361
Non-trainable params: 1,652
_________________________________________________________________
