# YOLOv3 Object Detection with Darknet

![Docker Automated build](https://img.shields.io/docker/cloud/automated/tancnle/darknet-yolo.svg?style=popout-square)
![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/tancnle/darknet-yolo.svg?style=popout-square)

A convenient way to do object detection using YOLOv3 model via Docker.

## Intro. 
This project fork from [tancnle/docker-darknet](https://github.com/tancnle/docker-darknet) . 
I testing on Windows 10 with Docker-CE (2.2.0.3) 

## Usage
==All command run as Administrator on the command line ==

Build image 
```bash=
docker build -t darknet-yolo .
```

Make sure your image ready 
```bash= 
docker image ls
```

Run object detection on an image
```bash=
docker run --name yolo-test -v "./output":/output --interactive --rm darknet-yolo <  storefront.jpg
```
> Here, darknet-you is tag name of image ,
> storefront.jpg is input image 

View the image with polygon-bounding boxes
```bash=
open output/prediction.png
```

## Advanced.

You can change the your weight file in the Dockerfile file
```bash=21
# Download weights for YOLOv3 dection
RUN curl -sSLO https://pjreddie.com/media/files/yolov3.weights
```



## Example Output

<img width="49%" src="./examples/storefront.jpg">  <img width="49%" src="./examples/detected-storefront.jpg">

```bash=
Loading weights from yolov3.weights...Done!
/tmp/image: Predicted in 266.171836 seconds.
pottedplant: 98%
bicycle: 85%
bicycle: 66%
```
> Run with Inter X3480 3.2G on Win 10


## References
* YOLO: Real-Time Object Detection (https://pjreddie.com/darknet/yolo/)
* Darknet (https://github.com/pjreddie/darknet)
* [9 Common Dockerfile Mistakes](https://runnable.com/blog/9-common-dockerfile-mistakes)
