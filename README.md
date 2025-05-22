## 프로그래머스 웹 프로그래밍
### 20250522(목) [과제](https://github.com/sujin209/programmers)
---
**CLI로 github에 push하기**
- 새로운 폴더 생성하고 VS code에서 폴더 열기
- html파일작성
- README파일, .gitignore파일작성
- 터미널(git bash) 열기

    1. `git init` : 초기화, 레포지토리연결
    2. `git add .` : 모든파일 스테이징하기
    3. `git commit -m "커밋메시지"` : 파일 commit
    4. `git remote add origin 깃허브주소` 
    5. `git push origin main`

---
**CLI git 명령어**
|명령어|설명
|---|---|
| `git init` | 초기화, 레포지토리연결 |
| `git status` | 현재상태 |
| `git add <파일이름>` | 해당파일 스테이징하기 |
| `git add .` | 모든파일 스테이징하기 |
| `git commit -m "커밋메시지"` | 파일 commit |
| `git commit -am "커밋메시지"` | 파일스테이징 + 파일commit |
| `git log` | 기록보기 |
| `git log --oneline` |   |
| `git reset --soft` | 특정커밋으로 돌아가기(코드는그대로) |
| `git reset --hard` | 특정커밋으로 돌아가기(코드도 원래대로) |
| `git checkout - b 브랜치이름` | 브랜치 새로 만들고 이동 |
| `git checkout 브랜치이름` | 브랜치로 이동 |
| `git switch 브랜치이름` |   |
| `git branch -D` | 브랜치삭제 |
| `git remote add origin 깃허브주소` |  |
| `git push origin main` |  |

