# IconSearch
Final Project for KAIST CS492I
### Introduction

When I got into designing the icon, it’s hard to check whether the design does exist or not, because there’re so various icon images. Also, when I put icon sketch to Google image search, it only shows the sketch images. In other words, Google image search doesn’t provide the result what we want to get.

Thus, I decided to make icon image searcher with sketch image as input and original icon image as output.


### Method

I tried to get an icon image from Google Play Store, but it was difficult to get data, so I used a data set called Icons50 of Kaggle.

In addition, in the past, SEnet was intended to be applied, but after applying the existing CNN, it was attempted to increase the accuracy. When working on the project, I used resnet34.

After that, I adopted the method of checking how accurate the results are with the test set I drew and made by myself.

In the resnet34 model, I use CrossEntropyLoss, which is useful for training an unbalanced training set. Also, the input was changed to suit this model.

When testing, we tried to find the most similar image using the knn algorithm, but it was difficult to apply, so we were satisfied with the classification.

### Results and analysis

The screenshot below shows Loss and Accuracy. The epoch proceeded to 50, and it can be seen that the more you do it, the higher the result is. However, the amount of data was not large, and there were often cases where the existing icons had the same shape but different colors, so the accuracy was 100%. If you proceed based on more and more diverse data, 100% accuracy will not come out, and you will be able to obtain data equivalent to that.

![Untitled](Icon%20Search%20by%20Sketch%20f161b1da67684e74be9b139b86b3aec6/Untitled%202.png)

![Untitled](Icon%20Search%20by%20Sketch%20f161b1da67684e74be9b139b86b3aec6/Untitled%203.png)

The evaluation is following.

![evaluation for epoch=50](Icon%20Search%20by%20Sketch%20f161b1da67684e74be9b139b86b3aec6/Untitled%204.png)

evaluation for epoch=50

Also, even if the epoch was set to 10, it was found that all but one of the testsets were successfully classified, and some reliable results were obtained.

### Discussion and Contribution

It was disappointing that it was applied in a shallower way than previously planned, but based on this result, I think that it can be further developed in the future. Also, I had a lot of difficulty following the deep learning class, but I think it's meaningful how I made a model using my dataset.

I conducted my project by myself, and reference many things...

**Reference**

[https://inyl.github.io/programming/2017/08/11/cnn_image_search.html](https://inyl.github.io/programming/2017/08/11/cnn_image_search.html)

[https://github.com/sethuiyer/Image-to-Image-Search](https://github.com/sethuiyer/Image-to-Image-Search)

[http://solarisailab.com/archives/1422](http://solarisailab.com/archives/1422)

[https://velog.io/@usrnamejm/Tensorflow-WARNINGtensorflowYour-input-ran-out-of-data](https://velog.io/@usrnamejm/Tensorflow-WARNINGtensorflowYour-input-ran-out-of-data)

[https://github.com/awslabs/deeplearning-benchmark/blob/master/tensorflow/inception/inception/data/build_image_data.py](https://github.com/awslabs/deeplearning-benchmark/blob/master/tensorflow/inception/inception/data/build_image_data.py)

[https://maduinos.blogspot.com/2019/10/ml-tensorflow-03-inception-v3.html](https://maduinos.blogspot.com/2019/10/ml-tensorflow-03-inception-v3.html)

[https://colab.research.google.com/github/google/eng-edu/blob/master/ml/pc/exercises/image_classification_part3.ipynb](https://colab.research.google.com/github/google/eng-edu/blob/master/ml/pc/exercises/image_classification_part3.ipynb)

[https://airsbigdata.tistory.com/220](https://airsbigdata.tistory.com/220)

[https://deep-learning-study.tistory.com/561](https://deep-learning-study.tistory.com/561)

[https://github.com/ndb796/CNN-based-Celebrity-Classification-AI-Service-Using-Transfer-Learning/blob/main/Celebrity Classifier Service Using Crawling and Transfer Learning.ipynb](https://github.com/ndb796/CNN-based-Celebrity-Classification-AI-Service-Using-Transfer-Learning/blob/main/Celebrity%20Classifier%20Service%20Using%20Crawling%20and%20Transfer%20Learning.ipynb) *especially
