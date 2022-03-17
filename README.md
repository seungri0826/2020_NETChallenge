# 2020 NET 챌린지 시즌 7

## 프로젝트 개요
- __주제__: CCTV를 이용한 택배 도난 방지 시스템
- __팀명__: 왕밤빵
- __기간__: 2020.07~2020.12
- __수상__: 금상(한국지능정보사회진흥원장상), 특별상(통신사상, LGU+)
- **사용한 기술**
  - 환경 - HPC(Ubuntu 18.04), PaaS-TA
  - 하드웨어 - NVIDIA Jetson Nano(Ubuntu 18.04), Raspberry Pi(w/카메라모듈), Android 단말기
  - 언어 - Python, C(Darknet), Android Studio, PHP
  - 라이브러리 및 프레임워크 - Darknet(YOLOv3), Zbar, Zxing

<br>

## Darknet 수정 코드
- [GITHUB REPO](https://github.com/seungri0826/wbb_Darknet)
- Real time object detection을 위한 Darknet(YOLOv3) 프레임워크 응용
- 택배 상자 이미지의 학습은 HPC에서 진행하였고, 그에 따른 `.weights` 파일은 용량 문제로 업로드하지는 못함
- 주요 수정 기능
  - 지정된 위치의 CCTV 이미지(일정 시간마다 업데이트 됨)를 자동으로 불러와 object detection 수행
  - CCTV 이미지 속의 택배 상자 개수를 검출하여 파일 입출력으로 내보냄
  - 한 번의 weight upload 만으로 연속적인 물체 인식이 가능

<br>

## /var/www/html 내 php 코드 (compare_box)
- [GITHUB REPO](https://github.com/seungri0826/wbb_PHP)
- Edge AI 구현을 위한 php 코드
- Darknet 실행, 라즈베리파이 CCTV로부터 사진 전송 받기, 도난 상황 감지 알고리즘 실행

<br>

## 동작 흐름
![](https://user-images.githubusercontent.com/43572543/158789823-2252186f-ee94-4a2e-88d3-73c02efb31d4.png)

<br>

## 시스템 구성
![](https://user-images.githubusercontent.com/43572543/158789942-16b22d97-79d1-49a3-9cb0-c1411de34872.png)

<br>

## 도난 상황 발생 시 동작
![](https://user-images.githubusercontent.com/43572543/158790025-27e199c7-ceec-4243-a5d9-d94f22dd6d6b.png)
