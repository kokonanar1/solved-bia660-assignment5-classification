Download Link: https://assignmentchef.com/product/solved-bia660-assignment5-classification
<br>
<h1>Classification</h1>

This assignment needs train.csv and test.csv. train.csv is for training and test.csv is for test. Both of them have samples in the following format:

<table width="0">

 <tbody>

  <tr>

   <td width="43"><strong>label</strong></td>

   <td width="355"><strong>text</strong></td>

  </tr>

  <tr>

   <td width="43">2</td>

   <td width="355">I must admit that I’m addicted to “Version 2.0…</td>

  </tr>

  <tr>

   <td width="43">1</td>

   <td width="355">I think it’s such a shame that an enormous tal…</td>

  </tr>

  <tr>

   <td width="43">2</td>

   <td width="355">The Sunsout No Room at The Inn Puzzle has oddl…</td>

  </tr>

  <tr>

   <td width="43">…</td>

   <td width="355">…</td>

  </tr>

 </tbody>

</table>

Write a function <strong>classify</strong> to conduct a classification experiement as follows:

<ol>

 <li>Take the training and testing file names (strings) as inputs, e.g. classify(training_file, testing_file).</li>

 <li>Classify text samples in the training file using <strong>Multinomial Naive Bayes model</strong> as follows:</li>

 <li>First apply grid search with <strong>5-fold cross validation</strong> to find the best values for parameters <strong>min_df</strong>, <strong>stop_words</strong>, and <strong>alpha</strong> of Naive Bayes model that are used the modeling pipeline. Use f1-macro as the scoring metric to select the best parameter values. Potential values for these parameters are:</li>

</ol>

min_df’ : [1,2,3]

stop_words’ : [None,”english”] alpha: [0.5,1,2]

<ol>

 <li>Using the best parameter values, train a Multinomial Naive Bayes classifier with all samples in the training file</li>

 <li>Test the classifier created in Step 2.b using the test file. Report the testing performance as:</li>

</ol>

Precision, recall, and f1-score of each label

Treat label 2 as the positive class, plot precision-recall curve and ROC curve, and calculate

AUC.

<ol start="4">

 <li>Your function “classify” has no return. However, when this function is called, the best parameter values from grid search is printed and the testing performance from Step 3 is printed.</li>

</ol>

<h1>Q2. How many samples are enough? Show the impact of sample size on classifier performance</h1>

This question will use train_large.csv dataset.

Write a function “impact_of_sample_size” as follows:

Take the full file name path string for a dataset inputs, e.g. impact_of_sample_size(dataset_file). Starting with 800 samples from the dataset, <strong>in each round you build a classifier with 400 more samples</strong>. i.e. in round 1, you use samples from 0:800, and in round 2, you use samples from 0:1200, …, until you use all samples.

In each round, do the following:

<ol>

 <li>create tf-idf matrix using TfidfVectorizer with <strong>stop words removed</strong></li>

 <li>train a classifier using <strong>multinomial Naive Bayes</strong> model with 5-fold cross validation 3. train a classifier using <strong>linear support vector machine</strong> model with 5-fold cross validation 4. for each classifier, collect the following average metrics across 5 folds:</li>

</ol>

average F1 macro average AUC: treat label 2 as the positive class, and set “roc_auc” along with “f1_macro” as metrics

Plot a line chart (two lines, one for each classifier) show <strong>the relationship between sample size and F1-score</strong>. Similarly, plot another line chart to show <strong>the relationship between sample size and AUC</strong>

Write your analysis in a <strong>separate pdf file (not in code)</strong> on the following: (1 point) How does the sample size affect each classifier’s performance?

How many samples do you think would be needed for each model for good performance? How is performance of SVM classifier compared with Naïve Bayes classifier, as the sample size increases?

There is no return for this function, but the charts should be plotted.

<h1>Q3 (Bonus): Predict duplicate questions by classification</h1>

You have tired to predict duplicate questions using the dataset ‘quora_duplicate_question_500.csv’ by similarity. This time, try to use a classification model to predict if a question pair (<em>q</em><sub>1</sub>, <em>q</em><sub>2</sub>) are indeed duplicate.

<table width="0">

 <tbody>

  <tr>

   <td width="303"><strong>q1</strong></td>

   <td width="325"><strong>q2</strong></td>

   <td width="95"><strong>is_duplicate</strong></td>

  </tr>

  <tr>

   <td width="303">How do you take a screenshot on a Mac laptop?</td>

   <td width="325">How do I take a screenshot on my MacBook Pro? …</td>

   <td width="95">1</td>

  </tr>

  <tr>

   <td width="303">Is the US election rigged?</td>

   <td width="325">Was the US election rigged?</td>

   <td width="95">1</td>

  </tr>

  <tr>

   <td width="303">How scary is it to drive on the road to Hana g…</td>

   <td width="325">Do I need a four-wheel-drive car to drive all …</td>

   <td width="95">0</td>

  </tr>

  <tr>

   <td width="303">…</td>

   <td width="325">…</td>

   <td width="95">…</td>

  </tr>

 </tbody>

</table>

In your Assignment 4, with cosine similarity, the AUC is about 74%. In this assignment, define a function <strong>classify_duplicate</strong> to achieve the following:

Take the full name of the dataset file (i.e.’quora_duplicate_question_500.csv’) as the input <strong>do feature engineering to extract a number of good features</strong>. A few possible options for feature engineering can be:

Unigram, bigram, trigram etc.

Keep or remove stop words

Different metrics, e.g. cosine similarity, BM25 score

<a href="https://en.wikipedia.org/wiki/Okapi_BM25">(</a><u><a href="https://en.wikipedia.org/wiki/Okapi_BM25">https://en.wikipedia.or</a></u><a href="https://en.wikipedia.org/wiki/Okapi_BM25">g</a><u><a href="https://en.wikipedia.org/wiki/Okapi_BM25">/wiki/Okapi</a></u><a href="https://en.wikipedia.org/wiki/Okapi_BM25">_</a><u><a href="https://en.wikipedia.org/wiki/Okapi_BM25">BM25 </a></u><a href="https://en.wikipedia.org/wiki/Okapi_BM25">(</a><u><a href="https://en.wikipedia.org/wiki/Okapi_BM25">https://en.wikipedia.or</a></u><a href="https://en.wikipedia.org/wiki/Okapi_BM25">g</a><u><a href="https://en.wikipedia.org/wiki/Okapi_BM25">/wiki/Okapi</a></u><a href="https://en.wikipedia.org/wiki/Okapi_BM25">_</a><u><a href="https://en.wikipedia.org/wiki/Okapi_BM25">BM25)</a></u>), etc.

build a <strong>classification model (e.g. SVM) using these features to predict if a pair questions are duplicate or not</strong>.

Your target is to <strong>improve the average AUC of the positive class through 5-fold cross validation by at least 1%, reaching 75% or higher</strong>. return the average AUC

In [238]: <em># Q1 </em>In [240]: <em>#Q3</em>

tfidf__stop_words: None best f1_macro: 0.7134380001639543

precision    recall  f1-score   support

1       0.74      0.76      0.75        99            2       0.76      0.74      0.75       102

micro avg       0.75      0.75      0.75       201    macro avg       0.75      0.75      0.75       201 weighted avg       0.75      0.75      0.75       201

0.835016835016835




Q3:  0.760092681967682 In [ ]: