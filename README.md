# Trash Car Train Data Set Preparation



[toc]



## Introduction

There has 4 classes and 5 instance in the `trash_c4_i5` dataset in total. This booklet is used to guide image taking and labeling to create `trash_c4_i5` dataset.

## Image prepare

1. Number
   We need 100 images per instance. 50 images on the green floor and 50 images on the mutative background.

2. Environment

   1. Green floor images:
      1. Multiple instances on the same images.
      2. Simulate real environment.
   2. Mutative background images: 3. Keep lighting strength changing. 4. Background changing. NO TWO SAME IMAGE.

3. Naming

   Image should start at `001.jpg` and end at `100.jpg` the corresponding label should as same as images.

4. Files Level

   ```
   trash_c4_i5
   |-- data
   	|-- predefined_classes.txt
   	|-- trash_c4_i5.yaml
   |-- images
       |-- train
           |-- 1.jpg
           ...
       |-- valid
           |-- 1.jpg
           ...
   |-- labels
       |-- train
           |-- 1.txt
           ...
       |-- valid
           |-- 1.txt
           ...
   ```

5. Camera and Image Size

   Use RGB camera which used in competition environment. And take the size of $640\times480$.  

## Label annotation

[Label app](https://github.com/tzutalin/labelImg): click to check and download.



The classes order is shown as below, DO NOT change this order.

```
bottle 
battery
cup
orange
paper
```

The file is arranged as below:

1. The default order is predefined in the file `trash_c4_i5/data/predefined_classes.txt` .

2. The annotations target dir is `trash_c4_i5/labels/`.

3. The images are saved in dir `trash_c4_i5/images/.`



The name of annotation must be as same as image. Must choose the `yolo` style to label all the images. 



The useful hotkeys:

| Ctrl + u         | Load all of the images from a directory   |
| ---------------- | ----------------------------------------- |
| Ctrl + r         | Change the default annotation target dir  |
| Ctrl + s         | Save                                      |
| Ctrl + d         | Copy the current label and rect box       |
| Ctrl + Shift + d | Delete the current image                  |
| Space            | Flag the current image as verified        |
| w                | Create a rect box                         |
| d                | Next image                                |
| a                | Previous image                            |
| del              | Delete the selected rect box              |
| Ctrl++           | Zoom in                                   |
| Ctrl--           | Zoom out                                  |
| ↑→↓←             | Keyboard arrows to move selected rect box |



## Train

> you can train with --img 1280 and/or --rect, though --rect is not recommended for best results. Which is trained as mosaics. 



## Reference

Image size

[1] https://github.com/ultralytics/yolov5/issues/974

[2] https://github.com/ultralytics/yolov5/issues/700

Multiple GPU:

[3] https://github.com/ultralytics/yolov5/issues/475



