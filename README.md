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
- h1>h2>h3>h4>h5>h6 : 제목태그
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

---
### 20250523(금) [과제](https://github.com/sujin209/programmers)
---
