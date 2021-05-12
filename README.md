# Quantum Nearest Neighbors


In this repository, I implement the quantum machine learning algorithm introduced in [this paper](https://arxiv.org/pdf/1412.3646.pdf) by [Maria Schuld](https://scholar.google.com/citations?user=_ih_hwUAAAAJ&hl=en), [Ilya Sinayskiy](https://scholar.google.co.za/citations?user=tL1_WfsAAAAJ&hl=en) and [Francesco Petruccione](https://scholar.google.com/citations?user=chM4fT4AAAAJ&hl=en).

The algorithm is proposed to solve **classification problems**: assign one out of a number of discrete classes to an observation, according to a rule learned from a set of labeled (classified) examples. Some examples of such problems are:

- Diagnosing a disease given a number of symptoms;
- Credit decision based on probability of default;
- An email being automatically marked as \'important\' or \'spam\';
- A handwritten digit on a postal envelope being recognised by a scanning device. 

We will be working in the **supervised learning** paradigm, in which we have data on both predictors and targets to learn from. 

A possible approach for classification is the following:

- Define some distance metric;
- Assign the new vector to the class whose members are most similar in terms of this distance (i.e., whose members are closest to it). 

A common distance measure is the Hamming distance, which is used when the features are encoded as binary strings. It is defined as the number of different bits, or components, among a pair of binary strings.

The **quantum nearest neighbors** algorithm is a quantum classification algorithm, which uses the aforementioned distance criterion for classification, based on Hamming distance. Schematically, the algorithm goes like:
  
- We first create a superposition of the training data set;

- Then write the Hamming distance between the input observation and each example in the training set into the amplitude of each vector in the superposition;

- Measuring the class-qudit then retrieves the desired class with the highest probability.

For more details on the algorithm, please see [this Notebook](https://github.com/andre-juan/quantum_nearest_neighbors/blob/main/quantum-nearest-neighbors_theory.ipynb). There, the points mentioned above are detailed and expressed in a more formal, mathematical way.

______________

This repo contains the following Jupyter notebook files:

- `quantum-nearest-neighbors_theory`: Notebook with markdown cells containing a detailed exposition of the algorithm. This serves both as a theoretical foundation as well as a reference for the implementation steps.
- `quantum-nearest-neighbors_theory.html`: Same notebook as the one above, but downloaded as a HTML file, as the LaTex doesn't seem to render correctly on GitHub.
- `quantum-nearest-neighbors_particular`: Python/Qiskit implementation of the algorithm for a particular case (4 training examples, 4 features each, 2 of each class). This notebook contains a step-by-step implementation, which is constructed and validated carefully. I recommend first understanding well this code, and then jump to the generic implementation in the notebook below.
- `quantum-nearest-neighbors_arbitrary`: Python/Qiskit implementation of the generic algorithm (arbitrary number of training examples and features). This implementation is more concise, and could be used directly in different datasets (some examples are provided in the end). 

