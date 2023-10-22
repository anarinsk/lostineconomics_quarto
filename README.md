# lostineconomics_quarto

new blog based on quarto

## Updated 

### 20231022 Codespaces 생성 
- github codespaces를 통해서 로컬 환경 없이 문서를 컴파일하고 푸시한다. 
- codespaces 내에 파이썬 환경까지 제공하여 코드 실행까지 가능하다.

#### Action items
[LINK](
https://www.lostineconomics.com/posts/computer-tool/2023-10-20-github-codespaces.html) 참고

### 20231018 파이썬 실행 환경 
- 글 중에서 python runtime이 필요한 경우 이를 어떵게 제공할 것인가
- pixi를 통해서 `.`에 제공한다. 

#### Action items 
- `.gitignore`에 python 관련 항목 포함 
- pixi를 통해서 필요한 패키지 설치 
- vs code에서 컴파일 할 때 `F1 > "파이썬 인터프리터 선택"`해서 `.pixi/env/bin/python` 선택

~~### 20230317 - 폰트 로딩 방식 개선~~


~~- `_quarto.yml` 파일 수정~~

~~- html 꼭지 아래 `fonts.html`을 미리 로딩하게 함~~

~~- `fonts.html`에 사용 폰트들 임베딩~~

~~- `ansri-custom.scss`에서 `@import` 모두 제거~~

