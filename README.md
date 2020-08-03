# Libs_Multiplatform —— Create Library used in different platform
+ This repository contain some libraries which can be used in different platforms such as Linux, Windows and Mac. Anyone who want to use the libraries can download this repository and add to your own project easily.   
+ The general step to get the library from source codes is shown as:
```
git clone (the github address)  # download source codes
cd  /path   # Enter the repository directory
mkdir build  # Create the compile workspace
cd ./build
cmake ..   # U can configure some parmeters(e.g., DNN_STATIC_LIB in nanomsg, DOPENCV_EXTRA_MODULES_PATH in OpenCV)
make -j4  or cmake --build .  # Compile the source codes
sudo make install  or sudo cmake --build . --target install  # Install the results(library and include files) to some directory
```
#### Comments
+ Actually it's not necessary to run the install step; U can find the include files in source codes and obtain the libraries in the build directory.  
+ All libraries in this repository is compiled using **master** branch.  
+ All libraries in this repository only supports C++ environment.
# apriltag
+ AprilTag library is constructed using my other repository [AprilTag_MultiPlatform](https://github.com/tzhangZJU/AprilTag_MultiPlatform). Now the apriltag library is compiled using [AprilTag_MultiPlatform](https://github.com/tzhangZJU/AprilTag_MultiPlatform.git) based official AprilTag 3 on 2020-08-03.  

# nanomsg
+ Nanomsg library is constructed based [official version](https://github.com/nanomsg/nanomsg). To get static version, -DNN_STATIC_LIB=ON should be a parameter in cmake. This library is compiled on 2020-07-13.

# opencv
+ OpenCV library is the one of the most widely used libraries during my work. To use OpenCV in different platforms easily, i often add the corresponding OpenCV library to my project. The official OpenCV codes can be obtained in [github](https://github.com/opencv/opencv) and the **contrib part** is [here](https://github.com/opencv/opencv_contrib). To compile the contrib part, the parameter -DOPENCV_EXTRA_MODULES_PATH should be defined in cmake command. A example command which could get the OpenCV library in Mac shown as:
```
cmake -DCMAKE_BUILD_TYPE=Release -DOPENCV_EXTRA_MODULES_PATH=../../opencv_contrib/modules 
-DBUILD_TESTS=OFF -DBUILD_SHARED_LIBS=OFF -DWITH_IPP=OFF -DCMAKE_INSTALL_PREFIX=../install 
-DWITH_LAPACK=OFF -DWITH_AVFOUNDATION=OFF -DWITH_FFMPEG=OFF -DWITH_OPENCL=OFF -DHAVE_OPENCL=OFF -DWITH_ITT=OFF ..
```
+ This library is compiled on using **OpenCV 4.0.1** 2020-07-17.
# yaml-cpp
+ The yaml-cpp can be used to parse the yaml file using C++ and its source code is [here](https://github.com/jbeder/yaml-cpp). This library is compiled on 2020-07-13.