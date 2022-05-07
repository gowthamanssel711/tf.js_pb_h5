# tf.js_pb_h5


## tfjs converter library
>  [Library Doc](https://github.com/tensorflow/tfjs/tree/master/tfjs-converter#getting-started)


### Convert Model

#### Package

`$  pip install tensorflowjs[wizard]`

#### Execute command

Note : output directory should not exists (h5_mod).

    tensorflowjs_converter --input_format=tfjs_layers_model --output_format=keras C:\Users\gwt1cob\Downloads\tf_m\model.json C:\Users\gwt1cob\Downloads\tf_m\out\h5_mod
    

It will convert to .pb model 

### Convert .pb to .h5

```
import os
import tensorflow as tf
from tensorflow.keras.preprocessing import image

pb_model_dir = "out/h5_mod"
h5_model = "./mymodel.h5"

# Loading the Tensorflow Saved Model (PB)
model = tf.keras.models.load_model(pb_model_dir)
print(model.summary())

# Saving the Model in H5 Format
tf.keras.models.save_model(model, h5_model)

# Loading the H5 Saved Model
loaded_model_from_h5 = tf.keras.models.load_model(h5_model)
print(loaded_model_from_h5.summary())

```
