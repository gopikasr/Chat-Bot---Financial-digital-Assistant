# Chat-Bot--Financial+digital-Assistant
A Chat Bot which can work as  a FINANCIAL + DIGITAL ASSISTANT CHATBOT using DEEPLEARNING & NATURAL LANGUAGE PROCESSING. And I proposed a name for the Chat Bot as Fin-Bot.

# (i)	Digital Assistant-> The chat bot is a perfect digital assistant in an e-commerce website to guide you through our shop by telling you the products available, the place with which the shop is located, the costs of the products etc- Its main speciality is "THIS CHATBOT WILL BARGAIN WITH THE CUSTOMER FOR A PRODUCT FOR THE COMPANY". 

# (ii)	Financial Assistant -> The chat bot can also answer you if you ask some terms in Financial Market, this will equip you so that you will get answer to the point. I have trained for about about 40 frequently used but so relevant terms in financial and Economic Market.(For eg: bitcoin, bank, crowd funding, real interest rate, liquidity etc-)
# DATA
I created the dataset manually. For building a Chat Bot intent recognition is one
of the important thing. The chat bot should understand what the customer or the person is saying
and it should match it correctly with the corresponding tag which have the possible responses of
the question / comment the customer said.
I used a dictionary format and named it as data and its stating large dictionary is “intents” where I
added 4 subparts in the dictionary format itself namely “tags” , “patterns”, “responses” and
“context set”. The tags are basically to identify the intent. So, if a customer asks “when will the
shop be open?”, the Chat Bot will connect it to the tag: “time”. This tag contains several possible
answers in the responses inside the tag. After recognizing the tag, the Chat Bot will choose any
one of the responses randomly from the “responses” in the corresponding “tag”. So, this is the
idea.
In the above format I have manually created 47 tags with each having 4 or 5 patterns and responses.
In the patterns, I added the possible questions that the customer might ask on the basis of the tag I defined. In the responses, I put the possible answers or comments
that I need my Chat Bot to give back to the customer according to the tag. 


# The strategy is as follows:

# (i)Preprocessing using Natural Language Processing(NLP)
Once the Fin-Bot gets the input from the customer. It will first tokenize the sentence. Tokenizing
helps us to break down our big sentence to small tokens/individual meaningful words. So, if the
input is “Hey who are you?”, then after tokenization it becomes [“Hey”, “who”, “are”, “you” “?”].
Next step is making all the letters into lowercase in the tokenized words. So, in the above given
sentence, after making all into lower case it becomes [“hey”, “who”, “are”, “you”, “?”].
Next step, we need stem the words. Next is making the words into lower case and then stemming.
Stemming means to find the root word. Suppose we have two seperate words "eating" and "eaten",
then after stemming all of them is just "eat". So, the above sentence after stemming also, gives
[“hey”, “who”, “you”, “?”] since these words don’t have much to stem.
Next step is removing punctuation marks from the array. Then the above array becomes [“hey”,
“who”, “are”, “you”].
Now, then we convert the sentence to a bag of words (BOW). Bag of Words (BOW) method is
below. It is a famous method in NLP for simplifying the given sentence. The sentence is being represented as the bag of its words. Here, Grammar and word order won't be taking into account.
So, BOW is a collection/group of words to represent a particular sentence with word count.
We can demonstrate it as follows:- Suppose the array of all the possible words we defined is
[“Hey”, “who”, “are”, “you”, “bye”, “hope”, “to”, “see”,“later”]
So the tokenized sequence [“Hey”, “who”, “are”, “you”] can be represented with respect to the
all the word is a bag [1, 1, 1, 1, 0, 0, 0, 0, 0]. (If that word is present at that particular position
all words, then give one, else give zero.

# (ii)MODEL: Deep Learning model using PyTorch
I used PyTorch. The neural network is a feed forward neural net with two hidden layers. This
feed forward neural network will take the bag of words that we created above as input. Then
there is 3 fully connected linear layers (FC), in which first one layer has the no of different
patterns as the input size. And then the others are two hidden layers.
And then the output layer where output size is same as the no of different classes. Then, applying
the softmax function for the output gives probabilities for each classes. I also added batch
normalization between the layers for better accuracy. Input size=209 and the hidden size=8 and
the output size=47[no of classes/no of tags]. 

# (ii)TRAINING
The no of parameters in the model are 2207 which can be easily calculated from the model using
weights and biases(consider Batch normalization too with other layers).
The input sequence after preprocessing using NLP will be trained using the PyTorch model
described above. The optimizer used is Adam and the Loss function is Cross entropy Loss. The final accuracy after training is about 96% and I ran for 1000 epochs. (May be using Batch
Normalization would be reason for getting good accuracy and more data).

# (iii)INCORPORATING BARGAINING TASK
The bargaining offer is only allowed for one product which is of 30 Rs in the ecommerce
website. It is clearly possible to
make the Chatbot Bargain for several other products in the similar way I incorporated this
bargaining task for one product.

# End Result
The Chat Bot worked pretty nicely. The training accuracy was about 96 % and it varies in range
of 94%-96%. Also, it worked perfectly. Since, I trained it for about 42 tags and also I have included
the terms used in financial market to the Chat Bot. So, when I ask it about some terms, it replies by randomly choosing one response form the “responses” after preprocessing using NLP and
training with PyTorch Neural Network. 

# All other details and the theoretical frame work is given in detail in the following article/publication in medium.
“A FINANCIAL + DIGITAL ASSISTANT CHATBOT(Fin-Bot) using DEEP LEARNING & NATURAL LANGUAGE PROCESSING” by Gopika S R 
https://link.medium.com/pVJwtcyiRcb




