# transfer from ResNet50
```python
from keras.applications.resnet50 import ResNet50
from keras.preprocessing import image
from keras.applications.resnet50 import preprocess_input

# base on pretrained vgg
input_tensor = Input(shape=(155, 155, 3))
basemodel = ResNet50(include_top=False, weights='imagenet', input_tensor=input_tensor)
target_layer_name = basemodel.layers[17].name
target_layer = basemodel.get_layer(target_layer_name)
m = Model(inputs=basemodel.input, outputs=target_layer.output)
m.summary()
```
