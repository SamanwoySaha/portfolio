---
title: ztm
draft: true
tags:
  - flashcards/ML
date: 04-Sep-2025
---
# Machine Learning

What -> the field of study that gives computers the ability to learn
without being explicitly programmed

Why 
?
Consider how you would write a spam filter using 
![[Pasted image 20250905114745.png]]
![[Pasted image 20250905114906.png]]
![[Pasted image 20250905114913.png]]
Applying ML techniques to dig into large amounts of data can help discover patterns that were not immediately apparent. This is called data mining.
![[Pasted image 20250905115529.png]]

Machine Learning is great for:
- Problems for which existing solutions require a lot of fine-tuning or long lists of rules: one Machine Learning algorithm can often simplify code and perform better than the traditional approach.
- Complex problems for which using a traditional approach yields no good solution: the best Machine Learning techniques can perhaps find a solution.
- Fluctuating environments: a Machine Learning system can adapt to new data.
- Getting insights about complex problems and large amounts of data.
+++

Use Cases
?
- Analyzing images of products on a production line to automatically classify them
	- This is image classification, typically performed using convolutional neural networks
- Detecting tumors in brain scans
	- This is semantic segmentation, where each pixel in the image is classified (as we want to determine the exact location and shape of tumors), typically using CNNs as well.
- Automatically classifying news articles
	- This is natural language processing (NLP), and more specifically text classification, which can be tackled using recurrent neural networks (RNNs), CNNs, or Transformers 
- Automatically flagging offensive comments on discussion forums
	- This is also text classification, using the same NLP tools.
- Summarizing long documents automatically
	- This is a branch of NLP called text summarization, again using the same tools.
- Creating a chatbot or a personal assistant
	- This involves many NLP components, including natural language understanding (NLU) and question-answering modules.
- Forecasting your company’s revenue next year, based on many performance metrics
	- This is a regression task (i.e., predicting values) that may be tackled using any regression model, such as a Linear Regression or Polynomial Regression model (see Chapter 4), a regression SVM (see Chapter 5), a regression Random Forest (see Chapter 7), or an artificial neural network (see Chapter 10). If you want to take into account sequences of past performance metrics, you may want to use RNNs, CNNs, or Transformers (see Chapters 15 and 16).
- Making your app react to voice commands
	- This is speech recognition, which requires processing audio samples: since they are long and complex sequences, they are typically processed using RNNs, CNNs, or Transformers (see Chapters 15 and 16).
- Detecting credit card fraud
	- This is anomaly detection (see Chapter 9).
- Segmenting clients based on their purchases so that you can design a different marketing strategy for each segment
	- This is clustering (see Chapter 9).
- Representing a complex, high-dimensional dataset in a clear and insightful diagram
	- This is data visualization, often involving dimensionality reduction techniques
- Recommending a product that a client may be interested in, based on past purchases
	- This is a recommender system. One approach is to feed past purchases (and other information about the client) to an artificial neural network and get it to output the most likely next purchase. This neural net would typically be trained on past sequences of purchases across all clients.
- Building an intelligent bot for a game
	- This is often tackled using Reinforcement Learning (RL; see Chapter 18), which is a branch of Machine Learning that trains agents (such as bots) to pick the actions that will maximize their rewards over time (e.g., a bot may get a reward every time the player loses some life points), within a given environment (such as the game). The famous AlphaGo program that beat the world champion at the game of Go was built using RL.
+++

Criteria of classification
?
- Whether or not they are trained with human supervision (supervised, unsupervised, semisupervised, and Reinforcement Learning)
- Whether or not they can learn incrementally on the fly (online versus batch learning)
- approaches to generalization / Whether they work by simply comparing new data points to known data points, or instead by detecting patterns in the training data and building a predictive model, much like scientists do (instance-based versus model-based learning)
+++

## Supervised/Unsupervised Learning

