# YOLOv9 for Fire Detection 
Fire detection task aims to identify fire or flame in a video and put a bounding box around it.
We focused on fire detection in tunnels, and added an algorithm that also eliminates vehicle objects to eliminate mistaking the vehicle's backlight for fire.

## Setting
* Python 3.8.12
* Pytorch 2.0.1+cu118
* opencv-python 4.1.1
* YOLOv9
* HPC innovation hub(NVIDIA Tesla V100)

## Model Train
```
  python train_dual.py --workers 4 --device 0 --batch 16 --data ../fire.yaml --img 640 --cfg models/detect/yolov9-m.yaml --weights '' --name yolov9-m --hyp hyp.scratch-high.yaml --min-items 0 --epochs 50 --close-mosaic 15
```
We train yolo fire detection model to yolov9-m size.
In additional, We use a pretraining vehicle yolo model to eliminate vehicle's backlight(possible fire detection).

## Implement Image
<img width="580" alt="스크린샷 2024-09-17 오후 8 04 09" src="https://github.com/user-attachments/assets/5a4ed9ef-3ac7-4567-bcda-6bdbfcfacded">

## Reference
https://github.com/spacewalk01/yolov5-fire-detection

