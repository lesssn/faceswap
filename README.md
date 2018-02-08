
**Notice:** This repository is not operated or maintained by [/u/deepfakes](https://www.reddit.com/user/deepfakes/). Please read the explanation below for details.

---

# deepfakes_faceswap

Faceswap是一个利用深度学习识别图片和视频中的人脸并能进行交换人脸的工具

## 概述
The project has multiple entry points. You will have to:
 - 生成图片 (或者使用下面提供的训练数据)
 - 从原始图片中提取（**Extract**） 人脸
 - 使用图片训练（**Train**）一个模型 (或者使用下面提供的训练数据)
 - 使用生成的模型转换(**Convert**) sources中的图片

### Extract
从你的安装目录, 运行`python faceswap.py extract`. 该命令会从`src`文件中的图片提取出人脸导出到`extract`文件夹.

### Train
从软件安装目录，运行`python faceswap.py train`进行训练，训练时从两个包含人脸的图片目录中的图片训练模型并将生成的模型保存到`models`目录。

### Convert
从软件安装目录, 运行 `python faceswap.py convert`. 该命令会将`original`目录中图片替换人脸并将新生成的图片保存到`modified`目录.

#### General notes:
- All of the scripts mentioned have `-h`/`--help` options with a arguments that they will accept. You're smart, you can figure out how this works, right?!

Note: there is no conversion for video yet. You can use MJPG to convert video into photos, process images, and convert images back to video

## Training Data  
**Whole project with training images and trained model (~300MB):**  
https://anonfile.com/p7w3m0d5be/face-swap.zip or [click here to download](https://anonfile.com/p7w3m0d5be/face-swap.zip)

## How To setup and run the project

### Setup 

Clone the repo and setup you environment. There is a Dockerfile that should kickstart you. Otherwise you can setup things manually, see in the Dockerfiles for dependencies.

Check out [../blob/master/INSTALL.md](INSTALL.md) and [../blob/master/USAGE.md](USAGE.md) for basic information on how to configure virtualenv and use the program.

You also need a modern GPU with CUDA support for best performance

**Some tips:**

Reusing existing models will train much faster than starting from nothing.  
If there is not enough training data, start with someone who looks similar, then switch the data.

#### Docker
If you prefer using Docker, You can start the project with:
 - Build: `docker build -t deepfakes .`
 - Run: `docker run --rm --name deepfakes -v [src_folder]:/srv -it deepfakes bash` . `bash` can be replaced by your command line 
Note that the Dockerfile does not have all good requirments, so it will fail on some python 3 commands.
Also note that it does not have a GUI output, so the train.py will fail on showing image. You can comment this, or save it as a file.

## How to contribute

### For people interested in the generative models
 - Go to the 'faceswap-model' to discuss/suggest/commit alternatives to the current algorithm.

### For devs
 - Read this README entirely
 - Fork the repo
 - Download the data with the link provided below
 - Play with it
 - Check issues with the 'dev' tag
 - For devs more interested in computer vision and openCV, look at issues with the 'opencv' tag. Also feel free to add your own alternatives/improvments
 
### For non-dev advanced users
 - Read this README entirely
 - Clone the repo
 - Download the data with the link provided below
 - Play with it
 - Check issues with the 'advuser' tag
 - Also go to the 'faceswap-playground' repo and help others.

### For end-users
 - Get the code here and play with it if you can
 - You can also go to the 'faceswap-playground' repo and help or get help from others.
 - Be patient. This is relatively new technology for developers as well. Much effort is already being put into making this program easy to use for the average user. It just takes time!
 - **Notice** Any issue related to running the code has to be open in the 'faceswap-playground' project!

### For haters
Sorry no time for that

# About github.com/deepfakes

## What is this repo?
It is a community repository for active users.

## Why this repo?
The joshua-wu repo seems not active. Simple bugs like missing _http://_ in front of url has not been solved since days.

## Why is it named 'deepfakes' if it is not /u/deepfakes?
 1. Because a typosquat would have happened sooner or later as project grows
 2. Because all glory go to /u/deepfakes
 3. Because it will better federate contributors and users
 
## What if /u/deepfakes feels bad about that?
This is a friendly typosquat, and it is fully dedicated to the project. If /u/deepfakes wants to take over this repo/user and drive the project, he is welcomed to do so (Raise an issue, and he will be contacted on Reddit). Please do not send /u/deepfakes messages for help with the code you find here.

# About machine learning

## How does a computer know how to recognise/shape a faces? How does machine learning work? What is a neural network?

It's complicated. Here's a good video that makes the process understandable:
[![How Machines Learn](https://img.youtube.com/vi/R9OHn5ZF4Uo/0.jpg)](https://www.youtube.com/watch?v=R9OHn5ZF4Uo)

Here's a slightly more in depth video that tries to explain the basic functioning of a neural network:
[![How Machines Learn](https://img.youtube.com/vi/aircAruvnKk/0.jpg)](https://www.youtube.com/watch?v=aircAruvnKk)

tl;dr: training data + trial and error
