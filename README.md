
# Edge Impulse ESP32 Cam Arduino Nano Tinkercode Setup

This is an AI Image Classification using Edge Impulse as model training and ESP32 Cam as inference device. The ESP32 cam will communicate with Arduino nano using Serial Port communication to send the inference results once requested.



## Acknowledgements

 - [EloquentESP32Cam for Image Collection](https://github.com/eloquentarduino/EloquentEsp32cam)
 - [Edge Impulse Github](https://github.com/edgeimpulse)


## Usage/Examples

1.  Train AI Model with Edge Impulse using image captured with ESP32Cam(EloquentESP32Cam library)
2.  Export model to Arduino library 
3.  Upload model and code for inferencing to  ESP32Cam
4.  Open, modify and upload Tinkercode block for Arduino Nano



## Step by Step

## 1.  Install EloquentESP32Cam library in Arduino IDE

![alt text](https://github.com/apauaie/ai_esp32_cam_ei/blob/main/media/1InstallEloquentESP32Cam.png?raw=true)


## 2.  Open Examples->EloquentESP32Cam->Collect_images_for_EdgeImpulse

![alt text](https://github.com/apauaie/ai_esp32_cam_ei/blob/main/media/2OpenExample.png?raw=true)

## 3.  Change WIFI SSID and KEY, change wroom_s3 to aithinker 

![alt text](https://github.com/apauaie/ai_esp32_cam_ei/blob/main/media/3ModifyWifiandCamera.png?raw=true)


## 4.  Upload Code to AI Thinker ESP32Cam 

![alt text](https://github.com/apauaie/ai_esp32_cam_ei/blob/main/media/4UploadCode.png?raw=true)


## 5.  Open Serial Port in Arduino IDE to check the IP Address of the ESP32Cam

## 6.  Ensure you are using the same Wifi. Copy and Paste the IP Address to web browser(Chrome/Edge) address bar

## 7.  Point the camera towards the first image (class1), then Click Start Collecting. Repeat the process for all classes required. 

## 8.  Login to edgeimpulse and create a new project

![alt text](https://github.com/apauaie/ai_esp32_cam_ei/blob/main/media/8_CreateNew_Project_EdgeImpulse.png?raw=true)


![alt text](https://github.com/apauaie/ai_esp32_cam_ei/blob/main/media/8_Create_New_Project_EI.png?raw=true)

## 9.  Find the Data Acquisition menu and click Add Existing Data -> Upload Data . 

![alt text](https://github.com/apauaie/ai_esp32_cam_ei/blob/main/media/9_Upload_Data.png?raw=true)
![alt text](https://github.com/apauaie/ai_esp32_cam_ei/blob/main/media/9_Upload_Data2.png?raw=true)

## 10. Upload each folder extracted from previous capture process. Make sure to label each class properly. Ensure you have at least 50 images for each class.

![alt text](https://github.com/apauaie/ai_esp32_cam_ei/blob/main/media/10_Upload_Captured_Image.png?raw=true)

![alt text](https://github.com/apauaie/ai_esp32_cam_ei/blob/main/media/10_Completed_Upload.png?raw=true)

## 11. Find Impulse Design menu and click Create Impulse

![alt text](https://github.com/apauaie/ai_esp32_cam_ei/blob/main/media/11_Create_Impulse.png?raw=true)



## 12. Add the 'Image' Processing Block and 'Transfer Learning' Learning Block. Save the Impulse.

![alt text](https://github.com/apauaie/ai_esp32_cam_ei/blob/main/media/12_Add_Image_.png?raw=true)

![alt text](https://github.com/apauaie/ai_esp32_cam_ei/blob/main/media/12_Add_Transfer_Learning.png?raw=true)

![alt text](https://github.com/apauaie/ai_esp32_cam_ei/blob/main/media/12_Save_Impulse.png?raw=true)



## 13. Select RGB, then Save Parameters and Generate Features in the Impulse Design-> Image menu

![alt text](https://github.com/apauaie/ai_esp32_cam_ei/blob/main/media/13_Complete_Generate.png?raw=true)

![alt text](https://github.com/apauaie/ai_esp32_cam_ei/blob/main/media/13_Generate_Features.png?raw=true)
![alt text](https://github.com/apauaie/ai_esp32_cam_ei/blob/main/media/13_Selec_RGB_Save.png?raw=true)



## 14. Click Start Training on the Transfer Learning menu. Ensure the accuracy is close to 100%. Otherwise, check your input images or change the model. 

![alt text](https://github.com/apauaie/ai_esp32_cam_ei/blob/main/media/14_Start_Training.png?raw=true)

![alt text](https://github.com/apauaie/ai_esp32_cam_ei/blob/main/media/14_Compete_Training.png?raw=true)

## 15. Use the EON Tuner, Retrain Model, Live Classification and Model Testing to optimize your model.


## 16. Once satisfied with the model, Click the Deployment menu. Select Deployment -> Arduino library

![alt text](https://github.com/apauaie/ai_esp32_cam_ei/blob/main/media/16_Deploy_Arduino_Li.png?raw=true)



## 17. Select EON Compiler and click Build. It will generate an Arduino Library zip file. 

![alt text](https://github.com/apauaie/ai_esp32_cam_ei/blob/main/media/17_Select_EON_and_Built.png?raw=true)

![alt text](https://github.com/apauaie/ai_esp32_cam_ei/blob/main/media/17_Build_Completed.png?raw=true)

## 18. Install the Arduino library Zip file in Arduino IDE. Click on Sketch-> Include Library -> Add .ZIP Library

![alt text](https://github.com/apauaie/ai_esp32_cam_ei/blob/main/media/18_Install_Build_Library.png?raw=true)



## 19. Open and Upload the file esp32_camera_rbtx.ino. This is modified from original EdgeImpulse Arduino Library. You can modify the detection threshold in this file.

![alt text](https://github.com/apauaie/ai_esp32_cam_ei/blob/main/media/19_Modify_threshold.png?raw=true)

![alt text](https://github.com/apauaie/ai_esp32_cam_ei/blob/main/media/19_Open_esp32_camera_rbtx.png?raw=true)


## 20. Once uploaded, open Serial Monitor and send character 'a' to ESP32Cam. If you receive the name/label of the class, then the inference is working.




## 21. Unplug USB connection to ESP32Camp. Make connection from ESP32Cam to Arduino Nano/ Mechabot Rush. VCC to 5V, GND to GND, TX(GPIO1) to RX(Pin 4), RX(GPIO3) to TX(Pin 7). Ensure servo in connected to Pin 8 on Rush.




## 22. In Tinkercode, open file tinkercode_Test_AI_esp32cam.xml.



## 23. Modify the text of class1,class2,class3 variable to same name/label from EdgeImpulse.



## 24. Upload the code after selecting the com port and Arduino Nano as the board.


## 25. Open Serial Monitor and send character 's' to see response from ESP32Cam. It should print Detecting.... then the class that is detected. It will print 'non' if no classes was detected above the threshold. 


## 26. Open and Modify example tinkercode_pathfinder_AI_esp32cam.xml in Tinkercode to fit your requirement for detection.







## Appendix

Any additional information goes here


## Authors

- [@apauaie](https://www.github.com/apauaie)


<!-- ![Logo](https://tinkercode.my/app/wp-content/uploads/2022/11/TinkerCodeLogoCircle-768x802.png =250x250) -->

<img src="https://tinkercode.my/app/wp-content/uploads/2022/11/TinkerCodeLogoCircle-768x802.png" width=50% height=50%>

## License

[![GPLv3 License](https://img.shields.io/badge/License-GPL%20v3-yellow.svg)](https://opensource.org/licenses/)


