# MNIST-CNN

The CNN architecture has been trained on the MNIST Dataset for recognizing Hand written Digits, and the architecture has attained a consistent accuracy of **99.50%** with **9,722** Params and less than **15 epochs**.

The Final Model has been achieved with the series of changes:

### Step 1
#### Basic Working Model is setup 

Results

- Parameters : 6.3M
- Best Training Accuracy: 99.88%
- Best Test Accuracy: 99.36%

Analysis

- Extremely Heavy Model as it uses 6.3 Million Params for a simple MNIST Dataset.
- Model is over fitted on the traning set as the difference between training and test accuracy is high

### Step 2
#### Getting the Basic Skeleton of the Network Right

Results

- Parameters : 114.3k
- Best Training Accuracy: 99.45%
- Best Test Accuracy: 99.01%

Analysis

- Still the Model is Heavy but we got the skeleton right 
- Model is weaker than the previous model for sure as the accuracy at the first epoch is 66.44%.
- Model is sort of overfitted.

### Step 3
#### Making the Model Lighter

Results
- Parameters: 9.7k
- Best Training Accuracy: 99.15%
- Best Test Accuracy: 98.71%

Analysis
- The model parameters have been drastically reduced to 9.7k params.
- Model is overfitted.

### Step 4
#### Adding Batch Normalization to push the models accuracy

Results
- Parameters: 9.9k
- Best Training Accuracy: 99.69%
- Best Test Accuracy: 99.17%

Analysis
- The model efficiency is increased but the model is overfitted.
- We need to add some regularization


### Step 5
#### Adding Regularization to reduce the model overfitting

Results
- Parameters: 9.9k
- Best Training Accuracy: 99.29%
- Best Test Accuracy: 99.21%

Analysis:
- The Regularization worked as overfitting has been reduced now, as difference between training accuracy and test accuracy has been reduced.
- Still we are not able to achieve our target accuracy of 99.4, for that replacing a large sized kernel in the last layer with Global Average Pooling and compensating with another layer.

### Step 6
#### Replacing the Large Sized Kernel in the last layer with GAP and add a Conv layer to increase the model efficiency

Results
- Parameters: 9.7k
- Best Training Accuracy: 99.25%
- Best Test Accuracy: 99.37%

Analysis
- Still we are not able to achieve our target accuracy of 99.4, for that rotating the images in the training set randomly between (-7, 7) degrees.
- There is a high back and forth jittering at high epochs due to high learning rate, Adding a LR Scheduler helps in smooth convergence.

### Step 7
#### Adding Random Rotation Transform to the training data set and adding LR Scheduler to reduce the juggling after achieved the desired accuracy

Results
- Parameters: 9.7k
- Best Training Accuracy: 99.25%
- Best Test Accuracy: 99.50%

Analysis
- The Model with 9.7k params achieved the target accuracy of 99.4% at the 7th epoch and it consistently maintained 99.45% accuracy in the next epochs this shows that the LR Scheduler worked very well in convergence.