Classification
?
classified according to the amount and type of supervision they get during training
- supervised learning, 
- unsupervised learning, 
- semisupervised learning,
- Reinforcement Learning.
+++
### Supervised Learning

what -> the training set you feed to the algorithm includes the desired solutions, called labels

classification
?
- classification
	- ![[Pasted image 20250905135237.png]]
	- k-Nearest Neighbors
	- Logistic Regression
	- Support Vector Machines (SVMs)
	- Decision Trees and Random Forests
	- Neural networks
- regression
	- ![[Pasted image 20250905135303.png]]
	-  k-Nearest Neighbors
	- Linear Regression
	- Support Vector Machines (SVMs)
	- Decision Trees and Random Forests
	- Neural networks
+++

### Unsupervised Learning

What ->  the training data is unlabeled

Classification
?
- Clustering
	- ![[Pasted image 20250905140442.png]]
	- K-Means
	- DBSCAN
	- Hierarchical Cluster Analysis (HCA)
- Anomaly detection and novelty detection
	- ![[Pasted image 20250905140740.png]]
	- One-class SVM
	- Isolation Forest
- Visualization and dimensionality reduction
	- Principal Component Analysis (PCA)
	- Kernel PCA
	- Locally Linear Embedding (LLE)
	- t-Distributed Stochastic Neighbor Embedding (t-SNE)
		- ![[Pasted image 20250905140511.png]]
- Association rule learning
	- Apriori
	- Eclat
+++

### Semisupervised Learning

What 
?
Since labeling data is usually time-consuming and costly, you will often have plenty of unlabeled instances, and few labeled instances. Some algorithms can deal with data that’s partially labeled. This is called semisupervised learning 
![[Pasted image 20250905181837.png]]
Some photo-hosting services, such as Google Photos, are good examples of this. Once you upload all your family photos to the service, it automatically recognizes that the same person A shows up in photos 1, 5, and 11, while another person B shows up in photos 2, 5, and 7. This is the unsupervised part of the algorithm (clustering). Now all the system needs is for you to tell it who these people are. Just add one label per person4  and it is able to name everyone in every photo, which is useful for searching photos.

Most semisupervised learning algorithms are combinations of unsupervised and
supervised algorithms. For example, deep belief networks (DBNs) are based on unsupervised components called restricted Boltzmann machines (RBMs) stacked on top of one another. RBMs are trained sequentially in an unsupervised manner, and then the whole system is fine-tuned using supervised learning techniques.
+++

### Reinforcement Learning

What 
?
Reinforcement Learning is a very different beast. The learning system, called an agent in this context, can observe the environment, select and perform actions, and get rewards in return (or penalties in the form of negative rewards, as shown in
Figure 1-12). It must then learn by itself what is the best strategy, called a policy, to get the most reward over time. A policy defines what action the agent should choose
when it is in a given situation.
![[Pasted image 20250905182238.png]]
For example, many robots implement Reinforcement Learning algorithms to learn
how to walk. DeepMind’s AlphaGo program is also a good example of Reinforcement
Learning: it made the headlines in May 2017 when it beat the world champion Ke Jie
at the game of Go. It learned its winning policy by analyzing millions of games, and
then playing many games against itself. Note that learning was turned off during the
games against the champion; AlphaGo was just applying the policy it had learned.
+++
## Batch and Online Learning

### Batch Learning

What -> In batch learning, the system is incapable of learning incrementally: it must be trained using all the available data. This will generally take a lot of time and computing resources, so it is typically done offline. First the system is trained, and then it is launched into production and runs without learning anymore; it just applies what it has learned. This is called offline learning.

