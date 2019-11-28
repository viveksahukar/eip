# eip
eip ai course assignment 3 depthwise convolution
Final validation accuracy for base model: 82.77%
My model best validation accuracy: 79.06%
# Define the model

# (Output size, receptive field) mentioned in tuple form after adding each layer as comment.

model_2 = Sequential()
model_2.add(SeparableConv2D(48, 3, 3, activation='relu', input_shape=(32, 32, 3))) # (30, 3)
model_2.add(BatchNormalization())
model_2.add(Dropout(0.1))

model_2.add(SeparableConv2D(48, 3, 3, activation='relu')) # (28, 5)
model_2.add(BatchNormalization())
model_2.add(Dropout(0.1))


model_2.add(MaxPooling2D(pool_size=(2, 2))) # (14, 6)
model_2.add(BatchNormalization())
model_2.add(Dropout(0.1))

model_2.add(SeparableConv2D(96, 3, 3, activation='relu')) # (12, 9)
model_2.add(BatchNormalization())
model_2.add(Dropout(0.1))

model_2.add(SeparableConv2D(96, 3, 3, activation='relu')) # (10, 13)
model_2.add(BatchNormalization())
model_2.add(Dropout(0.1))

model_2.add(MaxPooling2D(pool_size=(2, 2))) # (5, 15)
model_2.add(BatchNormalization())
model_2.add(Dropout(0.1))

model_2.add(SeparableConv2D(192, 3, 3, activation='relu')) # (3, 19)
model_2.add(BatchNormalization())
model_2.add(Dropout(0.1))

model_2.add(SeparableConv2D(192, 3, 3, activation='relu')) # (1, 27)
model_2.add(BatchNormalization())
model_2.add(Dropout(0.1))


model_2.add(SeparableConv2D(num_classes, 1, 1, activation='relu')) # (10, 27)
model_2.add(BatchNormalization())



model_2.add(Flatten())
model_2.add(Activation('softmax')) #(10, 27)



