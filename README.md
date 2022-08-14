# YOLOv6
## Quick Start

### Install

```shell
git clone https://github.com/FelixZhao7/YOLOv6.git
cd YOLOv6
pip install -r requirements.txt
```

### Inference

First, download a pretrained model from the YOLOv6 [release](https://github.com/meituan/YOLOv6/releases/tag/0.1.0)

Second, run inference with `tools/infer.py`

```shell
python tools/infer.py --weights yolov6s.pt --source img.jpg / imgdir
                                yolov6n.pt
```

### Training



```shell
python tools/train.py --batch 32 --conf configs/yolov6s.py --data data/coco.yaml --device 0
                                        
```
- data: prepare [COCO](http://cocodataset.org) dataset, [YOLO format coco labels](https://github.com/meituan/YOLOv6/releases/download/0.1.0/coco2017labels.zip) and specify dataset paths in data.yaml
- make sure your dataset structure as follows:
```
├── coco
│   ├── annotations
│   │   ├── instances_train2017.json
│   │   └── instances_val2017.json
│   ├── images
│   │   ├── train2017
│   │   └── val2017
│   ├── labels
│   │   ├── train2017
│   │   ├── val2017
│   ├── LICENSE
│   ├── README.txt
```


### Evaluation

Reproduce mAP on COCO val2017 dataset

```shell
python tools/eval.py --data data/coco.yaml --batch 32 --weights yolov6s.pt --task val
                                                                yolov6n.pt
```
