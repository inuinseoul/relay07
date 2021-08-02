# ✨2주차

| 구분| 설명 |
| -------- | -------- |
| **기능A** | 서비스에서 사용할 데이터를 수집하고 사용자에게 맞는 추천 데이터를 선별하는 기능을 개발한다.  |


## 🏃‍♂️Member

| G07 | 김승현  | 김일혁 | 박인우 | 문구화 | 설민욱 | 이노원 | 이동현 | 임도연 |
| :--------: | :--------: | :--------: | :--------: | :--------: |:--------: | :--------: | :--------: | :--------: |

## ✏기능 상세 설명
### 수집
- 사용자가 원하는 자격증을 수집합니다.
- 수집한 자격증 키워드에 대한 강의, 책, 기출문제를 수집합니다. > 공공데이터

### 추천
- 자격증에 대한 수집 데이터를 Client에 띄워줌으로 사용자에게 추천합니다.

## 🖥구현

- API key는 `lib/config/key.dart`에 아래와 같은 형식으로 작성
```
String keyYoutube = 'Your Youtube API key';
String naverClientID = 'Your ClientID';
String naverClientSecret = 'Your ClientSecret';
String keyWorkbook = 'Your Workbook key';
```

### 1. 데이터 수집
1. `자격증 종류` : [한국산업인력공단_국가자격 종목 목록 정보 API](https://www.data.go.kr/data/15041600/openapi.do)
2. `강의` : [Youtube API](https://www.data.go.kr/data/15041600/openapi.do)
3. `교재` : [Naver Open API](https://developers.naver.com/docs/search/book/)
4. `기출문제` : [한국산업인력공단_국가자격 공개문제 조회 서비스 API](https://www.data.go.kr/tcs/dss/selectApiDataDetailView.do?publicDataPk=15075141)


### 2. 기능 구현

- 시연 영상 (이미지 클릭)

<a href="https://youtu.be/4k2H3TtgBio"><img src="https://user-images.githubusercontent.com/64943924/127784922-3f43cf3a-e033-4347-9eef-91c402bdff7f.jpg" width="300"></a>



1. `메인 페이지` : search bar를 통해 원하는 자격증을 선택

   1-1. `자격증 목록` - [자격증 목록 API 구현](https://github.com/boostcampwm-2021/relay_07/blob/main/week2/License.md)

   1-2. `검색기능` - [검색창 및 체크리스트 구현](https://github.com/boostcampwm-2021/relay_07/blob/main/week2/Search.md)

    <details><summary><strong>구현 화면</strong></summary>
    <img src="https://user-images.githubusercontent.com/64943924/127784923-30142b91-a6ce-4a3f-b02a-b47b873e8a58.jpg" width="300">
    </details>

2. `결과 페이지` : 선택한 자격증에 대한 추천 도서, 추천 강의, 기출 자료 제공

   2-1. `추천 도서` - [도서 API 구현](https://github.com/boostcampwm-2021/relay_07/blob/main/week2/BookAPI.md)

    <details><summary><strong>구현 화면</strong></summary>
    <img src="https://user-images.githubusercontent.com/64943924/127784922-3f43cf3a-e033-4347-9eef-91c402bdff7f.jpg" width="300">
    </details>

   2-2. `추천 강의` - [Youtube API 구현](https://github.com/boostcampwm-2021/relay_07/blob/main/week2/YoutubeAPI.md)

    <details><summary><strong>구현 화면</strong></summary>
    <img src="https://user-images.githubusercontent.com/64943924/127784920-23034cb8-1ed0-458b-be19-720178a13450.jpg" width="300">
    </details>

   2-3. `기출 문제` - [기출문제 API 구현](https://github.com/boostcampwm-2021/relay_07/blob/main/week2/WorkbookAPI.md)

    <details><summary><strong>구현 화면</strong></summary>
    <img src="https://user-images.githubusercontent.com/64943924/127784918-b07c3822-b3ab-44ec-a872-3152517a67bc.jpg" width="300">
    </details>

### 3. 에러 발생 시 해결 방안
> Error: Cannot run with sound null safety, because the following dependencies 와 같은 오류가 발생할 경우
- `flutter run --no-sound-null-safety`

## ❌구현하지 못한 사항
- 파일 저장은 성공적으로 되지만, 사용자가 직접 해당 폴더에 접근이 불가능
- 파일 다운로드 시 진행 dialog를 구현하지 못함
