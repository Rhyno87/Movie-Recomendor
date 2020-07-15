# Movie-Recomendor
## Using recurrent neural network in Keras to classify a movie review

In this Capstone Project, sentiminent analsis (Natural Language Processing) is done using recurrent neural networks in Keras to try and classify a movie review as either positive or negative. This task proceeds using the following steps:
1. Get the dataset
2. Preprocessing the Data
3. Build the Model
4. Train the model
5. Test the Model
6. Predict Something

Keras will be used to import built-in IMDb movie review . This dataset contains a collection of 50,000 reviews from IMDb and contains an even number of positive and negative reviews. A negative review has a score ≤ 4 out of 10 (label = 0), and a positive review has a score ≥ 7 out of 10 (lable =1). Neutral reviews are not included in the dataset.

### Get the dataset
You can now load the dataset using the load_data function.
If you look at the data once loaded you will realise that it has been already
pre-processed. All words in a review have been mapped to integers.
These integers represent the words sorted by their frequency. So 4 represents the
4th most used word, 5 the 5th most used word and so on. The integer 1 is reserved
for the start marker, the integer 2 for an unknown word and 0 for padding. The
label is also an integer (0 for negative, 1 for positive).

### Preprocessing the Data
In order to feed this data into our RNN, all input (reviews) must have the same length. Since the reviews lengths differe, the review needs to be trimmed to its first 500 words. If reviews are shorter than 500 words, padding them with zeros is required.
The data set is split into training and testing data subsets. The code below checks the size of these training and testing data sets after preprocessing.

### Build the Model
We can now build our model. Deep learning text classification model architectures
generally consist of the following components connected in sequence.
In summary, the model created is a recurrent neural network (RNN) with one embedding, one LSTM layer and 1 dense layer (due to binary outcome). 

### Train the model

To train the model, it first has be complied by indicating the loss function, optimizer and valuation metric we are measuring, to use to train the model. Once complied, the training is has to be completed with specified number of training epochs and batch size. Binary crossentropy is used as the loss input due to the outcome being binary i.e. positive or negative.

### Test the Model
After training the model go ahead and test the model. Check the accuracy of your
model. If low, check what values you can tweak in order to increase the accuracy.

### Prediction

To use the model to predict that a sentence is positive or negative, the sentence has to be converted to the respective word integers and then padded to match the data. This is then in the correct format to be inputted into the model.
