  1. 기본 명령어
    
  3.1 Setup
  
  git init : 저장소(repository) 생성
  
  git clone [원격 저장소 url] : 해당 주소의 내용을 복제하여 저장소 생성
  
  git config user.name [작성자 이름] : 작성자 이름 설정
  
  git config user.email [이메일 계정] : 작성자 이메일 설정
  
  git config --list : 저장소 설정 전체 출력
  
  git config --get [설정항목] : 일부 설정항목만 출력(ex : git config --get user.name)
  
  git help [커맨드 이름] : 도움말

  1.2 Stage & commit
git add [파일이름] : 수정된 파일을 staging area 올리기
git add [디렉토리 명] : 해당 디렉토리 내에 수정된 모든 파일들을 staging area에 올리기
git add . : working directory 내에 수정된 모든 파일들을 staging area에 올리기 (untracked 파일 제외)
git commit : 이력 저장(commit)
git commit -m "[메시지]" : vim을 사용하지 않고 인라인으로 메시지를 추가하여 commit
git commit -am "[메시지]" : add와 commit을 일괄적으로 진행

  1.3 Inspect
git status
git status : 저장소 파일의 상태정보 출력
git status -s : 파일 상태정보를 간략하게 표시

git log
git log : 저장소의 commit이력을 출력
git log --pretty=oneline : 각 commit을 한줄로 출력(--pretty 옵션 사용)
git log --oneline : 각 commit을 한줄로 출력
git log --decorate=full : 브랜치나 태그정보를 상세히 출력
git log --graph : 그래프 형태로 출력

git show
git show : 가장 최근의 commit 정보 출력
git show [commit hash] : 해당 commit의 정보 출력
git show HEAD : HEAD가 참조하는 commit의 정보 출력
git show HEAD^^^ : HEAD를 기준으로 3단계 이전의 commit정보 출력
git show HEAD~[n] : HEAD를 기준으로 n단계 이전의 commit정보 출력

git diff
git diff : 최근 commit과 변경사항이 발생한(Unstaged) 파일들의 내용비교
git diff --staged : 최근 commit과 Staging area의 파일들 간의 변경사항 출력
git diff [commit hash1] [commit hash2] : 두 commit의 파일들 간의 변경사항 출력

2. Commit 조작
  2.1 Checkout
git checkout [commit hash] : 해당 commit으로 파일상태 변경
git checkout - : HEAD가 이전에 참조했던 commit으로 상태변경
git checkout master : HEAD가 master를 참조
git checkout HEAD~n : HEAD를 기준으로 n단계 이전 commit으로 상태변경

  2.2 Undoing changes
git reset : Staging area의 파일 전체를 unstaged 상태로 되돌리기
git reset [파일명] : 해당 파일을 unstaged 상태로 되돌리기
git commit --amend : 최근 커밋을 수정하기
git commit --amend -m "[commit 메시지]" : 해당 메시지로 commit 수정하기
git reset [commit hash] : 해당 commit으로 브랜치의 참조를 변경
git reset –-hard [commit hash] : working directory, staging area, commit 모두 reset
git reset –-mixed [commit hash] : working directory 유지, staging area, commit reset , default option
git reset –-soft [commit hash] : working directory, staging area 유지, commit reset
git reset HEAD^ : HEAD를 기준으로 직전의 commit으로 reset
git reset HEAD~[정수] : HEAD를 기준으로 정수 값 단계 전 commit으로 reset

3. Branch 작업
  3.1 Setup
git branch : 브랜치 목록 표시
git branch [브랜치명] : 해당 브랜치 명으로 브랜치 생성
git checkout [브랜치명] : 해당 브랜치로 전환
git checkout –b [브랜치명] : 브랜치 생성과 동시에 전환
git branch -m [브랜치명] [새로운 브랜치명] : 브랜치명 변경
git branch –d [브랜치명] : 해당 브랜치 삭제

  3.2 merge, rewrite
merge
git merge [브랜치명] : 현 브랜치에 해당 브랜치의 내용 병합
git merge --ff [브랜치명] : fast-forward 관계에 있으면 commit을 생성하지 않고 현재 브랜치의 참조 값 만 변경(default)
git merge --no-ff [브랜치명] : fast-forward 관계에 있어도 merged commit 생성
git merge --squash [브랜치명] : fast-forward 관계에 있어도 merged commit 생성, merging 브랜치 정보 생략

rebase
git rebase [브랜치명] : 현재 브랜치가 해당 브랜치(브랜치명)에부터 분기하도록 재배치
git rebase --continue : 충돌 수정 후 재배치 진행(commit 대신)
git rebase --abort : rebase 취소

cherry-pick
git cherry-pick [commit hash] : 해당 commit의 내용을 현재 브랜치에 추가. 뒤에 commit hash 를 연속 입력하면 복수 추가 가능
git cherry-pick [commit hash start].. [commit hash end] : 해당 구간의 commit을 한번에 추가
git cherry-pick –-abort : 충돌과 같은 상황이 발생했을 때 cherry-pick 취소
git cherry-pick –-continue : 충돌 상황 해결 후 cherry-pick 진행
git cherry-pick –m [parent number] [merge commit ID] : merge commit을 추가. merge commit의 경우 어떤 부분의 merge를 가져올지 알 수 없다. 그래서 parent number를 추가해야 한다.(1부터 시작하며 main line이 1)
