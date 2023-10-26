# AI-집중교육1 4조
## CCTV영상을 활용한 보행자 및 차량 방향 탐지

## 데이터
출처: [AI Hub 교통문제 해결을 위한 CCTV 교통 영상(시내도로)](https://www.aihub.or.kr/aihubdata/data/view.do?currMenu=115&topMenu=100&aihubDataSe=realm&dataSetSn=165)

### 구축 내용 및 제공 데이터량
* 데이터 규모 : 총 505시간 동영상 및 학습데이터 57만장 이미지 (Bbox용 동영상 500시간/Tracking용 동영상 5시간 별도)
* 학습데이터 형태
  - Bounding Box (Detection) 이미지 18만장
  - Tracking 이미지 36만장
  - Segmentation 이미지 3만장
* 날씨 : 악천후(눈, 비, 안개) 영상과 데이터 10% 이상 확보
* 차종분류 : 승용차, 소형버스, 대형버스, 트럭, 대형트레일러, 오토바이, 보행자 7종 분류
* 시간대 : 새벽 2-3시, 오전 6-9시, 낮 12-15시, 밤 17-20시


## preprocessing.ipynb
전처리 코드
1. 드라이브 연결
2. 사람이 존재하는 이미지 및 개수 파악
3. JSON 수정 및 바운딩 박스 파악
4. 차선 화살표 바운딩 박스 추가
5. road bbox에 따른 차량 방향 체크 프로그램 실행은 여기서부터
6.이미지 사이즈 올바른 것만 뽑아내버리기
7. json attribute 추가



## train_yolov8_for_car_tracking.ipynb
yolo 모델 코드
1. Install dependencies
2. Imports
3. Constants
4. Convert dataset to yolo format
5. Train
6. Test
7. Image predict
8. Tracking predict
9. 동영상에 모델 적용
10. 동영상 프레임들로 저장
11. 프레임들을 다시 동영상으로 저장
