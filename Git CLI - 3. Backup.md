# [Git CLI - Backup]

## 용어정리
- Local Repository --> (push) --> Remote Repository ; 같은 상태 유지 가능, 백업
- clone: 원격저장소와 지역저장소가 완전히 같은 상태가 되도록 하는 것.
- Local Repository <-- (pull) <-- Remote Repository
- git hosting: 원격 저장소 제공

## Git hosting
- GitHub: 전 세계 수많은 오픈소스들이 저장되고 있음
- GitLab.com

## 원격저장소와 연결
- 깃허브; HTTPS
…or push an existing repository from the command line

> git remote add origin https://github.com/Sang-Yeong/my-repo.git
> git push -u origin master

```
git push -u origin master을 작성하고 실행시키는 과정에서

error: failed to push some refs to 'https://github.com/Sang-Yeong/myrepo.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

이런 error발생 할 수 O <-- README.md 때문

> git pull origin master --allow-unrelated-histories

문장이 필요함.
```

> git remote: 원격저장소 제대로 연결 되었는지 확인
> git remote -v: 원격저장소의 주소 확인


## git push
> git push
> git push --set-upstream origin master: origin을 git push 키워드를 썼을때 기본적인 저장소로 set해놓기 위한 명령어


## git clone
저장소를 만드는 방법 2가지: init, clone
start a working area (see also: git help tutorial)
   clone     Clone a repository into a new directory	: 이미 있는 것으로 부터 복제
   init      Create an empty Git repository or reinitialize an existing one	: 최초로 저장소 생성

> git clone ___주소___
> git clone https://github.com/Sang-Yeong/my-repo.git : 현재 이 명령을 실행시킨 디렉토리에 my-repo 디렉토리가 생성, 만약 다른 디렉토리를 생성하고 싶으면 뒤에 이어서 적으면 돼.


## git pull
## git과 오픈소스
- clone을 통해 오픈소스 다운받기 가능



※ pwd: 현재 위치한 디렉토리 알려주는 명령어
※ git remote -v: 어떤 원격 저장소에 연결되어 있는지를 알 수 있게 해주는 명령어
