# 종우 ♥ 연서 결혼 소식 페이지

빌드 도구 없이 `index.html` 한 파일로 동작하는 모바일 페이지입니다. 초대 문구 없이 두 사람의 결혼 소식과 양가 성함, 날짜만 담았습니다. GitHub Pages에 올리면 바로 주소가 생깁니다.

```
index.html   본문 (디자인·내용·동작이 모두 이 파일 안에 있습니다)
og.png       카카오톡·문자로 링크를 보낼 때 뜨는 미리보기 이미지 (1200×630)
README.md    이 설명서
```

## 1. 어디에 올라가 있나

- 저장소: https://github.com/kaiser-ryu/wedding (main 브랜치, 루트 폴더)
- 주소: https://kaiser-ryu.github.io/wedding/
- GitHub Pages 설정: Settings → Pages → Source **Deploy from a branch**, Branch **main** / **/ (root)**

파일을 고친 뒤 main 에 올리기만 하면 1분 안에 반영됩니다. (GitHub 웹에서 파일을 열어 연필 아이콘 → 수정 → Commit changes 해도 됩니다)

### 회사 제출용 버전 (`info/`)

- 주소: https://kaiser-ryu.github.io/wedding/info/
- 파일: `info/index.html` (가족용 `index.html`과 별개로 고칩니다)
- 가족용과 다른 점: 신부 측 부친 성함 제외, 시간(낮 12시) 표시, **일시 · 장소** 섹션 추가
  (영의정 · 경기 의정부시 범골로145번길 40 궁전빌딩 3층, 네이버 지도·카카오맵 링크)
- 장소·시간은 `info/index.html` 의 `CONFIG` 에서 `venue`, `date.hour` 로 고칩니다.

## 2. 미리보기 카드

`index.html` 윗부분의 `og:image` / `og:url` 두 줄이 위 주소로 들어가 있습니다. 카카오톡은 미리보기를 한동안 기억하므로, 이미지나 제목을 바꾼 뒤 옛 카드가 보이면
https://developers.kakao.com/tool/debugger/sharing 에서 주소를 넣고 **초기화** 하면 됩니다.

## 3. 내용 고치기

`index.html` 아래쪽 `const CONFIG = { ... }` 블록만 고치면 됩니다. 따옴표 안의 글자만 바꿔 주세요.

| 항목 | 설명 |
|---|---|
| `groom` / `bride` | 이름, 영문 이름(맨 아래 서명), 부모님 성함, 장남/장녀 |
| `date` | 날짜. `hour`에 0~23 숫자를 넣으면 시간이 함께 표시됩니다 (`null`이면 날짜만) |
| `greeting` | 인사말. 문단은 대괄호로, 줄은 따옴표로 나눕니다 |
| `gallery` | 사진. 저장소에 `images` 폴더를 만들어 올리고 `"images/01.jpg"` 처럼 적습니다. 비우면 섹션이 숨겨집니다. (가로 1,200px 정도로 줄여서 올리면 빨리 뜹니다) |
| `kakaoJsKey` | 카카오톡 공유 버튼용 키 (아래 4번). 비우면 버튼이 숨겨집니다 |
| `siteUrl` | 링크 복사 버튼이 복사할 주소 (현재 https://kaiser-ryu.github.io/wedding/) |
| `credit` | 맨 아래 작은 글씨 (선택) |

달력, D-day(한국 시간 기준), 요일, 영문 날짜는 `date` 값으로 자동 계산됩니다.

## 4. 카카오톡 공유 버튼 (선택)

"링크 복사" 만으로도 카카오톡에 보내면 미리보기 카드가 뜨므로 꼭 필요한 건 아닙니다. 노란 버튼을 쓰고 싶을 때만:

1. https://developers.kakao.com → 내 애플리케이션 → **애플리케이션 추가**
2. 앱 설정 > **플랫폼 > Web** 에 사이트 도메인 등록: `https://kaiser-ryu.github.io`
3. 앱 설정 > **앱 키** 의 **JavaScript 키**를 복사해 `kakaoJsKey: "여기"` 에 붙여 넣기

## 5. 참고

- `index.html` 에 `noindex` 가 들어 있어 검색엔진에는 잡히지 않습니다. 링크를 아는 사람만 볼 수 있습니다.
- 폰트(Fraunces, 고운바탕)는 Google Fonts에서 불러옵니다. 폰트가 늦게 뜨는 동안에는 기기 기본 명조체로 보입니다.
- 수정 후에는 파일을 다시 올리기만 하면 1분 안에 반영됩니다. 브라우저가 옛 버전을 보여 주면 새로고침해 주세요.
