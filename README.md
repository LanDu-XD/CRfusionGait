# CRfusionGait: Camera and Radar Sensor Fusion Gait Recognition dataset
CRfusionGait is an open-source gait recognition dataset collected with camera and radar sensors. It can be used to study multi-modality gait recognition and single-modality gait recognition based on radar or camera sensors. Our artical "Robust Gait Recognition based on Deep CNNs with Camera and Radar Sensor Fusion" is undergoing review. Our dataset and codes will be made public in the near future. We hope that our work can serve as a baseline and inspire further research. Following, we introduce the composition and implementation details of this dataset.
## Dataset Introduction
![Fig 6 new路线图](https://user-images.githubusercontent.com/115384654/194757102-53ec81ba-145c-4e68-a4c0-6e4534f9bfae.png)
*  **121 person:** 121 volunteers of different ages, gender, heights, weights are involved.<br>
*  **8 views:** 8 different walking views, including the degree of 0,30,45,60,90,300,315,330.<br>
*  **3 walking conditions:** 3 different walking conditions, including normal walking, walking carrying a bag and walking wearing a coat.<br>
## Dataset Implementation
### Hardware Configuration
#### 1. FMCW Radar
* Our radar gait data is collected by one TI AWR1843 mmWave radar, which is composed of an AWR1843 Boost EVM(left two pictures) and a DCA 1000 EVM(rirht two pictures).
![1843](https://user-images.githubusercontent.com/115384654/194759060-b4351388-de3f-467b-ba04-be657d32c000.png)

* The parameters of the radars are set as follows:

Parameter | Value | Parameter | Value
:----:  | :----:  | :----: | :----:  
Start frequency | 77GHz| Chirp repetition period|78.125us
Frequency slope | 9.753MHz/us | Chirp duration| 60us
ADC sample time | 40.96us|ADC sample points| 512
Chirps in one frame | 255| Frame interval| 19.922ms
Number of consecutive frames | 60 | Duration | 1.195s
Idle time | 0.005s | Tx/Rx channel| 1/4

Under these settings, the range resolution is 0.375 m and the velocity resolution is 0.097m/s.
#### 2. Optical Camera
* The optical camera gait images are collected by BASLER acA1600-60gc industrial cameras. The frame rate of Optical cameras is set to 50 fps, and the resolution of captured images is 1600 x 1200 (width x height).
### System overview
![Fig 2](https://user-images.githubusercontent.com/115384654/194761030-ff5a786a-4c15-485e-bff0-da9c060470fd.png)
### Data preprocessing
#### 1. Radar data
Millimeter-wave radar  emits linear frequency modulated continuous wave (LFMCW)  and receives the echo signal reflected from the human body.  The time-Doppler spectrograms of the echo signal can be  obtained by time-frequency analysis, which reflect the transformed  relationship between micro-Doppler frequency and  amplitude of human parts with time.  The specific process includes: 1) Mixing the echo signal with the transmit signal to  obtain the intermediate frequency (IF) signal;  2) Doing the fast Fourier transform along the range dimension (Range FFT) on  the IF signal to obtain the time-range map;  3) Performing static  clutter removal (SCR) in the time-range map;  4) Selecting the  range unit where the person is located in the time-range map  to do the short-time Fourier transform (STFT).
#### 2.Camera data
The  raw optical data is presented in the form of video, which can  portray the information of human appearance very well. We  use the deeplabV3+  to detect and  segment the person in raw video. After person detection and  segmentation, we can obtain the silhouette sequence, which is  further compressed to obtain GEIs.
### Data Illustration
#### 1. Radar data
![Fig 8](https://user-images.githubusercontent.com/115384654/194760866-50f4c3d6-0ea3-4886-8a23-b929f21b1029.png)
#### 2. Camera data
![Fig 7](https://user-images.githubusercontent.com/115384654/194760889-d8e8ad3b-2e2b-4846-b92f-046d2c54cf07.png)
## Dataset Statistic
updating
## Code
updating
## Citation
Our artical "Robust Gait Recognition based on Deep CNNs with Camera and Radar Sensor Fusion" is undergoing review.
updating
