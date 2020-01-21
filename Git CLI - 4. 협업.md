# [Git CLI - 협업]

## git으로 혼자 작업하기
> git remote add origin ___주소___
> git push -u origin master: 지역저장소의 master와 원격저장소의 master를 직접 페어링, 연결 시켜주어야 함.

## git으로 같이 작업하기
- 협업을 위해서는 public, private상관없이 모두 승인이 필요함.
- Collaborators & teams


## git push & pull
## git pull & fetch 그리고 원격 브랜치(remote branch)
> git pull -> commit -> push
> git fetch -> git merge FETCH_HEAD -> commit -> push

$ git log --all --graph --oneline
*   d91ef8f (HEAD -> master, origin/master) Merge branch 'master' of https://github.com/Sang-Yeong/git4-collaboration-cli
|\
| * 02b7eec work 2b
* | 189c52d work 2a
|/

master: 지역저상소의 master branch
origin/master: 원격저장소 중 origin이라는 저장소의 master branch를 가리킨다.
	마지막으로 master branch의 어떤 버전을 가지고 왔는지를 의미...??

> git pull || git merge origin/master; 현재 master branch가 origin/master보다 한단계 '뒤'에 있다면
> git push; 현재 master branch가 origin/master보다 한단계 '앞'에 있다면

> git pull == git fetch를 통해 원격저장소만 업데이트 시킴 + git merge origin/master

merge시킬걸 하나하나 알아보기 힘드니까
.git/FETCH_HEAD 파일에서 '원격저장소에 가장 최근에 merge한 내용'이 적혀있음.
>git fetch; git merge FETCH_HEAD 라고 하면 알아서 최근에 fetch했던 내용 merge시켜줌.



## git으로 오픈소스 참여하기
### patch: push권한이 없는 개발자가 자신의 소스를 오픈소스 제공자에게 전해주고 싶을 때
> git format-patch __오픈소스에 올려진 가장 마지막 작업 코드__
하고나면 2개의 파일 형성

> cp: copy
> cp ../c/*.patch .
> git am: apply mailbox
> git am -3 -i *.patch : 3way merge, interactive mode( 패치 하나를 적용할 때마다 사용자에게 어떻게 적용할건지 물어보게 하는 것 )


### pull request
- pull: 원격저장소에 있는 내용을 땡겨간다.
- request: 요청하다
- 내가 작업하는 내용을 땡겨가 주십시오.
- 'Fork': 그 사람의 계정으로 이 저장소가 복제된다. 원격저장소를 내껄로 가지고 온거다. 
	clone: 같은 저장소에서 작업을 하는 것.
	fork: 저장소를 내껄로 가지고 와 작업을 하는 것. 마음대로 수정 가능
- Compare: 이전 원격저장소의 내용과 내가 수정한 내용을 비교해주는 것.
	Create pull request: 오리지널에게 수정된 내용을 땡겨가라고 요청하는 것.
- Pull request


※ git l 설정방법
nano ~/.gitconfig
[alias]
l = log --all --graph --oneline

