<br />
<div align="center">
  <h3>Git</h3>
  <small>깃 or 깃허브 사용 시 팁/에러/해결 정리</small>
</div>

## 📝 목차

- [간단한 팁](#-간단한-팁)
- [상세한 팁](#-상세한-팁)
- [에러 내역](#-에러-내역)
- [참고](#-참고)

## 😄 간단한 팁

단건/짧은 내용/간단한 팁 정리

- remote -> local 덮어쓰기
  - git fetch -all
  - git reset --hard origin/main
- 소스 충돌시 특정 브랜치 원복
  - git checkout 복사한 4자리 이상 해시코드
  - git restore main

## 😳 상세한 팁

다건/긴 내용/상세한 팁 정리

- 리모트 - 로컬 연결
  - 기존 소스 없을때
    - 깃허브 new repo -> git clone -> 소스 복사 or 작업
  - 기존 소스 있을때
    - 깃허브 new repo
    - 소스 업로드 작업폴더 이동
    - 터미널 열고 git init
    - git remote add origin [원격저장소 주소]
    - 연결 끝
    - 소스 업로드 시작
    - git add .
    - git commit
    - git push origin main

## 😨 에러 내역

에러제목/발생상황/에러내역/원인/처리 순으로 정리

```
- 첫 push 에러
- 처음 repo 연결 후 push시 에러
- hint: Updates were rejected because the remote contains work that you do
  hint: not have locally. This is usually caused by another repository pushing
  hint: to the same ref. You may want to first integrate the remote changes
  hint: (e.g., 'git pull ...') before pushing again.
  hint: See the 'Note about fast-forwards' in 'git push --help' for details.
- 같은 레퍼지스토리에 push를 줬다는게 원인 (remote의 readme.md파일을 로컬이 몰라서 발생)
- git push -f origin main
- readme.md 파일 삭제되는 현상. 풀 받고 처리해야 할듯
```

```
- 첫 push 에러
- 처음 repo 연결 후 push시 에러
- error: src refspec main does not match any
- pull 없이 push해서 생기는 문제
- git pull
```

```
- 첫 pull 시도시
- 처음 repo 연결 후 push전에 pull 먼저 시도할 경우
- error: src refspec main does not match any
There is no tracking information for the current branch.
Please specify which branch you want to merge with.
See git-pull(1) for details.
- 연결된 branch가 없음 (리모트로 연결 했음에도)
- git branch -M main
- git branch --set-upstream-to=origin/<branch> main
- 위에 걸로 해결 안됨 . remote에 readme.md 파일을 생성 안하여 리포지토리가 없었던 거였음. 깃허브에서 임시파일 생성
- 그래도 해결 안됨. git init 부터 다시 하고 강제 push
```

```
- sts에서 깃 커밋시 에러
- sts에서 처음 깃 연결후 터미널 말고 gui로 커밋시 아이디/패스워드 로그인 불가
- not auth
- 토큰방식으로 깃 연결방식이 변경
- 참고 : https://joytk.tistory.com/58
- 토큰발급후 아이디(깃아이디)/ 패스워드(토큰)으로 입력
```

```
- sts에서 깃 커밋시 에러
- 깃 커밋시 rejected-non-fast-forward 오류
- main->main rejected-non-fast-forward
- 로컬 에서 원격으로 반영할려고 하는데, 원격브랜치가 로컬보다 이전 버전이 아니라는 뜻
- git pull실행
```

## 😎 참고

참고할 사이트/블로그 정리

- GitHub 이모지: https://gist.github.com/AliMD/3344523
