# 은퇴참견 모아보기 — 공유 대시보드

저장소에 올릴 파일은 세 개입니다. 별도 빌드나 설치가 필요 없습니다.

| 파일 | 역할 |
|---|---|
| `index.html` | 대시보드 본체 |
| `banner.png` | 상단 채널 배너 |
| `og-image.png` | 카톡 링크 미리보기 썸네일 (1200×630) |

세 파일을 같은 위치(저장소 루트)에 올려야 합니다.

## 1. 깃허브에 올리기

1. github.com에서 **New repository** → 이름은 영문 소문자로 (예: `retire-ep4`), **Public** 선택 → Create.
2. 저장소 화면에서 **Add file → Upload files** → 세 파일 모두 드래그 → **Commit changes**.
   (저장소가 비어 있으면 Add file 대신 파란 박스의 *uploading an existing file* 링크를 누르세요.)
3. 상단 **Settings → Pages** → Source를 **Deploy from a branch**, Branch를 **main / (root)** 로 지정 → Save.
4. 1~2분 뒤 `https://사용자명.github.io/저장소명/` 주소가 생성됩니다.

## 2. 주소 반영하기

주소가 `https://psyops42-art.github.io/pension_info/` 와 다르면 `index.html` 상단 두 줄을 바꿔주세요. 카톡 링크 미리보기가 이 값을 읽습니다.

```html
<link rel="canonical" href="https://psyops42-art.github.io/pension_info/">
<meta property="og:url" content="https://psyops42-art.github.io/pension_info/">
```

수정 후 다시 업로드(또는 깃허브 웹에서 연필 아이콘으로 편집)하면 즉시 반영됩니다.

## 3. 회차 추가·수정

`index.html` 중간의 `SERIES` 블록 한 곳만 고치면 화면 전체에 반영됩니다.

```js
{ ep:5, name:"인출기투자 편", partial:true,
  full:{ id:"영상ID", title:"제목", note:"한 줄 설명" },
  shorts:[ { id:"영상ID", title:"제목" }, ... ] }
```

- `id`는 주소 뒤 11자리입니다. 본편 `youtu.be/**NdNuP3ZK1Vg**`, 숏츠 `shorts/**WaocIi2JWME**`
- 숏츠는 배열 순서대로 EP.1, EP.2… 로 번호가 붙습니다.
- `partial:true`는 "나머지 숏츠 순차 공개" 안내를 띄웁니다. 다 채워지면 지우세요.
- 썸네일은 유튜브에서 자동으로 불러오므로 이미지를 따로 준비할 필요가 없습니다.

## 4. 카톡 미리보기가 이상할 때

카카오는 링크 미리보기를 캐시합니다. 주소나 썸네일을 수정한 뒤에는
https://developers.kakao.com/tool/clear/og 에서 해당 주소를 넣고 캐시를 지운 다음 다시 공유하세요.