Epoch 1/50
390/390 [==============================] - 30s 77ms/step - loss: 1.6669 - acc: 0.4160 - val_loss: 1.4396 - val_acc: 0.5021
Epoch 2/50
390/390 [==============================] - 18s 46ms/step - loss: 1.2266 - acc: 0.5850 - val_loss: 1.1596 - val_acc: 0.5982
Epoch 3/50
390/390 [==============================] - 18s 47ms/step - loss: 1.0708 - acc: 0.6377 - val_loss: 1.1267 - val_acc: 0.6155
Epoch 4/50
390/390 [==============================] - 19s 48ms/step - loss: 0.9581 - acc: 0.6746 - val_loss: 0.9301 - val_acc: 0.6785
Epoch 5/50
390/390 [==============================] - 18s 46ms/step - loss: 0.8841 - acc: 0.6993 - val_loss: 0.8782 - val_acc: 0.6966
Epoch 6/50
390/390 [==============================] - 18s 47ms/step - loss: 0.8316 - acc: 0.7158 - val_loss: 0.8486 - val_acc: 0.7037
Epoch 7/50
390/390 [==============================] - 18s 47ms/step - loss: 0.7917 - acc: 0.7281 - val_loss: 0.8505 - val_acc: 0.7070
Epoch 8/50
390/390 [==============================] - 18s 47ms/step - loss: 0.7539 - acc: 0.7389 - val_loss: 0.8621 - val_acc: 0.7064
Epoch 9/50
390/390 [==============================] - 18s 47ms/step - loss: 0.7286 - acc: 0.7488 - val_loss: 0.8518 - val_acc: 0.7112
Epoch 10/50
390/390 [==============================] - 18s 47ms/step - loss: 0.6988 - acc: 0.7595 - val_loss: 0.7364 - val_acc: 0.7465
Epoch 11/50
390/390 [==============================] - 18s 47ms/step - loss: 0.6754 - acc: 0.7676 - val_loss: 0.7430 - val_acc: 0.7473
Epoch 12/50
390/390 [==============================] - 18s 47ms/step - loss: 0.6534 - acc: 0.7727 - val_loss: 0.7118 - val_acc: 0.7543
Epoch 13/50
390/390 [==============================] - 19s 48ms/step - loss: 0.6378 - acc: 0.7790 - val_loss: 0.7514 - val_acc: 0.7439
Epoch 14/50
390/390 [==============================] - 18s 47ms/step - loss: 0.6203 - acc: 0.7849 - val_loss: 0.6729 - val_acc: 0.7711
Epoch 15/50
390/390 [==============================] - 19s 48ms/step - loss: 0.6044 - acc: 0.7932 - val_loss: 0.7229 - val_acc: 0.7524
Epoch 16/50
390/390 [==============================] - 18s 47ms/step - loss: 0.5937 - acc: 0.7954 - val_loss: 0.6911 - val_acc: 0.7659
Epoch 17/50
390/390 [==============================] - 18s 47ms/step - loss: 0.5765 - acc: 0.7995 - val_loss: 0.7359 - val_acc: 0.7443
Epoch 18/50
390/390 [==============================] - 18s 47ms/step - loss: 0.5616 - acc: 0.8053 - val_loss: 0.6578 - val_acc: 0.7775
Epoch 19/50
390/390 [==============================] - 18s 47ms/step - loss: 0.5547 - acc: 0.8067 - val_loss: 0.7031 - val_acc: 0.7657
Epoch 20/50
390/390 [==============================] - 18s 47ms/step - loss: 0.5400 - acc: 0.8122 - val_loss: 0.6700 - val_acc: 0.7709
Epoch 21/50
390/390 [==============================] - 18s 47ms/step - loss: 0.5299 - acc: 0.8151 - val_loss: 0.6573 - val_acc: 0.7766
Epoch 22/50
390/390 [==============================] - 18s 47ms/step - loss: 0.5232 - acc: 0.8181 - val_loss: 0.7004 - val_acc: 0.7692
Epoch 23/50
390/390 [==============================] - 18s 47ms/step - loss: 0.5170 - acc: 0.8189 - val_loss: 0.6613 - val_acc: 0.7757
Epoch 24/50
390/390 [==============================] - 18s 47ms/step - loss: 0.5052 - acc: 0.8225 - val_loss: 0.6559 - val_acc: 0.7761
Epoch 25/50
390/390 [==============================] - 18s 47ms/step - loss: 0.5024 - acc: 0.8243 - val_loss: 0.7061 - val_acc: 0.7632
Epoch 26/50
390/390 [==============================] - 18s 47ms/step - loss: 0.4944 - acc: 0.8270 - val_loss: 0.6956 - val_acc: 0.7668
Epoch 27/50
390/390 [==============================] - 18s 47ms/step - loss: 0.4856 - acc: 0.8297 - val_loss: 0.7360 - val_acc: 0.7550
Epoch 28/50
390/390 [==============================] - 18s 47ms/step - loss: 0.4833 - acc: 0.8294 - val_loss: 0.6865 - val_acc: 0.7713
Epoch 29/50
390/390 [==============================] - 18s 47ms/step - loss: 0.4720 - acc: 0.8335 - val_loss: 0.6497 - val_acc: 0.7797
Epoch 30/50
390/390 [==============================] - 18s 47ms/step - loss: 0.4623 - acc: 0.8374 - val_loss: 0.6489 - val_acc: 0.7823
Epoch 31/50
390/390 [==============================] - 18s 47ms/step - loss: 0.4649 - acc: 0.8368 - val_loss: 0.6693 - val_acc: 0.7735
Epoch 32/50
390/390 [==============================] - 19s 48ms/step - loss: 0.4575 - acc: 0.8402 - val_loss: 0.6482 - val_acc: 0.7823
Epoch 33/50
390/390 [==============================] - 18s 47ms/step - loss: 0.4460 - acc: 0.8437 - val_loss: 0.6395 - val_acc: 0.7876
Epoch 34/50
390/390 [==============================] - 18s 47ms/step - loss: 0.4458 - acc: 0.8431 - val_loss: 0.6751 - val_acc: 0.7742
Epoch 35/50
390/390 [==============================] - 18s 47ms/step - loss: 0.4431 - acc: 0.8454 - val_loss: 0.6825 - val_acc: 0.7760
Epoch 36/50
390/390 [==============================] - 19s 48ms/step - loss: 0.4375 - acc: 0.8464 - val_loss: 0.6466 - val_acc: 0.7884
Epoch 37/50
390/390 [==============================] - 18s 47ms/step - loss: 0.4289 - acc: 0.8473 - val_loss: 0.6676 - val_acc: 0.7795
Epoch 38/50
390/390 [==============================] - 18s 47ms/step - loss: 0.4335 - acc: 0.8461 - val_loss: 0.7051 - val_acc: 0.7691
Epoch 39/50
390/390 [==============================] - 19s 47ms/step - loss: 0.4258 - acc: 0.8499 - val_loss: 0.6323 - val_acc: 0.7906
Epoch 40/50
390/390 [==============================] - 18s 47ms/step - loss: 0.4195 - acc: 0.8523 - val_loss: 0.6941 - val_acc: 0.7772
Epoch 41/50
390/390 [==============================] - 19s 47ms/step - loss: 0.4221 - acc: 0.8502 - val_loss: 0.6604 - val_acc: 0.7830
Epoch 42/50
390/390 [==============================] - 19s 48ms/step - loss: 0.4090 - acc: 0.8550 - val_loss: 0.6895 - val_acc: 0.7767
Epoch 43/50
390/390 [==============================] - 18s 47ms/step - loss: 0.4077 - acc: 0.8561 - val_loss: 0.6661 - val_acc: 0.7821
Epoch 44/50
390/390 [==============================] - 18s 47ms/step - loss: 0.4115 - acc: 0.8545 - val_loss: 0.6624 - val_acc: 0.7839
Epoch 45/50
390/390 [==============================] - 18s 47ms/step - loss: 0.4010 - acc: 0.8574 - val_loss: 0.6822 - val_acc: 0.7778
Epoch 46/50
390/390 [==============================] - 18s 47ms/step - loss: 0.4015 - acc: 0.8578 - val_loss: 0.6926 - val_acc: 0.7778
Epoch 47/50
390/390 [==============================] - 18s 47ms/step - loss: 0.3971 - acc: 0.8576 - val_loss: 0.6814 - val_acc: 0.7820
Epoch 48/50
390/390 [==============================] - 18s 47ms/step - loss: 0.3954 - acc: 0.8599 - val_loss: 0.6528 - val_acc: 0.7877
Epoch 49/50
390/390 [==============================] - 19s 48ms/step - loss: 0.3929 - acc: 0.8603 - val_loss: 0.6763 - val_acc: 0.7787
Epoch 50/50
390/390 [==============================] - 18s 47ms/step - loss: 0.3879 - acc: 0.8613 - val_loss: 0.6820 - val_acc: 0.7839
Model 2 took 931.45 seconds to train
