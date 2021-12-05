# Image Steganalysis using Machine Learning Algorithms

What's this project about ?
-----------
steganalysis-ml is a steganalysis tool for detecting LSB Steganography in JPEG monochromatic images. Different machine learning classifiers were used to classify images in two classes: 'stego' and 'clean'.

Use the function 'stego_or_clean' in 'detect_stego.ipynb' file to analyze an image as an input.



![0_nCbBS1_pq9N5nDh4](https://user-images.githubusercontent.com/70814339/144764562-a8652667-46ea-47a8-9ab1-b62173f09707.png)

Machine Learning Classifiers:
-----------
In this project, five different classifiers were trained and tested using 70,000 images:
-   [Support Vector Machines (SVMs)](https://scikit-learn.org/stable/modules/generated/sklearn.svm.SVC.html)
-   [K-Nearest Neighbors](https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.KNeighborsClassifier.html)
-   [Random Forests](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html)
-   [Multilayer Perceptron](https://scikit-learn.org/stable/modules/generated/sklearn.neural_network.MLPClassifier.html)
-   [Naive-Bayes](https://scikit-learn.org/stable/modules/generated/sklearn.naive_bayes.GaussianNB.html)

Features Vector Extraction:
-----------
The features vector is 8 statistical measurements extracted from the histograms of the images:
- [Kurtosis](https://fr.wikipedia.org/wiki/Kurtosis#:~:text=En%20th%C3%A9orie%20des%20probabilit%C3%A9s%20et,la%20distribution%20d'une%20variable)
- [Skewness](https://en.wikipedia.org/wiki/Skewness)
- [Standard Deviation](https://en.wikipedia.org/wiki/Standard_deviation)
- [Range](https://en.wikipedia.org/wiki/Range_(statistics))
- [Median](https://en.wikipedia.org/wiki/Median)
- [Geometric Mean](https://en.wikipedia.org/wiki/Geometric_mean)
- [Hjorth Mobility](https://en.wikipedia.org/wiki/Hjorth_parameters#Hjorth_Mobility)
- [Hjorth Complexity](https://en.wikipedia.org/wiki/Hjorth_parameters#Hjorth_Complexity)

Dataset:
-----------
This is a dataset consisting of 8 features extracted from 70,000 monochromatic still images adapted from the Genome Project Standford's database, that are labeled in two classes: LSB steganography (1) and without LSB Steganography (0).

These features are Kurtosis, Skewness, Standard Deviation, Range, Median, Geometric Mean, Hjorth Mobility, and Hjorth Complexity, all extracted from the histograms of the still images, including random spatial transformations.

The steganographic function embeds five types of payloads, from 0.1 to 0.5.

You can find more details in the following link:

https://ieee-dataport.org/open-access/steganalysis-still-images-lsb-steganography-features-dataset

Training and Testing the Classifiers:
-----------
The five classifiers were trained with 56,000 images and tested with 14,000 images. Here are the accuracies of our classifiers:

Classifier     |   Train Set                  |   Test Set
:-      |   :-                      |    :-
SVMs       |   90.94           |   90.3
KNN       |   94.37         |   92.94
Random Forest*       |   98.4                 |   93.21
Multilayer Perceptron       |   92.6                  |   92.11
Naive-Bayes      |   89.84                   |   85.1

*: As we see, Random Forest Classifier has the best performance on the used dataset.

Future Work:
-----------
- This project will be soon extended to a Web Application for LSB Detection using all the five classifiers above.
- Due to the limited dataset, the classifiers don't perform well on high-resolution images as well as steganography techniques other than LSB Steganography. So the model needs a larger and more variant dataset to have wider use cases.

P.S:
  This is a Specific Steganalysis (LSB Steganography) and not a Blind Steganalysis.
