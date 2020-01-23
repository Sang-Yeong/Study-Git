[Git CLI - Cherry-pick & rebase]

# Cherry-pick의 개념과 기본사용법
- 하나의 파일을 생성하면 충돌과 같은 상황이 발생할 수 있기 때문에 --> 버전 만들때마다 파일 생성할거야.
$ touch init.txt; git add inti.txt; git commit -m "init"
	- ' ; ': 세미콜론으로 하면 한 줄에 여러개의 명령 가능

* 5c89b50 (topic) t3
* eb24474 t2
* 78cb5d0 t1
| * 8326b57 (HEAD -> master) m2
| * d660009 m1
|/
* 8bf576c init
- t2에서 작업한 내용이 m2에도 적용시키고 싶다. t2파일을 master로 가져오고싶다.

user@Sangyeong MINGW64 /c/git4-cherry-pick_rebase (master)
$ ls
init.txt  m1  m2
에서 	init.txt  m1  m2  t2
이렇게 표현할 때 cherry-pick이 사용된다.
: t2가 생성될 때 생긴 변화만을 가져오겠다.

1. 병합될 branch로 checkout해야함.
2. git cherry-pick '__고유번호__': 체리를 가지고 오듯이 cherry-pick하겠어




# Rebase의 개념과 기본 사용법
- base: 공통의 조상
- A -> B -> C -> M1 -> M2; master branch
	     -> T1 -> T2; topic branch
이때 master branch의 base를 C가 아닌 T2로 변경하고자 할때 rebase사용
- checkout을 통해 이동시킬 branch로 설정
> git checkout master
> git rebase topic	// topic branch가 가리키고 있는 commit로 base를 옮기겠다.
==> A -> B -> C -> T1 -> T2 -> M1 -> M2

- M1의 변화와 T2의 working copy를 합쳐서 새로운 버전인 M1이 형성. 처음의 M1과  'A -> B -> C -> T1 -> T2 -> M1 -> M2'여기서의 M1은 변경사항은 동일하나 working copy는 다르다.
- M2와  'A -> B -> C -> T1 -> T2 -> M1 -> M2'이곳에서의 M1이 합쳐져 새로운 M2형성.
- 마지막으로 master branch는  A -> B -> C -> T1 -> T2 -> M1 -> M2 이곳의 M2를 가리키게 된다.
==> 선형적으로 보이게 하는 "rebase"

- 주의: 원격저장소로 push된 다음에 rebase하면 X
- 주의: M2와 T2가 merge된 상태와 rebase된 상태의 새로운M2는 같아야 한다.
