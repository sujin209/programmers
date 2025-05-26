## 주요 Git CLI 명령어
---
### 🔧 초기 설정 관련
- git config --global user.name "이름" : 사용자 이름 설정
- git config --global user.email "이메일" : 사용자 이메일 설정
- git config --list : 설정 확인
- git config --global -e

### 🗂️ 저장소 관리
- git init : 현재 디렉토리를 Git 저장소로 초기화(=GUI 레포지토리연결)

### 📝 변경 사항 추적
- git status : 현재 작업 상태 확인 (변경 파일 등)
- git add <파일> : 변경 파일을 스테이지 영역에 추가
- git add . : 모든 변경 파일을 스테이지에 추가
- git commit -m "커밋 메시지" : 스테이지에 있는 변경사항 커밋
- git commit -am "커밋 메시지" : 모든 변경 파일을 스테이지에 추가하고 스테이지에 있는 변경사항 커밋
- git reset --soft/--hard : 해당 커밋으로 리셋(--soft는 로컬 코드 변경 x, --hard는 로컬 코드 변경 o)
※ git commit : 커밋 메시지 입력창이 자동으로 뜸. 입력 후 저장하고 닫으면 됨

### 🔄 버전 이동 & 기록 보기
- git log : 커밋 로그 보기
- git log --oneline : 한 줄 요약 로그 보기
- git checkout <브랜치명> : 다른 브랜치로 전환

### 🌿 브랜치
- git branch : 현재 브랜치 목록 확인
- git branch <이름> : 새 브랜치 생성
- git checkout -b <이름> : 브랜치 생성 + 이동
- git switch -c <이름> : 브랜치 생성 + 이동(checkout보다 최근명령어)
- git merge <브랜치> : 현재 브랜치에 다른 브랜치 병합
    - 옮기고자하는 브랜치에서 실행
    - sujin -> main이면 main에서 실행행
- git branch -D <이름> : 브랜치 삭제

### ☁️ 원격 저장소
※ 원격 저장소에 업로드하기 전 반드시 github에 접속하여 새 repository 생성해야 함

- git remote add origin <repository 주소> : 현재 프로젝트를 원격 저장소와 연결
- git remote -v : 원격 저장소 목록 확인
- git push origin <브랜치> : 원격 저장소의 특정 브랜치에 업로드
---
### 20250522(목) [과제](https://github.com/sujin209/programmers)
---
## HTML문법
### 🏷️기본태그
- h1 > h2 > h3 > h4 > h5 > h6 : 제목태그
- p : 문단태그
    - lorem : 의미없는 문장 생성
- a : 링크
    - href="이동할주소" - 필수속성
- strong, em : 강조
- br, hr : 구분선
- ol > li : 순서가 있는 리스트(1-2-3)
- ul > li : 순서가 없는 리스트
- img : 이미지
- abbr : 축약어
    - title에 축약어설명 작성
### 🏷️시맨틱태그
- header : 헤더
- footer : 푸터
    - 헤더와 푸터 제외한 나머지는 main
- nav : 네비게이션
- section : 섹션
    - 1개 이상의 h태그 존재해야함(h1제외)
- aside : 구역나누기(사이드부분)
### 🏷️form태그
- form : 입력정보를 전송해야하는 경우
- input : 입력받을때 사용
    - required 있으면 필수입력사항
    - password 타입 : 복사붙여넣기 x, 보안
    - range 타입: 진행률(드래그)
    - color 타입 : 색상선택
    - checkbox 타입 : 체크박스
    - email 타입 : 이메일(@)
    - file 타입 : 파일선택, 여러개선택가능(multiple속성)
    - radio 타입 : 라디오버튼, 같은 name 속성 가지고 있으면 1개만 선택가능
- label : 레이블
- button : 버튼
    1) input(type=button value=버튼이하는일)
    2) button(type=button)
    3) div(tabIndex=0 role=button)
- select : 선택가능(option : 선택항목)
### 🧱 인라인&블록
- 인라인(inline) _ex. span_
    -  가로방향
    - 줄바꿈발생x
    - 컨텐츠크기에 따라 크기 지정
    - 크기지정불가능(width, height, margin, transform x)
- 블록(block) _ex. div_
    - 세로방향
    - 줄바꿈발생o
    - 부모컨테이너의 크기에 따라 크기 지정
    - 크기지정가능(width, height, margin, transform o)
- 예외태그 img, input : 크기지정가능
---
## CSS
### 🔗 적용방식 
- 내부방식
    - head > style > div{background-color : yellow} 
- 외부방식
    - head > link rel=stylesheet href=<css주소>
- 인라인방식
    - div style="background-color : yellow" : 태그 안에 작성

적용순서 : **cascading**
- 인라인방식 1순위 , css순서대로 위에서부터 읽으면서 덮어쓰기
- ! important 넣으면 무조건 적용
### 🔧 선택자
- 요소(태그)선택자_1점
    - 특정타입의 모든 HTML요소선택
    - p{ }
