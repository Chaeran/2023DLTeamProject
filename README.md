# 2023DLTeamProject : 운전자 스마트폰 사용감지 딥러닝모델

- 운전자의 스마트폰 사용을 holding, calling, texting으로 나눠서 탐지하는 모델들을 학습하고 성능 비교
- 사용모델 : yolov5, fasterRCNN, RetinaNet </h5>
- 국토교통부의 조사에 따르면 운전자 및 보행자의 안전에 큰 위협이 될 수 있는 운전 중 스마트폰 사용이 42%로 굉장히 높음. 향후 스마트폰 사용을 실시간으로 인지하고, 단계적인 알람을 통해 운전자에게 경고를 주는 기능을 구현한다면 교통 안전성을 높이는데 도움이 될것.
- 데이터 출처 : AI hub, train set : 228개 / test set : 57개

<h3>yolov5</h3>
<img width="1028" alt="스크린샷 2023-07-15 154439" src="https://github.com/Chaeran/2023DLTeamProject/assets/33537808/ced4205e-8638-443c-9f63-4f5045220cbd">
- Ultralytic의 YOLOv5s API를 사용한 Transfer Learning
<br><br><br>

<h3>fasterRCNN</h3>
<img width="1028" alt="스크린샷 2023-06-18 044410" src="https://github.com/Chaeran/2023DLTeamProject/assets/33537808/9bb0c436-7a08-4e13-af67-1f1dd2fad227">
- Pytorch의 fasterrcnn_resnet50 API를 사용한 Transfer Learning
<br><br><br>

<h3>RetinaNet</h3>
<img width="1028" alt="스크린샷 2023-07-15 160036" src="https://github.com/Chaeran/2023DLTeamProject/assets/33537808/4965a989-823c-4bd7-b415-b64687597cce">
- Pytorch의 RetinaNet_resnet50_fpn를 사용한 Transfer Learning
<br><br><br>

<h3>결과</h3>
<img width="918" alt="스크린샷 2023-07-08 194332" src="https://github.com/Chaeran/2023DLTeamProject/assets/33537808/918b24c8-c340-482d-bc76-f9a359a4ad3a">
<img width="920" alt="스크린샷 2023-07-08 194351" src="https://github.com/Chaeran/2023DLTeamProject/assets/33537808/b1804f8b-105a-4550-9696-247e2b6bb68c">
<br>
- 모델 학습 및 성능 비교 결과, ‘실시간 휴대폰 사용’ 모션에 따른 차등적 경고 프로그램에 적합한 모델로 Yolo v5을 선정하였음.<br>
- 선정한 이유는 다음과 같음.<br>

  > 1. mAP로 비교한 정확도에서 다른 모델과 비교했을 때 높은 성능을 보임<br>
  > 2. 실시간 처리속도 FPS가 다른 모델보다 뛰어남<br>
  > 3. 다른 모델들과 달리 세 모션이 가장 비등하게 탐지되었음<br>

<br><br><br><br>

<h3>향후 개선점</h3>

- AIhub에서 수집한 데이터는 특성상 한정적이었음. 특히 테스트 데이터셋이 학습에 사용된 데이터셋과 구조적으로 비슷하여 정확도가 비교적 높았던 점이 아쉬웠음. 조도, 다른 사람, 다른 차(배경) 등 다양한 변수를 고려하여 학습시키면 보다 좋은 성능의 객체 탐지 모델을 기대할 수 있을 듯함.
- ‘실시간 휴대폰 사용 탐지’라는 주제에 맞게 실제 카메라를 사용하여 탐지 시간을 비교해보기.
- 모델의 hyperparmeter의 finetuning을 더 진행해보면서 각 모델별로 최상의 성능을 나타내는 모델끼리 비교한다면 더 정확한 결과를 얻을 수 있을 것.
- yolo의 다른 버전을 사용해서 비교해보기.

<h3>프로젝트 정보</h3>

- 2023년 1학기 딥러닝 수업 팀프로젝트
- 개발 인원 : 김수인 김리주 지수연 유채란
- 개발 기간 : 2023년 5월~6월
- 기술 스택 : pytorch, python




