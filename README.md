# Star Point 1: Decision Tree
If you're gotten here and you still want more, we're providing this "star point" option. However, this is just a suggestion. Any significant extension or project will be considered for a star point. If you're interested, keep reading.

First, what is a "star point"? Star points are challenging, open-ended extensions designed to engage those who really want to learn more and go beyond the basic requirements. However, these are not extra credit. If you do "enough" star point and are "close enough" to the boundary, you may be moved up to the higher grade, but do these star point extensions because you are intellectually curious and want a challenge. Not for the grade. The course staff will not answer questions like "If I do this, will I get a star point?". If you are doing the star point extension just to get the star point, then you're doing it for the wrong reason. Only do it if you would be happy whether or not you get the point in the end.

This assignment's suggested star point extension is to learn about and implement a decision tree, which is a tree-structure used in machine learning. Here are the steps to completing this extension.

1. Learn about Decision Trees, including how they work, how to use them for classification, and how to build them from data. You can use any resources you like, but we recommend the following series of videos which provide a pretty good and concise introduction: http://bit.ly/D-Tree You should initially watch the first three videos in this sequence, and then optionally watch more, depending on how far you want to take your extension.

2. Implement a Decision Tree Classifier that can learn from data. At a minimum you should implement the ID3 algorithm without using information gain to select the best attribute to split. That is, it's OK to simply select attributes randomly. Of course you are free to be as sophisticated as you like with your decision tree learning. Your classifier must support at least the following two operations:
  * Learn from data: Given a data set, train the decision tree classifier to classify new examples with the same attributes of the training data.
  * Classify new example: Given a new example with the same attributes as the tree was trained on, output a decision.

  Note that it is fine to hard-code your decision tree for a single data set. You do not need to make it general purpose in terms of the attributes, but it must adapt to the data on which it is trained. Also, you can implement the above functionality however you choose, but make sure you explain your implementation sufficiently (see below).

3. Illustrate your Decision Tree in action. Train your decision tree on (a subset of) the data set of your choice and then use it to classify labeled examples from that data set on which it was NOT trained. Calculate the accuracy of its classifications. Here is one possible data set to use: http://archive.ics.uci.edu/ml/datasets/Mushroom, but you are free to use any other data set you want.

4. Write up your implementation and your results. This is the most important step, and without it you will not get any credit for this star point. Provide a writeup in a PDF or plain text file that describes the following:

 * The classes and functions you implemented and how they implement the functionality described above. Include how you selected the attributes to split on (whether you used random selection, or information gain) and if you included any pruning or other optimizations to improve the classifier.
 * Where to obtain the data that your decision tree can be trained/tested on
 * How to train your decision tree
 * How to test your trained decision tree on additional examples
 * The tests you ran and the accuracy of your decision tree on the test set

Again, the most important component of your star point is this writeup. We want to know that you really explored this topic and learned something. It's up to you to let us know that you did.

The starpoint will appear as a separate assignment on vocareum, Follow instructions shown in [ppt](https://docs.google.com/a/eng.ucsd.edu/presentation/d/1YetM0OgcJd5kezmThk_swNFq4O8iyjGqXoXrL5MxdW8/edit?usp=sharing) to create your github repo for the star point.
Note that the github repo for starpoint will be empty. Add all your code and write up and push it to github.
You can finally submit it using instructions as discussed earlier.
