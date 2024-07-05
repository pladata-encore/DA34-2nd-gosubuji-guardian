## 이상행동 탐지를 통한 도난 행위 알림서비스 - Guardian Project

---

#### 🗓️ 프로젝트 일정 : 2024/4/18 ~ 2024/4/25


#### 🌱 팀원(github)

[😎강동욱](https://github.com/ddsntc1)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[🤩강민지](https://github.com/lucide99)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[😊김성욱](https://github.com/maniac00)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;


#### Environment & Tech
![Cuda](https://img.shields.io/badge/Cuda-black?style=for-the-badge&logo=nvidia)
![Opencv](https://img.shields.io/badge/Opencv-blue?style=for-the-badge&logo=opencv)
![Pytorch](https://img.shields.io/badge/Pytorch-yellow?style=for-the-badge&logo=pytorch)
![mediapipe](https://img.shields.io/badge/Tool-Mediapipe-black)
![yolov5](https://img.shields.io/badge/Tool-Yolov5-black)

---

<p align="center">
   <img src ="https://github.com/ddsntc1/guardian_project/assets/38596856/dbcc4d24-ba69-49c4-98d1-9200fa8e45c9.jpg" style="width:50% ;height:50%">
</p>

#### 프로젝트 시나리오

**[설정 상황]**
> 기술의 발전과 인력난의 심화 속에 무인 아이스크림할인점, 무인 문방구, 무인 편의점 등 **무인 판매점**의 수가 증가하고 있다.
> 이에 따라 도난 발생이 자주 일어나며 무인 판매점의 점주가 직접 CCTV를 확인하여 도난 상황을 찾아내는 시간이 상당히 소요되는 것이 현실이다.
> **Guardian**이라는 프로젝트명으로 무인 판매점 이외 도난 가능성이 있는 장소에 대해서 이상행동을 탐지하고 알림 서비스를 제공하려고 한다.


**[요구 사항]**
> 기존 CCTV 카메라에 Image Deep Learning 모델을 적용시켜 행동 발생시점을 탐지하려고 한다.
> 
**[Idea]**

> 1) yolo v5 모듈을 사용하여 사람 객체 탐지
> 2) 해당 객체 내 mediapipe를 이용하여 사람의 몸 관절의 위치(좌표) landmark 정보 습득
> 3) landmark 정보의 sequence값을 LSTM(Long Short-Term Memory)로 학습하여 행동을 판단하는 DL 모델 생성
> 4) RasberryPi 기반 카메라로 실시간 탐지에 응용


**[한계점]**
> 해당 모델을 서비스화 하기 위해서 H/W 부분의 개발이 필요하다.


---


  
#### Source Data
학습을 위한 데이터 소스는 ai-hub의 'TS_03.이상행동_12.절도.zip(26.65GB)'영상을 사용했습니다. 
* https://www.aihub.or.kr/aihubdata/data/view.do?currMenu=&topMenu=&aihubDataSe=data&dataSetSn=71550

  
#### 데이터 전처리


#### 향후 튜닝요소
* 학습한 영상은 물건을 집으면 바로 주머니나 가방에 넣기 때문에, 물건을 집었다가 내려놓는 케이스를 '도난'으로 처리함
    * 향후 학습 영상 촬영시 집었다가 놓는 케이스를 별도로 넣을 필요가 있음 

### 레퍼런스 정보
* https://blog.naver.com/112fkdldjs/222972860886
* https://github.com/seonydg/LSTM-for-Anomaly-Detection
