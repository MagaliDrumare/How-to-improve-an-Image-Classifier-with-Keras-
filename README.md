
# A voir et à Savoir : 
#### Keras est une API écrite en python qui tourne sur tensorflow. Une boîte à outils pour le "deep learning" qui permet de réduire la compléxité des algorithmes et rendre la discipline plus accessible. 
* Keras website : API, written in Python and capable of running on top of TensorFlow http://keras.io
* The Keras workflow, expanded (TensorFlow Dev Summit 2017), François Cholet: https://youtu.be/UeheTiBJ0Io

#### Comment améliorer un simple Neural Network avec Keras? 

#### Première version du modèle avec un seul hidden layer 

```
model = Sequential()
model.add(Dense(N_HIDDEN, input_shape=(RESHAPED,)))
model.add(Dense(NB_CLASSES))
model.add(Activation('softmax'))
model.summary()
````

#### Modifier la structure: augmenter la taille du réseau de neurones en ajoutant des 'Hidden Layer'. Les layers sont appelés "cachés" car ils ne sont pas connectés directement aux inputs ni aux outputs. 

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

#### Technique de régularisation du Dropout : 
- Le Dropout est une technique de régularisation pour lutter contre le surapprentissage (overfitting). 
Il s'agit de désativer un % de neurones du réseau au hasard à chacune des itérations.
- Understanding Dropout : https://youtu.be/3gWFv_W1GVc (by Andrew Ng)

```
DROPOUT =0.3 (30% des neurones sont activés arbitrairement. Lorsque DROPOUT =1, il n'y a pas de désactivation)
model = Sequential()
model.add(Dense(N_HIDDEN, input_shape=(RESHAPED,)))
model.add(Activation('relu'))
model.add(Dropout(DROPOUT))
model.add(Dense(N_HIDDEN))
model.add(Activation('relu'))
model.add(Dropout(DROPOUT))
```
#### Choisir la bonne méthode d'optimisation (Optimizers) : 
- Keras permet d'implémenter au choix trois optimizers différents : SDG (stochastic gradient descent); RMSProp et Adam.
- The Evolution of Gradient Descent : https://youtu.be/nhqo0u1a6fw (by Siraj Raval)

```
# Stochatic Gradient Descent: OPTIMIZER = SGD()
# RMS : OPTIMIZER = RMSprop()
# Adam : OPTIMIZER = Adam()
```

#### Autres méthodes d'amélioration : modifier les Hyper-paramètres (hyperparameters)
- NB_EPOCH : Augmenter le nombre d'épochs (augmenter le temps de computation) 
- Modifier le learning rate (0.1, 0.01, 0.001, 0.0001) 
- N_HIDDEN : Augmenter le nombre de neurones des "Hidden Layer" (128,256,512,1024)
- BATCH_SIZE = 128 : Changer la taille du l'échantillon Batch_size (32,64,128,256,512)

