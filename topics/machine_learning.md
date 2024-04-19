## Introduction

Abstrac and formal problems, easily described by formal and mathematical rules, are usually difficult for human beings to solve, but straightforward for computers. However, intuitive problems, difficult to describe formally, are easy for humans to solve, but difficult for computers because it's difficult to articulate them formally. A solution to intuitive problems is to allow computers to learn from experience and understand the world in terms of a hierarchy of concepts, with each concept defined in terms of its relation to simpler concepts. This allows the computer to learn complicated concepts by building them out of simpler ones (**deep learning**). By gathering knowledge from experience, we avoid the need for human operators to formally specify all of the knowledge that the computer needs. Human's life require an immense amount of amount of knowledge about the world, which is subjective and intuitive, and therefore difficult to articulate formally. Computers need to capture this same knowledge in order to behave intelligently.

**Knowledge base approach:** Many AI projects (like Cyc) tried to hard-code knowledge about the world in formal languages, but none of them led to a major success.

**Machine learning (ML):** AI capability of acquiring its own knowledge by extracting patterns from raw data. Examples: logistic regression (for recommending cesarean delivery), Bayes (for separating spam emails). 
  - Logistic regression: Its performance depends heavily on the **representation** of data (set of chosen features extracted from data). Each piece of data included in the representation is a **feature**. It learns how each feature correlates with various outcomes. However, sometimes it's difficult to know what features to extract (e.g. how to describe how a chair looks like in pixel values?).

**Representation learning (RL):** Machine learning approach that discovers not only the mapping from representation to output, but also the representation itself (i.e. to discover a good set of features). This improves performance and allows quick adaptation to new tasks. Example: autoencoder (it converts input data into different representation [encoder] and converts it back in the original format with new properties [decoder], preserving as much information as possible). The features should separate the **factors of variation** that explain the observed data (color, position, shape...), which refer to separate sources of influence not usually combined by multiplication. Factors are often not directly observed quantities (invisible forces, abstractions that explain observed data in a simpler way, etc.). However, often, many factors influence every piece of data (the color depends on the amount of light, the shape depends on the viewing angle...), so we need to disentangle the factors and discard those that we don't care about. Sometimes it's very difficult to extract such high-level, abstract features from raw data to obtain a representation.

**Deep learning (DL) or Artificial neural networks (ANNs):** Machine learning approach that solves the problem of representation learning (of getting a disentangled representation) by introducing representations expressed in terms of other, simpler representations. It builds complex concepts (high abstractions) out of simpler concepts (lower abstractions). It studies models that involve a greater amount of composition of learned functions or learned concepts than traditional machine learning does. Examples: 
- The complex concept of a human image is represented by combining simpler concepts (corners, contours...), which are in turn defined in terms of even simpler concepts (edges...). 
- **Multilayer perceptron (MLP) (or Feedforward deep network):** Mathematical function mapping some set of input values to output values. This function is composed by many simpler functions, each one providing a new representation of the input.
Furthermore, depth allows the computer to learn a multi-step program, where one layer is executed after another. The more depth, the more sequential instructions. This helps the model organize its processing.

There are 2 main ways of measuring the depth of a model:
- Depth of the computational graph: Number of sequential instructions executed to evaluate the architecture. Length of the longest path through a flow chart describing how to compute each of the model's outputs given its inputs. It may vary between 2 equivalent programs. 
- Depth of the probabilistic modeling graph: Graph of the concepts. 
The first may be much deeper than the second because the flowchart of the computations needed to compute the representation of each concept may be much deeper (detect eye > detect face > detect second eye in the shadow) than the graph of the concepts (detect eyes > detect face). This is so because the system's understanding of the simpler concepts can be refined given information about the more complex concepts.

Sets and subsets:
AI:[ML:[RL:[DL:[...], ...], ...], ...]


## Applied math

### Linear algebra

**Scalar:** It's a single number. 
**Vector:** It's an array of numbers (represented as a column enclosed in brackets), each one identified with one index. We can consider it a point in space (each element is the coordinate along a different axis). 
- **Set** of elements x<sub>1</sub>, x<sub>3</sub> and x<sub>6</sub> = S = {1,3,6} = x<sub>S</sub>. 
**Complement** of a set. Examples: x<sub>-2</sub> = vector x without element 2.  x<sub>-S</sub> = vector x without set S. 
A **matrix** is a 2D array of numbers, each one identified 2 indices (height/row m, width/column n)
- A<sub>i,j</sub> = element at position (i,j) | A<sub>m,n</sub> = bottom right entry
- A<sub>i,:</sub> = all numbers with vertical coordinate i (use : to refer to all elements in that line)
**Tensor:** Array with more than 2 axes.
- A<sub>i,j,k</sub> = element at position (i,j,k)




















