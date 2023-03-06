# 브랜치 생성 및 Fork 진행하기

## Flow

1. 내 닉네임으로 Github Project Repository에서 Branch를 생성한다.
2. 해당 Repository에서 내 Github 계정으로 원하는 브랜치를 `Fork`한다.
3. 원하는 Local Directory 위치에서 Forked Project를 `Clone`한다.
   * ex. `git clone -b main --single-branch {my-remote-url} {Directory Name}`
4. Branch 생성 및 작업하기&#x20;
   1. 기능 구현을 위해 브랜치를 생성한다. `git switch -c {branch-name}`
      1. Branch 네이밍: 해당 branch에서 수행할 대표 작업이 드러나도록 작성한다. ex. `docs/학습 및 구현 계획 작성`
   2. 해당 브랜치에서 작업할 세부 기능 목록을 작성한다.
   3. 세부 기능 단위로 구현하고 나서 `Commit` 한다.
      1. 해당 작업에 대한 간단한 설명을 포함하여 Commit 제목과 내용을 **잘** 작성한다.
      2. 필요한 경우 Commit log를 작성하기 전에 참고할 만한 모범 사례를 찾아본다.
   4. 주기적으로 내 Github 계정 Remote Origin Repository으로 업로드 한다. `git push origin {branch-name}`
   5. 일정 부분까지 구현을 진행한 후 Github Project Repository로 `Pull Request`를 제출한다.
   6. Review를 거쳐 PR이 승인되고 Merge되면, Head branch로 변경한 후 작업 Branch를 삭제한다. ex. `git switch {head-branch-name}` -> `git branch -D {삭제할 브랜치 이름}`
   7. 해당 브랜치 작업을 모두 완료하면 다음에 작업을 진행할 Branch를 생성하여 과정을 반복한다.
5. Branch Sync를 위해 내 Local 저장소에 base 저장소 최초 등록하기
   1. 등록된 저장소 확인하기 `git remote -v`
   2. upstream 등록하기 `git remote add -t {branch-name} upstream {base-remote-url}`
6. upstream과 branch 정보 업데이트하기 `git fetch upstream {branch-name}`
7. upstream과 내 local 브랜치 Sync `git rebase upstream/{branch-name}`
8. 내 Remote origin repo branch에 올리기 `git push origin {branch-name}`

{% embed url="https://lucas.codesquad.kr/masters-2023/course/CS16/CS16.%EB%B2%84%EC%A0%84%EA%B4%80%EB%A6%AC%EC%99%80-PR/PR%EC%9A%B4%EC%98%81%EB%B0%A9%EC%8B%9D" %}
