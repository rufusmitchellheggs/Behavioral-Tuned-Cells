# Behavioural-Tuned-Cells

Whose behavior? Ca2+ imaging in medial prefrontal cortex during social dominance interactions in a Tube-Test (accompanying code)

In this repository you can find the classification pipeline used to identify behaviourally tuned neurons.

<img width="511" alt="image" src="https://user-images.githubusercontent.com/38789733/156197726-d5835942-f7b2-4f5e-ae58-9af03e07f482.png">

### Methodology:
Each neural event train (as desribed in the paper) was convolved with a Gaussian function (σ  = 12.5ms, window width of 2σ) to obtain a time series of instantaneous firing rates.  The Kraskov Mutual Information Score (MIS) was then calculated independently between each neuron and each behavior (sklearn.feature_selection.mutual_info_classif).  Neurons were classified as encoding a specific behavior during a session (i.e. 5 trials) if they met the following criteria: (1) calcium transient events were present in over 33% of the behavioral occurrences, (2) the cell achieved a MIS greater than chance. Chance-level mutual information for a cell was determined by performing 2,000 shuffles of a cells event train and calculating the mutual information between each shuffled event train. The cell was considered as encoding a specific behavior cell if its MIS exceeded the 95th percentile of the values for the shuffled data.

### Behaviors considered:
1. MOVE FORWARD
2. PUSH
3. RESISTANCE
4. RETREAT
5. STILLNESS
6. WITHDRAWAL
