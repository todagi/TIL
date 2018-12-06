## Keras install

1. Anaconda Prompt
```python

pip install keras 
```

2. Jupyter notebook
```python

!pip install keras
```

## Keras version check

```python
import keras

print('Keras Version : {0}.format(keras.__version__))

```

## Keras Sequential


1. a list of layer instances 

```python

from keras.models import Sequential
from keras.layers import Dense, Activation

model = Sequential( [ Dense(32, input_shape = (784, ) ),
                      Activation('relu'),
                      Dense(10),
                      Activation('softmax'),
                      ])

```

2. **.add()** method

```python

model = Sequential()
model.add(Dense(32, input_dim = 784))
model.add(Activation('relu'))
model.add(Dense(10))
model.add(Activation('softmax'))

```