- id 선택자_100점
    - 특정id를 가진 페이지의 요소선택(1개만 적용가능)
    - #아이디이름름{ }
- class 선택자_10점점
    - 특정class를 가진 페이지의 요소선택(여러개 적용 가능)
    - .클래스이름{ }
- 속성선택자_11점
    - 특정속성을 갖는 페이지의 요소선택
    - p[name=이름]{ }
- 가상클래스선택자_110점
    - 가상으로 선택할 수 있는 선택자
    - #id:hover{ }, p:focus{ }
    - transition, transform 다 적용가능

우선순위 : 점수기준, 점수 같으면 cascading

### 🪢상속&역상속
- 상위요소 - 부모 - 자식 - 하위요소
- 부모 > 자식 : 상속
    - font-style(서체, 글자크기, 자간, 행간 등) 물려줌
- 자식 > 부모 : 역상속
    - height(높이)
    - 부모요소의 높이(css로 지정) < 자식요소의 높이인 경우 
        - 레이아웃깨짐
- 우선순위 : 자식 >>> 부모
---
### 20250523(금) [과제](https://github.com/sujin209/programmers)
---
### ⚒️ 선택자조합
- 띄어쓰기O  (조건1 조건2)
    - 조건1에 해당하는 항목 중 조건2에 해당하는 항목
    -  ex. `.list .menu`
        ```
        <div class="list">
            <div class="menu"></div>
        </div>
- 띄어쓰기X  (조건1조건2)
    - 조건1, 조건2에 모두 해당하는 항목
    -  ex. `.list.menu`

        ```
        <div class="list menu"></div>
- 친자식선택자 (조건1>조건2)
    - 조건1에 해당하는 요소의 친자식 중 조건2에 부합하는 요소
- 다중선택자( , )
    - , 로 선택하고싶은 조건 나열
- 단일대상선택자(클래스/아이디작성x)
    - n번째속성선택 = 조건:nth-child()
        - n번째 : n
        - 홀짝 : odd/even
        - k의배수번째 : kn
    - 마지막자식선택 = 조건:last-child
    - 첫번째자식선택 = 조건:first-child
### 🕸️ CSS Nesting
- 조건1 안에 조건1과의 선택자조합을 다 작성하는 방법 
- 취향차이라서 편한대로 작성가능
### 🥇선택자우선순위
- 하위속성이 많을수록 우선적용
1️⃣ .header > .inner > ul > .list
### 📦 박스모델링
- margin : 컨텐츠밀기
    - auto = 자동설정(좌우방향 모두 auto면 가운데정렬)
    - margin-inline = x축방향
    - margin-block = y축방향
- padding : 컨텐츠 전체 크기 증가(살찌는것처럼)
- border : 테두리
    - box_size = border-box 속성 지정하면 border 설정해도 box 크기 그대로
컨텐츠 > padding > border > margin 순서
### 🔧 CSS속성
- color 색상
- font-size 글자크기
- font-family 폰트
- font-weight 굵기
- line-height 행간
- letter-spacing 자간
- background 관련
    - background-attatchment, background-clip, background-color, background-image, background-origin, background-position, background-repeat, background-size
### 🔧 float 속성
- 사용목적 : 컨텐츠 가로 배치, 층수구별
- **모든컨텐츠는 1층에서 시작, float속성 주면 2층으로 이동**
    - *float 사용해도 text 위층으로 올라가지 않고 신문처럼 구성됨*
    - ex. container > div 3개
        - div 3개를 다 float하면 container 크기 0 -> **높이상속은 1층에 있을 때만 가능**
         1️⃣ container에 높이 강제부여
         2️⃣ container에 overflow : hidden 속성부여<br> &nbsp;&nbsp; - 자식요소가 부모컨테이너 밖으로 나갈 수 없음
         3️⃣container 안에 p태그 만들고 clear : both 속성부여<br> 
### 🚩position**
|구분|relative|absolute|fixed|
|---|---|---|---|
|층수|1층|2층|2층|
|기준점|자신|부모(position O)|브라우저
|가운데정렬|margin : 0 auto|공식|공식|
|사용예시|기준점을 잡아주기 위해|독립적요소|화면고정|
|필수입력값|없음|x축, y축|x축, y축|
- relative : 상하/좌우에서 값 1개씩만 지정가능
- absolute의 기준이 되는 position : 보통 relative로 설정(1층이라서)
- 가운데정렬 
    ```
    position: absolute;
    left: 50%;
    top: 50%;
    translate:-50% -50%;
- sticky 
    - 부모요소 끝날때까지 위치고정
    - 부모요소에 GPU사용속성 있는 경우/스크롤 커스텀 시 동작x
### 🔩flexbox**
---
### 🗣️ 프로그램용어
- `*` 아스테리스크
- `-` 하이픈
- `_` 언더스코어
- `__` 언더
- `&` 엔퍼센드
### ✍️네이밍규칙
- kebab-case : ease-in-out-bounce
- snake_case : ease_in_out_bounce
- camelCase : easeInOutBounce
- PascalCase : EaseInOutBounce
