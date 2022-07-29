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

## 😎 참고

참고할 사이트/블로그 정리

- GitHub 이모지: https://gist.github.com/AliMD/3344523
