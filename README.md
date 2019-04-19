# tf-pose-estimation

Openpose的tensorflow实现版本。

## 搭建运行环境

### 依赖库

第一步我们需要将以下的依赖库安装起来，这是本教程实现中必不可缺的主要依赖。

- python3
- tensorflow 1.4.1+
- opencv3, protobuf, python3-tk
- slidingwindow
### 安装

将github的项目克隆到本地，进入到tf—pose目录下，有一个requirements.txt文件，这个文本文件中写好了所有需要的第三方库，比如numpy等，
使用pip命令，可以一次性将这些第三方库安装好。
```bash
$ git clone git@github.com:yinyuecheng1/tf-pose-estimation.git
$ cd tf-openpose
$ pip3 install -r requirements.txt
```
编译第三方库，这里涉及到用swig来编译C++的源码，如果你使用windows系统，那么需要再安装好visual studio 2015和swig，并且配置好环境变量参数，swig只要简短的讲swig.exe添加到系统环境变量中。linux系统下，使用会很方便，直接编译即可。
```bash
$ cd tf_pose/pafprocess
$ swig -python -c++ pafprocess.i && python3 setup.py build_ext --inplace
```

## Demo

### 视频测试

使用方法：我们直接跳过模型训练这一步，直接使用训练好的模型进行测试，run_video.py会读入视频的内容，进行姿态识别之后，再将结果写入新的视频中。
使用方法很简单，运行如下命令即可。

```
$ python3 run_video.py  --video '../cai.mp4'
```



### OpenPose

[1] https://github.com/CMU-Perceptual-Computing-Lab/openpose

[2] Training Codes : https://github.com/ZheC/Realtime_Multi-Person_Pose_Estimation

[3] Custom Caffe by Openpose : https://github.com/CMU-Perceptual-Computing-Lab/caffe_train

[4] Keras Openpose : https://github.com/michalfaber/keras_Realtime_Multi-Person_Pose_Estimation

### Lifting from the deep

[1] Arxiv Paper : https://arxiv.org/abs/1701.00295

[2] https://github.com/DenisTome/Lifting-from-the-Deep-release

### Mobilenet

[1] Original Paper : https://arxiv.org/abs/1704.04861

[2] Pretrained model : https://github.com/tensorflow/models/blob/master/slim/nets/mobilenet_v1.md

### Libraries

[1] Tensorpack : https://github.com/ppwwyyxx/tensorpack

### Tensorflow Tips

[1] Freeze graph : https://github.com/tensorflow/tensorflow/blob/master/tensorflow/python/tools/freeze_graph.py

[2] Optimize graph : https://codelabs.developers.google.com/codelabs/tensorflow-for-poets-2
