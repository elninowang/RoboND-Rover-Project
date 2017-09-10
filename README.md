[//]: # (Image References)
[image_0]: ./misc/rover_image.jpg
[![Udacity - Robotics NanoDegree Program](https://s3-us-west-1.amazonaws.com/udacity-robotics/Extra+Images/RoboND_flag.png)](https://www.udacity.com/robotics)
# Search and Sample Return Project 搜索和样品回收项目

![alt text][image_0] 

This project is modeled after the [NASA sample return challenge](https://www.nasa.gov/directorates/spacetech/centennial_challenges/sample_return_robot/index.html) and it will give you first hand experience with the three essential elements of robotics, which are perception, decision making and actuation.  You will carry out this project in a simulator environment built with the Unity game engine.  

这个项目是在[美国航空航天局样本返回挑战](https://www.nasa.gov/directorates/spacetech/centennial_challenges/sample_return_robot/index.html)之后建模的，它将为您提供机器人三个基本要素的第一手体验 ，这是感知，决策和启动。 您将在使用Unity游戏引擎构建的模拟器环境中执行此项目。

## The Simulator 模拟器
The first step is to download the simulator build that's appropriate for your operating system.  Here are the links for [Linux](https://s3-us-west-1.amazonaws.com/udacity-robotics/Rover+Unity+Sims/Linux_Roversim.zip), [Mac](https://s3-us-west-1.amazonaws.com/udacity-robotics/Rover+Unity+Sims/Mac_Roversim.zip), or [Windows](https://s3-us-west-1.amazonaws.com/udacity-robotics/Rover+Unity+Sims/Windows_Roversim.zip).  

第一步是下载适合您的操作系统的模拟器构建。 以下是[Linux](https://s3-us-west-1.amazonaws.com/udacity-robotics/Rover+Unity+Sims/Linux_Roversim.zip)，[Mac](https://s3-us-west-1.amazonaws.com/udacity-robotics/Rover+Unity+Sims/Mac_Roversim.zip) 或 [Windows](https://s3-us-west-1.amazonaws.com/udacity-robotics/Rover+Unity+Sims/Windows_Roversim.zip)。


You can test out the simulator by opening it up and choosing "Training Mode".  Use the mouse or keyboard to navigate around the environment and see how it looks.

您可以通过打开模拟器并选择“训练模式”来测试模拟器。 使用鼠标或键盘来浏览环境，看看它的外观。

## Dependencies 依赖
You'll need Python 3 and Jupyter Notebooks installed to do this project.  The best way to get setup with these if you are not already is to use Anaconda following along with the [RoboND-Python-Starterkit](https://github.com/ryan-keenan/RoboND-Python-Starterkit). 

您将需要安装Python 3和Jupyter笔记本来完成此项目。 如果您还没有使用Anaconda，则可以使用[RoboND-Python-Starterkit](https://github.com/ryan-keenan/RoboND-Python-Starterkit) 进行安装。

Here is a great link for learning more about [Anaconda and Jupyter Notebooks](https://classroom.udacity.com/courses/ud1111)

这里了解更多关于 [Anaconda and Jupyter Notebooks](https://classroom.udacity.com/courses/ud1111) 

## Recording Data 记录数据
I've saved some test data for you in the folder called `test_dataset`.  In that folder you'll find a csv file with the output data for steering, throttle position etc. and the pathnames to the images recorded in each run.  I've also saved a few images in the folder called `calibration_images` to do some of the initial calibration steps with.  

我在一个名为`test_dataset`的文件夹中保存了一些测试数据。 在该文件夹中，您将找到一个csv文件，其中包含转向，节气门位置等的输出数据以及每次运行中记录的图像的路径名。 我还在名为 `calibration_images` 的文件夹中保存了几个图像，以执行一些初始校准步骤。

The first step of this project is to record data on your own.  To do this, you should first create a new folder to store the image data in.  Then launch the simulator and choose "Training Mode" then hit "r".  Navigate to the directory you want to store data in, select it, and then drive around collecting data.  Hit "r" again to stop data collection.

这个项目的第一步是自己记录数据。 为此，您应该首先创建一个新的文件夹来存储图像数据。然后启动模拟器并选择“训练模式”，然后点击“r”。 导航到要存储数据的目录，选择它，然后围绕收集数据。 再次点击“r”停止收集数据。

## Data Analysis 数据分析
Included in the IPython notebook called `Rover_Project_Test_Notebook.ipynb` are the functions from the lesson for performing the various steps of this project.  The notebook should function as is without need for modification at this point.  To see what's in the notebook and execute the code there, start the jupyter notebook server at the command line like this:

名为 `Rover_Project_Test_Notebook.ipynb` 的IPython笔记本中包含执行本项目各个步骤的功能。 笔记本电脑应该按原样运行，无需修改。 要查看笔记本电脑中的内容并执行代码，请在命令行中启动jupyter笔记本电脑服务器，如下所示：

```sh
jupyter notebook
```
This command will bring up a browser window in the current directory where you can navigate to wherever `Rover_Project_Test_Notebook.ipynb` is and select it.  Run the cells in the notebook from top to bottom to see the various data analysis steps.  

此命令将在当前目录中打开一个浏览器窗口，您可以在其中导航到 `Rover_Project_Test_Notebook.ipynb`，然后选择它。 从上到下运行笔记本，查看各种数据分析步骤。

The last two cells in the notebook are for running the analysis on a folder of test images to create a map of the simulator environment and write the output to a video.  These cells should run as-is and save a video called `test_mapping.mp4` to the `output` folder.  This should give you an idea of how to go about modifying the `process_image()` function to perform mapping on your data.  

笔记本中的最后两个单元格用于在测试图像文件夹上运行分析，以创建模拟器环境的映射，并将输出写入视频。 这些单元格应该按原样运行，并将一个名为`test_mapping.mp4`的视频保存到`output`文件夹。 这应该让您了解如何修改 `process_image()` 函数来对数据执行映射。

## Navigating Autonomously 自主导航
The file called `drive_rover.py` is what you will use to navigate the environment in autonomous mode.  This script calls functions from within `perception.py` and `decision.py`.  The functions defined in the IPython notebook are all included in`perception.py` and it's your job to fill in the function called `perception_step()` with the appropriate processing steps and update the rover map. `decision.py` includes another function called `decision_step()`, which includes an example of a conditional statement you could use to navigate autonomously.  Here you should implement other conditionals to make driving decisions based on the rover's state and the results of the `perception_step()` analysis.

名为 `drive_rover.py` 的文件将用于以自主模式导航环境。 该脚本从`perception.py`和`decision.py`中调用函数。 IPython笔记本中定义的功能都包含在`perception.py`中，您的工作是使用适当的处理步骤填写名为 `perception_step()` 的函数，并更新漫游器映射。 `decision.py` 包括另一个名为 `decision_step()` 的函数，其中包含一个可用于自主导航的条件语句的示例。 在这里，您应该实现其他条件来根据流动站的状态和 `perception_step()` 分析的结果进行驾驶决策。

`drive_rover.py` should work as is if you have all the required Python packages installed. Call it at the command line like this: 

如果您安装了所有必需的Python软件包，`drive_rover.py`  应该可以正常工作。 在命令行中调用它，如下所示：

```sh
python drive_rover.py
```  
Then launch the simulator and choose "Autonomous Mode".  The rover should drive itself now!  It doesn't drive that well yet, but it's your job to make it better!  

然后启动模拟器并选择 "Autonomous Mode"。 Rover应该现在开车了！ 它没有开车，但是，这是你的工作，使它更好！

**Note: running the simulator with different choices of resolution and graphics quality may produce different results!  Make a note of your simulator settings in your writeup when you submit the project.**

**注意：运行模拟器具有不同选择的分辨率和图形质量可能会产生不同的结果！ 在您提交项目时，在备注中记下您的模拟器设置。**

### Project Walkthrough 项目演练
If you're struggling to get started on this project, or just want some help getting your code up to the minimum standards for a passing submission, we've recorded a walkthrough of the basic implementation for you but **spoiler alert: this [Project Walkthrough Video](https://www.youtube.com/watch?v=oJA6QHDPdQw) contains a basic solution to the project!**.

如果你正在努力开始这个项目，或者只是想要一些帮助，让您的代码达到最低标准的传递提交，我们已经记录了一个基本实现的演练，但**扰流警报：这[项目演练视频](https://www.youtube.com/watch?v=oJA6QHDPdQw)包含项目的基本解决方案！**。
