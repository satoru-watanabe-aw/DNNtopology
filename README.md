# Overview
This repository publishs the source codes used in the paper "Topological Measurement of Deep Neural Networks Using Persistent Homology." It includes four Python notebooks. 
* makeModelMNIST.ipynb
* makeModelCIFAR10.ipynb
* makeSimplex.ipynb
* drawDiagram.ipynb

### makeModelMNIST.ipynb, makeModelCIFAR10.ipynb
These notebooks train models on the MNIST and CIFAR10 data sets and store models in "models" directory.

### makeSimplex.ipynb
This notebook constructs simplexes on the trained models stored in "models" directory and outputs the results to "simplexes" directory.

### drawDiagram.ipynb
This notebook draws persistent homology diagrams using Dionysus library using the files in "simplexes" directory.

![PHdiagram](https://user-images.githubusercontent.com/61130343/75102558-beef6380-5630-11ea-8a13-94c985f92fe8.png)

# Usage
The notebooks are developed for the execution in Google Colaboratory.
The first cells of the notebooks mount Gdrive, comment them out if unnecessary.

The configuration file (requirements.txt) is provided, which was generated with "pip freeze" command.

## Paramenter setting in notebooks 

### makeModelMNIST.ipynb and makeModelCIFAR10.ipynb

They have four parameters for specifing the input data and network structures.
* class_list 
* firstLayerSize 
* secondLayerSize 
* outputNeuron 

"class_list" restricts the input data to the classes.
For example, class_list = [0, 1, 2, 3, 4] restricts the input data to the five classes.
"firstLayerSize", "secondLayerSize", and "outputNeuron" specifies the number of neurons in the models.

### makeSimplex.ipynb
This notebook has seven parameters for constracting simplexes from the training models.

* layerNumber
* layerNumber1
* layerNumber2
* firstLayerSize
* secondLayerSize
* outputNeuron
* class_list

(0, 1, 2) and (13, 15, 16) are used for (layerNumber, LayerNumber1, layerNumber2) in the MNIST and CIFAR-10 data set, respectively.

"firstLayerSize", "secondLayerSize", "outputNeuron", and "class_list" are to be set the same parameters in the notebook that generated the model.

### drawDiagram.ipynb
This notebook inputs 64 files generated by "makeSimplex.ipynb" from "simplexes" directory. 

# Sample data

### drawDiagram.ipynb
Sample data enable drawDiagram.ipynb to work without other notebooks.

"simplexes/sample" directry has 64 files generated by makeSimplex.ipynb.
A persistent homology diagram is drawn by changing the input directory to "simplexes/sample" in drawDiagram.ipynb.


### makeSimplex.ipynb
Sample models enable makeSimplex.ipynb to work without makeModel notebooks.

"models" directory has a sample model generated by makeModelMNIST.ipynb.
The notebook can work by chaninging the "model_name" parameter to the sample model name.
