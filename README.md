# CRfusionGait: Camera and Radar Sensor Fusion Gait Recognition dataset
CRfusionGait is an open-source gait recognition dataset collected with camera and radar sensors. It can be used to study multi-modality gait recognition and single-modality gait recognition based on radar or camera sensors. Our artical "Robust Gait Recognition based on Deep CNNs with Camera and Radar Sensor Fusion" is undergoing review. Our dataset and codes will be made public in the near future. We hope that our work can serve as a baseline and inspire further research. Following, we introduce the composition and implementation details of this dataset.
## Dataset Introduction
![Fig 6 new路线图](https://user-images.githubusercontent.com/115384654/194757102-53ec81ba-145c-4e68-a4c0-6e4534f9bfae.png)
*  **121 person:** 121 volunteers of different ages, gender, heights, weights are involved.<br>
*  **8 views:** 8 different walking views, including the degree of 0,30,45,60,90,300,315,330.<br>
*  **3 walking conditions:** 3 different walking conditions, including normal walking, walking carrying a bag and walking wearing a coat.<br>
## Dataset Implementation
## Hardware Configuration
### 1. FMCW Radar
* Our radar gait data is collected by one TI AWR1843 mmWave radar, which is composed of an AWR1843 Boost EVM(left two pictures) and a DCA 1000 EVM(rirht two pictures).
![1843](https://user-images.githubusercontent.com/115384654/194759060-b4351388-de3f-467b-ba04-be657d32c000.png)

* The parameters of the radars are set as follows:

Parameter | Value | Parameter | Value
----  | ----  | ---- | ----  
Start frequency | 77GHz| Chirp repetition period|78.125us
Frequency slope | 9.753MHz/us | Chirp duration| 60us
ADC sample time | 40.96us|ADC sample points| 512
Chirps in one frame | 255| Frame interval| 19.922ms
Number of consecutive frames | 60 | Duration | 1.195s
Idle time | 0.005s | Tx/Rx channel| 1/4
