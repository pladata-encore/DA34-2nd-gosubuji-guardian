# guardian 프로젝트
본 프로젝트는 Image deep learning 기술을 사용하여 이상 탐지(anomaly detection)를 실습하는 것을 목적으로 합니다. 기본적인 아이디어는 1) 사람을 yolo v5 모듈을 사용하여 탐지하고, 2) mediapipe로 사람의 몸 관절의 위치를 landmark 정보로 습득한 후, 3) 해당 landmark 정보의 sequence값을 LSTM(Long Short-Term Memory)로 학습하여 모델 학습을 진행하여, 4) 해당 모델로 RasberryPi 기반 카메라로 실시간 탐지에 응용하는 것입니다.
### 함께한 팀 정보
* 조직 : Playdata AI풀스택개발과정 34기
* 팀원 : 강동욱, 강민지, 김성욱
### Source Data
학습을 위한 데이터 소스는 ai-hub의 'TS_03.이상행동_12.절도.zip(26.65GB)'영상을 사용했습니다. 
* https://www.aihub.or.kr/aihubdata/data/view.do?currMenu=&topMenu=&aihubDataSe=data&dataSetSn=71550
### 데이터 전처리
절도 영상을 
### 향후 튜닝요소
* 학습한 영상은 물건을 집으면 바로 주머니나 가방에 넣기 때문에, 물건을 집었다가 내려놓는 케이스를 '도난'으로 처리함
    * 향후 학습 영상 촬영시 집었다가 놓는 케이스를 별도로 넣을 필요가 있음 

### 레퍼런스 정보
* https://blog.naver.com/112fkdldjs/222972860886
* https://github.com/seonydg/LSTM-for-Anomaly-Detection