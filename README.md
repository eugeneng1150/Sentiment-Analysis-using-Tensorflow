# Sentiment-Analysis-of-Amazon-products

# 1. Data Cleaning
 - Removed HTML tags using regular expressions.
 - Expanded contractions (e.g., "don't" to "do not") for better processing.
 - Removed punctuation to simplify text analysis.
 - Converted all text to lowercase for uniformity.

# 2. Tokenization
 - Removed stopwords (e.g., "the", "is", "and") that do not contribute to sentiment.
 - Applied lemmatization to reduce words to their base form (e.g., "running" to "run").
 - Created word clouds to visualize frequent words in positive and negative reviews.

# 3. Vectorization
 - Transformed text data into numerical format using TF-IDF (Term Frequency-Inverse Document Frequency).

# 4. Model Training
 - Used a Dense layer with 64 neurons with a dropout rate of 0.50, achieved an accuracy of 82% on the test set.

# 5. Hyper Parameter Tuning using keras_tuner
 I performed hyperparameter tuning in two stages using keras_tuner:

 - Stage 1: Tuned the number of units in the first dense layer, the activation function, and the dropout rate. The final output layer was fixed with 3 neurons and a softmax activation function for multi-class classification.

 - Stage 2: Tuned the optimizer (choosing between Adam and SGD) and the learning rate to find the most effective training configuration.

# 6. Final Model building
 - Using the best hyperparameters obtained from tuning, I built the final model. However, the accuracy achieved was 80%, which was lower than the initial model trained without tuning.
 - Upon analyzing the accuracy and validation curves, it became evident that the model was overfitting—performing well on training data but poorly on validation data.

# 7. Future considerations
- Apply L1/L2 regularization:  Penalizes large weights in the loss function.
- Early Stopping: Stops training when validation performance stops improving.
- Batch Normalization: Normalizes layer inputs, helping stabilize and generalize training.
