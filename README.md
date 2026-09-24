# 순무

작은 행복을 꽃말로 가진 순무가 화면 가운데에서 3D로 천천히 도는 모바일 웹페이지입니다.

## 기능

- **3D 순무**: three.js로 그린 순무가 회전합니다. 좌우로 밀면 직접 돌릴 수 있습니다.
- **확대**: 두 손가락 핀치, 마우스 휠, 더블 탭/더블클릭, 화면 오른쪽 위의 `+` `−` `1×` 버튼 (최대 4배).
- **순무 디자인하기**: 몸통 모양, 분홍/흰색 경계, 가로 줄무늬, 색, 잎, 회전 속도를 슬라이더로 조절합니다.
  - `이 모양 저장`을 누르면 브라우저(localStorage)에 저장되어 다음에 열 때 그 모양으로 시작합니다.
  - `설정값 복사`로 현재 값을 JSON으로 복사할 수 있습니다.
- **이미지 저장**: 지금 보이는 각도와 확대 상태 그대로 1080×1350 PNG로 저장합니다.

## 실행

빌드 과정이 없는 정적 파일 하나(`index.html`)입니다.

- 브라우저에서 `index.html`을 바로 열거나
- 로컬 서버로 띄웁니다: `python3 -m http.server 8000` → http://localhost:8000

### GitHub Pages로 배포

1. 이 폴더를 저장소로 push합니다.
2. 저장소 **Settings → Pages**에서 Source를 `Deploy from a branch`, 브랜치 `main`, 폴더 `/ (root)`로 지정합니다.

## 의존성

- [three.js r128](https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js) (cdnjs)
- Google Fonts: Gowun Batang, Gowun Dodum, IBM Plex Mono

인터넷 연결이 없으면 3D 순무와 글꼴이 표시되지 않습니다.

## 기본 모양 바꾸기

`index.html`의 `DEFAULTS` 객체 값을 바꾸면 됩니다. `설정값 복사`로 얻은 JSON의 값을 그대로 옮겨 넣을 수 있습니다.
