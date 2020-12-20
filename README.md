# PersonRecognition

# Get Target face embedding
regcognition을 원하는 이미지 (혹은 이미지가 들어있는 폴더)와 동영상 경로 입력
retina facenet 을 이용해 이미지에서 얼굴이 있는 box 좌표를 얻어 crop
facenet 을 이용해 target face 의 embedding 값 추출 (target face embedding)

# Target Face detection on Video
동영상 frame에서 retina facenet으로 얼굴 box를 얻고 facenet으로 embedding 값 추출 (frmae face embedding)
target face embedding과 face detection embedding을 cosine
target face와 가장 유사도가 높은 frame face의 박스 좌표 추출

# Person Detection
동영상 frame에서 keras retinanet을 이용해 person인 경우만 박스 추출

# Person Recognition
person box 안에 face box가 존재한다면 person 박스를 제외한 나머지 부분을 검은색으로 패딩처리
