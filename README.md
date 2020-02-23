# Overview
This repository publishs the source codes used in the paper "Topological Measurement of Deep Neural Networks Using Persistent Homology." It includes four Python notebooks. 
* makeModelMNIST.ipynb
* makeModelCIFAR10.ipynb
* makeSimplex.ipynb
* drawDiagram.ipynb

### makeModelMNIST.ipynb, makeModelCIFAR10.ipynb
These notebooks make traind models on the MNIST and CIFAR10 data sets and store them in "models" directory.

### makeSimplex.ipynb
This notebook constructs simplexes on trained models stored in "models" directory and outputs the results in "simplexes" directory.

### drawDiagram.ipynb
This notebook draws persistent homology diagrams using Dionysus library using the files in "simplexes" directory.

![PHdiagram](https://user-images.githubusercontent.com/61130343/75102558-beef6380-5630-11ea-8a13-94c985f92fe8.png)

# Usage
The notebooks are developed for the execution in Google Colaboratory. 
They mounts gdrive in their first cells, comment them out if unnecessary.

## Paramenters 

### makeModelMNIST.ipynb and makeModelCIFAR10.ipynb

They have four parameters for specifing the input data and network structures.
* class_list = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
* firstLayerSize = 300
* secondLayerSize = 100
* outputNeuron = 10

"class_list" limits the input class in the data sets.
For example, class_list = [0, 1, 2, 3, 4] limits the input data to the five classes.
"firstLayerSize", "secondLayerSize", and "outputNeuron" specifies the number of neurons in the models.

### makeSimplex.ipynb
This notebook has seven parameters for constracting simplexes from the training models.
"firstLayerSize", "secondLayerSize", "outputNeuron", and "class_list" are to be set the same parameters in makeModelMNIST.ipynb or makeModelCIFAR10.ipynb.

* layerNumber
* layerNumber1
* layerNumber2
* firstLayerSize
* secondLayerSize
* outputNeuron
* class_list

(0, 1, 2) and (9, 11, 12) are used for (layerNumber, LayerNumber1, layerNumber2) in the MNIST and CIFAR-10 data set, respectively.

### drawDiagram.ipynb
This notebook inputs 64 files generated by "makeSimplex.ipynb" from "simplexes" directory, the directory name is a parameter of this notebook.

# Sample execution

### drawDiagram.ipynb
Sample simplex data enable drawDiagram.ipynb to work without other notebooks.

"simplexes/sample" directry has 64 files generated by makeSimplex.ipynb.
A persistent homology diagram is drawn by changing the parameter to "simplexes/sample" in drawDiagram.ipynb.


### makeSimplex.ipynb
Sample models enable makeSimplex.ipynb to work without makeModel notebooks.

"models" directory has sample models generated by makeModelMNIST.ipynb and makeModelCIFAR10.ipynb.
Sample executions are possible by specifing them in the "model_name" parameter in makeSimplex.ipynb.

