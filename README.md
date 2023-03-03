# 잘나왔닷
<img src="https://user-images.githubusercontent.com/58325946/222323571-894bbb90-18ef-46d0-ae41-71bfbe308e69.png" width="405" height="500"> 

### 저는 이 프로젝트에서 full stack을 담당하였으며, 세부적으로는 
#### frontend react native의 비동기처리를 이용한 amazon aws의 데이터 업로딩&다운로딩 처리
#### backend flask 서버구현, amazon aws과의 데이터 api connection 담당
#### python deep learning 이미지 유사도 측정, opencv seamlessclone을 이용한 이미지 자동합성기술 개발, 논문 참조를 통한 마스크 착용 상태에서도 눈 크기측정이 가능하도록 개발하였습니다.
#### 이전에는 클라우드 스토리지로 azure을 이용한 blob처리를 통하여 api를 전달하는 식으로 개발을 진행하였었는데, amazon aws의 버킷서비스가 flask와 react native 연결에 용이하다고 판단하여 추후에는 amazon aws 클라우드 스토리지로 변경하였습니다.

---
## 개발스택
![image](https://user-images.githubusercontent.com/58325946/222321730-e8e9eeca-104e-4bf7-b6a2-2b57e87600ab.png)


## 소개
<img src="https://user-images.githubusercontent.com/58325946/222318128-d2fe6d3a-d18d-47f1-a178-87050c98cc61.png" width="500" height="280"> 

## 조원 소개

- 주현우
- 최가인
- 이유진
- 김재현
- 임성용

---

## DL

- 딥러닝 모델 및 데이터 처리 Python 코드가 담긴 디렉토리입니다.

### app.py

- 백엔드 역할을 담당하는 코드.
- Flask를 통해 앱으로부터 신호를 주고 받아 요구하는 작업을 수행합니다.
- AWS를 활용하여 앱으로부터 편집할 이미지를 받아서 처리한 후 다시 앱으로 전송합니다.
- 아래 언급될 detect_faces_masks.py, draw_face.py, combine.py 모두 import 되고 돌아가게됩니다.

### detect_faces_masks.py

- 유사한 사진들로부터 얼굴 객체를 탐지하여 crop한 다음 jpg 형태로 저장합니다.
- 리턴값으로 각 객체의 파일명 및 좌표들을 불러옵니다.

### draw_face.py

- detect_faces_masks.py의 리턴값들을 활용하여 어떤 얼굴을 편집하고 있는지 박스를 그려 사용자에게 보여줍니다.

### combine.py

- 사용자가 지정한 얼굴을 자연스럽게 합성시킵니다.

### star_mask.py

- crop한 얼굴 사진들중에서 제일 잘 나온 사진을 판별하여 해당 사진에 별 표시를 추가합니다.

---

## frontend

- React Native 프레임워크로 제작된 프론트앤드 코드가 담긴 디렉토리입니다.

### src\screens\Login.js

- 로그인 화면이 담겨있습니다. 로그인을 하면 SelectHome.js 로 넘어갑니다.

### src\screens\PickerScreen.js

- 갤러리로부터 사진을 고르는 화면입니다.

### src\screens\SelectHome.js

- PickerScreen.js 와 연결하여 편집을 진행할 사진을 고른 후 대표사진을 선정하는 화면입니다.
- 선택한 사진들을 AWS로 업로드한 후 서버에 신호를 전송하여 얼굴 객체를 뽑아 전달 받습니다.
- 위 작업이 끝나면 PhotoEditing.js 로 넘어갑니다

### src\screens\PhotoEditing.js

- 얼굴 합성을 진행하는 화면입니다.
- 가장 좌측 얼굴부터 사용자로부터 선택받아 실시간으로 합성을 진행하여 보여줍니다.
- 모든 얼굴들에 대한 합성이 끝나면 Ending.js 로 넘어갑니다.

### src\screens\Ending.js

- 최종 사진을 표출하고 sns에 공유할 수 있는 화면입니다.

---
## 어플 동작 영상
https://user-images.githubusercontent.com/58325946/222324836-1f55353f-3bf2-42d6-a05e-d9295f683c13.mp4

## 프로젝트 발표자료
https://youtu.be/8lqacLEb3to

## Referenced Documents

- https://github.com/Linzaer/Ultra-Light-Fast-Generic-Face-Detector-1MB
- https://pyimagesearch.com/2017/04/24/eye-blink-detection-opencv-python-dlib/ 
- http://vision.fe.uni-lj.si/cvww2016/proceedings/papers/05.pdf
- DeepFake using with opencv seamlessclone function
<img src="https://user-images.githubusercontent.com/58325946/220177423-6e58cbd0-ec34-4130-94e5-684cc90189bf.gif" width="500" height="280"> 

