# Building a Spam Filter with Naive Bayes
 The multinomial Naive Bayes algorithm is used along with a dataset of 5,572 SMS messages that are already classified by humans to build a spam filter

This project is about building a spam filter for SMS messages using the multinomial Naive Bayes algorithm. The goal is to classify messages as either spam or ham (non-spam).

The project involves several steps:

- Data Cleaning: The SMS messages are cleaned by removing punctuation and converting all words to lowercase.
- Creating a Vocabulary: A vocabulary is created by extracting unique words from the cleaned messages.
- Calculating Constants: The constants required for the Naive Bayes algorithm, such as the probabilities of spam and ham, are calculated using the training set.
- Calculating Parameters: The parameters for each word in the vocabulary are calculated using the training set.
- Classifying New Messages: A function is created to classify new messages as spam or ham based on the calculated parameters and constants.
- Measuring Accuracy: The accuracy of the spam filter is measured by applying it to a test set of messages and comparing the predicted labels with the actual   labels.

The spam filter achieves an accuracy of approximately 98.74% on the test set. 

Potential next steps: 
- analysing incorrectly classified messages 
- making the filtering process more complex by considering letter case.

The Naive Bayes algorithm will need to know the probability values of the two equations below to be able to classify new messages:


\begin{equation}
P(Spam | w_1,w_2, ..., w_n) \propto P(Spam) \cdot \prod_{i=1}^{n}P(w_i|Spam)
\end{equation}

\begin{equation}
P(Ham | w_1,w_2, ..., w_n) \propto P(Ham) \cdot \prod_{i=1}^{n}P(w_i|Ham)
\end{equation}


Also, to calculate P(w<sub>i</sub>|Spam) and P(w<sub>i</sub>|Ham) inside the formulas above, we'll need to use these equations:

\begin{equation}
P(w_i|Spam) = \frac{N_{w_i|Spam} + \alpha}{N_{Spam} + \alpha \cdot N_{Vocabulary}}
\end{equation}

\begin{equation}
P(w_i|Ham) = \frac{N_{w_i|Ham} + \alpha}{N_{Ham} + \alpha \cdot N_{Vocabulary}}
\end{equation}
