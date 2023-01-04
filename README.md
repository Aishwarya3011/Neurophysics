# Neurophysics: Unsupervised Machine Learning for neural behavior quantification

## Data:

The data for this project is a .mat file which has been protected for privacy reasons. Here is a gist of the data and the analysis.

1. Rat walks on an elevated table to get food.
2. 12 trials done on different rats.
3. Position (x, y) of a rat across n observation time points.
4. Direction of a rat (in radians) across n observation time points.
5. Number of firing neurons per trial.
6. Spike time per neuron per experiment.

## Objective:

1. Spike time position relative to rat’s position.
2. Probability of spikes as a function of direction (-180 to +180 degrees).
3. Clusters identifying neuron’s firing patterns.  
4. Grouping neurons that fire together for a given stimuli.
5. Repeated across different trials and different neurons in each trial. 

## Implementation:

### 1. Spike time position relative to rat’s position

- Spikes were recorded before the movement began and after the movement stopped.
- Rat was thinking something before the movement and after stopping.
- Clip all entries that occurred before, after the actual recording.
- Spike times do not match observation times.
- Relative position at the time of the spike approximated to mean position for observation time immediately less than, greater than a given spike time.

### 2. Probability of spikes as a function of direction

- Clip all entries that occurred before, after the actual recording.
- Spike times do not match observation times.
- Relative direction at the time of the spike approximated to mean direction for observation time immediately less than, greater than a given spike time.
- Gaussian Probability Density Function as line plot of direction (in degrees) vs relative frequency of spikes (rfs).
- On an average, max firing occurred in the direction range -50 to 50 degrees. 

### 3. Clusters identifying neuron’s firing patterns

- Unsupervised learning for clustering.
- K-means clustering using cluster size of 5.
- Cluster plotting with different shapes and colors of markers to identify various clusters.
- Cluster centroids marked with red stars.

### 4. Grouping neurons that fire together for a given stimuli 

- Compare the distance between the centroids of various clusters of different neurons.
- Sort the values to determine cluster centroids closest to one another.
- Pair the neurons with the closest centroids and form an adjacency matrix.



