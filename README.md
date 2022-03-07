# CNN-Algorithm

CNN is a very famous and successful algorithm to do natural language processing. So we plan to use the CNN algorithm to predict the score of new commodities.

First, in terms of data processing, we clean the text in the review, normalize text, unify all text into lowercase letters, and remove punctuation and stop words. The data types of user ID and item ID are strings and cannot be used directly. We convert them to integers and sort them.

After data processing, we take following data:

• User ID

• Item ID

• Rating

• User review

• Item review

Second, we build the CNN model. We created two input layers, item review and user review. Here we have two input layers, item review and user review. The reason for this is simple, adding an item review input layer can increase accuracy. The reason for the better results may be the increase in the dimension of the word vector.

Then we need to convert the text into a matrix. This process is obtained through the Global vectors for word representation model(GloVe). There are two main types of learning word vector representation methods: one is based on global matrix factorization, such as Latent Semantic Analysis(LSA), and the other is a local context window method, such as the CBOW and skip-gram methods proposed by Mikolov in 2013. However, these two methods have their own shortcomings. Although LSA effectively uses statistical information, it is very poor in terms of vocabulary analogy, while CBOW and skipgram can perform vocabulary analogy very well, but because of these two The method is based on a local context window method, therefore, it does not make effective use of global lexical co-occurrence statistics. GloVe combines the advantages of matrix decomposition Latent Semantic Analysis’s global statistical information and the advantages of local context window. Incorporating global prior statistical information can speed up the training of the model and control the relative weight of words.

The converted matrix passes through the convolutional layer, pooling layer, fully connected layer, and to the output layer. Fig shows us the structure of CNN.

![CNN Model Fig]()

In the present work we have described a series of experiments with convolutional neural networks built on top of GloVe. Despite little tuning of hyperparameters, a simple CNN performs remarkably well. Our results prove an accepted fact that CNN is an indispensable algorithm in the ﬁeld of natural language processing.