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
![](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/01cb4a71-9e37-46df-b4d5-bf421b42da1a/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220317%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220317T054909Z&X-Amz-Expires=86400&X-Amz-Signature=294c0df65d361776c42432c94ea50526b3b8a0580f4d976be0a91d73925a9026&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22&x-id=GetObject)

<br>

## 시스템 구성
![](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/c1a6107c-1cf3-4fc3-a018-2d1d32165776/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220317%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220317T102254Z&X-Amz-Expires=86400&X-Amz-Signature=03996bf728d3afaf71c236b74c131539557f34754d3ce5a1f0750be62ebdea64&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22&x-id=GetObject)

<br>

## 도난 상황 발생 시 동작
![](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/9b0abeba-b6aa-4e83-9114-4df1d76502cd/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220317%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220317T063852Z&X-Amz-Expires=86400&X-Amz-Signature=eda00363ba4fb79cfeaa765aae2b4fd0823075627bdc166ff7f6a5f4c58908e2&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22&x-id=GetObject)
