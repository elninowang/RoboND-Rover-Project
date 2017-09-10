## Project: Search and Sample Return 项目:搜索和样品返回

### Writeup Template: You can use this file as a template for your writeup if you want to submit it as a markdown file, but feel free to use some other method and submit a pdf if you prefer.

编写模板：如果您要将其作为一个标记文件提交，您可以使用此文件作为模板，但如果愿意，请随时使用其他方法并提交pdf。

---

**The goals / steps of this project are the following:**  **本项目的目标/步骤如下：**

**Training / Calibration** **训练/矫正**

* Download the simulator and take data in "Training Mode"
* Test out the functions in the Jupyter Notebook provided
* Add functions to detect obstacles and samples of interest (golden rocks)
* Fill in the `process_image()` function with the appropriate image processing steps (perspective transform, color threshold etc.) to get from raw images to a map.  The `output_image` you create in this step should demonstrate that your mapping pipeline works.
* Use `moviepy` to process the images in your saved dataset with the `process_image()` function.  Include the video you produce as part of your submission.

* 下载模拟器并在"Training Mode"下取数据
* 测试提供的Jupyter Notebook中的功能
* 添加功能来检测感兴趣的障碍物和样品（金色岩石）
* 使用适当的图像处理步骤（透视变换，颜色阈值等）填写 `process_image()` 函数，以从原始图像获取到地图。 您在此步骤中创建的`output_image'应该会显示您的映射管道是否正常工作。
* 使用`moviepy`来处理保存的数据集中的 `process_image()`函数的图像。 将您所生产的视频作为您提交的一部分。

**Autonomous Navigation / Mapping** **自主导航/映射**

* Fill in the `perception_step()` function within the `perception.py` script with the appropriate image processing functions to create a map and update `Rover()` data (similar to what you did with `process_image()` in the notebook). 
* Fill in the `decision_step()` function within the `decision.py` script with conditional statements that take into consideration the outputs of the `perception_step()` in deciding how to issue throttle, brake and steering commands. 
* Iterate on your perception and decision function until your rover does a reasonable (need to define metric) job of navigating and mapping.  

* 使用适当的图像处理函数在 `perception.py` 脚本中填入 `perception_step()` 函数，以创建地图并更新 `Rover()` 数据（类似于在 `process_image()`中所做的那些笔记本。
* 在`decision.py`脚本中填入`decision_step（）`函数，其中条件语句在决定如何发出油门，制动和转向命令时考虑到`perception_step()`的输出。
* 迭代您的感知和决策功能，直到您的流动站合理（需要定义度量）导航和映射作业。

[//]: # (Image References)

[image1]: ./misc/rover_image.jpg
[image2]: ./calibration_images/example_grid1.jpg
[image3]: ./calibration_images/example_rock1.jpg 

## [Rubric](https://review.udacity.com/#!/rubrics/916/view) Points
### Here I will consider the rubric points individually and describe how I addressed each point in my implementation.  

在这里，我将分别考虑这些标题，并描述我在实现过程中对每一个问题的解决方法。

---
### Writeup / README  写/自述

#### 1. Provide a Writeup / README that includes all the rubric points and how you addressed each one.  You can submit your writeup as markdown or pdf.  

提供一个写入/自述文件，其中包含所有的标题以及如何处理每个要点。 您可以提交您的writeup作为markdown或pdf。

You're reading it!

你正在读它！

### Notebook Analysis 笔记本分析
#### 1. Run the functions provided in the notebook on test images (first with the test data provided, next on data you have recorded). Add/modify functions to allow for color selection of obstacles and rock samples.

#### 1. 在测试图像上运行笔记本中提供的功能（首先是提供的测试数据，接下来记录的数据）。 添加/修改功能以允许障碍物和岩石样品的颜色选择。

Here is an example of how to include an image in your writeup.

这是一个如何在你的写作中包含一个图像的例子。

![alt text][image1]

#### 1. Populate the `process_image()` function with the appropriate analysis steps to map pixels identifying navigable terrain, obstacles and rock samples into a worldmap.  Run `process_image()` on your test data using the `moviepy` functions provided to create video output of your result. 

#### 1.使用适当的分析步骤填充 `process_image()` 函数，将标识可导航地形，障碍物和岩石样本的像素映射到世界地图中。 使用提供的 `moviepy` 函数创建视频输出结果，在测试数据上运行 `process_image()`。

And another! 和另一个！

![alt text][image2]
### Autonomous Navigation and Mapping

### 自动导航和映射

#### 1. Fill in the `perception_step()` (at the bottom of the `perception.py` script) and `decision_step()` (in `decision.py`) functions in the autonomous mapping scripts and an explanation is provided in the writeup of how and why these functions were modified as they were.

#### 1.在自动映射脚本中填写 `perception_step()`（位于 `perception.py` 脚本底部）和 `decision_step()` 在这些函数是如何以及为什么被修改的。

#### 2. Launching in autonomous mode your rover can navigate and map autonomously.  Explain your results and how you might improve them in your writeup.  

#### 2.以自主模式启动您的流动站可以自主导航和映射。解释你的结果，以及你如何改进他们的写作。

**Note: running the simulator with different choices of resolution and graphics quality may produce different results, particularly on different machines!  Make a note of your simulator settings (resolution and graphics quality set on launch) and frames per second (FPS output to terminal by `drive_rover.py`) in your writeup when you submit the project so your reviewer can reproduce your results.**

**注意：运行不同分辨率和图形质量选择的模拟器可能会产生不同的结果，特别是在不同的机器上！在提交项目时，记下您的模拟器设置（启动时设置的分辨率和图形质量）和每秒帧数（FPS输出到终端的“drive_rover.py”），以便您的评论者可以重现您的结果。

Here I'll talk about the approach I took, what techniques I used, what worked and why, where the pipeline might fail and how I might improve it if I were going to pursue this project further.  

在这里，我将谈谈我采取的方法，我使用了什么技术，什么工作以及为什么管道可能会失败，以及如果我要进一步追求这个项目，我可以改进什么。

![alt text][image3]


