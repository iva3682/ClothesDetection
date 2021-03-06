# ClothesDetection with YOLO3 (Detection, Training, and Web deploy)

![Example image](./output/Kingsman.png)

### Installing
To install the dependencies, run

```pip install -r requirements.txt```

### Prepare data
1. Data preparation

Download the dataset from 

```git clone https://github.com/EscVM/OIDv4_ToolKit```

2. Install the required packages

```cd OIDv4_ToolKit && pip3 install -r requirements.txt```

3. Use the ToolKit to download images for Object Detection

```! cd OIDv4_ToolKit &&  python3 main.py downloader --classes Shorts Dress Coat Suit Skirt Jacket Jeans Swimwear --type_csv train --multiclasses 1 --limit 600```

```! cd OIDv4_ToolKit &&  python3 main.py downloader --classes Shorts Dress Coat Suit Skirt Jacket Jeans Swimwear --type_csv validation --multiclasses 1 --limit 300```

4. Convert dataset in comfortable format

```! cd OIDv4_ToolKit && python3 convert_xml.py```

5. Generate anchors for your dataset (optional)

```python gen_anchors.py -c config.json```

### Start the training process
1. Start the training process

```python train.py -c config.json```

### Perform detection using trained weights on image, set of images, video, or webcam
1. It carries out detection on the image and write the image with detected bounding boxes to the output folder.

```python predict.py -c config.json -i /path/to/image/or/video```

2. or Start the web app
```python3 web_app.py```

![WEb App](./temp/screenshot_web_app.png)

### References
https://github.com/experiencor/keras-yolo3 - YOLOv3 model training.