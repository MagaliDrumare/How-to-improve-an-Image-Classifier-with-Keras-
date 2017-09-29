# How to improve a model with Keras 

* Première version du modèle avec un seul hidden layer 
```
model = Sequential()
model.add(Dense(N_HIDDEN, input_shape=(RESHAPED,)))
model.add(Dense(NB_CLASSES))
model.add(Activation('softmax'))
model.summary()
````

* Modifier la structure: augmenter la taille du réseau de neurones en ajoutant des 'Hidden Layer'. Les layers sont appelés "cachés" car ils ne sont pas connectés directement aux inputs ni aux outputs. 
'''
model = Sequential()
model.add(Dense(N_HIDDEN, input_shape=(RESHAPED,)))
model.add(Activation('relu'))
model.add(Dense(N_HIDDEN))
model.add(Activation('relu'))
model.add(Dense(NB_CLASSES))
model.add(Activation('softmax'))
model.summary()
```

* 


