assignment 2

Log for the model training

Train on 60000 samples, validate on 10000 samples
Epoch 1/20

Epoch 00001: LearningRateScheduler setting learning rate to 0.003.
60000/60000 [==============================] - 20s 331us/step - loss: 0.5482 - accuracy: 0.8458 - val_loss: 0.3793 - val_accuracy: 0.9146
Epoch 2/20

Epoch 00002: LearningRateScheduler setting learning rate to 0.0022744503.
60000/60000 [==============================] - 16s 263us/step - loss: 0.2604 - accuracy: 0.9227 - val_loss: 0.0662 - val_accuracy: 0.9869
Epoch 3/20

Epoch 00003: LearningRateScheduler setting learning rate to 0.0018315018.
60000/60000 [==============================] - 15s 257us/step - loss: 0.2015 - accuracy: 0.9394 - val_loss: 0.0501 - val_accuracy: 0.9884
Epoch 4/20

Epoch 00004: LearningRateScheduler setting learning rate to 0.0015329586.
60000/60000 [==============================] - 15s 256us/step - loss: 0.1745 - accuracy: 0.9451 - val_loss: 0.0403 - val_accuracy: 0.9894
Epoch 5/20

Epoch 00005: LearningRateScheduler setting learning rate to 0.0013181019.
60000/60000 [==============================] - 15s 254us/step - loss: 0.1547 - accuracy: 0.9481 - val_loss: 0.0315 - val_accuracy: 0.9918
Epoch 6/20

Epoch 00006: LearningRateScheduler setting learning rate to 0.0011560694.
60000/60000 [==============================] - 16s 259us/step - loss: 0.1462 - accuracy: 0.9495 - val_loss: 0.0320 - val_accuracy: 0.9914
Epoch 7/20

Epoch 00007: LearningRateScheduler setting learning rate to 0.0010295127.
60000/60000 [==============================] - 15s 257us/step - loss: 0.1335 - accuracy: 0.9507 - val_loss: 0.0310 - val_accuracy: 0.9921
Epoch 8/20

Epoch 00008: LearningRateScheduler setting learning rate to 0.0009279307.
60000/60000 [==============================] - 15s 258us/step - loss: 0.1277 - accuracy: 0.9521 - val_loss: 0.0281 - val_accuracy: 0.9921
Epoch 9/20

Epoch 00009: LearningRateScheduler setting learning rate to 0.0008445946.
60000/60000 [==============================] - 16s 259us/step - loss: 0.1200 - accuracy: 0.9542 - val_loss: 0.0277 - val_accuracy: 0.9919
Epoch 10/20

Epoch 00010: LearningRateScheduler setting learning rate to 0.0007749935.
60000/60000 [==============================] - 16s 259us/step - loss: 0.1162 - accuracy: 0.9553 - val_loss: 0.0257 - val_accuracy: 0.9928
Epoch 11/20

Epoch 00011: LearningRateScheduler setting learning rate to 0.0007159905.
60000/60000 [==============================] - 16s 259us/step - loss: 0.1133 - accuracy: 0.9540 - val_loss: 0.0238 - val_accuracy: 0.9939
Epoch 12/20

Epoch 00012: LearningRateScheduler setting learning rate to 0.000665336.
60000/60000 [==============================] - 15s 257us/step - loss: 0.1068 - accuracy: 0.9560 - val_loss: 0.0234 - val_accuracy: 0.9933
Epoch 13/20

Epoch 00013: LearningRateScheduler setting learning rate to 0.0006213753.
60000/60000 [==============================] - 15s 258us/step - loss: 0.1075 - accuracy: 0.9562 - val_loss: 0.0230 - val_accuracy: 0.9934
Epoch 14/20

Epoch 00014: LearningRateScheduler setting learning rate to 0.0005828638.
60000/60000 [==============================] - 15s 257us/step - loss: 0.1054 - accuracy: 0.9556 - val_loss: 0.0222 - val_accuracy: 0.9932
Epoch 15/20

Epoch 00015: LearningRateScheduler setting learning rate to 0.0005488474.
60000/60000 [==============================] - 15s 258us/step - loss: 0.1025 - accuracy: 0.9556 - val_loss: 0.0230 - val_accuracy: 0.9942
Epoch 16/20

Epoch 00016: LearningRateScheduler setting learning rate to 0.0005185825.
60000/60000 [==============================] - 15s 258us/step - loss: 0.1047 - accuracy: 0.9544 - val_loss: 0.0205 - val_accuracy: 0.9942
Epoch 17/20

Epoch 00017: LearningRateScheduler setting learning rate to 0.000491481.
60000/60000 [==============================] - 15s 257us/step - loss: 0.0969 - accuracy: 0.9579 - val_loss: 0.0221 - val_accuracy: 0.9935
Epoch 18/20

Epoch 00018: LearningRateScheduler setting learning rate to 0.0004670715.
60000/60000 [==============================] - 15s 257us/step - loss: 0.0981 - accuracy: 0.9563 - val_loss: 0.0207 - val_accuracy: 0.9940
Epoch 19/20

Epoch 00019: LearningRateScheduler setting learning rate to 0.0004449718.
60000/60000 [==============================] - 15s 257us/step - loss: 0.0957 - accuracy: 0.9575 - val_loss: 0.0247 - val_accuracy: 0.9926
Epoch 20/20

Epoch 00020: LearningRateScheduler setting learning rate to 0.000424869.
60000/60000 [==============================] - 15s 258us/step - loss: 0.0956 - accuracy: 0.9574 - val_loss: 0.0191 - val_accuracy: 0.9943
<keras.callbacks.callbacks.History at 0x25b1b2d8288>


Log for model.evaluate on test data
[0.019068540751887485, 0.9943000078201294]

Strategy used:
Maxpooling and 1x1 convolution reduces the number of parameters. However, when I used maxpooling second time, the accuracy dropped significantly. So I just reduced the number of channels in 7th convolutional layer from 16 to 10 and I crossed validation accuracy benchmark of 99.4% in 15th epoch. My test accuracy is also above 99.4% benchmark.
