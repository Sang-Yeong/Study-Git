# [Git CLI - 버전관리]

## 설치
- console
- terminal

## 버전관리의 시작: 저장소(repository)를 만드는 방법
> ls -al : 디렉토리 안에있는 파일보기
> git init . : 이제부터 이 디렉토리를 버전관리 할거야
	init: initialize(초기화) repository

## 버전의 생성
- Repository(저장소): 버전이 저장되는 곳
> git: git repository
- Working tree: 파일을 만들고 수정하면서 아직 버전으로 만들어 지기 전 단계, 수정한 내용이 들어가있다.
- Staging Area: 생성된 파일 중 버전으로 만들고 싶은 파일을 선택하여 이곳에 올려놓아 하나의 버전으로 만든다.

> nano 파일명.txt: 나노 에디터로 txt파일 작성하고 만들기
> cat 파일명.txt: 파일 내용을 보여주기
> git status: 깃의 상태 물어보기, working tree status
> git add 파일명.txt: untracked files: 추적할 수 없는 파일 --> staging area에 올려놓아야 함, add to staging area
> git commit: git아 버전 만들어, create version
> git commit -m "커밋할때 부연설명"
> git log: 역사, show version

## 여러개의 파일을 버전으로 만들기
> git log --stat: 버전에 해당하는 여러개의 파일 목록을 구체적으로 다 보여줌
> git add *2↑--> git commit 하면 여러개의 파일을 commit할 수 있음

## 버전간의 차이점 비교
> git diff: show changes
> git reset --hard: 가장 마지막으로 작업했던 내용이 다 사라짐
> git log -p: 패치

## checkout과 시간여행: working tree를 변경시키는 방법
최신버전: master
> git checkout  원하는 commit고유 번호
> git checkout master : 가장 최신의 상태로 복원

+ .gitignore
+ branch
+ tag: commit id를 쉽게 표현
+ backup

## 보충
> ### add를 커밋할 때마다 하지 않는 방법
>> git add . : 현재 디렉토리 밑에있는 모든 파일을 add한다. 꼭 파일명 하나하나를 지정하지 않아도 돼.
>> git commit -am "" : add와 commit을 한번에!
>### commit메시지를 작성할 때 실행되는 기본 에디터를 변경하는 방법
>> git config --global core.editor "nano"

## 버전 삭제 - git reset
> git reset --hard __commit고유 번호__

## 버전 되돌리기 - git revert
기존 커밋은 내버려두고 새로운 커밋을 만들어 그 커밋에서 일어난 변화를 취소시킨것이다.
다시, 
M4
M3
M2
M1
이 있을 때, M3로 되돌아가고 싶다면 M4를 revert해서 M4에서 일어난 변화를 취소시켜 M3로 돌아가게끔 하는 방식이다.

※M1으로 돌아가고 싶다고 바로 M2를 revert하면 충돌(complict)이 일어나.
M4부터 M2까지 차례로 revert해야해. 역순으로 차근차근.



