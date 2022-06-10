# splunk video booth

### Introduction
Object Tracking pipeline leveraging YOLOv4, DeepSORT, and Tensorflow.  DeepSORT (Simple Online and Realtime Tracking 
with a Deep Association Metric) uses deep convolutional neural networks to perform object detection.

![alt text](https://github.com/cramerry/VideoBooth/blob/main/Screen%20Shot%202022-06-10%20at%202.45.32%20PM.png?raw=true)
### Installation
  * It is recommended to first 
  * Download model weights, place in /data directory.
  * Create a tools/splunk.py file with Splunk HEC endpoint & headers, example:
    
    splunk_ep = https://[SplunkIP]:8088/services/collector/event
    
    headers2 = {'Authorization': 'Splunk [SplunkToken]', 'Content-Type': 'application/json'}
  * Refer to [yolov4-deepsort](https://github.com/theAIGuysCode/yolov4-deepsort) repo for detailed instructions on
    pipeline implementation options.

### Usage
```
python object_tracker.py --weights ./checkpoints/yolov4-tiny-416 --model yolov4 --video 0 --tiny --info
```

### Acknowledgments/References
![alt text](https://miro.medium.com/max/1400/0*-S2EkuGhkP9tp9It.JPG)
  * [https://github.com/theAIGuysCode/yolov4-deepsort](https://github.com/theAIGuysCode/yolov4-deepsort)
  * [https://github.com/nwojke/deep_sort](https://github.com/nwojke/deep_sort)
  * [https://github.com/hunglc007/tensorflow-yolov4-tflite](https://github.com/hunglc007/tensorflow-yolov4-tflite)
  * [Simple Online and Realtime Tracking with a Deep Association Metric](https://arxiv.org/abs/1703.07402)
  * [DeepSORT — Deep Learning applied to Object Tracking](https://medium.com/augmented-startups/deepsort-deep-learning-applied-to-object-tracking-924f59f99104)
  * [Tensorflow Object Detection in 5 Hours with Python](https://www.youtube.com/watch?v=yqkISICHH-U)
