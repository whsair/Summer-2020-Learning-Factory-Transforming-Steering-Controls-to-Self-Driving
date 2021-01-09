# Penn State Learning Factory: Transforming Steering Controls to Self-driving
#### Director: [Professor. Leung, Siu Ling](https://www.me.psu.edu/department/directory-detail-g.aspx?q=SZL12)
#### Range: 05/2020 - 08/2020
###### Only includes data & reports


### Weekly expectations
- Week 1-2: Learn about machine learning and deep learning using Matlab on-ramp training

- Week 3-4: Setup Jetbot and learn how to do classification and regression using Jetbot.

- Week 4: Discuss individual tasks for each person.

- Week 5: Test out the “out-of-box” functions

- Week 6-10:

  - Steering Wheel Controls

  - Design roadmap 

  - Object recognition 
  
  - Object Detection(my job)
  
** All robots needs to ship back to the university by the end of the summer internship training.

** For further details, please see [weekly reports](weekly%20reports)

### Final deliverable
- A well-designed autonomous vehicle town design with essential building structures, road system components, and signs for path following.

- A steering wheel control platform for a Jetbot.

- Sign classification or object detection algorithm using deep learning technique.

- Results: [Final Group Report](https://youtu.be/vH0zk6sewjk)

## Object detection

### Goal:
-	Designed a wireless steering wheel controller for a robot vehicle to study autonomous control and collect data for deep learning database

-	Designed and tested a control platform to drive the NVIDIA JetBot by a Bluetooth steering wheel controller

-	Doing transfer learning on YOLOv4 tiny and Mobilenet v2 models for object detection; optimized the models to reach a recalling rate of over 80 and accuracy rate of over 95

### Specific instructions: see [final wrapped-up file](weekly%20reports/Final%20wrapped%20up.pptx)

### Equipments
- [Waveshare JetBot AI Kit a Literally Smart Robot Powered by Jetson Nano](https://www.amazon.com/Waveshare-JetBot-Kit-Accessories-JetBot-Blue/dp/B07V8JL4TF/ref=sr_1_2_sspa?dchild=1&keywords=jetbot&qid=1610200453&sr=8-2-spons&smid=A50C560NZEBBE&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUExR0RIWTQwUjg2SzBTJmVuY3J5cHRlZElkPUEwODA3NTYzMk5HWFBHRlZBTlRQRSZlbmNyeXB0ZWRBZElkPUEwMDkzNzkwQ0dMQ0dYWEhGR09CJndpZGdldE5hbWU9c3BfYXRmJmFjdGlvbj1jbGlja1JlZGlyZWN0JmRvTm90TG9nQ2xpY2s9dHJ1ZQ&th=1)
- [18650 Battery, 3800mAh 3.7V18650 Rechargeable Lithium Battery](https://www.amazon.com/Rechargeable-High-capacity-Environmental-Replacement-Flashlights/dp/B08SBLWM81/ref=sr_1_1_sspa?dchild=1&keywords=jetbot+battery+18650&qid=1610200894&sr=8-1-spons&psc=1&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUEzMDdTTlRSUFk1RExKJmVuY3J5cHRlZElkPUEwOTMwMjcyTEtJR0VDSVNPRVlCJmVuY3J5cHRlZEFkSWQ9QTAzMTEyMzgzNk5YVFM1T0dKUFFUJndpZGdldE5hbWU9c3BfYXRmJmFjdGlvbj1jbGlja1JlZGlyZWN0JmRvTm90TG9nQ2xpY2s9dHJ1ZQ==)

- LEGO City Curve and Crossroad

- [homemade traffic signs](datasets/train_traffic_signs.PNG) (stop, intersection, no left turn, parking, one way)

<p float= "left">
  <img src="https://github.com/whsair/Summer-2020-Learning-Factory-Transforming-Steering-Controls-to-Self-Driving/blob/main/equips.JPG" width="300" height="300" /> 
  <img src="https://github.com/whsair/Summer-2020-Learning-Factory-Transforming-Steering-Controls-to-Self-Driving/blob/main/jetbot.JPG" width="300" height="300"/> 
  <img src="https://github.com/whsair/Summer-2020-Learning-Factory-Transforming-Steering-Controls-to-Self-Driving/blob/main/initi.JPG" width="300" height="300"/> 
  <img src="https://github.com/whsair/Summer-2020-Learning-Factory-Transforming-Steering-Controls-to-Self-Driving/blob/main/roads1.JPG" width="300" height="300"/> 
  <img src="https://github.com/whsair/Summer-2020-Learning-Factory-Transforming-Steering-Controls-to-Self-Driving/blob/main/roads2.JPG" width="300" height="300"/>
  <img src="https://github.com/whsair/Summer-2020-Learning-Factory-Transforming-Steering-Controls-to-Self-Driving/blob/main/size.JPG" width="300" height="300"/> 
  
</p>


### Jetbot Set up
    - JetPack-4.3 Jetson Nano
    - OpenCV-4.1.1
    - TensorRT 6
    - tensorflow 1.15.2 object detection API
    - Pycuda
    - onnx 1.14
- package links: https://jkjung-avt.github.io/jetpack-4.3/
- reference project: https://github.com/jkjung-avt/tensorrt_demos

### Datasets
Collecting 981 in total 224 x 224 raw image by using jetbot camera (high noise && mantual labeled)

    - intersection 195 imgs
    - no left turn 199 imgs
    - no way 197 imgs
    - parking 199 imgs
    - stop 191 imgs
** Format: PASCAL VOC created by [LabelImg](https://github.com/tzutalin/labelImg)

**[Raw images](datasets/Images_og.zip)

**[Raw images (TFRecord)](datasets/traffic_signs.v3-init_dataset.tfrecord.zip)

- Data augmentation
    - resize to 300 x 300 pixels
    - Herizontal flip
    - Rotation between -15 deg to 15 deg
    - Format: Tensorflow TFRecord
    
** [Augmented Datasets](https://drive.google.com/file/d/1tyJhGx-yAy0F_25qsXxzo2VB9SH43WuC/view?usp=sharing)

****_@copyright free to use_**

### Video Reports
- Teleoperation: [Teleoperation Testing](https://drive.google.com/file/d/1SEkde6XVzkewT6LH91lM18Px4zhJcs8a/view?usp=sharing)

- Detecto testing: [1.MOV](https://drive.google.com/file/d/1SEkde6XVzkewT6LH91lM18Px4zhJcs8a/view?usp=sharing) & [2.MOV](https://drive.google.com/file/d/1AMLOAk8_cQoaDnBBNYpHbcnsGg_yG-T5/view?usp=sharing)

- MAX POWER MODE (connected to wires): [SSDMobile-V2](https://drive.google.com/file/d/1UFFwuGqpXytgDv--Ih3T0ZB56-IWadab/view?usp=sharing) & [YOLO-V4-Tiny](https://drive.google.com/file/d/1TgTh_AS7PfQYSGVkxI1BSDHEpGDbUsXR/view?usp=sharing)

- WIRELESS MODE: [SSDMobile-V2](https://drive.google.com/file/d/1c3l0KR-jy-uijQPBIO5OA5TKZKatR8bF/view?usp=sharing) & [YOLO-V4-Tiny](https://drive.google.com/file/d/1Xm74NVDunqzRvSBPHtUBWtQi36dGzhC4/view?usp=sharing)

  - first trial
  
![plot](first_test.gif)

### Wireless Control
Implemented by remote desk
 - NoMachine

## Final Report
  - [Individual report](https://youtu.be/VCOE-HqE7u8)
  - [Group report](https://youtu.be/vH0zk6sewjk)
  
