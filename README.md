# caffe-yolov3
# Paltform
Have tested on Ubuntu16.04LTS with Jetson-TX2 and Ubuntu16.04LTS with gtx1060;

NOTE: You need change CMakeList.txt on Ubuntu16.04LTS with GTX1060.

# Install
git clone https://github.com/xiaoyuetang/caffe-yolov3

cd caffe-yolov3

mkdir build

cd build

cmake ..

make -j6

# Darknet2Caffe
darknet2caffe link [github](https://github.com/xiaoyuetang/darknet2caffe)


# Demo
First,download model and put it into dir caffemodel.

$ `./x86_64/bin/demo ../prototxt/yolov4.prototxt ../caffemodel/yolov4.caffemodel ../images/dog.jpg` 

# Eval
1. Run
$ `./x86_64/bin/eval ../prototxt/yolov4.prototxt ../caffemodel/yolov4.caffemodel /path/to/coco/val2017/`

generate `coco_results.json` on `results/`.

2. Run
$ `python coco_eval/coco_eval.py --gt-json path/to/coco/annotations/instances_val2017.json  --pred-json results/coco_results.json`

3. Eval results Yolov4 input size 608x608 from this repo.
```
 Average Precision  (AP) @[ IoU=0.50:0.95 | area=   all | maxDets=100 ] = 0.428
 Average Precision  (AP) @[ IoU=0.50      | area=   all | maxDets=100 ] = 0.664
 Average Precision  (AP) @[ IoU=0.75      | area=   all | maxDets=100 ] = 0.461
 Average Precision  (AP) @[ IoU=0.50:0.95 | area= small | maxDets=100 ] = 0.241
 Average Precision  (AP) @[ IoU=0.50:0.95 | area=medium | maxDets=100 ] = 0.492
 Average Precision  (AP) @[ IoU=0.50:0.95 | area= large | maxDets=100 ] = 0.575
 Average Recall     (AR) @[ IoU=0.50:0.95 | area=   all | maxDets=  1 ] = 0.331
 Average Recall     (AR) @[ IoU=0.50:0.95 | area=   all | maxDets= 10 ] = 0.517
 Average Recall     (AR) @[ IoU=0.50:0.95 | area=   all | maxDets=100 ] = 0.544
 Average Recall     (AR) @[ IoU=0.50:0.95 | area= small | maxDets=100 ] = 0.363
 Average Recall     (AR) @[ IoU=0.50:0.95 | area=medium | maxDets=100 ] = 0.609
 Average Recall     (AR) @[ IoU=0.50:0.95 | area= large | maxDets=100 ] = 0.710

```

4. Eval results Yolov4 input size 608x608 from offical model [AlexeyAB/YoloV4](https://github.com/AlexeyAB/darknet).
```
 Average Precision  (AP) @[ IoU=0.50:0.95 | area=   all | maxDets=100 ] = 0.505
 Average Precision  (AP) @[ IoU=0.50      | area=   all | maxDets=100 ] = 0.749
 Average Precision  (AP) @[ IoU=0.75      | area=   all | maxDets=100 ] = 0.557
 Average Precision  (AP) @[ IoU=0.50:0.95 | area= small | maxDets=100 ] = 0.357
 Average Precision  (AP) @[ IoU=0.50:0.95 | area=medium | maxDets=100 ] = 0.559
 Average Precision  (AP) @[ IoU=0.50:0.95 | area= large | maxDets=100 ] = 0.613
 Average Recall     (AR) @[ IoU=0.50:0.95 | area=   all | maxDets=  1 ] = 0.368
 Average Recall     (AR) @[ IoU=0.50:0.95 | area=   all | maxDets= 10 ] = 0.598
 Average Recall     (AR) @[ IoU=0.50:0.95 | area=   all | maxDets=100 ] = 0.634
 Average Recall     (AR) @[ IoU=0.50:0.95 | area= small | maxDets=100 ] = 0.500
 Average Recall     (AR) @[ IoU=0.50:0.95 | area=medium | maxDets=100 ] = 0.680
 Average Recall     (AR) @[ IoU=0.50:0.95 | area= large | maxDets=100 ] = 0.757

```

# Download Model

Baidu link [model](https://pan.baidu.com/s/1yiCrnmsOm0hbweJBiiUScQ)


# Note

1.Only inference on GPU platform,such as RTX2080, GTX1060,Jetson Tegra X1,TX2,nano,Xavier etc.

2.Support model such as yolov4,yolov3,yolov3-spp,yolov3-tiny etc.


### References
Appreciate the great work from the following repositories:
- [official/Yolo](https://pjreddie.com/darknet/yolo/)
- [AlexeyAB/YoloV4](https://github.com/AlexeyAB/darknet)
