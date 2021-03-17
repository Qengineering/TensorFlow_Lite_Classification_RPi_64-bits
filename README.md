![output image](https://qengineering.eu/images/SDcard16GB_tiny.jpg) Find this example on our [SD-image](https://github.com/Qengineering/RPi-image)
# TensorFlow_Lite_Classification_RPi_64-bits
![output image]( https://qengineering.eu/images/SchoolbusUb.png )<br/>
## TensorFlow Lite classification running on a bare Raspberry Pi 4
[![License](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)<br/><br/>
A fast C++ implementation of TensorFlow Lite classification on a bare Raspberry Pi 4. The Raspberry Pi 64 bits version of Ubuntu is used as operating system. Once overclocked to 1925 MHz, your app runs at 23 FPS without any hardware accelerator.

https://arxiv.org/pdf/1712.05877.pdf <br/>
Training set: COCO with 1000 objects<br/>
Size: 224x224 <br/>

## Benchmark.
| Model | RPI 4 @1950 MHz - 64 OS |
|  :------------: | :-------------: |
|  Mobile_V1 Lite |  38.5 FPS |
|  Mobile_V2 Lite |  45.5 FPS |
|  Inception_V2 Lite |  10.0 FPS |
|  Inception_V4 Lite |  2.0 FPS |

With a regular 32 bits Raspbian OS you get lower frame rates see: https://github.com/Qengineering/TensorFlow_Lite_Classification_RPi_32-bits <br/>
<br/>
Special made for a bare Raspberry Pi see: https://qengineering.eu/install-ubuntu-18.04-on-raspberry-pi-4.html <br/>
<br/>
To extract and run the network in Code::Blocks <br/>
$ mkdir *MyDir* <br/>
$ cd *MyDir* <br/>
$ wget https://github.com/Qengineering/TensorFlow_Lite_Classification_RPi_64-bits/archive/master.zip <br/>
$ unzip -j master.zip <br/>
Remove master.zip and README.md as they are no longer needed. <br/> 
$ rm master.zip <br/>
$ rm README.md <br/> <br/>
Your *MyDir* folder must now look like this: <br/> 
tabby.jpeg <br/>
schoolbus.jpg <br/>
grace_hopper.bmp <br/>
Labels.txt <br/>
TensorFlow_Lite_Mobile.cpb <br/>
TensorFlow_Lite_Class.cpp<br/>
 <br/>
Next, choose your model from TensorFlow: https://www.tensorflow.org/lite/guide/hosted_models <br/> 
Download a quantized model, extract the .tflite from the tarball and place it in your *MyDir*. <br/> <br/>
Now your *MyDir* folder may contain: mobilenet_v1_1.0_224_quant.tflite. <br/>
Or: inception_v4_299_quant.tflite. Or both of course. <br/> <br/>
Enter the .tflite file of your choice on line 54 in TensorFlow_Lite_Class.cpp <br/>
The image to be tested is given a line 84, also in TensorFlow_Lite_Class.cpp <br/> <br/>
Run TestTensorFlow_Lite.cpb with Code::Blocks. Remember, you also need a working OpenCV 4 on your Raspberry. <br/>
Preferably use our installation here: https://qengineering.eu/install-ubuntu-18.04-on-raspberry-pi-4.html
