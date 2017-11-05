---
layout: post
section-type: post
title: Using Transfer Learning
category: Deep Learning
tags: [ 'tutorial' ]
---


To explain this, let us take the example of Inception-v3(an image classifying model), developed by Google.
This model has been trained on a huge dataset of images(Imagenet) which consists more than a million images 
of over 1000 classes. Now to make a model which classifies a dataset in some set of labels requires training over 
a large set of data specially when you are using deep learning algorithms. Training such a large data is not very economical 
in terms of time and space. It requires CPUs with large memory or good GPUs like NVIDIA(GEFORCE), TITAN X etc. Now, even if you 
train your data on these, it will take hours to train and if the data is of order of millions, weeks of time is taken.
Here transfer learning comes into play. According to wikipeda, " Transfer learning or inductive transfer is a research problem in machine learning that focuses on storing knowledge gained while solving one problem and applying it to a different but related problem." Instead of learning the weights from randomly initialised values, we initialise them to the values learnt by a standard model like Inception-v3.

### Retraining Inception-v3 for our own dataset

First Step is to Prepare the dataset
<pre><code data-trim class="none">

1.Download the dataset for the labels you want to classify. For each class, you should have 1000 images at least.
2.Keep the images of each label in a separate folder and give the folder a name same as the label.
3.Put all the folders in a single folder and name it.
4.That's it, you have prepared your datset.

</code></pre>

### Train the dataset

<pre><code data-trim class="none">
1.You need to have two codes for it.
2.First one is the retrain code given in the tensorflow repository.
 This code downloads the inception model and trains the dataset.
3.Second one is the label_image code to predict the label.
4.Use the retrain code in terminal using the code given below:

python retrain.py   --bottleneck_dir=bottlenecks   --how_many_training_steps=1000 --train_batch_size=100   --model_dir=inception   --summaries_dir=training_summaries/basic  --output_graph=retrained_graph.pb   --output_labels=retrained_labels.txt   --image_dir= Dataset_Name

5.Use the label-image in terminal like this:

python label_image.py image_name.jpg

6.Now you have learnt to classify your own dataset using transfer learning.

</code></pre>

*** We have now learnt the basics of how to use transfer learning. But a good model doesn't only requires a structure. Apart from a good structure, good accuracy is also required. If you retrain the Inception-v3 model for small number of classes(less than 25), it will give you a decent accuracy(~80%) if other hyperparameters are set wisely. But if the number of classes are increased to say 150. It will be a hazard, giving you merely 30-40% accuracy. In the next blog we will see such a problem and 
and see some ways to tackle it. *** 
