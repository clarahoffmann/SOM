# <p align='center'>Measuring similarity of German politician's tweets with self-organizing maps</p>

# Results

<p align="center">
<img src="https://github.com/clarahoffmann/SOM/blob/master/postmodel3d.png" />
</p>

* The top German politicians don't have a party-specific style when they're campaigning for elections
* After the election some winning parties (CDU \& AfD) exhibit similar tweet styles. They align in a cluster together.
* The members of the SPD strongly change their tweeting style after their bad election result. They decluster with other parties.

# Algorithm
The algorithm described by Kohonen (1990) works as follows:

0. Define a two- or three-dimensional of neurons i and assign every neuron a coordinate in the feature space (also called weight vector). We can assign the weight vector randomly in the cube spanned by the min and max value of all features. Alternatively, we can span the grid in the space spanned by the largest two eigenvectors (principal components).

1. Choose one data point at a time -- either systematically or randomly. If the number of observations is really small, we can use bootstrapping to make sure we reach the necessary number of iterations

2. Compute the Euclidean distances from the data point to each neuron.

3. Identify the neuron with the smallest distance to the data point. This is the best matching unit (BMU).

4. Update the coordinates of the BMU and the neurons using a neighborhood function (f.e. gaussian, bubble, etc.)
The learning rate in the neighborhood function determines how much the position of neurons change iteration and decreases with time. 

5. Start again with 1. until you reached the desired amount of iterations. 
