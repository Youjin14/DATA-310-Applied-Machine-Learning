## Word Embeddings
1.Why is using one-hot encoding an inefficient towards vectorizing a corpus of words?  How are word embeddings different? (see this video https://www.youtube.com/watch?v=EEk6OiOOT2c )

One-hot ecoding is insufficient because a one-hot encoded vector is sparse (meaning, most indices are zero). "Imagine we have 10,000 words in the vocabulary. To one-hot encode each word, we would create a vector where 99.99% of the elements are zero." (TF Hub) Word embeddings, on the other hand, give us a way to use an efficient, dense representation in which similar words have a similar encoding. Additionally, we do not have to specify this encoding by hand. Word embeddings are created with dense vectors of floating point values (the length of the vector is a parameter you specify). Instead of specifying the values for the embedding manually, they are trainable parameters. 

2.Compile and train the model from the tensorflow exercise.  Plot the training and validation loss as well as accuracy.  Post your plots and describe them.

![training and validation loss](https://user-images.githubusercontent.com/67920289/88754931-f6a58e80-d12d-11ea-954a-2ec84af7ceea.png)

![training and validation accuracy](https://user-images.githubusercontent.com/67920289/88754941-ff966000-d12d-11ea-8bf2-a04ad62d8f6c.png)

With most training models, the tensorflow exercise training model increases in accuracy and the loss decreases with more epochs. On the other hand, the validation data has a loss that increases with a large spike and drop from the eighth to ninth epoch. However, the accuracy tended to stay consistant and was at a high 0.8-0.9 range. 

## Text Classification with an RNN
1.Again compile and train the model from the tensorflow exercise.  Plot the training and validation loss as well as accuracy.  Stack two or more LSTM layers in your model.  Post your plots and describe them

![ACCURACY](https://user-images.githubusercontent.com/67920289/88757763-c3b2c900-d134-11ea-85d1-389cf32a7319.png)

![LOSS](https://user-images.githubusercontent.com/67920289/88757775-cd3c3100-d134-11ea-89d7-bf4c0de5df13.png)

The training model performed better than the validation model (of course :) ) The accuracy and loss were consistant for the validation loss <- most likely because running through an already built model (rather than creating/adding more to the training model).
