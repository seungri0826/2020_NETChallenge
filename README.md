# 2020_NETChallenge
2020 NET 챌린지 시즌 7 기록
- __팀명__: 왕밤빵
- __주제__: CCTV를 이용한 택배 도난 방지 시스템
- __수상__: 금상(한국지능정보사회진흥원장상), 특별상(통신사상, LGU+)

### Darknet 수정 코드
- [LINK](https://github.com/seungri0826/wbb_Darknet)
- Real time object detection을 위한 Darknet 프레임워크 응용
- 택배 상자 이미지의 학습은 HPC에서 진행하였고, 그에 따른 `.weights` 파일은 용량 문제로 업로드하지는 못함
- 주요 수정 기능
  - 지정된 위치의 CCTV 이미지(일정 시간마다 업데이트 됨)를 자동으로 불러와 object detection 수행
  - CCTV 이미지 속의 택배 상자 개수를 검출하여 파일 입출력으로 내보냄

### /var/www/html 내 php 코드 (compare_box)
- [LINK](https://github.com/seungri0826/wbb_PHP)
- Edge AI 구현을 위한 php 코드
- Darknet 실행, 라즈베리파이 CCTV로부터 사진 전송 받기, 도난 상황 감지 알고리즘 실행
