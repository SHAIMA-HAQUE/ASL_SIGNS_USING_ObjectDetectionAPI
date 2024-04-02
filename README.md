1. Git clone this repo
2. We need a virtual environment using Python 3.9 and Tensorflow 3.12  (very important)

```conda create -n py39 python=3.9```
```conda actiavte py39```

3. Try `python --version` and 
`python -c "import tensorflow as tf;print(tf.reduce_sum(tf.random.normal([1000, 1000])))"` to test if they are installed correctly 

4.  In the terminal cd into Tensorflow folder and run `git clone https://github.com/tensorflow/models.git`. You should get a models folder containing the entire repo inside it

5. Also in the terminal run the following commands -  `wget https://github.com/protocolbuffers/protobuf/releases/download/v3.13.0/protoc-3.13.0-linux-x86_64.zip`

6. `cd ./Tensorflow/models/research`

7. `protoc object_detection/protos/*.proto --python_out=.`

8. `git clone https://github.com/cocodataset/cocoapi.git`

9. `cd cocoapi/PythonAPI`

10. `make`

11. `cp -r pycocotools /content/tensorflow_models/models/research`

12. `python -m pip install .`

13. `python object_detection/builders/model_builder_tf2_test.py` - all tests should pass here if your python and tensorflow versions are alright. If not some problems and their potential solutions which I had referred to are added below.

14. The above steps will make the object detection api ready to use

15. Go to `train.ipynb` in code and change the `label names`. Create the tfrecord and check if they are present in annotations folder

16. Next all instructions are given in code

Tensorflow Object Detection API - https://tensorflow-object-detection-api-tutorial.readthedocs.io/en/latest/install.html







Object Detection module not found - https://github.com/tensorflow/models/issues/10113, https://github.com/tensorflow/models/issues/2543 , https://github.com/googlecolab/colabtools/issues/4000


pip3 install --upgrade protobuf==3.20.0

https://stackoverflow.com/questions/55870127/module-tensorflow-has-no-attribute-contrib - no contrib

Generate tfrecord labeldict error - https://stackoverflow.com/questions/63763809/error-when-converting-xml-files-to-tfrecord-files

Export tflite from a checkpoint - https://github.com/tensorflow/models/blob/master/research/lstm_object_detection/g3doc/exporting_models.md

Object Detection training pipeline - https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/configuring_jobs.md

tf.contrib.slim error - https://stackoverflow.com/questions/58628439/upgrading-tf-contrib-slim-manually-to-tf-2-0

tensorflow has no attribute contrib - https://github.com/tensorflow/models/issues/7767

pyyaml error temporary fix - pip install pyyaml==5.3

If object detection test not passing - https://github.com/tensorflow/models/issues/11129#top

how to solve this error ? : AttributeError: module 'keras._tf_keras.keras.layers' has no attribute 'experimental' #64349 - https://github.com/tensorflow/tensorflow/issues/64349