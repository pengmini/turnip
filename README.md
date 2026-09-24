# 순무

작은 행복을 꽃말로 가진 순무가 화면 가운데에서 3D로 천천히 도는 모바일 웹페이지입니다.

## 기능

- **3D 순무**: three.js로 그린 순무가 회전합니다. 좌우로 밀면 직접 돌릴 수 있습니다.
- **확대**: 두 손가락 핀치, 마우스 휠, 더블 탭/더블클릭, 화면 오른쪽 위의 `+` `−` `1×` 버튼 (최대 4배).
- **순무 디자인하기**: 몸통 모양, 분홍/흰색 경계, 가로 줄무늬, 색, 잎, 회전 속도를 슬라이더로 조절합니다.
  - `이 모양 저장`을 누르면 브라우저(localStorage)에 저장되어 다음에 열 때 그 모양으로 시작합니다.
  - `설정값 복사`로 현재 값을 JSON으로 복사할 수 있습니다.
- **이미지 저장**: 지금 보이는 각도와 확대 상태 그대로 1080×1350 PNG로 저장합니다.
- **카톡 공유**: 오른쪽 위 버튼. 카카오 JavaScript 키를 넣으면 카카오톡 공유 카드(이미지 `og.png` + 버튼)로 보내고, 키가 없으면 휴대폰 기본 공유창, 그것도 없으면 링크 복사로 동작합니다.

## 실행

빌드 과정이 없는 정적 파일 하나(`index.html`)입니다.

- 브라우저에서 `index.html`을 바로 열거나
- 로컬 서버로 띄웁니다: `python3 -m http.server 8000` → http://localhost:8000

### GitHub Pages로 배포

1. 이 폴더를 저장소로 push합니다.
2. 저장소 **Settings → Pages**에서 Source를 `Deploy from a branch`, 브랜치 `main`, 폴더 `/ (root)`로 지정합니다.

## 카카오톡 공유 설정

1. [Kakao Developers](https://developers.kakao.com)에서 애플리케이션을 만듭니다.
2. **앱 키 → JavaScript 키**를 복사해 `index.html` 아래쪽의 `const KAKAO_JS_KEY = '';` 에 넣습니다.
3. **JavaScript SDK 도메인**에 페이지 주소를 등록합니다. 예: `https://<아이디>.github.io`
   (로컬에서 시험하려면 `http://localhost:8000`도 등록)
4. 공유 카드 이미지는 저장소의 `og.png`를 씁니다. 바꾸고 싶으면 1200×630 이미지로 교체하세요.
5. (선택) SDK 무결성 검사를 쓰려면 [SDK 다운로드 페이지](https://developers.kakao.com/docs/ko/javascript/download)에서
   2.8.3 버전의 `integrity` 값을 복사해 SDK `<script>` 태그에 추가합니다.

링크 미리보기용 `og:image`는 상대 경로(`og.png`)로 되어 있습니다. 카카오톡/메신저 링크 미리보기를 확실히 하려면
배포 주소가 정해진 뒤 `https://<아이디>.github.io/<저장소>/og.png` 처럼 전체 주소로 바꿔 주세요.

## 의존성

- [three.js r128](https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js) (cdnjs)
- Google Fonts: Gowun Batang, Gowun Dodum, IBM Plex Mono
- [Kakao JavaScript SDK 2.8.3](https://developers.kakao.com/docs/ko/javascript/download) (카톡 공유)

인터넷 연결이 없으면 3D 순무와 글꼴이 표시되지 않습니다.

## 기본 모양 바꾸기

`index.html`의 `DEFAULTS` 객체 값을 바꾸면 됩니다. `설정값 복사`로 얻은 JSON의 값을 그대로 옮겨 넣을 수 있습니다.
