# Number-Plate-Detection
Test Project for Number Plate Detection Using YOLOv7


## Installation

Docker environment (recommended)
<details><summary> <b>Expand</b> </summary>

``` shell
# create the docker container, you can change the share memory size if you have more.
nvidia-docker run --name yolov7 -it -v your_coco_path/:/coco/ -v your_code_path/:/yolov7 --shm-size=64g nvcr.io/nvidia/pytorch:21.08-py3

# apt install required packages
apt update
apt install -y zip htop screen libgl1-mesa-glx

# pip install required packages
pip install seaborn thop

# go to code folder
cd /yolov7
```

</details>

## Training

[`yolov7_training.pt`](https://github.com/WongKinYiu/yolov7/releases/download/v0.1/yolov7_training.pt)
['Dataset'](https://drive.google.com/file/d/1ZYvRJVmKzgOY52iVfxP4lHjt9aMS_K1t/view?usp=sharing)

Download pretrained model and extract it to project path.
change directories in './Dataset/data.yaml' file based on your data path 

``` shell
--workers 8 --device 0 --batch-size 8 --data Dataset/data.yaml --img 640 640 --cfg cfg/training/custom.yaml --weights 'yolov7_training.pt' --name yolov7-custom --hyp data/hyp.scratch.custom.yaml 
```


