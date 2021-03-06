_**RoboComp** is an open-source Robotics framework providing the tools to create and modify software components that communicate through public interfaces. Components may require, subscribe, implement or publish interfaces in a seamless way. Building new components is done using two domain specific languages, IDSL and CDSL. With IDSL you define an interface and with CDSL you specify how the component will communicate with the world. With this information, a code generator creates C++ and/or Python sources, based on CMake, that compile and execute flawlessly. When some of these features have to be changed, the component can be easily regenerated and all the user specific code is preserved thanks to a simple inheritance mechanism._

* * *


# [Introduction](/website/2016/05/18/BasilWeek1/)

18 May 2016

# INTRODUCTION

Hi all,My name is Basil M Varghese.I am doing my Btech on Electrical Engineering from Indian Institute of Technology Ropar.I am a participant on Google Summer of Codes 2016 under the Organization Robocomp.Before continuing this page I insist you to read about the [robocomp platform](http://robocomp.github.io/website/) if you haven’t.

My aim is to built a GUI tool to deploy and control all the components in a component graph tree created by the framework.The framework already have a similar tool for deploying the components and control them through [yakuake](https://apps.ubuntu.com/cat/applications/precise/yakuake/) tabs for every component.It is currently using Qpainter Widget for drawing the component tree and to select the functionalities.I will be putting the QtGraphicsView framework for the job as it uses Binary space partitioning which will drastically increase the tool’s capacity and functionalities.My job also include building a method to control the deployed components from within the tool itself.

I have divided my work plan into differnt milestones.I have listed it below.

*   Understanding the current code base. * Some part of the code can be reused and it is very important to know the flow and flaw of the current system to create a new tool. * Approximate required time:2 weeks
*   Creating a standalone GUI * This part include building the gui for controlling part,Deploying part and editing part.New icons and menus will be added. * Approximate required time:2 week
*   Creating the new version of rcmanager * This part include building working system for controlling ,Deploying and edit the component. * Approximate required time:4 weeks
*   Testing the code and bug fixing * I have to run the tool with some of the already built component graphs and fix the bugs that may encounter. * Approximate required time:2 weeks
*   Documentation of the new tool * This include documenting about the working of rcmanager in framework website and also making a manual guide of the tool inside the rcmanager itself. * Approximate required time:2 week

So In my plan, I will be able to build a working, fairly documented Gui tool in 12 weeks.The remaining 1 week is part of the contingency plan :).

* * *

Basil M Varghese



# [Introduction about me and my project](/website/2016/05/16/dgallegosWeek0/)

16 May 2016

Hello! My name is Daniel Gallego Sánchez, and I’m going to introduce me in this post. My date of birth is 11/08/1994, I’m ending computer engineering from the University of Extremadura, and actually I am refining my final degree project. Since last year, I have been working in the Robotics Laboratory of the UEx, Robolab. Today, I am using the robotic framework implemented by the laboratory, Robocomp, to perform my degree project which consists in improvement to robocompDSL tool.

Since I am familiar with my organization and mentors, I have started to work in my GSoC project with one of the most basic steps for any teamwork, creating a branch of RoboComp called robocompdslROS. Here I will update all changes and improvement to robocompDSL tool and finally, in August, when all tests are satisfactory I’ll do the **Pull-request**.

My plan to work is spend 1 or 2 hours a day during the month of May and the first week of June, because I haven’t finished my studies. Once I finished (in the first week of June), I’m going to try to keep school hours, working in the mornings and some afternoons if it’s necessary. My main idea is to finish as soon as possible to spend the remaining time testing and fixing bugs that emerge. It would also be very useful for my project to make an user manual robocompDSL tool with the new improvements.

Main idea of this project is the intercompatibility between ROS and RoboComp frameworks. This will required to know about their middlewares, architecture, code generators and know their main differences and similarities. With this intercompatibility you will be able to develop components with Robocomp which may communicate with components **(nodes)** developed with ROS. This offers a wide range of possibilities that benefits both users who often use ROS as those using Robocomp.

What do you need to understand my GSoC project? Well, I will work with **DSL** (domain-specific language), **ROS**, **RoboComp**, **Python**, **C++**, and some **Python modules and tools** called _Cog_, _PyParsing_, etc. Below this post, you will be able to find some links with documentation about this knowledge required.

I will not really use ROS, but it’s necessary to know how it works to carry out the project.

Cog: https://www.python.org/about/success/cog/

PyParsing: http://pyparsing.wikispaces.com/

DSL: https://en.wikipedia.org/wiki/Domain-specific_language

RoboComp’s repository: https://github.com/robocomp


# [Introduction, Problem Statement and deliverables](/website/2016/05/11/swapsharmaWeek0/)

11 May 2016

# Introduction

It is my real pleasure to work with RoboComp in Gsoc. My name is Swapnil Sharma and I am going to introduce myself and give a brief overview of problem statemnt and its deliverables in this first post. I am doing my B.Tech from IIT Mandi with CS Major.

# Problem Statement

> Automating the uploading of binary files using git-annex

Currently, the process of uploading binary files is tedious and lengthy and users have to run many commands whenever they want to upload a small file.

So, to prevent the user from getting lost, a special tool is required which can automate the uploading process of binary. It will take care of all the steps required to upload a binary file to a server storage and adding its link to git-annex for its managment.

# Deliverables

The end product of this project will be a command line utility that will take the name of the binary file from user and upload that particular file to storage server.

Swapnil Sharma


# [GSoC 2016 Ideas](/website/2016/04/25/gsoc16ideas/)

25 Apr 2016

## RoboComp’s DSL based code generator

RoboComp’s components are automatically generated using a tool named robocompdsl which takes as input a text file written in a domain-specific language (DSL) named (Component Description Specific Language). These files describe several characteristics of the components such as the network connections to other components, the programming language in which it is going to be written (currently C++ and Python languages are supported), the kind of user interface it will have (if any) and other options such as if the component will make use of third-party libraries. Given a CDSL file and a path, robocompdsl generates a source code tree ready to be compiled for the component described in the file. In this source code tree there are files which the user will not need to modify (these are called generic files) and files in which the user is supposed to type the code (specific files). Once a component has been generated, only generic files are overwritten upon re-generation, new specific files are created with an additional ‘.new’ extension. This tool allows users to create components very quickly, avoids frequent errors and contributes to keep high quality coding standards.

Despite the undeniable benefits brought by robocompdsl, there are some important updates to make and new features to introduce. This is one of the goals of this GSoC’16 proposal. In particular, we propose these first three new features:

## 1\. Qt5 and ROS support

Qt5 support. Currently only Qt4, both in C++ and Python, are supported. Supporting Qt5 would be interesting because the new version of the library is now quite mature, has new features and someday Qt4 will be outdated. Also, there is already support for Qt5 in Python through PyQt5\. The work needed for this activity will deal with the necessary modifications in the DSL parsing and code generation.

ROS support (currently underway). ROS support is a pressing issue mainly due to the high popularity of ROS and the possibility to access a number of robot hardware elements that provide ROS interfaces and other interesting packages provided by research groups and companies. Also, it is the usual way of talking to virtual referees in robotic competitions. Supporting ROS within our framework will allow users to use ROS and RoboComp components seamlessly.

Technologies involved: C++, Python, Qt5, ROS

Mentor: Luis J. Manso Backup mentor: Marco A. Gutiérrez

## 2\. Javascript support

NodeJS component code generation. An interesting diversion from current robotics technologies based on C++ and Python would be the use of Javascript as the language to code some highly concurrent components. Most components combine push-pull and RPC communication models to talk to other components in their graph of processes. Additionally, several more threads are normally used to handle the component’s internal workings. In this activity, the code generator will be extended to include Javascript running in a server as a new target language for components. The main restriction here is that ZeroC releases a version of the Ice middleware running on Node, since the web browser version is already out.

_Technologies involved: C++, Python, Qt5, OSG_

Mentor: Luis J. Manso

Backup mentor: Marco A. Gutiérrez

## 3\. Automatic code generation for State Machines

Currently, the code generator only generates code for the generic part of the component, including the communications middleware and the binary building machinery. In this activity we want to extend robocompdsl to allow for the specification of a state machine, as the computing model driving the specific functionality of the component. The component definition language will now include instructions to define a set of states and transitions between them, so a functioning machine using Qt State Machine Framework is automatically instantiated when generated.

_Technologies involved: C++, Python, Qt_

Mentor: Pablo Bustos Backup mentor: Luis J. Manso

## Interesting improvements for RoboComp’s inner workings dealing with installation, deployment, math libraries, etc.

## 4\. Facilitating the deployment of RoboComp on different platforms

Deployment of a complex framework on different, heterogeneous platforms is always a difficult problem. Also, horizontally scaling the deployment of components when more computational resources are needed is also a complicated issue. The idea of this activity is to ease the deployment of the Robocomp framework within several different platforms and to provide tools to decouple the logical graph of processes from the underlying hardware. In order to achieve that the thing needed to be done are:

*   First, a refactoring of the CMake structure within RoboComp is needed so basic requirements for installation are reduced to a minimum. On the same page, this activity should ease the task for new developers to add new libraries, classes, tools or modules to the framework.
*   To facilitate the deployment on different operating systems, a fully functional Docker container for RoboComp will be developed so instant deployment will be available on heterogeneous platforms through the docker tool.
*   A semi-automatic procedure to update changes from the repository to the Docker container will be established.
*   To study and analyze virtual infrastructure solutions, such as Open Stack, to provide a virtualized infrastructure that can integrate the physical cluster onboard the robot and external servers for less responsive, but highly computationally demanding, tasks.

_Technologies involved: cmake, docker, git_

Mentor: Marco A. Gutiérrez

Backup Mentors: Luis J. Manso

## 5\. Automating the uploading of binary files for git-annex

The process of uploading binary files to git-annex is currently a tedious task and it ends up with developers trying to avoid the use of this tool and looking for alternatives to store binary files. A new alternative needs to be developed ether having a specific tool for that automates the addition of new bin files to git-annex or switching to a new tool that takes care of the binary files. First a tedious research in current alternatives and or proper solutions to the git-annex problem should be discussed. After the community selects one among the proposed solutions this must be implemented by the student and all previous binaries should be ported to the new solution.

The final solution should basically be a command that would take the binary as an input upload it to the storage server and add the link to git-annex or the selected technology in charge of the binary files tracking.

_Technologies involved: git, git-annex, C++, cmake_

Mentors: Rajath Kumar

Backup mentor: Felipe Cid

## 6\. Writing a name and port service for running components

This activity deals with writing a new component in RoboComp that will provide a naming and port service. When starting, components will now contact this new service to advertise its name, available interfaces and request a valid port. Other components starting later will be able to query the service for component names and interfaces, and therefore being able to establish their proxy connections in real time, eliminating the need for complex and tedious configuration files. Extensive tests with large networks of components will be performed and more advances query capabilities for the service will be explored.

Technologies involved: C++, Python, Qt

Mentor: Luis J. Manso Backup mentor: Marco A. Gutiérrez

## 7\. A new graphical tool for deploying components

Building on the existing python-based Manager tool in RoboComp, this activity will improve the current Python based design with more features. The new tool will facilitate the creation and modification of deployment files and will allow a much better access to the management interfaces of the componets. It will be based on Qt’s Graphics View Framework. With this new tool we expect that larger component networks with more than 50 componentes, will be easy to deploy and monitor at run time. The current tool, Manager, reads an XML file with a description of all components involved in the deployment, their localization (IP and port) and configuration parameters. With this information the program starts all the processes and detaches from them once they are up and safe. From there on, the program’s UI displays a graph of the running components, their dependencies and some basic information about them. We would like to improve this program in several ways:

*   Add a tools palette in the UI so new components can be created and dragged to the central canvas. Once there the XML file will be updated. Also, the components could be interconnected by the user as long as some basic syntactic and semantic rules are obeyed.
*   Add a new panel in the UI to allow the user to communicate with the components through the existing CommonBehavior interface. This interfaces is created for all components and provides a common way to query their running status, memory use, iteration main period, pause, resume, abort and to change in line some of the configuration parameters.

Technologies involved: Python, PySide, Qt

Mentor: Pablo Bustos Backup mentor: Luis J. Manso

## 8\. Port of RoboComp’s math library, QMat, to Eigen3

Long before Eigen was out there we wrote QMat, a linear algebra library written as a wrapper to other existing math libraries such as IPP or GSL or even our own code. QMat has a lot o nice methods and functions that we have written as we needed them and that are specially suited for our other core library InnerModel. InnerModel is class that holds and allows access to the kinematic tree used by most of the components in RoboComp. This tree represents the state of the robot and the world perceived by it. It can be displayed in 3D using OpenSceneGraph (see activity 11) and used to perform many importan calculations in robotics. In this activiy We would like to:

*   port QMat to Eigen
*   write a QMat/InnerModel without dependencies of RoboComp and that can be used as an independent piece of code for kinematic representations and calculations.

Technologies involved: C++, Eigen

Mentor: Luis J. Manso Backup mentor: Pablo Bustos

## And finally, some work on computer vision and 3D graphics

## 9\. Object detection for simulated environments

We have several algorithms that are trained with information from real environments. Making this algorithms work in our simulation environment is not the straightforward task it should be. We would like to have a tool that takes as input several 3D objects and generates the infrastructure needed to train these algorithms. As an example provided to users different algorithms must be trained so their effectivity can be tested with the robocomp simulation environment. Development of some Neural Networks Structures might be required to improve the algorithms results.

_Technologies involved: CNN, C++_

Mentors: Ramón Cintas, Felilpe Cid

Backup Mentors: Marco A. Gutiérrez

## 10\. Computer vision components and integration with openDetection

Open Detection is a library developed by a student during GSoC 2015\. The idea was to develop a library to ease the development of computer vision tasks such as object recognition. This library is now a stand alone project but in robocomp we would like to keep a link with it and have some examples integrated in our components structure. An automated integration of this library should be performed such as it becomes transparent for the robocomp user. Also several components should be developed making use of the main features of this library so the computer vision algorithms from Open Detection can be used through different components interfaces.

Along with this some extra components will be required to be developed as an abstraction for the main features of other Computer Vision Libraries such as OpenCV and the Point Cloud Library.

_Technologies involved: C++, OpenCV, Pointcloud Library, cmake_

Mentor: Kripasindhu Sarkar

Backup mentor: Marco A. Gutiérrez

## 11\. 3D visualization of internal structures in real time

Current Model graphs used in RoboComp mainly for cognitive world modeling are not clear to understand, especially when they are big, which they usually are. Making these graphs easier to read and their information easier to access is a key task that will ease the task of debugging and understanding these graphs and in consequence a robot’s mind. Specific research and tests with roboticists should be performed in order to find a way of displaying this information that helps anyone understand the whole graph. Once specific key assets are detected they should be implemented one by one and properly tested with some roboticists to ensure they are widely accepted as a proper enhancement. Several of these features should be developed until the graph becomes easily readable and can be easily managed through the graphical interface provided in robocomp.

_Techonolgies involved: python, Qt5, OSG, Active grammar-based Modeling (AGM)_

Mentors: Luis J. Manso, Pablo Bustos

Backup mentor: Ramon Cintas, Marco A. Gutiérrez

## 12\. Gazebo-RoboComp integration

Currently RoboComps uses a lightweight non-physics simulator based on OpenSceneGraph. In order to work on more demanding robots such as hexapods and drones we need to write an adpatation layer to a physics-based simulator like Gazebo. The idea is to write a set of plugins for Gazebo, each one providing one or several of the RoboComp low-level hardware interfaces. To test the new functionality, two controllers will be written for two robots in the lab, one for a Phantom X Hexapod and one for a Parrot drone.

_Techonologies involved: C++, Gazebo, RoboComp_

Mentors: Pablo Bustos, Luis Manso

Backup mentor: Ramon Cintas

## 12\. RoboComp and RTAB-Map Integration

The main objective of the proposal is to successfully incorporate within the RoboComp robotic framework RGB-D localization and mapping capabilities. Concretely, the proposal would take advantage of RTAB-Map (Real-Time Appearance-Based Mapping), a RGB-D Graph-Based SLAM solution. Taking into account that both RoboComp and RTAB-Map are coded in C++ and well documented, GSoC students are expected to carry out the integration after a small documentation stage with no explicit cross-platform drawbacks. RTAB-Map has been properly integrated in ROS, which can also serve as a reference for students. Objectives of the proposal Among all the functionalities offered by RTAB-Map, we are mainly interested on the mapping and localization based on RGB-D sensors such as Microsoft Kinect or Asus XTion. Generated maps should be stored using the file format of the Point Cloud Library, which would facilitate further developments relying on such interesting library including segmentation and recognition based on 3D features. Moreover, generated maps may serve for the generation of synthetic environments for the RCIS simulator. This process would allow RoboComp developers to perform more realistic simulations using scenes fully connected to real-world.

**Expected results**

*   Generation of RGB-D mapping RoboComp components
*   Generation of RGB-D localization RoboComp components
*   Generation of maps stored in the PCL file format
*   Export RGB-D maps perceived in real-world to simulated RSIM environments.

**Further developments** While RTAB-Map algorithms mainly rely on visual descriptors, namely SIFT and SURF, this solution could be extended to include within its pipeline several 3D features already implemented in the PCL, such as SHOT or FPFH. This novelty would allow the SLAM algorithms to properly work under challenging situations with poor or even lack of illumination. Students desired skills

*   C++ programming
*   Localization and mapping
*   3D graphics toolkits
*   3D processing libraries
*   RPC frameworks

**Useful links** RoboComp: https://github.com/robocomp/robocomp RTAB-MAP:http://introlab.github.io/rtabmap/ Point Cloud Library (PCL): http://pointclouds.org/ ICE:https://zeroc.com/products/ice Open Scene Graph: http://www.openscenegraph.org/

Mentors: Jesús Martínez, Cristina Romero

Backup mentor: Ismael García-Varea


# [Packaging FCL and libccd](/website/2015/08/21/nithin11/)

21 Aug 2015

I assume that you have an debian package folder in your source directory. If not refer to the intro to debian packaging tutorial.

Now lets assume that you are going to upload the package for the first time into a ppa.

###Creating source package

*   Rename the source directory into <project_name>- <version>eg libccd-2.01</version></project_name>
*   Crate a .tar.gz compressed file of the source directory, and place it outside source directory
*   Rename the compressed file into <project_name>_<version>.orig.tar.gz</version></project_name>
*   Now run `debuild -k<gpg_key> -S -sa` if you want to include the whole source tar in upload
*   Or run `debuild -k<gpg_key> -S -sd` if you don’t want to include the whole source tar in upload

###So when should you upload the source? when you are uploading for the first time (obviously) and whenever you make some changes to your source code. but as launchpad wont allow files with same name, you should increase your version number so that the source tar get a new name. For increasing the version number you should increase it in changelog for example in this case `fcl (1.0-0ppa0) vivid; urgency=low` increase 1.0-0ppa0 to 1.1-0ppa0 also remember to rename all names accordingly (source folder and source tar)

but if you have only changed some file in the debian directory. For example, edited changelog or added a dependency. In those cases you can skip the source upload but in such cases you have to increase your ppa number in your changelog for example in this line `fcl (1.0-0ppa0) vivid; urgency=low` change 0ppa0 to 0ppa1.

###uploading Now once you have generated the .source_changes file use dput to upload



```
dput ppa:<your-lp-id>/<name> <file_name>.source_changes

```


###NB

*   if you want to add any dependency, edit the file debian/control add add it to `Depends` or `Build-Depends` field
*   if you want to change the target generation , edit the distribution name in first line of debian/changelog

* * *

Nithin Murali

[Older](/web/page7) [Newer](/web/page5)