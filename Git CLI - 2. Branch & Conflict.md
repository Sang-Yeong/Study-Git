# [Git CLI - Branch & Conflict]
- branch: 가지, 같은 뿌리에서 나왔지만 서로 다른 역사를 써가는 것
	서로 다른 작업이 추가된 복제본이 필요한 경우가 많이 존재한다.
- Conflict(충돌): branch끼리 병합할 때, 같은 파일인데 같은 부분을 수정했다면 --> 사용자에게 수동으로 수정을 해달라고 Conflict함.



## 브랜치의 기본 사용법
> git log --all : 앞으로 만들게 될 모든 브랜치가 보이게 하는 것
> git log --all --graph --oneline
> git branch ____
> git checkout ____ : head가 ____를 가리키게 된다.



## 브랜치 병합
- merge: 합친다, 병합한다.
    *a----|
*  *m---* m: merge commit
    *g
합칠려고 하는 브랜치의 공통의 조상을 'base'라고 한다.
> git init manual-merge
> git commit --amend : commit메세지 변경

### 병합방법
1. master브랜치로 설정
2. 병합하고 싶은 브랜치를 merge명령어로 설정
> git merge ___

### Conflict
예시)	
	# Title
	content
	<<<<<<< HEAD	// 현재 head는 master
	master
	=======	//구분자
	o2
	>>>>>>> o2
충돌해결)
	# Title
	content
	master, o2

한 다음에 git add work.txt 하면 충돌을 해결함을 git에게 알려줌.


## 3 way merge VS. 2 way merge
두 개의 branch와 그 둘의 뿌리인 base와의 9;비교를 통해 merge하여 자동화를 더 많이 이루어낼 수 있다.


## 외부 도구를 이용해서 병합하는 방법; 전문적인 외부 도구를 이용해. 서 병합하는 방법
> git mergetool
검색창: p4Merge


## reset VS. checkout
Head
Branch
Commit
조작방법: checkout VS. reset

- 저장소를 만들었을 때; Head, master 생성(보통 master branch위에서 만들어지는 것)
- checkout은 결국에 head값을 바꾸는 것이다, head를 제어한다. (change)
- detached 상태: head가 브랜치를 가리키지 않고 commit 버전을 직접적으로 가리키고 있는 상태
- reset: head가 branch를 가리키고 있는 동안은 branch를 제어한다. (delete)



※ 에디터 바꾸고 싶을 때
git config --global core.editor "nano" 