cons
?
If you want a batch learning system to know about new data (such as a new type of
spam), you need to train a new version of the system from scratch on the full dataset
(not just the new data, but also the old data), then stop the old system and replace it
with the new one.
Fortunately, the whole process of training, evaluating, and launching a Machine
Learning system can be automated fairly easily (as shown in Figure 1-3), so even a
batch learning system can adapt to change. Simply update the data and train a new
version of the system from scratch as often as needed.
This solution is simple and often works fine, but training using the full set of data can
take many hours, so you would typically train a new system only every 24 hours or
even just weekly. If your system needs to adapt to rapidly changing data (e.g., to predict stock prices), then you need a more reactive solution.
Also, training on the full set of data requires a lot of computing resources (CPU,
memory space, disk space, disk I/O, network I/O, etc.). If you have a lot of data and
you automate your system to train from scratch every day, it will end up costing you a
lot of money. If the amount of data is huge, it may even be impossible to use a batch
learning algorithm.
Finally, if your system needs to be able to learn autonomously and it has limited
resources (e.g., a smartphone application or a rover on Mars), then carrying around
large amounts of training data and taking up a lot of resources to train for hours
every day is a showstopper.
+++

### Online Learning

What
?
In online learning, you train the system incrementally by feeding it data instances sequentially, either individually or in small groups called mini-batches. Each learning step is fast and cheap, so the system can learn about new data on the fly, as it arrives 
![[Pasted image 20250905182925.png]]
![[Pasted image 20250905183435.png]]
+++

pros
?
Online learning is great for systems that receive data as a continuous flow (e.g., stock prices) and need to adapt to change rapidly or autonomously. It is also a good option if you have limited computing resources: once an online learning system has learned about new data instances, it does not need them anymore, so you can discard them (unless you want to be able to roll back to a previous state and “replay” the data). This can save a huge amount of space.

Online learning algorithms can also be used to train systems on huge datasets that
cannot fit in one machine’s main memory (this is called out-of-core learning). The
algorithm loads part of the data, runs a training step on that data, and repeats the
process until it has run on all of the data
+++

Learning Rate -> One important parameter of online learning systems is how fast they should adapt to changing data: this is called the learning rate. If you set a high learning rate, then your system will rapidly adapt to new data, but it will also tend to quickly forget the old data (you don’t want a spam filter to flag only the latest kinds of spam it was shown). Conversely, if you set a low learning rate, the system will have more inertia; that is, it will learn more slowly, but it will also be less sensitive to noise in the new data or to sequences of nonrepresentative data points (outliers).

challenge
?
A big challenge with online learning is that if bad data is fed to the system, the sys‐
tem’s performance will gradually decline. If it’s a live system, your clients will notice.
For example, bad data could come from a malfunctioning sensor on a robot, or from
someone spamming a search engine to try to rank high in search results. To reduce
this risk, you need to monitor your system closely and promptly switch learning off
(and possibly revert to a previously working state) if you detect a drop in perfor‐
mance. You may also want to monitor the input data and react to abnormal data (e.g.,
using an anomaly detection algorithm).
+++
## Instance-based vs Model-based Learning

### Instance Based Learning

What 
?
the system learns the examples by heart, then generalizes to new cases by using a similarity measure to compare them to the learned examples (or a subset of them). 
![[Pasted image 20250905183857.png]]
+++

### Model based learning

What 
?
from a set of examples is to build a model of these examples and then use that model to make predictions. This is called model-based learning
![[Pasted image 20250905184025.png]]
+++

Model selection -> consists in choosing the type of model and fully specifying its architecture.

Training a model -> means running an algorithm to find the model parameters that will make it best fit the training data (and hopefully make good predictions on new
data).

Cost function -> you need to define the parameter values θ0  and θ1. How can you know which values will make your model perform best? To answer this question, you need to specify a performance measure. You can either define a utility function (or fitness function) that measures how good your model is, or you can define a cost function that measures how bad it is. For Linear Regression problems, people typically use a cost function that measures the distance between the linear model’s predictions and the training examples; the objective is to minimize this distance.
## Challenges

### bad data

