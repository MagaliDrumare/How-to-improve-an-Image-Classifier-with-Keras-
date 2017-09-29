
# A voir et à Savoir : 
#### Keras est une API écrite en python qui tourne sur tensorflow. Une boîte à outils pour le "deep learning" qui permet de réduire la compléxité des algorithmes et rendre la discipline plus accessible. 
* Keras website : API, written in Python and capable of running on top of TensorFlow http://keras.io
* The Keras workflow, expanded (TensorFlow Dev Summit 2017), François Cholet: https://youtu.be/UeheTiBJ0Io

# Comment améliorer un modèle? 

* Première version du modèle avec un seul hidden layer 

```
model = Sequential()
model.add(Dense(N_HIDDEN, input_shape=(RESHAPED,)))
model.add(Dense(NB_CLASSES))
model.add(Activation('softmax'))
model.summary()
````

* Modifier la structure: augmenter la taille du réseau de neurones en ajoutant des 'Hidden Layer'. Les layers sont appelés "cachés" car ils ne sont pas connectés directement aux inputs ni aux outputs. 

```
model = Sequential()
model.add(Dense(N_HIDDEN, input_shape=(RESHAPED,)))
model.add(Activation('relu'))
model.add(Dense(N_HIDDEN))
model.add(Activation('relu'))
model.add(Dense(NB_CLASSES))
model.add(Activation('softmax'))
model.summary()

Amélioration = an additional 2.2% accuracy on the test
```

* Technique du Dropout : 
-Le Dropout est une technique de régularisation pour lutter contre le surapprentissage (overfitting). 
Il s'agit de désativer un % de neurones du réseau au hasard à chacune des itérations.
-Understanding Dropout : https://youtu.be/3gWFv_W1GVc (by Andrew Ng)

```
DROPOUT = 0.3 (30% des neurones seront activés arbitrairement/ si DROPOUT=1, 100% des neurones sont activés)
model = Sequential()
model.add(Dense(N_HIDDEN, input_shape=(RESHAPE
