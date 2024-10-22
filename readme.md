# Beauty AI

## Features

Beauty is an AI drive app that can help user become beautiful.

it contain those functions:

1. face score cheek

2. face beauty report

3. face imporve proposals

4. face comparison ( pk )

right now, it can only support asian women

and other function is under construction

The latest Android Version download:

https://gitee.com/knifecms/beauty/releases

(there is no web connection data transfer, every function works in mobile locally )

| 
<img src="https://images.gitee.com/uploads/images/2021/1113/184617_abba5aa6_6788.jpeg" width="240px" /> |
<img src="https://images.gitee.com/uploads/images/2021/1113/184630_b9985938_6788.jpeg" width="240px" /> |
<img src="https://images.gitee.com/uploads/images/2022/0127/140034_fa2edae2_6788.jpeg" width="240px" /> |
|---|---|---|


## Project Introduce


### 1.face contour detection

use Dlib 

### 2.face skin detection

byol + lda

### 3.Overall characteristics

resnet

## Sub projects

1. [android beauty app](./App/readme.md)

2. [deep learning face beauty research](./dl/readme.md)

3. [asian face leaderboard](./leaderboard/readme.md)

    and leaderboard website: http://1mei.fit

## Environment

- Python 3.8

## Usage in python

#### 1.clone:

    git clone https://gitee.com/knifecms/beauty.git
    or
    git clone https://github.com/showkeyjar/beauty.git

#### 2.Install depend;

##### 2.1 new install:

    conda install cmake
    conda install nodejs
    conda install dlib

##### 2.2 Import conda env：

    conda env create -f face.yaml

#### 3.Modify predict.py image path

    # change the detect image path
    test = "data/2.jpg"

#### 4.Execute:

    python predict.py

    you can get beauty score in [0-5], the higher the better

#### 5.Interpretation of results:

    execute dir landmarks/ 
    
        1_gen_feature.py 
        
        2_prepare_data.py 
        
    gen features in: data/face/features.csv

    then run:
    
    python predict_interpret.py

#### 6.run in cam:

    python predict_cam.py

#### 7.run web service:

    python predict_server.py

    or run:
    
    ./restart_server.sh

preview：

http://locahost:5000/pred


we use two tech to explain result: lime and shap(recommend)

![face point](img/point.jpg)

![face_reoprt](img/report.jpg)

## Todo

1.redesign the face report, do not use AI explain framework but combine small face part scores.

2.face score explain

3.use lbph in android to detect skin type

4.use semantic structural features

### DEV:

train data:

https://github.com/HCIILAB/SCUT-FBP5500-Database-Release

Directory description:

    App     	    android project
    dl              deep learning models
    doc             documents
    feature         face features
    landmarks       face landmarks process
    leaderboard     asian face leaderboard
    logs            log dirs
    model           trained models
    static          flask web assets
    template        flask templates
    test            unit test


![ak net](./img/s1.png)

## reference

https://wenku.baidu.com/view/b10e711ba58da0116c1749e6.html

https://wenku.baidu.com/view/29392bbb9fc3d5bbfd0a79563c1ec5da50e2d6eb.html

https://max.book118.com/html/2017/1115/140076049.shtm

## Other research progress

https://github.com/bknyaz/beauty_vision

https://github.com/ustcqidi/BeautyPredict

http://antitza.com/assessment_female_beauty.pdf


The Beauty of Capturing Faces: Rating the Quality of Digital Portraits
https://arxiv.org/abs/1501.07304v1

SCUT-FBP5500: A Diverse Benchmark Dataset for Multi-Paradigm Facial Beauty Prediction
https://arxiv.org/abs/1801.06345v1

Understanding Beauty via Deep Facial Features:
https://arxiv.org/pdf/1902.05380.pdf