Insufficient Quantity of Training Data
?
For a toddler to learn what an apple is, all it takes is for you to point to an apple and
say “apple” (possibly repeating this procedure a few times). Now the child is able to
recognize apples in all sorts of colors and shapes. Genius.

Machine Learning is not quite there yet; it takes a lot of data for most Machine Learn‐
ing algorithms to work properly. Even for very simple problems you typically need
thousands of examples, and for complex problems such as image or speech recogni‐
tion you may need millions of examples (unless you can reuse parts of an existing
model).
+++

The Unreasonable Effectiveness of Data
?
In a famous paper published in 2001, Microsoft researchers Michele Banko and Eric
Brill showed that very different Machine Learning algorithms, including fairly simple
ones, performed almost identically well on a complex problem of natural language
disambiguation  once they were given enough data (as you can see in Figure 1-20
![[Pasted image 20250905190820.png]]
As the authors put it, “these results suggest that we may want to reconsider the trade-off between spending time and money on algorithm development versus spending it on corpus development.”

The idea that data matters more than algorithms for complex problems was further
popularized by Peter Norvig et al. in a paper titled “The Unreasonable Effectiveness
of Data”, published in 2009.10 It should be noted, however, that small- and medium-
sized datasets are still very common, and it is not always easy or cheap to get extra
training data—so don’t abandon algorithms just yet.
+++

Nonrepresentative Training Data
?
In order to generalize well, it is crucial that your training data be representative of the
new cases you want to generalize to. This is true whether you use instance-based
learning or model-based learning.
For example, the set of countries we used earlier for training the linear model was not
perfectly representative; a few countries were missing. Figure 1-21 shows what the
data looks like when you add the missing countries.
![[Pasted image 20250905191301.png]]
+++

Sampling Bias
?
It is crucial to use a training set that is representative of the cases you want to generalize to. This is often harder than it sounds: if the sample is too small, you will have sampling noise (i.e., nonrepresentative data as a result of chance), but even very large samples can be nonrepresentative if the sampling method is flawed. This is called sampling bias.
Here is another example: say you want to build a system to recognize funk music vid‐
eos. One way to build your training set is to search for “funk music” on YouTube and
use the resulting videos. But this assumes that YouTube’s search engine returns a set of videos that are representative of all the funk music videos on YouTube. In reality, the search results are likely to be biased toward popular artists (and if you live in Brazil you will get a lot of “funk carioca” videos, which sound nothing like James Brown). On the other hand, how else can you get a large training set?
+++

Poor-Quality Data
?
if your training data is full of errors, outliers, and noise (e.g., due to poor-
quality measurements), it will make it harder for the system to detect the underlying
patterns, so your system is less likely to perform well. It is often well worth the effort
to spend time cleaning up your training data.
+++

when you’d want to clean up training data
?
- If some instances are clearly outliers, it may help to simply discard them or try to fix the errors manually.
- If some instances are missing a few features (e.g., 5% of your customers did not specify their age), you must decide whether you want to ignore this attribute altogether, ignore these instances, fill in the missing values (e.g., with the median age), or train one model with the feature and one model without it.
+++

Irrelevant Features
?
As the saying goes: garbage in, garbage out. Your system will only be capable of learning if the training data contains enough relevant features and not too many irrelevant ones. A critical part of the success of a Machine Learning project is coming up with a good set of features to train on. This process, called feature engineering, involves the following steps:
- Feature selection (selecting the most useful features to train on among existing features)
- Feature extraction (combining existing features to produce a more useful one—as we saw earlier, dimensionality reduction algorithms can help)
- Creating new features by gathering new data
+++

### bad algorithms

Overfitting the Training Data
?
model performs well on the training data, but it does not generalize well.


Underfitting the Training Data
Stepping Back

## Testing and Validation
# End to End ML Project
# Classification
# Regression
# SVM
# Decision Trees
# Ensemble Learning
# Dimensionality Reduction
# Unsupervised Learning
# Deep Learning
# Reinforcement Learning
