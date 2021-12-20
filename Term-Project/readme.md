# ✨ Term-Project Report

## 주제

- 서울시 버스의 혼잡 정도를 분석하여 202번 노선이 심야버스로 선정되지 않은 이유 분석하기

---

## 주제 선정 계기

- 심야버스란 일명 올빼미 버스로, 대중교통이 끊긴 밤 12시 이후부터 새벽 5시까지 운행하는 버스입니다. 심야시간에 편리하고 저렴하게 이용할 수 있다는 것이 특징이며, 이는 공공 빅데이터를 활용하여 생활 속 문제를 해결한 대표적인 사례 중 하나로 꼽힙니다.
- 몇 년 전 올빼미 버스에 관한 기사를 흥미롭게 읽었던 기억이 있고, 평소 자주 타는 버스 또한 유동인구가 많은 것 같은데, 심야버스로 선정되지 않은 이유가 궁금해져서 프로젝트의 주제를 서울시 버스의 혼잡 정도를 분석하여 202번 버스가 심야버스로 선정되지 않은 이유를 찾는 것으로 정하게 되었습니다.

---

## 작업 환경

- Google Colaboratory에서 진행하였습니다.
- 1주차 수업에서 강조하셨던 깃을 최대한 활용하기 위해, 깃 플로우를 정해놓고 프로젝트를 진행하였습니다. 흐름은 아래와 같습니다.
- 작업할 TODO 목록을 단계별로 나누어서 이슈 생성 ➡️ 이슈의 번호에 맞춘 브랜치에서 작업 ➡️ pull request에 작업 내용 정리하고 merge

|issue|pull request|
|------|---|
|[데이터 정제](https://github.com/EunHee-Jeong/Open-Source-Project/issues/1)|Feature|
|[출력](https://github.com/EunHee-Jeong/Open-Source-Project/issues/2)|Feature|
|[비교](https://github.com/EunHee-Jeong/Open-Source-Project/issues/3)|Chore|

- 커밋 컨벤션

    ✅[CHORE] : 코드 수정, 내부 파일 수정
    ✨[FEAT] : 새로운 기능 구현
    ➕[ADD] : Feat 이외의 부수적인 코드 추가, 라이브러리 추가, 새로운 파일 생성 시
    ⚰️ [DEL] : 쓸모없는 코드 삭제
    🚚[MOVE] : 프로젝트 내 파일이나 코드의 이동

- 처음에 커밋을 단계별로 기록하기 위해 파이썬 파일을 따로 만들어서 구현이 추가될 때마다 내용을 업데이트 했다가, 코랩 자체에서 .ipynb 파일을 깃허브와 연동할 수 있다는 사실을 알게 되고 한번에 올리는 것으로 바꿨습니다. 그래서 파이썬 파일은 이슈 1번까지만 정리되어 있습니다!

---

## 사용한 오픈소스

- 데이터셋 (서울시 버스노선별 정류장별 승하차 인원 정보 (2021/11), 서울시 버스 정류소 좌표 데이터)
- 지도 (folium 라이브러리)

---

## 결과

- 1단계: 데이터(2021년 10월의 버스 노선별 승하차수) 정제 부분
    - 사진 순서 - 전체 데이터 / 202번 버스의 데이터 / 상위 5개 데이터

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/05f859b5-0b6e-4e91-bb30-ee0f83cecb00/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/db590b42-a17a-469c-940c-bb7e5cee1d36/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/13a60e41-0992-42ee-9430-609893a9526a/Untitled.png)

이를 통해 전체적으로 봤을 때는 충분히 많아 보이지만, 상위 5개와 비교했을 때는 3배 이상 차이가 나기 때문에 유동인구가 예상한 만큼 많은 것은 아니라는 사실을 알 수 있습니다.

- 2단계: 출력하기
    - 1단계에서 예측한 내용을 그래프 2개를 그려 실제로 비교해보았습니다.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ccbe3cb3-f5f5-49c1-9d3c-25ebee32a980/Untitled.png)

- 3단계: 비교하기 (미완성)
    - 확실히 주변과 비교했을 때는 유동인구가 많지만, 전체적으로 봤을 때는 적은 것을 확인할 수 있습니다.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/29332579-05a0-4cdf-b2f3-fb99bc63ccc1/Untitled.png)

- 기준 좌표만 넣었을 때는 아래와 같이 지형이 함께 표시가 되는데, 모든 정류장의 좌표를 넣으면 깨져서 나오는 문제가 있습니다.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/4e4cbc3f-273c-4788-b2cc-cc2315b3d07e/Untitled.png)

---

## 정리

- 처음에는 전체 버스 중에서 심야버스를 선정하는 것인 줄 알고 프로젝트를 시작하였습니다. 하지만 결과를 정리하며 심야버스는 모든 정거장의 유동 인구 데이터를 뽑아서 그에 맞게 지역과 배차를 정하고, 따로 노선을 운영하는 것임을 알게 되었습니다.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a6b3160a-00b7-4056-bc3d-8c20965d021c/Untitled.png)

- 분석 결과 202번 버스가 서울 시내의 상위 5개 노선과 비교했을 때는 당연히 유동인구 수가 적은 편이만, 지역 내에서는 많은 편이기 때문에 심야버스로 선정될 만한 충분한 근거가 있다는 결론을 얻게 되었고, 태릉입구역을 지나치는 N13번과 N61번이 이에 대한 심야버스 버전인 것 같다는 느낌을 받게 되었습니다.

---

## 라이센스

- 개인, GPL

---

## 참고한 자료와 사이트

- 시민 이동성 증진을 위한 교통 현황 분석(2018) - [서울디지털재단](http://www.sdf.seoul.kr/)
- 지도에 시각화하는 부분 코드 - [[Python] 공공api를 활용하여 내 주변 공적 마스크 판매처와 마스크 재고를 지도에 시각화해보자!](https://somjang.tistory.com/entry/Python-%EA%B3%B5%EA%B3%B5api%EB%A5%BC-%ED%99%9C%EC%9A%A9%ED%95%98%EC%97%AC-%EB%82%B4-%EC%A3%BC%EB%B3%80-%EA%B3%B5%EC%A0%81-%EB%A7%88%EC%8A%A4%ED%81%AC-%ED%8C%90%EB%A7%A4%EC%B2%98%EB%A5%BC-%EC%8B%9C%EA%B0%81%ED%99%94%ED%95%B4%EB%B3%B4%EC%9E%90)