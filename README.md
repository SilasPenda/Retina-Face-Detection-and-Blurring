# Retina-Face-Detection-and-Blurring

## Steps
<b>Step 1:</b> Follow this guide by Intel to download and install OpenVINO toolkit: https://www.intel.com/content/www/us/en/developer/tools/openvino-toolkit/download.html
<br/><br/>

<b>Step 2:</b> Download Retina Face model
```
omz_downloader --name retinaface-resnet50-pytorch --output_dir model --cache_dir model
```
<br/>
<b>Step 3:</b> Convert model from Pytorch to OpenVINO IR format
```
omz_converter --name retinaface-resnet50-pytorch --download_dir model --precisions FP32
```
<br/>
<br/><br/>
<b>Step 4a:</b> Run face detection without blurring
```
python face_detection.py -m .\model\public\retinaface-resnet50-pytorch\FP32\retinaface-resnet50-pytorch.xml -at retinaface-pytorch -i corridor_video.mp4
```
<br/>
<br/><br/>
<b>Step 4b:</b> Run face detection with blurring
```
python face_detection.py -m .\model\public\retinaface-resnet50-pytorch\FP32\retinaface-resnet50-pytorch.xml -b -at retinaface-pytorch -i corridor_video.mp4
```
<br/>
