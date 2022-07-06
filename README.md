# Some Tips：

## 一. 实现VGG13的几种方法

- #### 方法一：

  通过两个`tf.keras.Sequential`来分别完成卷积部分和全连接部分，然后通过`tf.GradientTape`求导完成整个网络过程的训练。

- #### 方法二：

  通过已有的`Conv2D(),Flatten(),Dense()`构造一个`tf.keras.Sequential`来完成整个网络的前向传播过程，然后通过`model.fit`来完成整个网络的训练。**一般需要实现的网络所用到的网络层在tensorflow中已经被实现（或者自己按照tensorflow的接口标准实现），则可以通过这种方法来实现网络的构建**

- #### 方法三：

  通过自定义一个`tf.keras.Model`类来实现整个网络的前向传播过程，然后通过`model.fit`来完成整个网络的训练。**在设计自己的网络时，通常采用这一方法。**



## 二. Tensorflow Usage

- #### 用法示例索引

  - ##### 1-全连接层用法

    - `tf.keras.layers.Dense(),tf.keras.Sequential()`
    - `tf.losses.categorical_crossentropy(from_logits=Trye)`<==>`tf.nn.softmax_cross_entropy_with_logits()`

  - ##### 2-Tensorboard可视化

    - `tf.summary.create_file_writer()`

  - ##### 3-通过Keras高级API进行网络训练

    - `model.build(),model.compile(),model.fit(),model.evaluate()`
    - `tf.keras.losses.CategoricalCrossentropy()`

  - ##### 4-自定义Layer层并通过`keras.Sequential`进行训练

  - ##### 5-自定义Layer层并通过自定义Model搭建模型

  - **6-模型的加载与保存**

    - `model.save_weights(),model.save(),tf.saved_model`

  - ##### 7-保存模型并完成追加训练

  - ##### 8-卷积层的使用

    - `tf.keras.layers.Conv2d(),tf.keras.layers.Flatten()`

  - ##### 9-BN层的使用

    - `tf.keras.layers.BatchNormalization()`